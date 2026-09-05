# INFRASTRUCTURE IA — GPU, SOUVERAINETÉ ET PUISSANCE DE CALCUL

**Objet** : Analyse des contraintes matérielles, géopolitiques et de souveraineté pour un datacenter IA en France  
**Date** : Septembre 2026  
**Statut** : Document de travail

---

## TABLE DES MATIÈRES

1. [Pénurie GPU — État des lieux 2026](#1-pénurie-gpu--état-des-lieux-2026)
2. [NVIDIA vs Chine — Géopolitique des puces](#2-nvidia-vs-chine--géopolitique-des-puces)
3. [Acteurs cloud et souveraineté](#3-acteurs-cloud-et-souveraineté)
4. [Puissance de calcul par unité de surface](#4-puissance-de-calcul-par-unité-de-surface)
5. [Infrastructure pour Kimi K3 — Cas d'étude](#5-infrastructure-pour-kimi-k3--cas-détude)
6. [Recommandations pour le datacenter Camp Français](#6-recommandations-pour-le-datacenter-camp-français)
7. [Références](#7-références)
8. [Lexique des acronymes](#8-lexique-des-acronymes)

---

## 1. PÉNURIE GPU — ÉTAT DES LIEUX 2026

### 1.1 Structure de la pénurie

La pénurie 2026 n'est **pas conjoncturelle mais structurelle**. Trois goulots d'étranglement se cumulent :

| Goulot | Acteur(s) | Capacité | Contrainte |
|--------|-----------|----------|------------|
| **HBM3e** (mémoire haute bande passante) | SK Hynix, Samsung, Micron | 100% vendue pour 2026 | Demande +80-100%/an, offre +50-60%/an |
| **CoWoS** (empaquetage avancé TSMC) | TSMC uniquement | Fully allocated → milieu 2027 | Pas de second fournisseur |
| **Fonderie 3nm/4nm** | TSMC N3/N3E | Priorité NVIDIA/AMD/hyperscalers | Les acheteurs non-prioritaires en queue |

### 1.2 Délais de livraison

| GPU | Délai (2026) | Prix évolution | Contrainte principale |
|-----|-------------|----------------|----------------------|
| **H100 SXM5** | 36-52 semaines | +20% (location) | HBM3 + CoWoS |
| **H200** | 36-52 semaines | +15-20% | HBM3e + CoWoS |
| **Blackwell B200/GB200** | 3-7 mois | +15-23% | CoWoS (principal) |
| **A100 (legacy)** | 2-4 semaines | +15% (location) | Rareté (fin de vie) |
| **AMD MI325X** | 18-26 semaines | Stable | CoWoS (filaire) |

### 1.3 Marché de détail

| Indicateur | Valeur | Source |
|-----------|--------|--------|
| Revenu NVIDIA datacenter Q1 FY27 | 75,2 Mds$ | NeuralWired |
| Capex hyperscalers 2026 | 600-630 Mds$ (~75% IA) | JP Morgan |
| Backlog B200 | ~3,6 millions d'unités | GPUaaS.com |
| Utilisation moyenne GPU cloud | **5%** | Cast AI (23 000 clusters) |
| Délai normalisation | **2028-2029** | Consensus industrie |

### 1.4 Conséquence

> *« Ce n'est pas un problème d'approvisionnement temporaire. C'est un réajustement structurel de qui contrôle le calcul. »*  
> — NeuralWired, mai 2026

**Les hyperscalers ont verrouillé les allocations.** Toute entreprise non adossée à un fonds souverain fait la queue sur le marché spot à des prix 20-30% supérieurs.

---

## 2. NVIDIA VS CHINE — GÉOPOLITIQUE DES PUCES

### 2.1 NVIDIA — Monopole de facto

| Donnée | Valeur |
|--------|--------|
| Part marché accélérateurs datacenter | **>80%** |
| Production puce IA 2025 | ~4,5 millions d'unités |
| Production prévue 2026 | ~6,75 millions (+50%) |
| Production prévue 2027 | ~10,125 millions (+50%) |
| Écosystème logiciel | **CUDA** (17 ans, standard de facto) |

### 2.2 Huawei Ascend — Alternative chinoise

| GPU | FP16 (TFLOPS) | Mémoire | Bande passante | Prix estimé | Process |
|-----|---------------|---------|----------------|-------------|---------|
| **Ascend 910B** | ~600 | 64 GB HBM2e | ~1 200 GB/s | 8 000-12 000 $ | SMIC 7nm |
| **Ascend 910C** | ~800 | 96 GB HBM2e | ~1 800 GB/s | 12 000-18 000 $ | SMIC 7nm |
| **NVIDIA H100** | 990 | 80 GB HBM3 | 3 350 GB/s | 25 000-40 000 $ | TSMC 4nm |
| **NVIDIA B200** | ~2 500 | 192 GB HBM3e | ~8 000 GB/s | ~50 000 $ | TSMC 4nm |
| **AMD MI300X** | 1 307 | 192 GB HBM3e | 5 300 GB/s | 10 000-15 000 $ | TSMC 5nm |

### 2.3 Écart de performance réel

| Comparaison | Ratio performance | Source |
|------------|-------------------|--------|
| Ascend 910C vs H100 | **~60%** | DeepSeek benchmarks |
| Ascend 910C vs H100 (entraînement) | ~50-60% | Awesome Agents |
| Ascend 910B vs H100 | ~40-50% | Awesome Agents |
| NVIDIA H100 vs B200 | ~3x | MLPerf v6.0 |

### 2.4 Limitations chinoises

| Contrainte | Détail |
|-----------|--------|
| **Fonderie** | SMIC bloqué à 7nm (pas d'EUV) |
| **HBM** | Dépendance aux fournisseurs coréens/américains (coupés par sanctions) |
| **Performance déclinante** | Ascend 950PR/950DT prévus 2026 = **moins puissants** que 910C actuel |
| **Logiciel** | CANN (écosystème >> CUDA) |
| **Production** | <1 million d'unités en 2026 (vs 6,75M pour NVIDIA) |

### 2.5 Enjeu européen

| Enjeu | Problème |
|-------|----------|
| **Dépendance NVIDIA** | 80% du marché, CUDA = lock-in logiciel |
| **Dépendance TSMC** | Toute la chaîne passe par Taïwan |
| **Open weights** | Modèles chinois (DeepSeek, Kimi) = open weights mais hardware chinois |
| **Acteurs européens** | Pas de fonderie avancée, pas de GPU concurrent |

### 2.6 Acteurs européens — État des lieux

| Acteur | Type | Position |
|--------|------|----------|
| **ASML** (NL) | Lithographie EUV | Monopole mondial (fournit TSMC, Samsung, Intel) |
| **Infineon** (DE) | Semi-conducteurs | Pas de GPU IA |
| **STMicroelectronics** (FR/IT) | Semi-conducteurs | Pas de GPU IA |
| **BSC/Barcelona Supercomputing** | HPC | RISC-V, pas de GPU |
| **Mistral AI** (FR) | Modèles IA | Open weights, pas de hardware |

**Réalité** : L'Europe n'a **aucun acteur capable de produire des GPU IA** à l'échelle. La dépendance à NVIDIA (puces) et TSMC (fabrication) est totale.

---

## 3. ACTEURS CLOUD ET SOUVERAINETÉ

### 3.1 Le problème CLOUD Act

| Texte | Portée | Impact |
|-------|--------|--------|
| **CLOUD Act** (US, 2018) | Autorise le gouvernement US à exiger les données de toute entreprise US, **peu importe le lieu de stockage** | Les cloud US (AWS, Azure, Google) peuvent être contraints de livrer vos données |
| **RGPD** (UE) | Protection des données personnelles | Protège contre les transferts illicites |
| **Data Act** (UE, 2025) | Encadre l'accès gouvernemental aux données | Conflit direct avec le CLOUD Act |

#### Témoignage clé

> *En juin 2025, le directeur juridique de Microsoft France a confirmé sous serment devant le Sénat qu'il ne pouvait pas garantir que les données européennes ne seraient pas transmises aux autorités américaines.*

### 3.2 Niveaux de souveraineté cloud

| Niveau | Description | Exposition CLOUD Act | Exemples |
|--------|-------------|---------------------|----------|
| **1 — Cloud standard US en UE** | Serveurs en Europe, entreprise US | **Élevée** | AWS standard, Azure, Google Cloud |
| **2 — Cloud souverain US** | Filiale européenne, infrastructure dédiée | **Moyenne-élevée** | AWS ESC, Azure Deutschland |
| **3 — Opérateur européen + techno US** | Entreprise européenne gère, technologie US sous licence | **Réduite** | S3NS (Google/Thales), Bleu (Microsoft/Orange) |
| **4 — 100% européen** | Aucune maison mère US, pas de composant US | **Nulle** | OVHcloud, Scaleway, IONOS, 3DS Outscale |

### 3.3 Acteurs cloud européens (Niveau 4)

| Fournisseur | Pays | GPU disponibles | Certifications | Particularité |
|-------------|------|----------------|----------------|---------------|
| **Scaleway** (Iliad) | FR | H100, H200, **B300** | GAIA-X, en cours SecNumCloud | Seul européen avec Blackwell B300 |
| **OVHcloud** | FR | H100, L40S, A10 | **SecNumCloud**, HDS, ISO 27001 | 46 datacenters, 1,6M clients |
| **3DS Outscale** (Dassault) | FR | NVIDIA (bare metal) | **SecNumCloud 3.2** | Qualifié depuis 2025 |
| **IONOS** (DE/UK) | DE | H100 | C5 (DE) | Filiale 1&1 |
| **Hetzner** | DE | A100, RTX 4090 | Pas de SecNumCloud | Budget-friendly |

### 3.4 Le Cloud & AI Development Act (CADA) — UE

| Donnée | Valeur |
|--------|--------|
| Adoption | 3 juin 2026 |
| Publication | 15 juillet 2026 |
| Entrée en vigueur | **4 août 2026** |
| Objectif 2030 | **Tripler** la capacité data center européenne |
| Mécanisme | Permis accéléré + guichet unique par État membre |
| Classification | 4 niveaux de souveraineté cloud |

### 3.5 Contrat européen clé

> *En avril 2026, la Commission européenne a attribué un contrat de **180 millions d'euros** pour le cloud souverain des institutions de l'UE à **quatre fournisseurs européens** (OVHcloud, Scaleway, Clever Cloud, DEEP).*  
> — Cloud Magazin, juillet 2026

### 3.6 Conséquence pour le datacenter Camp Français

| Si opérateur US | Si opérateur européen |
|-----------------|----------------------|
| CLOUD Act = accès US garanti | Pas d'accès US possible |
| Pas SecNumCloud possible | SecNumCloud 3.2 possible |
| Dépendance logicielle US | Indépendance totale |
| Marchés publics UE= bloqués | Marchés publics UE= ouverts |

---

## 4. PUISSANCE DE CALCUL PAR UNITÉ DE SURFACE

### 4.1 Définition du rack standard

| Paramètre | Valeur |
|-----------|--------|
| Standard | **OCP ORv3** (Open Rack v3) |
| Dimensions rack | 600 mm (L) × 1200 mm (P) = **0,72 m²** |
| Hauteur | 48U (2 133 mm) |
| Lames par rack | **24** (1U par lame) |
| Puissance rack | 30-50 kW (air) / 80-120 kW (liquid cooling) |
| Surface totale rack | **0,72 m²** au sol |

### 4.2 Densité de calcul par GPU

| GPU | Mémoire | FP16 (TFLOPS) | Puissance (W) | kWh/TJ | Coût GPU |
|-----|---------|---------------|---------------|--------|----------|
| H100 SXM5 | 80 GB | 990 | 700W | 0,71 | ~30 000 $ |
| H200 SXM5 | 141 GB | 990 | 700W | 0,71 | ~40 000 $ |
| B200 SXM | 192 GB | ~2 500 | 1 000W | 0,40 | ~50 000 $ |
| AMD MI300X | 192 GB | 1 307 | 750W | 0,57 | ~12 000 $ |
| Huawei 910C | 96 GB | ~800 | 600W | 0,75 | ~15 000 $ |

### 4.3 Configuration rack type — 8 GPU par lame

| Configuration | GPU/rack | Mémoire totale | FP16 total | Puissance rack | Surface |
|--------------|----------|----------------|------------|----------------|---------|
| **8× H100** (1 lame) | 8 | 640 GB | 7 920 TFLOPS | 5,6 kW | 0,72 m² |
| **8× H100** (3 lames) | 24 | 1 920 GB | 23 760 TFLOPS | 16,8 kW | 2,16 m² |
| **8× B200** (1 lame) | 8 | 1 536 GB | 20 000 TFLOPS | 8,0 kW | 0,72 m² |
| **8× B200** (3 lames) | 24 | 4 608 GB | 60 000 TFLOPS | 24,0 kW | 2,16 m² |
| **8× MI300X** (1 lame) | 8 | 1 536 GB | 10 456 TFLOPS | 6,0 kW | 0,72 m² |

### 4.4 Indicateur « tokens/seconde/m² »

| Configuration | tok/s (Llama 70B) | tok/s/m² | tok/s/kW |
|--------------|-------------------|----------|----------|
| 8× H100 | ~3 000 × 8 = **24 000** | **33 333** | 4 286 |
| 8× H200 | ~6 000 × 8 = **48 000** | **66 667** | 8 571 |
| 8× B200 | ~17 500 × 8 = **140 000** | **194 444** | 17 500 |
| 8× MI300X | ~8 000 × 8 = **64 000** | **88 889** | 10 667 |

### 4.5 Métrique de synthèse

**Puissance de calcul = (tokens/seconde) / (surface au sol en m²)**

| Indicateur | H100 | H200 | B200 | MI300X |
|-----------|------|------|------|--------|
| **tok/s/m²** (par lame 8 GPU) | 33 333 | 66 667 | **194 444** | 88 889 |
| **tok/s/kW** | 4 286 | 8 571 | **17 500** | 10 667 |
| **tok/s/$** (GPU) | 0,8 | 1,2 | **2,8** | 5,3 |

**Le B200 offre la meilleure densité de calcul par m² et par kWh.**

---

## 5. INFRASTRUCTURE POUR KIMI K3 — CAS D'ÉTUDE

### 5.1 Spécifications Kimi K3

| Paramètre | Valeur |
|-----------|--------|
| Architecture | MoE (Mixture-of-Experts) |
| Paramètres totaux | **2,8 trillions** |
| Paramètres actifs/token | **104 milliards** (16/896 experts) |
| Contexte | **1 048 576 tokens** (~1M) |
| Poids sur disque | **1,56 TB** (MXFP4) |
| Quantization | MXFP4 weights / MXFP8 activations |
| Encodage vision | MoonViT-V2 (401M params) |
| Licence | Kimi K3 License (MIT-like + clause MaaS) |

### 5.2 Métriques de performance (Lambda Labs)

| Métrique | Valeur (2× B200) |
|----------|-------------------|
| Time to first token | 9 425 ms (moy) / 79 958 ms (P99) |
| Time per output token | 102,66 ms (moy) / 140,70 ms (P99) |
| Inter-token latency | 102,61 ms (moy) / 1 353 ms (P99) |
| Configuration | TP=8, PP=2, 16 GPU B200 |
| Concurrent requests | 32 |
| Batch | 512 prompts, 8192 in / 2048 out tokens |

### 5.3 Besoin mémoire

| Composante | Taille |
|-----------|--------|
| Poids modèle (MXFP4) | **1,56 TB** |
| KV cache (contexte 1M, 32 requêtes) | **~400-600 GB** |
| Overhead framework | **~100 GB** |
| **Total** | **~2,0-2,3 TB** |

### 5.4 Configurations matérielles

#### Option 1 — B200 (recommandé NVIDIA)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **16× B200** (2 nœuds 8 GPU) |
| Mémoire totale | 16 × 192 GB = **3,07 TB** |
| Nœuds | 2 × HGX B200 |
| Interconnexion | InfiniBand 400 Gb/s |
| Poids = 1,56 TB | ✅ tient en mémoire |
| KV cache + overhead | ✅ marge suffisante |
| Surface | **2 × 0,72 = 1,44 m²** |
| Puissance | 2 × 8 kW = **16 kW** |
| Coût GPU estimé | 16 × 50 000 = **800 000 $** |

#### Option 2 — H200 (alternative)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **24× H200** (3 nœuds 8 GPU) |
| Mémoire totale | 24 × 141 GB = **3,38 TB** |
| Nœuds | 3 × HGX H200 |
| Interconnexion | InfiniBand 400 Gb/s |
| Poids = 1,56 TB | ✅ tient en mémoire |
| KV cache + overhead | ✅ marge suffisante |
| Surface | **3 × 0,72 = 2,16 m²** |
| Puissance | 3 × 5,6 kW = **16,8 kW** |
| Coût GPU estimé | 24 × 40 000 = **960 000 $** |

#### Option 3 — Quantization agressive (llama.cpp)

| Paramètre | Valeur |
|-----------|--------|
| Format | UD-IQ1_S (1-bit dynamique) |
| Taille modèle | **594 GB** |
| GPU requis | **8× H100** (1 nœud) |
| Qualité | ~79% top-1 accuracy, PPL 2,58 |
| Surface | **0,72 m²** |
| Puissance | **5,6 kW** |
| Coût GPU estimé | 8 × 30 000 = **240 000 $** |
| **Compromis** | Perte qualité significative |

### 5.5 Comparaison des options

| Option | GPU | Surface | Puissance | Coût GPU | Qualité | tok/s |
|--------|-----|---------|-----------|----------|---------|-------|
| **B200 (recommandé)** | 16× B200 | 1,44 m² | 16 kW | 800 k$ | ✅ Native | ~100 tok/s |
| **H200** | 24× H200 | 2,16 m² | 16,8 kW | 960 k$ | ✅ Native | ~70 tok/s |
| **H100 (native)** | 24× H100 | 2,16 m² | 16,8 kW | 720 k$ | ⚠️ Tight | ~50 tok/s |
| **Quantized 1-bit** | 8× H100 | 0,72 m² | 5,6 kW | 240 k$ | ❌ 79% | ~20 tok/s |

### 5.6 Infra complète recommandée

| Composant | Spécification | Coût estimé |
|-----------|---------------|-------------|
| **GPU** | 16× NVIDIA B200 SXM | 800 000 $ |
| **Serveurs** | 2× HGX B200 (8 GPU, liquid cooling) | 200 000 $ |
| **Interconnexion** | InfiniBand NDR 400 Gb/s | 50 000 $ |
| **Stockage** | 2 TB NVMe SSD (checkpoint) | 10 000 $ |
| **Réseau** | Switch InfiniBand, câblage | 20 000 $ |
| **Refroidissement** | Liquid cooling CDU (2×) | 60 000 $ |
| **Alimentation** | 30 kW alimentation redondante | 30 000 $ |
| **Rack** | 2× OCP ORv3 (liquid cooling) | 20 000 $ |
| **Logiciel** | vLLM, Kubernetes, monitoring | 10 000 $ |
| **TOTAL** | | **~1,2 M$** |

### 5.7 Besoin énergétique annuel

| Paramètre | Valeur |
|-----------|--------|
| Puissance calcul | 16 kW |
| Puissance refroidissement | ~5 kW |
| Puissance totale | **~21 kW** |
| Heures utilisation/an | 8 760 h |
| **Consommation annuelle** | **~184 MWh** |
| Coût électricité (0,15 €/kWh) | **~27 600 €/an** |

### 5.8 Infra pour usage « meilleur raisonnement »

Kimi K3 supporte 3 niveaux de « thinking effort » :

| Niveau | Usage | Token generating | Temps réponses |
|--------|-------|------------------|----------------|
| **Low** | Questions simples | Rapide | ~100 ms/tok |
| **High** | Raisonnement modéré | Moyen | ~100 ms/tok |
| **Max** | Raisonnement complexe, coding | Lent (beaucoup de tokens thinking) | ~100 ms/tok |

Pour le **meilleur raisonnement** (Max), il faut :
- **Contexte long** : 100K-1M tokens → KV cache important
- **Débit élevé** : 32+ requêtes concurrentes
- **Latence faible** : <200 ms inter-token

→ Configuration **16× B200** recommandée (Option 1).

---

## 6. RECOMMANDATIONS POUR LE DATACENTER CAMP FRANÇAIS

### 6.1 Positionnement

| Critère | Recommandation |
|---------|----------------|
| **Opérateur** | Européen (Niveau 4 souveraineté) — Scaleway, OVHcloud, ou équivalent |
| **GPU** | NVIDIA Blackwell B200 (seul européen avec B300 via Scaleway) |
| **Alternative** | AMD MI300X (192 GB, disponible Scaleway/OVHcloud) |
| **Logiciel** | CUDA (NVIDIA) ou ROCm (AMD) — pas de CANN (Huawei) |
| **Certification** | SecNumCloud 3.2 (ANSSI) |

### 6.2 Arguments souveraineté

| Argument | Justification |
|----------|--------------|
| Cloud Act = pas de cloud US | Même hébergé en France, AWS/Azure/Google = accès US |
| CADA (août 2026) | Marchés publics UE= exigeront niveau 3-4 |
| Contrat CE 180 M€ | Fournisseurs européens sélectionnés |
| SecNumCloud 3.2 | Seule certification anti-extraterritorialité |

### 6.3 Comparatif NVIDIA vs Huawei

| Critère | NVIDIA | Huawei Ascend |
|---------|--------|---------------|
| Performance | ✅ Référence mondiale | ❌ 60% de H100 |
| Disponibilité Europe | ⚠️ Pénurie | ❌ Pas dispo hors Chine |
| Logiciel | ✅ CUDA mature | ❌ CANN immature |
| Souveraineté UE | ⚠️ Dépendance US | ❌ Dépendance Chine |
| Open source | ✅ CUDA ecosystem | ⚠️ CANN partly open |
| Prix | ❌ Très élevé | ✅ 2-3× moins cher |

**Verdict** : Pour un datacenter souverain européen, **NVIDIA reste le choix par défaut** (CUDA, performance, disponibilité Scaleway/OVHcloud). Huawei = pas d'option pour l'Europe.

### 6.4 Phase de transition recommandée

| Phase | Horizon | Action |
|-------|---------|--------|
| **1 — Immédiat** | 2026-2027 | Cloud Scaleway/OVHcloud (B200/H100) — pas de construction datacenter |
| **2 — Court terme** | 2027-2028 | Contrat long terme GPU (Scaleway cluster dédié) |
| **3 — Moyen terme** | 2028-2030 | Construction datacenter souverain si volume le justifie |
| **4 — Long terme** | 2030+ | Évaluation GPU européens (si apparition) |

---

## 8. LEXIQUE DES ACRONYMES

### Matériel / Processeurs

| Acronyme | Signification |
|----------|---------------|
| **GPU** | Graphics Processing Unit — Processeur graphique, utilisé pour le calcul parallèle en IA |
| **ASIC** | Application-Specific Integrated Circuit — Circuit intégré spécialisé (ex. Google TPU) |
| **FPGA** | Field-Programmable Gate Array — Circuit reconfigurable après fabrication |
| **HBM** | High Bandwidth Memory — Mémoire haute bande passante (HBM2e, HBM3, HBM3e) |
| **HBM2e** | Génération améliorée de HBM2 (~3,2 TB/s par stack) |
| **HBM3** | HBM de 3e génération (~5 TB/s par stack, NVIDIA A100/H100) |
| **HBM3e** | HBM3 améliorée (~8 TB/s par stack, NVIDIA H200/B200) |
| **SXM** | Server Module X — Format carte GPU haute performance (NVIDIA) |
| **GB** | Gigaoctet — 10⁹ octets |
| **TB** | Téraoctet — 10¹² octets |
| **GB/s** | Gigaoctets par seconde — Unité de bande passante mémoire |
| **TB/s** | Téraoctets par seconde — Unité de bande passante mémoire |

### Mesures de performance

| Acronyme | Signification |
|----------|---------------|
| **TFLOPS** | Téra (10¹²) Floating Point Operations Per Second — Opérations virgule flottante par seconde |
| **PFLOPS** | Péta (10¹⁵) FLOPS — 1 000 TFLOPS |
| **EFLOPS** | Exa (10¹⁸) FLOPS — 1 000 PFLOPS |
| **FP16** | Floating Point 16-bit — Demi-précision (2 octets par paramètre) |
| **FP32** | Floating Point 32-bit — Précision simple (4 octets) |
| **FP64** | Floating Point 64-bit — Précision double (8 octets) |
| **INT8** | Integer 8-bit — Entier 8 bits (quantization) |
| **MXFP4** | Microscaling Floating Point 4-bit — Quantization ultra-agressive (1,56 TB pour Kimi K3) |
| **MXFP8** | Microscaling Floating Point 8-bit — Quantization pour activations |
| **PPL** | Perplexity — Mesure de qualité d'un modèle de langage (plus bas = mieux) |

### Processeurs spécifiques

| Acronyme | Signification |
|----------|---------------|
| **H100** | NVIDIA Hopper — GPU datacenter de 2022 (80 GB HBM3, 990 TFLOPS FP16) |
| **H200** | NVIDIA Hopper amélioré — GPU 2024 (141 GB HBM3e, 990 TFLOPS FP16) |
| **B200** | NVIDIA Blackwell — GPU 2024/2025 (192 GB HBM3e, ~2 500 TFLOPS FP16) |
| **GB200** | NVIDIA Grace Blackwell Superchip — CPU+GPU combiné |
| **GB300** | NVIDIA Blackwell Ultra — GPU 2025/2026 (amélioration B200) |
| **A100** | NVIDIA Ampere — GPU datacenter (2020, 40/80 GB HBM2e) |
| **MI300X** | AMD Instinct MI300X — GPU AMD (192 GB HBM3e, 1 307 TFLOPS FP16) |
| **MI325X** | AMD Instinct MI325X — GPU AMD (288 GB HBM3e, 2 615 TFLOPS FP16) |
| **L40S** | NVIDIA L40S — GPU inference/visualisation (48 GB GDDR6) |
| **Ascend 910B** | Huawei Ascend — GPU chinois (~600 TFLOPS FP16, 64 GB HBM2e) |
| **Ascend 910C** | Huawei Ascend — GPU chinois (~800 TFLOPS FP16, 96 GB HBM2e) |
| **TPU** | Tensor Processing Unit — Processeur IA propriétaire Google |
| **RISC-V** | Instruction set open source — Architecture alternative (pas encore GPU IA) |

### Fabrication / Semi-conducteurs

| Acronyme | Signification |
|----------|---------------|
| **TSMC** | Taiwan Semiconductor Manufacturing Company — Fonderie n°1 mondiale (Taïwan) |
| **SMIC** | Semiconductor Manufacturing International Corporation — Fonderie chinoise (plafonnée 7nm) |
| **EUV** | Extreme UltraViolet — Lithographie ultraviolette extrême (nœud 7nm et moins) |
| **DUV** | Deep UltraViolet — Lithographie standard (7nm+ sans EUV) |
| **nm** | Nanomètre — Unité de taille de nœud de gravure (plus petit = meilleur) |
| **CoWoS** | Chip on Wafer on Substrate — Empaquetage avancé TSMC pour GPU IA |
| **InFO** | Integrated Fan-Out — Alternative CoWoS (moins coûteuse, moins performante) |
| **GAA** | Gate-All-Around — Architecture transistor 3nm+ (futur 2nm) |
| **FinFET** | Fin Field Effect Transistor — Architecture transistor 14nm-3nm |
| **TSV** | Through-Silicon Via — Connexions verticales inter-couches |

### Logiciel / Frameworks

| Acronyme | Signification |
|----------|---------------|
| **CUDA** | Compute Unified Device Architecture — Plateforme logicielle NVIDIA (17 ans, standard de facto) |
| **CANN** | Compute Architecture for Neural Networks — Plateforme logicielle Huawei Ascend |
| **ROCm** | Radeon Open Compute — Plateforme logicielle AMD (alternative open source à CUDA) |
| **vLLM** | Virtual Large Language Model — Moteur d'inférence LLM haute performance |
| **TensorRT** | Moteur d'optimisation NVIDIA pour inférence |
| **TensorRT-LLM** | Extension TensorRT pour LLM |
| **PyTorch** | Framework d'entraînement IA (Meta) |
| **TP** | Tensor Parallelism — Parallélisme sur plusieurs GPU |
| **PP** | Pipeline Parallelism — Parallélisme sur couches du modèle |
| **DP** | Data Parallelism — Parallélisme sur batch de données |

### Cloud / Réseau

| Acronyme | Signification |
|----------|---------------|
| **IaaS** | Infrastructure as a Service — Infrastructure en tant que service |
| **PaaS** | Platform as a Service — Plateforme en tant que service |
| **SaaS** | Software as a Service — Logiciel en tant que service |
| **Bare Metal** | Serveur dédié physique (pas de virtualisation) |
| **InfiniBand** | Réseau haute performance RDMA (400 Gb/s, 800 Gb/s) |
| **NVLink** | Connexion GPU-NVIDIA propriétaire (900 GB/s) |
| **NVSwitch** | Switch NVLink (connexion multi-GPU) |
| **OCP** | Open Compute Project — Standard rack/datacenter open source |
| **ORv3** | Open Rack v3 — Standard rack OCP pour datacenter |
| **HGX** | NVIDIA HGX — Plateforme serveur 8 GPU NVIDIA |

### Réglementation / Souveraineté

| Acronyme | Signification |
|----------|---------------|
| **CLOUD Act** | Clarifying Lawful Overseas Use of Data Act — Loi US autorisant l'accès aux données hors US |
| **FISA** | Foreign Intelligence Surveillance Act — Loi US de surveillance étrangère |
| **RGPD** | Règlement Général sur la Protection des Données — GDPR en français |
| **SecNumCloud** | Certification ANSSI pour cloud souverain français (niveau 3.2) |
| **GAIA-X** | Initiative européenne d'infrastructure cloud souveraine |
| **CADA** | Cloud & AI Development Act — Règlement UE sur l'IA souveraine |
| **HDS** | Hébergeur de Données de Santé — Certification hébergement santé (France) |
| **ISO 27001** | Norme internationale de sécurité de l'information |
| **ANSSI** | Agence Nationale de la Sécurité des Systèmes d'Information |
| **ESCC** | European Sovereign Cloud Consortium — Consortium cloud souverain UE |

### Modèles d'IA

| Acronyme | Signification |
|----------|---------------|
| **LLM** | Large Language Model — Modèle de langage de grande taille |
| **MoE** | Mixture of Experts — Architecture multi-experts (Kimi K3 = 896 experts, 16 actifs) |
| **RLHF** | Reinforcement Learning from Human Feedback — Apprentissage par renforcement humain |
| **MaaS** | Model as a Service — Modèle en tant que service (API) |
| **MTP** | Multi-Token Prediction — Prédiction de plusieurs tokens simultanément (Kimi K3) |
| **tok/s** | Tokens par seconde — Débit d'inférence |

### Entreprises / Organisations

| Acronyme | Signification |
|----------|---------------|
| **NVIDIA** | Société US de GPU et IA (fondateur Jensen Huang) |
| **AMD** | Advanced Micro Devices — Concurrent US de NVIDIA (GPU Instinct) |
| **Intel** | Concurrent US (GPU Gaudi, fonderie propre) |
| **Huawei** | Technologie chinoise (GPU Ascend, plateforme CANN) |
| **TSMC** | Fonderie taïwanaise (AMD, NVIDIA, Apple, Qualcomm) |
| **SK Hynix** | Fonderie coréenne de mémoire (HBM) |
| **Samsung** | Fonderie coréenne de mémoire (HBM) |
| **Micron** | Fonderie US de mémoire (HBM) |
| **ASML** | Fournisseur néerlandais de machines lithographie EUV (monopole) |
| **Scaleway** | Cloud français (filiale Iliad) — Seul européen avec B300 |
| **OVHcloud** | Cloud français — 46 datacenters, 1,6M clients |
| **IONOS** | Cloud allemand (filiale 1&1) |
| **Hetzner** | Cloud allemand (budget-friendly) |
| **3DS Outscale** | Cloud français (filiale Dassault) — SecNumCloud 3.2 |

---

## 7. RÉFÉRENCES

### Sources principales

| Document | URL |
|----------|-----|
| NVIDIA GPU Shortage 2026 | [neuralwired.com](https://neuralwired.com/2026/05/30/nvidia-gpu-shortage-2026-ai-compute/) |
| GPU Supply Chain 2026 | [sourcebyspec.com](https://www.sourcebyspec.com/news/gpu-supply-chain-2026-cowos-hbm-and-wafer-bottlenecks-reshape-sourcing.html) |
| Kimi K3 GitHub | [github.com/MoonshotAI/Kimi-K3](https://github.com/MoonshotAI/Kimi-K3) |
| Kimi K3 GPU Requirements | [packet.ai](https://packet.ai/blog/moonshot-kimi-k3-gpu-requirements) |
| Kimi K3 Lambda Labs | [lambda.ai](https://lambda.ai/inference-models/moonshotai/kimi-k3) |
| Kimi K3 Hardware | [yottalabs.ai](https://www.yottalabs.ai/post/kimi-k3-hardware-requirements-gpu-memory-2026) |
| Huawei Ascend vs NVIDIA | [cfr.org](https://www.cfr.org/articles/chinas-ai-chip-deficit-why-huawei-cant-catch-nvidia-and-us-export-controls-should-remain) |
| Ascend 910C Performance | [awesomeagents.ai](https://awesomeagents.ai/hardware/huawei-ascend-910c/) |
| CLOUD Act et souveraineté | [bontrain.fr](https://bontrain.fr/ressources/cloud-act-donnees-europeennes) |
| 4 niveaux souveraineté | [fromeuropewithlove.eu](https://www.fromeuropewithlove.eu/fr/blog/quatre-niveaux-souverainete-cloud-guide-ctos-europeens) |
| CADA (Cloud & AI Development Act) | [genee.tech](https://www.genee.tech/blog/cloud-ai-development-act-cada-ue-data-centers-souverainete-aout-2026) |
| Scaleway GPU | [scaleway.com](https://www.scaleway.com/en/gpu-instances/) |
| OVHcloud sovereign cloud | [corporate.ovhcloud.com](https://corporate.ovhcloud.com/en/newsroom/news/ovhcloud-deep-clever-cloud-consortium/) |
| Cloud Act et FISA | [parlons.cloud](https://www.parlons.cloud/cloud-act-fisa-et-lillusion-du-datacenter-en-france/) |

---

*Document complémentaire au dossier d'opposition datacenter Camp Français — Septembre 2026*
