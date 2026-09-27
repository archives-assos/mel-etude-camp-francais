# DIMENSIONNEMENT DATACENTER — ENTRAÎNER DES MODÈLES FRONTIÈRE

**Objet** : déterminer la taille (GPU, racks, MW, m², €) d'un datacenter capable d'**entraîner** un modèle frontière, à partir des runs publics documentés
**Date** : Septembre 2026
**Statut** : Document de travail — généraliste (`generalites/`)
**Documents liés** : `infrastructure-ia-gpu-souverainete.md` (GPU, PUE, scénarios site), `bilan-carbone-productiviste-1.3GW.md` (énergie, coûts complets)

---

## TABLE DES MATIÈRES

1. [Entraîner ≠ inférer](#1-entraîner--inférer--deux-métiers-deux-dimensionnements)
2. [Méthode de calcul](#2-méthode-de-calcul--des-flops-au-mégawatt)
3. [Runs frontières documentés](#3-runs-frontières-documentés--les-faits-vérifiés)
4. [Abaque de dimensionnement](#4-abaque-de-dimensionnement)
5. [Contraintes spécifiques à l'entraînement](#5-contraintes-spécifiques-à-lentraînement)
6. [Lecture : que peut un site type 84 MW IT ?](#6-lecture--que-peut-un-site-type-84-mw-it-)
7. [Cas limite basse : entraîner un YOLO](#7-cas-limite-basse--entraîner-un-yolo)
8. [Datacenter inférence seule — taille et usagers](#8-datacenter-inférence-seule--taille-et-usagers)
9. [Références](#9-références)

---

## 1. ENTRAÎNER ≠ INFÉRER — DEUX MÉTIERS, DEUX DIMENSIONNEMENTS

| Critère | **Entraînement** (train) | **Inférence** (serve) |
|---|---|---|
| Charge | 1 run monolithique, des semaines, 24/7 à 100 % | Trafic variable, 5 % d'utilisation moyenne mesurée (Cast AI) |
| Réseau | 1 seul fabric RDMA, zéro partition tolérée | Partitionnable, multi-sites possibles |
| Fiabilité | 1 panne GPU = run menacé (checkpoint/restart) | Panne = instance remplacée, service continu |
| Puissance | Palier constant + à-coups de dizaines de MW | Courbe suivant le trafic |
| Durée de vie du besoin | 2-6 mois par run, puis cluster libéré ou réalloué | Permanent, croît avec les utilisateurs |
| Dimensionnant | **FLOPs totaux ÷ durée ÷ débit utile/GPU** | tokens/s, latence, utilisateurs simultanés |

Le dossier parent dimensionne surtout l'**inférence** (tok/s/m², utilisateurs). Le présent document dimensionne l'**entraînement**.

---

## 2. MÉTHODE DE CALCUL — DES FLOPS AU MÉGAWATT

### 2.1 Formule

```
N_GPU  =  FLOPs_total  ÷  (débit_utile_par_GPU  ×  durée_run_secondes)
P_IT   =  N_GPU  ×  ~1,1 kW        (GPU + serveurs + réseau au prorata)
P_soutirée = P_IT  ×  PUE (1,3-1,5)
Racks  =  N_GPU  ÷  8              (standard HGX 8 GPU)
Surface halls = Racks  ×  18-25 m² (liquid vs air, cf. parent §8)
CAPEX_GPU   =  N_GPU  ×  prix_unitaire (~30 k$ H100, ~50 k$ B200)
```

### 2.2 Le paramètre qui décide de tout : le débit utile (MFU)

Le débit catalogue ne sert jamais. Référence mesurée et publiée :

| GPU | Catalogue BF16 dense | **Utile mesuré en entraînement** | Source |
|---|---|---|---|
| H100 | 989 TFLOPS | **~400 TFLOPS (MFU ~40 %)** | Meta, Llama 3 (16 384 GPU, ACM 2025) |
| B200 | ~2 250 TFLOPS dense (2 500 sparse) | **~900 TFLOPS (hypothèse, MFU ~40 %)** | Hypothèse de travail, à resserrer |

Tout l'abaque §4 utilise **400 TFLOPS/H100** et **900 TFLOPS/B200**. Diviser le MFU par 2 (réseau faible, code non optimisé) = doubler le cluster.

---

## 3. RUNS FRONTIÈRES DOCUMENTÉS — LES FAITS VÉRIFIÉS

| Run | Calcul total | Cluster | Durée | Puissance IT estimée | Fait notable vérifié |
|---|---|---|---|---|---|
| **Llama 3 405B** (Meta, 2024) | **3,8e25 FLOPs** | **16 384× H100** | **54 jours**, >90 % temps utile | ~18 MW (16 384 × 1,1 kW) | 419 pannes (1/3 h), moitié HBM3 ; à-coups réseau de dizaines de MW |
| **Llama 4** (Meta, 2025) | ~2× Llama 3 | ~32 000× H100, FP8 | — | ~35 MW | MFU FP8 tombé à ~20 % : scaler ≠ optimiser |
| **Colossus 1** (xAI, Memphis, 2024) | — | 100 000× H100 → **200 000× H100/H200** | Built in 122 j, training en 19 j après 1er rack | 150 MW réseau + 150 MW batteries ; phase 2 → 300 MW | Démarré sur groupes gaz (7 MW réseau initiaux) ; 785 000 sq ft |
| **Colossus 2** (xAI, 2026) | 1 112k H100-éq (→1 824k projetés) | B200/B300 | Opérationnel | **946 MW IT** (→1 531 MW), **35,8 Md$** (→58) | Turbines gaz au Mississippi ; 2 500 emplois annoncés Nord-FR pour le pendant français |
| **GPT-4** (ordre public, non confirmé) | ~2,1e25 FLOPs (estimation Epoch) | ~25 000× A100 (estimation) | ~90-100 jours (estimation) | ~15 MW | Jamais confirmé par OpenAI — à citer comme estimation |

**Loi d'échelle observée** : la frontière double à peu près tous les **12-18 mois** en FLOPs (3,8e25 en 2024 → ~1e26 en 2025-2026 → ~1e27 visé 2027).

---

## 4. ABAQUE DE DIMENSIONNEMENT

Run de **90 jours**, MFU 40 %, PUE 1,4, 8 GPU/rack, 25 m²/rack (air) :

| Cible (ordre frontière) | FLOPs | N H100 (400 TF) | N B200 (900 TF) | P_IT | P_soutirée | Racks | Halls | CAPEX GPU |
|---|---|---|---|---|---|---|---|---|
| **Génération 2023** (GPT-4 class) | 2e25 | ~6 500 | ~2 900 | 7 / 3 MW | 10 / 4 MW | ~800 / 360 | 2 ha / 1 ha | ~200 / 150 M$ |
| **Génération 2024** (Llama-405B class) | 4e25 | **~13 000** | ~5 700 | 14 / 6 MW | 20 / 9 MW | ~1 600 / 700 | 4 ha / 1,8 ha | ~400 / 290 M$ |
| **Génération 2025-2026** (frontière actuelle) | 1e26 | **~32 000** | ~14 000 | 35 / 15 MW | **49 / 22 MW** | ~4 000 / 1 800 | 10 ha / 4,5 ha | ~1 000 / 700 M$ |
| **Génération 2027** (prochaine frontière) | 3e26 | ~96 000 | ~43 000 | 106 / 47 MW | 148 / 66 MW | ~12 000 / 5 400 | 30 ha / 13 ha | ~2,9 / 2,1 Md$ |
| **Méga-run** (Colossus-2 class) | 1e27 | ~320 000 | ~143 000 | 350 / 157 MW | **~490 / 220 MW** | ~40 000 / 18 000 | 100 ha / 45 ha | ~9,6 / 7,1 Md$ |

Vérification : 3,8e25 à 400 TFLOPS sur 54 jours → ~20 000 H100 théoriques vs 16 384 réels (Meta tourne à MFU >40 % et 90 %+ de temps utile) : l'abaque est **conservateur de ~20 %**, marge saine pour dimensionner.

**Énergie d'un run** : 1e26 sur H100 = 35 MW IT × 2 160 h ≈ **76 GWh** (≈ 106 GWh soutirés) ; 1e27 sur B200 = 157 MW × 2 160 h ≈ **340 GWh** (≈ 475 GWh soutirés, ~0,5 TWh — la conso annuelle d'une ville de 300 000 habitants pour **un seul entraînement**).

---

## 5. CONTRAINTES SPÉCIFIQUES À L'ENTRAÎNEMENT

1. **Fiabilité exponentielle** : 419 pannes en 54 jours à 16k GPU (1/3 h). À 100k+, c'est **plusieurs pannes par heure** : checkpoint toutes les minutes, 5-10 % du temps en reprise, équipe SRE dédiée 24/7.
2. **Réseau non négociable** : 1 fabric RDMA (InfiniBand ou Spectrum-X), 95 % de débit utile exigé ; l'Ethernet standard plafonne à ~60 % (NVIDIA/Colossus). Surcoût réseau : ~20-30 % du CAPEX IT.
3. **À-coups électriques** : variations synchrones de dizaines de MW (démarrage/arrêt synchro des GPU) — le poste HT et les onduleurs doivent les absorber sans décrocher (Meta l'a documenté comme limite dimensionnante).
4. **Refroidissement à palier constant** : 100 % de charge pendant des mois = le DLC (direct-to-chip) devient obligatoire au-delà de ~30 kW/rack ; l'air ne suit plus.
5. **Eau et bruit 24/7** : un run ne s'arrête ni la nuit ni la canicule — cumul avec les pics climatiques (§8 du parent, §été 2026 du dossier électricité).
6. **Post-run** : le cluster passe en inférence/fine-tuning ou se revend — prévoir la **deuxième vie** dès le CCTP (sinon 30 000 GPU dorment à 5 % d'utilisation).

---

## 6. LECTURE — QUE PEUT UN SITE TYPE 84 MW IT ?

Rappel parent §8 : site maximaliste 22 ha = 2 414 racks, 84 MW IT, 9 500 PFLOPS FP16 (H100) à 24 000 PFLOPS (B200).

| Besoin | Exigence | Verdict site 84 MW |
|---|---|---|
| Inférence modèle 27-70B (Qwen, Gemma) | 1-2 GPU | ✅ cent fois |
| Inférence DeepSeek-R1 671B Q4 | 6× H100, 0,72 m² | ✅ |
| **Entraînement 1e25** (recherche, fine-tune lourd) | ~6 500 H100, ~10 MW | ✅ tient sur 1/8 du site |
| **Entraînement 1e26** (frontière 2025-2026) | ~32 000 H100, ~49 MW soutirés | ✅ **tient sur un site**, mais le **monopolise 3 mois** (plus d'inférence en parallèle) |
| **Entraînement 3e26** (frontière 2027) | ~100-150 MW soutirés | ❌ **2 sites** ou 1 site + délestage total |
| **Méga-run 1e27** (Colossus-2 class) | ~220-490 MW, 18-40 000 racks | ❌ **échelle nationale** (cf. bilan §9 : Fouju 1,4 GW) |

**Conclusion dimensionnante** : un site de 22 ha peut **entraîner la frontière actuelle une fois par trimestre**, ou **servir des milliers d'utilisateurs en inférence en continu** — pas les deux. Choisir l'usage, c'est choisir le réseau, le refroidissement et le contrat électrique. Un « datacenter mixte » qui promet les deux avec 84 MW **survend sa capacité d'un facteur 2**.

---

## 7. CAS LIMITE BASSE — ENTRAÎNER UN YOLO

Même méthode (§2), autre bout de l'échelle : la détection d'objets temps réel (YOLO) s'entraîne sur **un poste de travail**, pas dans un datacenter. Démonstration chiffrée.

### 7.1 Modèles de référence (forward, 640 px, COCO)

| Modèle | Params | FLOPs forward | mAP 50-95 (COCO) | Source |
|---|---|---|---|---|
| YOLOv8n | 3,2 M | 8,7 G | 37,3 | Ultralytics docs / HF |
| YOLOv8m | 25,9 M | 78,9 G | 50,2 | Ultralytics docs |
| YOLOv8x | 68,2 M | 257,8 G | 53,9 | Ultralytics docs |
| YOLOv9-E | 58,1 M | 192,5 G | 55,6 | Papier YOLOv9 (arXiv 2402.13616) |
| YOLO11x | 56,9 M | 194,9 G | 54,7 | Ultralytics / HF |

Protocole standard : COCO train2017 (**118 000 images**), **300 epochs** par défaut (500 en config poussée, ex. run plateforme yolov8x : batch 16, 500 epochs).

### 7.2 Calcul total d'un entraînement (estimation)

Règle : entraînement ≈ **3× le forward** par image (forward + backward + update) :

```
FLOPs_train  =  3  ×  FLOPs_forward  ×  118 000  ×  epochs
```

| Run | Calcul estimé | vs Llama 3 405B (3,8e25) |
|---|---|---|
| YOLOv8n, 300 epochs | **~1e18 FLOPs** | 40 millions de fois moins |
| YOLOv8x, 300 epochs | **~2,7e19 FLOPs** | ~1 million de fois moins |
| YOLOv8x, 500 epochs | **~4,6e19 FLOPs** | ~800 000 fois moins |

Soit **6 à 7 ordres de grandeur** sous la frontière LLM : l'écart poste de travail ↔ datacenter tient dans ce tableau.

### 7.3 Temps et matériel (débit utile ~100 TFLOPS/GPU en vision, hypothèse)

| Run | 1× RTX 4090 (~450 W) | 1× A100 (~400 W) | 8× A100 (1 nœud, ~3,5 kW) |
|---|---|---|---|
| YOLOv8n, 300 ep (~1e18) | **~3 h** | ~3 h | <1 h |
| YOLOv8x, 300 ep (~2,7e19) | ~3 jours | ~3 jours | **~9 h** |
| YOLOv8x, 500 ep (~4,6e19) | ~5 jours | ~5 jours | **~16 h** |

Énergie : YOLOv8x complet sur 8× A100 ≈ 3,5 kW × 16 h ≈ **56 kWh (~3 €)**. Le même calcul donne ~106 GWh soutirés pour un run 1e26 (§4) : **facteur ~2 millions**.

### 7.4 Quand faut-il quand même un datacenter pour du YOLO ?

- **Balayage d'hyperparamètres** : 100 configs × 16 h = 1 600 GPU-heures → 1 rack pendant 1 semaine, pas un site.
- **Dataset custom géant** : 10 M d'images (×85 vs COCO) → YOLOv8x ≈ 4e21 FLOPs ≈ **12 h sur 1 000 H100** — un coin de datacenter, une journée.
- **Pré-entraînement backbone + distillation à grande échelle** : seul cas où la vision rejoint les ordres LLM, et c'est alors du ressort de l'abaque §4, plus de cette section.

**Conclusion** : entraîner un YOLO (y compris le plus gros, from scratch sur COCO) = **1 GPU de bureau à 1 nœud, quelques heures à quelques jours, <100 kWh**. Invoquer un datacenter de dizaines de MW pour de la détection d'objets classique, c'est confondre l'outil et l'argument commercial. Le datacenter ne devient dimensionnant pour la vision qu'au-delà de ~1e21 FLOPs (datasets ≥10 M d'images ou modèles fondation multimodaux).

---

## 8. DATACENTER INFÉRENCE SEULE — TAILLE ET USAGERS

### 8.1 Méthode : des tok/s aux usagers

```
tok/s_total  =  N_GPU  ×  tok/s/GPU (classe de modèle, H100, BF16)
tokens/jour  =  tok/s_total  ×  86 400  ×  0,5 (foisonnement jour/nuit)
               ×  0,2 (décote SLO : latence, longueurs mixtes, pics)
usagers/jour =  tokens/jour  ÷  budget_tokens_par_usager
```

Budgets par profil (hypothèses explicites) : **léger** (chat occasionnel) 3 000 tok/j · **standard** (chat régulier) 15 000 tok/j · **intensif** (agent de code, raisonnement) 100 000 tok/j.

### 8.2 Débit par GPU (H100, BF16, hypothèses calées sur le parent §4.4)

| Classe de modèle | tok/s/GPU | Base |
|---|---|---|
| ~8B (Llama-8B, Mistral-7B) | ~15 000 | Hypothèse (vLLM, gros batch) |
| ~27-32B (Qwen-27B, Gemma-31B) | ~6 000 | Cohérent parent : 1× H100 → 40-150 simultanés |
| ~70B (Llama-70B) | **~3 000** | Parent §4.4 : 8× H100 → 24 000 tok/s |
| MoE ~670B/37B actifs (R1 class) | ~500 | Cohérent parent : 6× H100 → 20-80 simultanés |

### 8.3 Abaque : 1 MW IT ≈ 115 H100 (8,75 kW/GPU tout compris, air, cf. parent §8)

| Puissance IT | N H100 | tok/s (classe 30B) | Usagers légers/j | Usagers standard/j | Usagers intensifs/j |
|---|---|---|---|---|---|
| 1 MW (1 rangée) | ~115 | ~0,7 M | ~800 000 | ~160 000 | ~24 000 |
| 10 MW (1 hall) | ~1 150 | ~6,9 M | ~8 M | ~1,6 M | ~240 000 |
| 40 MW (site moyen) | ~4 600 | ~28 M | ~32 M | ~6,5 M | ~1 M |
| **84 MW (site max 22 ha)** | **~9 600** | **~58 M** | **~67 M** | **~13 M** | **~2 M** |

Lecture : un site maximaliste en inférence 30B sert **~13 millions d'usagers standard par jour** — ou **2 millions d'agents intensifs**. En classe 70B, diviser par 2 ; en classe 8B, multiplier par 2,5. **Le même site qui entraîne la frontière 3 mois (§6) sert sinon des dizaines de millions d'usagers** : l'arbitrage train/serve se chiffre ici.

### 8.4 Cas vision : inférence YOLO = caméras servies

Débits mesurés A100 TensorRT (Ultralytics) : v8n 0,99 ms (~1 000 img/s) · v8m 1,83 ms (~540 img/s) · v8x 3,53 ms (~280 img/s). À 10 img/s par caméra :

| GPU | Caméras (v8m) | Caméras (v8x) |
|---|---|---|
| 1× A100/H100 | **~50** | ~28 |
| 1 rack 8 GPU (~70 kW) | **~400** | ~220 |
| 1 MW IT (~115 GPU) | **~5 700** | ~3 200 |
| 10 MW (1 hall) | **~57 000** | ~32 000 |

Une ville de 100 000 habitants (~2 000 caméras de vidéoprotection) s'analyse en v8m sur **~40 GPU, soit un demi-rack, ~350 kW** : l'inférence vidéo municipale ne justifie aucun datacenter dédié.

---

## 9. RÉFÉRENCES

| Donnée | Source |
|---|---|
| Llama 3 405B : 16 384 H100, 3,8e25 FLOPs, 400 TFLOPS/GPU, 419 pannes, >90 % utile | Meta (blog Llama 3.1) ; ACM ISCA 2025 « Scaling Llama 3 Training » ; TweakTown 07/2024 |
| Llama 4 : ~32k H100 FP8, MFU ~20 % | HN/discussion papier Llama 4 (2025) — ordre de grandeur |
| Colossus 1 : 100k→200k H100/H200, 122 j, Spectrum-X, 150+150 MW → 300 MW | NVIDIA (communiqué) ; PCMag 10/2024 ; Yahoo/Tom's 05/2025 |
| Colossus 2 : 1 112k H100-éq, 946 MW IT, 35,8 Md$ → 1 824k / 1 531 MW / 58 Md$ | Epoch AI, sept. 2026 |
| GPT-4 : ~2,1e25 FLOPs (estimation) | Epoch AI — estimation, non confirmée par OpenAI |
| Utilisation GPU cloud 5 % ; specs GPU, PUE, racks, m² | `infrastructure-ia-gpu-souverainete.md` §1, §4, §8 |
| Coûts réseau, énergie, EPR | `bilan-carbone-productiviste-1.3GW.md` |
| YOLOv8 : params, FLOPs, 300 epochs par défaut | Ultralytics docs (docs.ultralytics.com/models/yolov8) ; HF Ultralytics/YOLOv8 ; GitHub issue #3621 |
| YOLOv8x run plateforme : batch 16, 500 epochs | Ultralytics Platform (platform.ultralytics.com/ultralytics/yolov8/yolov8x) |
| YOLOv9-E : 58,1 M, 192,5 G, 500 epochs scratch | Papier YOLOv9 (arXiv 2402.13616) ; README yolov9 |
| YOLO11x : 56,9 M, 194,9 G | HF Ultralytics/YOLO11 |

---

*Méthode train : FLOPs ÷ (débit utile × durée) → GPU → ×1,1 kW → ×PUE → racks ÷8 → m². Méthode serve : N_GPU × tok/s/GPU × 86 400 × 0,5 × 0,2 ÷ budget/usager. Hypothèses marquées. Pour le détail par modèle, voir le parent §4-5.*
