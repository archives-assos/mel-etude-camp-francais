# INFRASTRUCTURE IA - GPU, SOUVERAINETÉ ET PUISSANCE DE CALCUL

**Objet** : Analyse des contraintes matérielles, géopolitiques et de souveraineté pour un datacenter IA en France  
**Date** : Septembre 2026  
**Statut** : Document de travail

---

## TABLE DES MATIÈRES

1. [Pénurie GPU - État des lieux 2026](#1-pénurie-gpu--état-des-lieux-2026)
2. [NVIDIA vs Chine - Géopolitique des puces](#2-nvidia-vs-chine--géopolitique-des-puces)
3. [Acteurs cloud et souveraineté](#3-acteurs-cloud-et-souveraineté)
4. [Puissance de calcul par unité de surface](#4-puissance-de-calcul-par-unité-de-surface)
5. [Études de cas - Modèles ouverts 2026](#5-études-de-cas--modèles-ouverts-2026)
   - 5.1 [Gemma 4](#51-gemma-4--cas-détude)
   - 5.2 [Qwen 3.8](#52-qwen-38--cas-détude)
   - 5.3 [DeepSeek-R1](#53-deepseek-r1--cas-détude)
   - 5.4 [Comparaison cross-modèles](#54-comparaison-cross-modèles)
6. [Recommandations pour le datacenter Camp Français](#6-recommandations-pour-le-datacenter-camp-français)
7. [Lexique des acronymes](#7-lexique-des-acronymes)
8. [Estimation de capacité de calcul - 22 ha](#8-estimation-de-capacité-de-calcul--22-ha)
9. [Références](#9-références)

---

## 1. PÉNURIE GPU - ÉTAT DES LIEUX 2026

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
> - NeuralWired, mai 2026

**Les hyperscalers ont verrouillé les allocations.** Toute entreprise non adossée à un fonds souverain fait la queue sur le marché spot à des prix 20-30% supérieurs.

---

## 2. NVIDIA VS CHINE - GÉOPOLITIQUE DES PUCES

### 2.1 NVIDIA - Monopole de facto

| Donnée | Valeur |
|--------|--------|
| Part marché accélérateurs datacenter | **>80%** |
| Production puce IA 2025 | ~4,5 millions d'unités |
| Production prévue 2026 | ~6,75 millions (+50%) |
| Production prévue 2027 | ~10,125 millions (+50%) |
| Écosystème logiciel | **CUDA** (17 ans, standard de facto) |

### 2.2 Huawei Ascend - Alternative chinoise

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

### 2.6 Acteurs européens - État des lieux

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
| **1 - Cloud standard US en UE** | Serveurs en Europe, entreprise US | **Élevée** | AWS standard, Azure, Google Cloud |
| **2 - Cloud souverain US** | Filiale européenne, infrastructure dédiée | **Moyenne-élevée** | AWS ESC, Azure Deutschland |
| **3 - Opérateur européen + techno US** | Entreprise européenne gère, technologie US sous licence | **Réduite** | S3NS (Google/Thales), Bleu (Microsoft/Orange) |
| **4 - 100% européen** | Aucune maison mère US, pas de composant US | **Nulle** | OVHcloud, Scaleway, IONOS, 3DS Outscale |

### 3.3 Acteurs cloud européens (Niveau 4)

| Fournisseur | Pays | GPU disponibles | Certifications | Particularité |
|-------------|------|----------------|----------------|---------------|
| **Scaleway** (Iliad) | FR | H100, H200, **B300** | GAIA-X, en cours SecNumCloud | Seul européen avec Blackwell B300 |
| **OVHcloud** | FR | H100, L40S, A10 | **SecNumCloud**, HDS, ISO 27001 | 46 datacenters, 1,6M clients |
| **3DS Outscale** (Dassault) | FR | NVIDIA (bare metal) | **SecNumCloud 3.2** | Qualifié depuis 2025 |
| **IONOS** (DE/UK) | DE | H100 | C5 (DE) | Filiale 1&1 |
| **Hetzner** | DE | A100, RTX 4090 | Pas de SecNumCloud | Budget-friendly |

### 3.4 Le Cloud & AI Development Act (CADA) - UE

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
> - Cloud Magazin, juillet 2026

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

### 4.3 Configuration rack type - 8 GPU par lame

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

## 5. ÉTUDES DE CAS - MODÈLES OUVERTS 2026

### 5.0 Vue d'ensemble des modèles étudiés

| Paramètre | Kimi K3 | Gemma 4 31B | Gemma 4 26B A4B | Qwen 3.8 27B | DeepSeek-R1 |
|-----------|---------|-------------|-----------------|--------------|-------------|
| **Architecture** | MoE | Dense | MoE | Dense (hybride) | MoE (MLA) |
| **Params totaux** | 2,8 T | 30,7 B | 25,2 B | 27 B | **671 B** |
| **Params actifs/token** | 104 B | 30,7 B | 3,8 B | 27 B | **37 B** |
| **Experts** | 896 (16 actifs) | - | 128 (8 actifs + 1 shared) | - | **256 (8 actifs)** |
| **Contexte natif** | 1 048 576 | 256 K | 256 K | 262 K (→ 1M YaRN) | **128 K** |
| **Poids BF16** | ~5,6 TB | ~62 GB | ~52 GB | ~56 GB | **~1,34 TB** |
| **Poids quantifié** | 1,56 TB (MXFP4) | 17,5 GB (Q4) | 14,4 GB (Q4) | 17,1 GB (Q4_K_M) | **408 GB (Q4)** |
| **Licence** | Kimi K3 (MIT-like) | Apache 2.0 | Apache 2.0 | Apache 2.0 | **MIT** |
| **Vision** | Oui | Oui | Oui | Oui | Non |
| **Thinking mode** | Oui | Oui | Oui | Oui | Oui (RL)

---

## 5.1 GEMMA 4 - CAS D'ÉTUDE

### 5.1.1 Spécifications Gemma 4

Gemma 4 est une famille de modèles open weights de Google DeepMind, disponible en 5 tailles. Pour un datacenter, les deux modèles pertinents sont le **31B Dense** (qualité maximale) et le **26B A4B MoE** (meilleur rapport débit/coût).

| Modèle | Params totaux | Params actifs | Architecture | Contexte | Vision | Audio |
|--------|---------------|---------------|--------------|----------|--------|-------|
| **E2B** | 2,3 B eff. (5,1 B incl. embeddings) | 2,3 B | Dense + PLE | 128 K | Oui | Oui |
| **E4B** | 4,5 B eff. (8 B incl. embeddings) | 4,5 B | Dense + PLE | 128 K | Oui | Oui |
| **12B Unified** | 11,95 B | 12 B | Dense, encoder-free | 256 K | Oui | Oui |
| **26B A4B** | 25,2 B | **3,8 B** | MoE (8/128 experts + 1 shared) | 256 K | Oui | Non |
| **31B Dense** | 30,7 B | 30,7 B | Dense | 256 K | Oui | Non |

### 5.1.2 Mémoire requise (poids uniquement)

| Modèle | BF16 (16-bit) | SFP8 (8-bit) | Q4_0 (4-bit) | Recommandé |
|--------|---------------|--------------|--------------|------------|
| **31B Dense** | 69,9 GB | 34,9 GB | 17,5 GB | A100 80GB ou H100 |
| **26B A4B MoE** | 57,7 GB | 28,8 GB | 14,4 GB | A100 40GB ou RTX 4090 |

> ⚠️ Le modèle 26B A4B MoE n'active que 3,8 B paramètres/token, mais **les 25,2 B doivent rester en mémoire** pour le routage des experts.

### 5.1.3 KV cache (contexte 256K)

| Modèle | KV cache (256K, BF16) | + Poids | Total estimé |
|--------|----------------------|---------|--------------|
| **31B Dense** | ~20-30 GB | 69,9 GB | **~90-100 GB** |
| **26B A4B MoE** | ~20-30 GB | 57,7 GB | **~78-88 GB** |

### 5.1.4 Configurations matérielles - Gemma 4 31B Dense

#### Option A - BF16 (qualité maximale)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **2× H100 80GB** (1 nœud) |
| Mémoire totale | 2 × 80 GB = **160 GB** |
| Poids BF16 = 69,9 GB | ✅ |
| KV cache 256K + overhead | ✅ (~90-100 GB total) |
| Surface | **0,72 m²** |
| Puissance | **~5,6 kW** |
| Coût GPU estimé | 2 × 30 000 = **60 000 $** |

#### Option B - Q4_0 (économique)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **1× RTX 4090 24GB** |
| Mémoire totale | **24 GB** |
| Poids Q4 = 17,5 GB | ✅ (tight, contexte limité à ~32K) |
| Surface | **poste de travail** |
| Puissance | **~450 W** |
| Coût GPU estimé | **~2 000 $** |

### 5.1.5 Configurations matérielles - Gemma 4 26B A4B MoE

#### Option A - BF16 (qualité max, débit élevé)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **2× H100 80GB** |
| Mémoire totale | **160 GB** |
| Poids BF16 = 57,7 GB | ✅ |
| KV cache 256K + overhead | ✅ |
| Surface | **0,72 m²** |
| Puissance | **~5,6 kW** |
| Coût GPU estimé | 2 × 30 000 = **60 000 $** |
| **Avantage** | Seulement 3,8 B actifs → débit token/s très élevé |

#### Option B - Q4_0 (ultra-économique)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **1× RTX 4090 24GB** |
| Mémoire totale | **24 GB** |
| Poids Q4 = 14,4 GB | ✅ (confortable, contexte ~64K) |
| Surface | **poste de travail** |
| Puissance | **~450 W** |
| Coût GPU estimé | **~2 000 $** |

### 5.1.6 Comparaison Gemma 4 - Datacenter vs Poste de travail

| Configuration | GPU | Surface | Puissance | Coût | Contexte max | Usage |
|--------------|-----|---------|-----------|------|-------------|-------|
| **31B BF16 (datacenter)** | 2× H100 | 0,72 m² | 5,6 kW | 60 k$ | 256 K | Production, multi-utilisateurs |
| **31B Q4 (poste)** | 1× RTX 4090 | bureau | 450 W | 2 k$ | ~32 K | Développement, test |
| **26B MoE BF16 (datacenter)** | 2× H100 | 0,72 m² | 5,6 kW | 60 k$ | 256 K | Production, haut débit |
| **26B MoE Q4 (poste)** | 1× RTX 4090 | bureau | 450 W | 2 k$ | ~64 K | Développement, test |

### 5.1.7 Capacité utilisateurs - Gemma 4 31B Dense (2× H100)

| Scénario | Requêtes concurrentes | Utilisateurs simultanés | Utilisateurs journaliers |
|----------|----------------------|------------------------|-------------------------|
| **Think Low** (questions simples) | ~80-100 | **~80-100** | ~800-1 000 |
| **Think High** (raisonnement) | ~50-60 | **~50-60** | ~500-600 |
| **Think Max** (coding complexe) | ~30-40 | **~30-40** | ~300-400 |

### 5.1.8 Verdict Gemma 4

> **Gemma 4 31B Dense** : modèle le plus capable de la famille, nécessite **2× H100** pour le datacenter (BF16, contexte 256K). Alternativement, **1× H100** suffit en Q8 (34,9 GB).
>
> **Gemma 4 26B A4B MoE** : meilleur rapport débit/coût - 3,8 B actifs = token/s très élevés, idéal pour le **serving à haut débit**. Même infra que le 31B.
>
> **Pour le datacenter Camp Français** : le **26B A4B MoE** est le meilleur choix si l'objectif est le débit (API publique). Le **31B Dense** si l'objectif est la qualité maximale (recherche, coding agent).

---

## 5.2 QWEN 3.8 - CAS D'ÉTUDE

### 5.2.1 Spécifications Qwen 3.8

Qwen 3.8 est une famille d'Alibaba, sortie en août 2026. Le modèle principal est le **27B dense** avec attention hybride (Gated DeltaNet + Attention complète).

| Paramètre | Qwen 3.8 27B | Qwen 3.8 Flash-Next | Qwen 3.8 Max (2,4T) |
|-----------|-------------|---------------------|---------------------|
| **Architecture** | Dense, hybride | MoE sparse | MoE sparse |
| **Params totaux** | **27 B** | 180 B (6 B actifs) | 2,4 T (95 B actifs) |
| **Params actifs/token** | 27 B | 6 B | 95 B |
| **Couches** | 64 (16 attention + 48 DeltaNet) | 48 | 92 |
| **Contexte natif** | **262 K** (→ 1M YaRN) | 262 K (→ 1M YaRN) | 262 K (→ 1M) |
| **Vision** | Oui (texte + image + vidéo) | Oui | Non (texte seul) |
| **Licence** | **Apache 2.0** | qwen-community-1.0 | qwen3.8-max (custom) |

#### Architecture hybride - Clé de voûte

Le 27B utilise un système **3:1** : 3 couches Gated DeltaNet (attention linéaire, état récurrent fixe) pour 1 couche d'attention complète (KV cache croissant). Sur 64 couches, **seules 16 couches** génèrent un KV cache qui croît avec le contexte.

**Conséquence** : le KV cache est **4× plus petit** qu'un modèle dense classique de même taille.

### 5.2.2 Mémoire requise (Qwen 3.8 27B)

| Quantization | Poids | KV cache (8K) | KV cache (256K) | Total (256K) |
|-------------|-------|---------------|-----------------|--------------|
| **BF16** | 55,6 GB | 0,54 GB | ~16 GB | **~72 GB** |
| **FP8** | ~28 GB | 0,54 GB | ~16 GB | **~45 GB** |
| **Q8_0** | 29 GB | 0,54 GB | ~16 GB | **~46 GB** |
| **Q4_K_M** | 17,1 GB | 0,54 GB | ~16 GB | **~34 GB** |
| **Q3_K_M** | 13,4 GB | 0,54 GB | ~16 GB | **~30 GB** |

> 💡 Grâce à l'attention hybride, le KV cache à 256K ne coûte que **~16 GB** au lieu de **~64 GB** pour un modèle dense classique. C'est **l'avantage concurrentiel majeur** de Qwen 3.8.

### 5.2.3 Configurations matérielles - Qwen 3.8 27B

#### Option A - BF16 (qualité maximale)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **2× H100 80GB** (1 nœud) |
| Mémoire totale | **160 GB** |
| Poids BF16 = 55,6 GB | ✅ |
| KV cache 256K = ~16 GB | ✅ |
| Total ~72 GB | ✅ large marge |
| Surface | **0,72 m²** |
| Puissance | **~5,6 kW** |
| Coût GPU estimé | 2 × 30 000 = **60 000 $** |

#### Option B - FP8 (meilleur compromis)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **1× H100 80GB** ou **1× L40S 48GB** |
| Mémoire totale | 80 ou 48 GB |
| Poids FP8 = ~28 GB | ✅ |
| KV cache 256K = ~16 GB | ✅ |
| Total ~45 GB | ✅ sur H100, ⚠️ tight sur L40S |
| Surface | **0,36 m²** |
| Puissance | **~3 kW** |
| Coût GPU estimé | **30 000 $** (H100) ou **15 000 $** (L40S) |

#### Option C - Q4_K_M (économique, production)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **1× RTX 4090 24GB** (poste) ou **1× A6000 48GB** (datacenter) |
| Poids Q4 = 17,1 GB | ✅ |
| KV cache 256K = ~16 GB | ⚠️ 24 GB tight → contexte réel ~32-64K |
| Surface | **bureau** ou **0,36 m²** |
| Puissance | **450 W** (RTX 4090) ou **300 W** (A6000) |
| Coût GPU estimé | **~2 000 $** (RTX 4090) ou **~5 000 $** (A6000) |

### 5.2.4 Comparaison Qwen 3.8 - Options datacenter

| Configuration | GPU | Surface | Puissance | Coût | Contexte | Usage |
|--------------|-----|---------|-----------|------|----------|-------|
| **27B BF16** | 2× H100 | 0,72 m² | 5,6 kW | 60 k$ | 256 K | Production, qualité max |
| **27B FP8** | 1× H100 | 0,36 m² | 3 kW | 30 k$ | 256 K | Production, bon compromis |
| **27B Q4 (A6000)** | 1× A6000 | 0,36 m² | 300 W | 5 k$ | 32-64 K | Production, budget |
| **27B Q4 (RTX 4090)** | 1× RTX 4090 | bureau | 450 W | 2 k$ | 32-64 K | Développement |

### 5.2.5 Capacité utilisateurs - Qwen 3.8 27B (2× H100, BF16)

L'attention hybride de Qwen 3.8 permet un throughput plus élevé qu'un modèle dense classique de même taille, car le KV cache réduit la pression mémoire.

| Scénario | Requêtes concurrentes | Utilisateurs simultanés | Utilisateurs journaliers |
|----------|----------------------|------------------------|-------------------------|
| **Think Low** (questions simples) | ~100-150 | **~100-150** | ~1 000-1 500 |
| **Think High** (raisonnement) | ~60-80 | **~60-80** | ~600-800 |
| **Think Max** (coding complexe) | ~40-50 | **~40-50** | ~400-500 |

### 5.2.6 Verdict Qwen 3.8

> **Qwen 3.8 27B** : le meilleur modèle **single-GPU** de cette étude. En **FP8 sur 1× H100**, il tient en **0,36 m²** avec un contexte de 256K - infiniment plus compact que les alternatives MoE géantes.
>
> **L'attention hybride** est l'avantage clé : KV cache 4× plus petit = plus d'utilisateurs simultanés par GB de VRAM.
>
> **Pour le datacenter Camp Français** : le **27B FP8 sur 1× H100** offre le meilleur ratio **coût/surface/capacité**. Idéal pour un SaaS ou un outil interne à 100+ utilisateurs.

---

## 5.3 DEEPSEEK-R1 - CAS D'ÉTUDE

### 5.2B.1 Spécifications DeepSeek-R1

DeepSeek-R1 (janvier 2025) est le modèle reasoning open emblématique - entraîné par RL pure (GRPO) sans SFT, licence MIT.

| Paramètre | Valeur |
|-----------|--------|
| **Architecture** | MoE - DeepSeekMoE (256 experts routés + 1 shared, top-8 routing) |
| **Params totaux** | **671 B** |
| **Params actifs/token** | **37 B** |
| **Couches** | 61 (3 dense + 58 MoE) |
| **Attention** | **MLA** (Multi-head Latent Attention) - KV cache ultra-compresse |
| **Contexte** | **128 K tokens** |
| **Vision** | Non (texte seul) |
| **Thinking** | Oui - chain-of-thought via RL (GRPO) |
| **Licence** | **MIT** |

> 💡 **MLA (Multi-head Latent Attention)** : DeepSeek compresse le KV cache en un vecteur latent de dimension réduite, réduisant la mémoire de 5-10× par rapport à une attention classique. Même avec 671B params, le KV reste petit.

### 5.2B.2 Mémoire requise

| Quantization | Poids | KV cache (8K) | KV cache (128K) | Total (128K) |
|-------------|-------|---------------|-----------------|--------------|
| **BF16** | 1 342 GB | 0,5 GB | ~8,8 GB | **~1 351 GB** |
| **FP8** | ~671 GB | 0,5 GB | ~8,8 GB | **~680 GB** |
| **Q4_K_M** | 408 GB | 0,5 GB | ~8,8 GB | **~417 GB** |
| **Q2_K** | 256 GB | 0,5 GB | ~8,8 GB | **~265 GB** |

> ⚠️ Les 671B paramètres doivent **tous rester en mémoire** (MoE), même si seuls 37B sont actifs par token. L'inférence est rapide (coût de 37B) mais la mémoire est celle de 671B.

### 5.2B.3 Configurations matérielles

#### Option A - Q4_K_M (recommandé production)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **6× H100 80GB** (1 nœud HGX) |
| Mémoire totale | 6 × 80 GB = **480 GB** |
| Poids Q4 = 408 GB | ✅ |
| KV cache 128K = ~9 GB | ✅ |
| Total ~417 GB | ✅ marge OK |
| Surface | **0,72 m²** (1 rack 6U) |
| Puissance | **~4,2 kW** |
| Coût GPU estimé | 6 × 30 000 = **180 000 $** |

#### Option B - Q2_K (budget)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **4× H100 80GB** |
| Mémoire totale | **320 GB** |
| Poids Q2 = 256 GB | ✅ |
| Total ~265 GB | ✅ |
| Surface | **0,48 m²** |
| Puissance | **~2,8 kW** |
| Coût GPU estimé | 4 × 30 000 = **120 000 $** |
| **Compromis** | Perte qualité notable |

#### Option C - BF16 (qualité maximale)

| Paramètre | Valeur |
|-----------|--------|
| GPU requis | **18× H100 80GB** (3 nœuds) ou **10× H200 141GB** |
| Mémoire totale | 1 440 GB (H100) ou 1 410 GB (H200) |
| Poids BF16 = 1,34 TB | ✅ |
| Surface | **1,44-2,16 m²** |
| Puissance | **12,6 kW** (H100) |
| Coût GPU estimé | 18 × 30 000 = **540 000 $** |

### 5.2B.4 Capacité utilisateurs - DeepSeek-R1 (6× H100, Q4)

Les 37B actifs + MLA permettent un throughput élevé malgré les 671B totaux.

| Scénario | Requêtes concurrentes | Utilisateurs simultanés | Utilisateurs journaliers |
|----------|----------------------|------------------------|-------------------------|
| **Questions simples** (reasoning léger) | ~60-80 | **~60-80** | ~600-800 |
| **Raisonnement modéré** (math, code) | ~40-50 | **~40-50** | ~400-500 |
| **Raisonnement complexe** (long CoT) | ~20-30 | **~20-30** | ~200-300 |

### 5.2B.5 Verdict DeepSeek-R1

> **DeepSeek-R1** : le modèle reasoning open le plus puissant disponible (MIT). Les **37B actifs** sur 671B = inference rapide, mais **417 GB de mémoire** = nécessite **6× H100** minimum.
>
> **Avantage clé** : MLA réduit le KV cache de 5-10× → plus d'utilisateurs simultanés qu'un MoE classique de même taille.
>
> **Inconvénient** : pas de vision, contexte 128K (pas 1M), gros budget infrastructure (180 k$ minimum).
>
> **Pour le datacenter Camp Français** : DeepSeek-R1 est le bon choix si l'objectif est le **reasoning de pointe** (math, code, recherche). Sinon, Qwen 3.8 ou Gemma 4 sont plus compacts et polyvalents.

---

## 5.4 COMPARAISON CROSS-MODÈLES

### 5.3.1 Infrastructure requise par modèle (datacenter, production)

| Modèle | Config | GPU | Surface | Puissance | Coût GPU | Contexte | Utiles simultanés |
|--------|--------|-----|---------|-----------|----------|----------|-------------------|
| **Kimi K3** | 16× B200 | 16 GPU | 1,44 m² | 16 kW | 800 k$ | 1 M | 50-200 |
| **DeepSeek-R1** | 6× H100 Q4 | 6 GPU | **0,72 m²** | **4,2 kW** | **180 k$** | 128 K | 20-80 |
| **Gemma 4 31B** | 2× H100 BF16 | 2 GPU | 0,72 m² | 5,6 kW | 60 k$ | 256 K | 30-100 |
| **Gemma 4 26B MoE** | 2× H100 BF16 | 2 GPU | 0,72 m² | 5,6 kW | 60 k$ | 256 K | 50-150 |
| **Qwen 3.8 27B** | 1× H100 FP8 | **1 GPU** | **0,36 m²** | **3 kW** | **30 k$** | 256 K | 40-150 |

### 5.3.2 Comparaison surface

```
Surface (m²) - plus petit = meilleur
═══════════════════════════════════════════════════
Qwen 3.8 27B     ████████ 0,36 m²  ← 1 GPU
DeepSeek-R1      ████████████████ 0,72 m²  ← 6 GPU
Gemma 4 31B      ████████████████ 0,72 m²  ← 2 GPU
Gemma 4 26B MoE  ████████████████ 0,72 m²  ← 2 GPU
Kimi K3          ████████████████████████████ 1,44 m²  ← 16 GPU
```

### 5.3.3 Comparaison énergie

```
Puissance (kW) - plus bas = meilleur
═══════════════════════════════════════════════════
Qwen 3.8 27B     ████████████████ 3,0 kW
DeepSeek-R1      ██████████████████████ 4,2 kW
Gemma 4 31B      ████████████████████████████ 5,6 kW
Gemma 4 26B MoE  ████████████████████████████ 5,6 kW
Kimi K3          ████████████████████████████████████████████████████████████████████ 16,0 kW
```

### 5.3.4 Comparaison utilisateurs simultanés

```
Utilisateurs simultanés (max) - plus haut = meilleur
═══════════════════════════════════════════════════
DeepSeek-R1      ████████████████████████████████████ 80
Kimi K3          ████████████████████████████████████████████████████████████████████████████████ 200
Gemma 4 31B      ██████████████████████████████████████████ 100
Gemma 4 26B MoE  ████████████████████████████████████████████████████████ 150
Qwen 3.8 27B     ████████████████████████████████████████████████████████ 150
```

### 5.3.5 Tableau récapitulatif - Score

| Modèle | Surface | Énergie | Utiles | Coût GPU | **Score global** |
|--------|---------|---------|--------|----------|-----------------|
| **Qwen 3.8 27B** | ⭐⭐⭐ (0,36) | ⭐⭐⭐ (3 kW) | ⭐⭐ (150) | ⭐⭐⭐ (30 k$) | **🏆 10/12** |
| **Gemma 4 26B MoE** | ⭐⭐ (0,72) | ⭐⭐ (5,6 kW) | ⭐⭐ (150) | ⭐⭐ (60 k$) | **8/12** |
| **DeepSeek-R1** | ⭐⭐ (0,72) | ⭐⭐⭐ (4,2 kW) | ⭐ (80) | ⭐ (180 k$) | **7/12** |
| **Gemma 4 31B** | ⭐⭐ (0,72) | ⭐⭐ (5,6 kW) | ⭐ (100) | ⭐⭐ (60 k$) | **6/12** |
| **Kimi K3** | ⭐ (1,44) | ⭐ (16 kW) | ⭐⭐⭐ (200) | ⭐ (800 k$) | **5/12** |

### 5.3.6 Ratio coût/utilisateur

| Modèle | Coût GPU | Utiles simultanés (max) | **Coût/utilisateur** |
|--------|----------|------------------------|---------------------|
| **Qwen 3.8 27B** | 30 k$ | ~150 | **~200 $/utilisateur** 🏆 |
| **Gemma 4 26B MoE** | 60 k$ | ~150 | **~400 $/utilisateur** |
| **Gemma 4 31B** | 60 k$ | ~100 | **~600 $/utilisateur** |
| **DeepSeek-R1** | 180 k$ | ~80 | **~2 250 $/utilisateur** |
| **Kimi K3** | 800 k$ | ~200 | **~4 000 $/utilisateur** |

### 5.3.7 Ratio surface/utilisateur

| Modèle | Surface | Utiles simultanés (max) | **Utiles/m²** |
|--------|---------|------------------------|--------------|
| **Qwen 3.8 27B** | 0,36 m² | ~150 | **~417/m²** 🏆 |
| **Gemma 4 26B MoE** | 0,72 m² | ~150 | **~208/m²** |
| **DeepSeek-R1** | 0,72 m² | ~80 | **~111/m²** |
| **Gemma 4 31B** | 0,72 m² | ~100 | **~139/m²** |
| **Kimi K3** | 1,44 m² | ~200 | **~139/m²** |

### 5.3.8 Ratio énergie/utilisateur

| Modèle | Puissance | Utiles simultanés (max) | **Utiles/kW** |
|--------|-----------|------------------------|--------------|
| **Qwen 3.8 27B** | 3 kW | ~150 | **~50/kW** 🏆 |
| **Gemma 4 26B MoE** | 5,6 kW | ~150 | **~27/kW** |
| **DeepSeek-R1** | 4,2 kW | ~80 | **~19/kW** |
| **Gemma 4 31B** | 5,6 kW | ~100 | **~18/kW** |
| **Kimi K3** | 16 kW | ~200 | **~13/kW** |

### 5.3.9 Recommandation par usage

| Usage | Modèle recommandé | Pourquoi |
|-------|-------------------|----------|
| **API publique haut débit** | Gemma 4 26B A4B MoE | 3,8 B actifs = token/s max, coût réduit |
| **Coding agent / Recherche** | DeepSeek-R1 ou Kimi K3 | R1 = reasoning MIT ; Kimi = contexte 1M |
| **Chat interne entreprise** | Qwen 3.8 27B FP8 | Meilleur coût/utilisateur, 262K contexte, Apache 2.0 |
| **Qualité maximale (peu d'utilisateurs)** | Gemma 4 31B Dense | Le plus capable de la famille Gemma |
| **Budget minimal** | Qwen 3.8 27B Q4 (1× RTX 4090) | 2 000 $ tout compris, 32-64K contexte |
| **Plus gros trafic possible** | Kimi K3 (16× B200) | Seul modèle gérant 1M contexte + 200 utilisateurs |
| **Reasoning math/code** | DeepSeek-R1 (6× H100) | Le meilleur reasoning open, MIT, RL pure |

### 5.3.10 Verdict global

> **Pour le datacenter Camp Français**, quatre scénarios se dégagent :
>
> 1. **Budget serré (< 50 k$)** → **Qwen 3.8 27B** sur 1× H100 (FP8). 0,36 m², 3 kW, 150 utilisateurs. Meilleur ROI de tous les modèles. Apache 2.0.
>
> 2. **Production SaaS (50-200 k$)** → **Gemma 4 26B A4B MoE** sur 2× H100. Débit maximal grâce aux 3,8 B actifs. Idéal pour une API publique à fort trafic.
>
> 3. **Reasoning de pointe (200 k$)** → **DeepSeek-R1** sur 6× H100. MIT, reasoning RL pur, le plus puissant pour math/code. Mais pas de vision, 128K contexte.
>
> 4. **Maxi-projet (500 k$+)** → **Kimi K3** sur 16× B200. Contexte 1M, 200 utilisateurs. Réservé aux cas d'usage nécessitant un contexte extrêmement long.

---

## 6. RECOMMANDATIONS POUR LE DATACENTER CAMP FRANÇAIS

### 6.1 Positionnement

| Critère | Recommandation |
|---------|----------------|
| **Opérateur** | Européen (Niveau 4 souveraineté) - Scaleway, OVHcloud, ou équivalent |
| **GPU** | NVIDIA Blackwell B200 (seul européen avec B300 via Scaleway) |
| **Alternative** | AMD MI300X (192 GB, disponible Scaleway/OVHcloud) |
| **Logiciel** | CUDA (NVIDIA) ou ROCm (AMD) - pas de CANN (Huawei) |
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
| **1 - Immédiat** | 2026-2027 | Cloud Scaleway/OVHcloud (B200/H100) - pas de construction datacenter |
| **2 - Court terme** | 2027-2028 | Contrat long terme GPU (Scaleway cluster dédié) |
| **3 - Moyen terme** | 2028-2030 | Construction datacenter souverain si volume le justifie |
| **4 - Long terme** | 2030+ | Évaluation GPU européens (si apparition) |

---

## 7. LEXIQUE DES ACRONYMES

### Matériel / Processeurs

| Acronyme | Signification |
|----------|---------------|
| **GPU** | Graphics Processing Unit - Processeur graphique, utilisé pour le calcul parallèle en IA |
| **ASIC** | Application-Specific Integrated Circuit - Circuit intégré spécialisé (ex. Google TPU) |
| **FPGA** | Field-Programmable Gate Array - Circuit reconfigurable après fabrication |
| **HBM** | High Bandwidth Memory - Mémoire haute bande passante (HBM2e, HBM3, HBM3e) |
| **HBM2e** | Génération améliorée de HBM2 (~3,2 TB/s par stack) |
| **HBM3** | HBM de 3e génération (~5 TB/s par stack, NVIDIA A100/H100) |
| **HBM3e** | HBM3 améliorée (~8 TB/s par stack, NVIDIA H200/B200) |
| **SXM** | Server Module X - Format carte GPU haute performance (NVIDIA) |
| **GB** | Gigaoctet - 10⁹ octets |
| **TB** | Téraoctet - 10¹² octets |
| **GB/s** | Gigaoctets par seconde - Unité de bande passante mémoire |
| **TB/s** | Téraoctets par seconde - Unité de bande passante mémoire |

### Mesures de performance

| Acronyme | Signification |
|----------|---------------|
| **TFLOPS** | Téra (10¹²) Floating Point Operations Per Second - Opérations virgule flottante par seconde |
| **PFLOPS** | Péta (10¹⁵) FLOPS - 1 000 TFLOPS |
| **EFLOPS** | Exa (10¹⁸) FLOPS - 1 000 PFLOPS |
| **FP16** | Floating Point 16-bit - Demi-précision (2 octets par paramètre) |
| **FP32** | Floating Point 32-bit - Précision simple (4 octets) |
| **FP64** | Floating Point 64-bit - Précision double (8 octets) |
| **INT8** | Integer 8-bit - Entier 8 bits (quantization) |
| **MXFP4** | Microscaling Floating Point 4-bit - Quantization ultra-agressive (1,56 TB pour Kimi K3) |
| **MXFP8** | Microscaling Floating Point 8-bit - Quantization pour activations |
| **PPL** | Perplexity - Mesure de qualité d'un modèle de langage (plus bas = mieux) |

### Processeurs spécifiques

| Acronyme | Signification |
|----------|---------------|
| **H100** | NVIDIA Hopper - GPU datacenter de 2022 (80 GB HBM3, 990 TFLOPS FP16) |
| **H200** | NVIDIA Hopper amélioré - GPU 2024 (141 GB HBM3e, 990 TFLOPS FP16) |
| **B200** | NVIDIA Blackwell - GPU 2024/2025 (192 GB HBM3e, ~2 500 TFLOPS FP16) |
| **GB200** | NVIDIA Grace Blackwell Superchip - CPU+GPU combiné |
| **GB300** | NVIDIA Blackwell Ultra - GPU 2025/2026 (amélioration B200) |
| **A100** | NVIDIA Ampere - GPU datacenter (2020, 40/80 GB HBM2e) |
| **MI300X** | AMD Instinct MI300X - GPU AMD (192 GB HBM3e, 1 307 TFLOPS FP16) |
| **MI325X** | AMD Instinct MI325X - GPU AMD (288 GB HBM3e, 2 615 TFLOPS FP16) |
| **L40S** | NVIDIA L40S - GPU inference/visualisation (48 GB GDDR6) |
| **Ascend 910B** | Huawei Ascend - GPU chinois (~600 TFLOPS FP16, 64 GB HBM2e) |
| **Ascend 910C** | Huawei Ascend - GPU chinois (~800 TFLOPS FP16, 96 GB HBM2e) |
| **TPU** | Tensor Processing Unit - Processeur IA propriétaire Google |
| **RISC-V** | Instruction set open source - Architecture alternative (pas encore GPU IA) |

### Fabrication / Semi-conducteurs

| Acronyme | Signification |
|----------|---------------|
| **TSMC** | Taiwan Semiconductor Manufacturing Company - Fonderie n°1 mondiale (Taïwan) |
| **SMIC** | Semiconductor Manufacturing International Corporation - Fonderie chinoise (plafonnée 7nm) |
| **EUV** | Extreme UltraViolet - Lithographie ultraviolette extrême (nœud 7nm et moins) |
| **DUV** | Deep UltraViolet - Lithographie standard (7nm+ sans EUV) |
| **nm** | Nanomètre - Unité de taille de nœud de gravure (plus petit = meilleur) |
| **CoWoS** | Chip on Wafer on Substrate - Empaquetage avancé TSMC pour GPU IA |
| **InFO** | Integrated Fan-Out - Alternative CoWoS (moins coûteuse, moins performante) |
| **GAA** | Gate-All-Around - Architecture transistor 3nm+ (futur 2nm) |
| **FinFET** | Fin Field Effect Transistor - Architecture transistor 14nm-3nm |
| **TSV** | Through-Silicon Via - Connexions verticales inter-couches |

### Logiciel / Frameworks

| Acronyme | Signification |
|----------|---------------|
| **CUDA** | Compute Unified Device Architecture - Plateforme logicielle NVIDIA (17 ans, standard de facto) |
| **CANN** | Compute Architecture for Neural Networks - Plateforme logicielle Huawei Ascend |
| **ROCm** | Radeon Open Compute - Plateforme logicielle AMD (alternative open source à CUDA) |
| **vLLM** | Virtual Large Language Model - Moteur d'inférence LLM haute performance |
| **TensorRT** | Moteur d'optimisation NVIDIA pour inférence |
| **TensorRT-LLM** | Extension TensorRT pour LLM |
| **PyTorch** | Framework d'entraînement IA (Meta) |
| **TP** | Tensor Parallelism - Parallélisme sur plusieurs GPU |
| **PP** | Pipeline Parallelism - Parallélisme sur couches du modèle |
| **DP** | Data Parallelism - Parallélisme sur batch de données |

### Cloud / Réseau

| Acronyme | Signification |
|----------|---------------|
| **IaaS** | Infrastructure as a Service - Infrastructure en tant que service |
| **PaaS** | Platform as a Service - Plateforme en tant que service |
| **SaaS** | Software as a Service - Logiciel en tant que service |
| **Bare Metal** | Serveur dédié physique (pas de virtualisation) |
| **InfiniBand** | Réseau haute performance RDMA (400 Gb/s, 800 Gb/s) |
| **NVLink** | Connexion GPU-NVIDIA propriétaire (900 GB/s) |
| **NVSwitch** | Switch NVLink (connexion multi-GPU) |
| **OCP** | Open Compute Project - Standard rack/datacenter open source |
| **ORv3** | Open Rack v3 - Standard rack OCP pour datacenter |
| **HGX** | NVIDIA HGX - Plateforme serveur 8 GPU NVIDIA |

### Réglementation / Souveraineté

| Acronyme | Signification |
|----------|---------------|
| **CLOUD Act** | Clarifying Lawful Overseas Use of Data Act - Loi US autorisant l'accès aux données hors US |
| **FISA** | Foreign Intelligence Surveillance Act - Loi US de surveillance étrangère |
| **RGPD** | Règlement Général sur la Protection des Données - GDPR en français |
| **SecNumCloud** | Certification ANSSI pour cloud souverain français (niveau 3.2) |
| **GAIA-X** | Initiative européenne d'infrastructure cloud souveraine |
| **CADA** | Cloud & AI Development Act - Règlement UE sur l'IA souveraine |
| **HDS** | Hébergeur de Données de Santé - Certification hébergement santé (France) |
| **ISO 27001** | Norme internationale de sécurité de l'information |
| **ANSSI** | Agence Nationale de la Sécurité des Systèmes d'Information |
| **ESCC** | European Sovereign Cloud Consortium - Consortium cloud souverain UE |

### Modèles d'IA

| Acronyme | Signification |
|----------|---------------|
| **LLM** | Large Language Model - Modèle de langage de grande taille |
| **MoE** | Mixture of Experts - Architecture multi-experts (Kimi K3 = 896 experts, 16 actifs) |
| **RLHF** | Reinforcement Learning from Human Feedback - Apprentissage par renforcement humain |
| **MaaS** | Model as a Service - Modèle en tant que service (API) |
| **MTP** | Multi-Token Prediction - Prédiction de plusieurs tokens simultanément (Kimi K3) |
| **tok/s** | Tokens par seconde - Débit d'inférence |

### Entreprises / Organisations

| Acronyme | Signification |
|----------|---------------|
| **NVIDIA** | Société US de GPU et IA (fondateur Jensen Huang) |
| **AMD** | Advanced Micro Devices - Concurrent US de NVIDIA (GPU Instinct) |
| **Intel** | Concurrent US (GPU Gaudi, fonderie propre) |
| **Huawei** | Technologie chinoise (GPU Ascend, plateforme CANN) |
| **TSMC** | Fonderie taïwanaise (AMD, NVIDIA, Apple, Qualcomm) |
| **SK Hynix** | Fonderie coréenne de mémoire (HBM) |
| **Samsung** | Fonderie coréenne de mémoire (HBM) |
| **Micron** | Fonderie US de mémoire (HBM) |
| **ASML** | Fournisseur néerlandais de machines lithographie EUV (monopole) |
| **Scaleway** | Cloud français (filiale Iliad) - Seul européen avec B300 |
| **OVHcloud** | Cloud français - 46 datacenters, 1,6M clients |
| **IONOS** | Cloud allemand (filiale 1&1) |
| **Hetzner** | Cloud allemand (budget-friendly) |
| **3DS Outscale** | Cloud français (filiale Dassault) - SecNumCloud 3.2 |

---

## 8. ESTIMATION DE CAPACITÉ DE CALCUL DÉPLOYABLE SUR LE SITE - 22 HECTARES

### 8.1 Objectif

Estimer la puissance de calcul (PFLOPS), la consommation électrique (MW) et les besoins en eau (m³/an) d'un datacenter IA maximaliste implanté sur les 22 ha du complexe moto, en tenant compte des contraintes physiques réelles du site.

### 8.2 Hypothèses de dimensionnement

| Paramètre | Hypothèse |
|-----------|-----------|
| Surface totale | 22 ha (220 000 m²) |
| Surface bâtiments (data halls + SMCC + refroidissement) | ~35 % → **7,7 ha** |
| Surface voirie, parkings, reculs, zone verte | ~65 % → 14,3 ha |
| Puissance par rack (GPU AI, air-cooled) | 35 kW |
| Puissance par rack (GPU AI, liquid-cooled) | 60 kW |
| PUE moyen | 1,35 (refroidissement adiabatique mixte) |
| Tension de raccordement | ≥ 63 kV (sous-station EDF sur le site) |
| Connectivité | Fibre optique (axe Lille-Paris, présences d'opérateur sur la MEL) |

### 8.3 Occupation du sol par composant

```
COMPOSITION DU SITE - 22 ha
═══════════════════════════════════════════════════════════════
│ Composant                          │ Surface    │ % site  │
═══════════════════════════════════════════════════════════════
│ Data halls (4 bâtiments)           │ 5,6 ha     │ 25,5 %  │
│ Sous-station HV/MV                 │ 0,4 ha     │ 1,8 %   │
│ Plant de refroidissement (ch. eau) │ 0,8 ha     │ 3,6 %   │
│ Bâtiment contrôle/SMCC/bureaux     │ 0,4 ha     │ 1,8 %   │
│ Torres aérocondenseurs (si air)    │ 0,5 ha     │ 2,3 %   │
│ Voirie interne + parkings          │ 1,8 ha     │ 8,2 %   │
│ Recul sécurité / zone verte        │ 2,5 ha     │ 11,4 %  │
│ Zone non-bâtie (rétention eau)     │ 10,0 ha    │ 45,5 %  │
═══════════════════════════════════════════════════════════════
│ TOTAL                              │ 22,0 ha    │ 100 %   │
```

### 8.4 Capacité en racks

**Scénario A - Air-cooled (refroidissement adiabatique) :**
- Surface data halls : 5,6 ha = 56 000 m²
- Densité : 1 rack / 25 m² (aisances, chemins de câbles, N+1)
- **Capacité : 2 240 racks × 35 kW = 78,4 MW IT**

**Scénario B - Liquid-cooled (DLC direct-to-chip) :**
- Surface data halls : 5,6 ha = 56 000 m²
- Densité : 1 rack / 18 m² (chambres plus denses)
- **Capacité : 3 110 racks × 60 kW = 186,6 MW IT**

**Scénario C - Hyperscale mixte (80 % air / 20 % liquid) :**
- 1 792 racks air-cooled × 35 kW = 62,7 MW
- 622 racks liquid-cooled × 60 kW = 37,3 MW
- **Total : 2 414 racks = 100,0 MW IT**

> **Conclusion : Le site peut accueillir 80 à 187 MW de charge IT, soit 2 à 5× la demande annoncée (15 MW).**

### 8.5 Puissance de calcul (PFLOPS)

Calcul basé sur les GPU NVIDIA de référence :

| GPU | FP32 (TFLOPS) | FP16 (TFLOPS) | Coût par unité | Rendement/W |
|-----|---------------|---------------|----------------|-------------|
| H100 SXM | 67 | 989 (sparse) | ~30 000 $ | 1,41 TFLOPS/kW |
| B200 | 90 | 2 500 (sparse) | ~40 000 $ | 3,57 TFLOPS/kW |

**Pour 2 414 racks à 35 kW (84,5 MW IT) :**

| Configuration | Nombre GPU | FP32 (PFLOPS) | FP16 (PFLOPS) |
|---------------|------------|---------------|---------------|
| 4× H100 / rack | 9 656 | 647 | 9 550 |
| 4× B200 / rack | 9 656 | 869 | 24 140 |
| 8× H100 / rack | 19 312 | 1 294 | 19 100 |

> **En configuration B200 (optimiste) : ~24 000 PFLOPS FP16, soit 24 ExaFLOPS.**
> **En configuration H100 (réaliste) : ~9 500 PFLOPS FP16, soit 9,5 ExaFLOPS.**
>
> À titre de comparaison, le plus grand cluster mondial (Colossus, xAI, Memphis) vise 200 000 GPU H100 = ~200 ExaFLOPS. Le site Camp Français pourrait représenter **5 à 12 % de cette capacité**.

### 8.6 Consommation électrique

| Composant | Scénario A (84 MW IT) | Scénario B (100 MW IT) |
|-----------|----------------------|----------------------|
| Charge IT | 84,5 MW | 100,0 MW |
| Refroidissement (PUE) | 29,0 MW | 35,0 MW |
| Éclairage, pertes SMCC | 12,5 MW | 15,0 MW |
| **Total site** | **126 MW** | **150 MW** |
| Consommation annuelle | 1 104 GWh/an | 1 314 GWh/an |

> **126 à 150 MW = la consommation électrique d'une ville de 100 000 habitants** (consommation moyenne française : 1 500 kWh/hab/an → 150 000 hab × 1 000 kWh = 150 GWh ; ici 1 100 à 1 300 GWh = 7 à 9× plus).
>
> **Réseau de transport :** Le site est à proximité de la ligne à haute tension 225 kV Lille-Douai. Le raccordement nécessite une nouvelle sous-station 225/20 kV dédiée, coût estimé : **80 à 150 M€** (fourniture + travaux Enedis/RTE). Délai : 3 à 5 ans.

### 8.7 Besoins en eau de refroidissement

Le choix du système de refroidissement détermine totalement l'empreinte hydrique.

| Technologie | WUE (L/kWh) | Conso. annuelle (m³/an) | Équiv. piscines olympiques |
|-------------|-------------|------------------------|---------------------------|
| Tour aérocondenseur (adiabatique) | 0,3 – 0,8 | 330 000 – 880 000 | 130 – 350 |
| Tour évaporative (classique) | 1,5 – 2,5 | 1 650 000 – 2 750 000 | 660 – 1 100 |
| Refroidissement liquide direct (DLC) | 0,05 – 0,15 | 55 000 – 165 000 | 22 – 66 |
| Refroidissement en boucle fermée (dry) | 0 | 0 | 0 |

**Pour 84,5 MW IT × 8 760 h/an :**

- **Scénario adiabatique (330 000 m³/an) :** 330 millions de litres = **330 piscines olympiques**. Équivalent à la consommation annuelle en eau potable de **2 200 habitants**.
- **Scénario évaporatif (1,65 million m³/an) :** 1,65 milliard de litres = **660 piscines olympiques**. Équivalent à **11 000 habitants**.
- **Scénario DLC (55 000 m³/an) :** 55 millions de litres = **22 piscines olympiques**. Équivalent à **370 habitants**.

> ⚠️ **Contrainte site Camp Français :** Le site repose sur la nappe de la Craie (nappe phréatique superficielle, < 5 m de profondeur, démontrée par les études du Grand Stade et Leroy Merlin). Le captage d'eau de refroidissement est quasi impossible : la nappe est déjà sollicitée par les usages agricoles, et le forage pourrait abaisser le niveau piézométrique, aggravant le risque d'inondation par remontée de nappe en hiver-printemps (pic en mars). **L'eau doit être acheminée par camion-citerne ou adduction, soit un coût logistique et carbone considérable.**

### 8.8 Contraintes spécifiques au site

| Contrainte | Impact | Gravité |
|------------|--------|---------|
| **Nappe haute (0-5 m)** | Impossible de creuser pour fondations profondes ou stockage souterrain | 🔴 Critique |
| **Sol argilo-calcaire** | Capacité portante limitée, fondations sur pieux nécessaires (+20-30 % coût construction) | 🟠 Majeur |
| **Accessibilité routière** | Route D549 étroite, pas d'accès autoroutier direct (A1 à 3 km mais bouchons) | 🟠 Majeur |
| **Raccordement électrique** | Sous-station 225 kV la plus proche à 2 km (Ronchin-Lesquin), travaux importants | 🟠 Majeur |
| **Proximité résidentielle** | 800 m, Ronchin nord, Lezennes et bientot l'ancien magasin Leroymerlin = zone urbaine | 🟡 Modéré |
| **Bruit — autoroute A1/A27** | A1 à ~1,5 km : 6 000 veh/j (16,5 % PL), **90 km/h** (VL) / 80 km/h (PL) — radar discriminant Lesquin + régulation dynamique. Lden ~70-75 dB(A) à 50 m, ~65-70 dB(A) à 100 m. Secteur affecté 300 m. Source existante forte | 🟠 Majeur |
| **Bruit — datacenter** | 75-85 dB(A) en continu (ventilateurs, tours aérocondenseurs) vs. 65 dB(A) (ancien circuit moto, ponctuel). Datacenter = bruit 24h/24 vs. week-ends occasionnels | 🔴 Critique |
| **Proximité golf** | Site en zone TRI (inondable), 4 CatNat Ronchin, nappe alimente Deûle | 🟠 Majeur |
| **Zones inondables** | Remontée nappe max en mars (11,45 m NGF), étiage en septembre (13,83 m) - risque critique hiver/printemps | 🔴 Critique |
| **Risque sismique** | Zone 2 (faible), mais fondations sur pieux = vulnérabilité | 🟢 Faible |

### 8.9 Scénarios de déploiement réalistes

| Scénario | Puissance IT | Racks | GPU (H100) | PFLOPS FP16 | Coût estimé | Délai | Bruit à 100 m (dB(A)) | Bruit à 800 m (dB(A)) | Eau (m³/an) |
|----------|-------------|-------|------------|-------------|-------------|-------|----------------------|----------------------|-------------|
| **Modeste** | 15 MW | 430 | 1 720 | 1 700 | 500 M€ | 2-3 ans | 55-60 | 42-47 | 59 000 |
| **Intermédiaire** | 40 MW | 1 140 | 4 560 | 4 510 | 1,2 Md€ | 3-4 ans | 60-65 | 47-52 | 158 000 |
| **Maximaliste** | 84 MW | 2 414 | 9 656 | 9 550 | 2,5 Md€ | 4-6 ans | 65-72 | 52-59 | 330 000 |
| **Avec B200** | 84 MW | 2 414 | 9 656 | 24 140 | 3,2 Md€ | 5-7 ans | 65-72 | 52-59 | 330 000 |

> **Propagation 100 m → 800 m** : atténuation ~12-15 dB (source surfacique étendue, 4 bâtiments de 14 000 m²). Le bruit autoroute A1 à 800 m du site est ~55-60 dB(A).
>
> **Bruit cumulé (datacenter + A1) à 800 m** — seuil réglementaire : 60 dB(A) jour / 50 dB(A) nuit :
> - **Modeste** : 47 dB(A) datacenter + 58 dB(A) A1 → **~60 dB(A)** → seuil jour atteint
> - **Intermédiaire** : 52 dB(A) datacenter + 58 dB(A) A1 → **~62 dB(A)** → dépassement seuil jour
> - **Maximaliste** : 59 dB(A) datacenter + 58 dB(A) A1 → **~64 dB(A)** → dépassement critique

> **Pour le Scénario maximaliste (84 MW, 2,5 Md€) :**
> - Nombre de data halls : 4 bâtiments de 14 000 m² chacun
> - Superficie totale bâtie : 77 000 m² (≈ 8 stades de football)
> - Surface totale utile : 220 000 m² (site complet)
> - Nombre de salles serveur : 120 (200 m² chacune)
> - Nombre de racks : 2 414
> - Nombre de GPU : 9 656 (4 par rack)
> - Puissance IT : 84 MW
> - Puissance totale : 126 MW (PUE 1,5)
> - Eau refroidissement (adiabatique) : 330 000 m³/an
> - Emploi permanent : 200-400 (ratio ~1 emploi/6 MW)

### 8.10 Implications pour l'argumentaire d'opposition

**1. L'argument du bruit :**
Le site subit déjà le bruit de l'**autoroute A1** (6 000 veh/j, 16,5 % PL, **90 km/h** — radar discriminant Lesquin + régulation dynamique) située à ~1,5 km — Lden ~55-60 dB(A) à 800 m du site. S'ajouterait le bruit du datacenter : **42-59 dB(A) à 800 m** selon le scénario. Le cumul A1 + datacenter à 800 m (distance des habitations Ronchin-Lezennes) atteint **60-64 dB(A)**, soit au-dessus du seuil réglementaire de 60 dB(A) jour. L'ancien circuit moto fonctionnait quelques week-ends par an ; le datacenter serait **24h/24, 365 jours/an**.

**2. L'argument de l'eau :**
59 000 à 330 000 m³/an d'eau de refroidissement (WUE ~0,45 L/kWh, recyclage à 90 %) = **drainage supplémentaire de la nappe de la Craie**. Or le site est inondable en hiver-printemps quand la nappe atteint 11,45 m NGF (mars). Ajouter un datacenter, c'est aggraver le risque d'inondation par remontée de nappes. Même le scénario modeste (59 000 m³/an) représente la consommation annuelle d'une commune de ~1 500 habitants.

**3. L'argument de la Jobs density :**
84 MW de puissance = 22 ha = **200-400 emplois permanents** (ratio 1 emploi/6 MW). Soit **18 emplois/ha**. Un centre commercial de 22 ha aurait 500-800 emplois. Un parc logistique : 300-500. Le datacenter est le mode d'occupation du sol le moins créateur d'emplois de la palette.

**4. L'argument du réseau :**
126 MW de puissance totale = **consommation électrique d'une ville de 100 000 habitants**. Le réseau électrique régional n'est pas dimensionné. Le raccordement 225 kV nécessite 3 à 5 ans de travaux et 80-150 M€ d'investissement public/privé. L'impact sur les tarifs réseau (CSPE/CSPP) se répartit sur l'ensemble des usagers.

**5. L'argument de la valeur foncière :**
22 ha à Lezennes = terrain urbanisable à haute valeur (800-1 200 €/m² en zone.mixte). Un datacenter = occupation longue durée (20-30 ans) avec valeur ajoutée locale quasi nulle (pas de commerces, pas de logements, pas de tourisme). **La collectivité perd le contrôle d'un patrimoine foncier stratégique.**

**6. L'argument de la dépendance technologique :**
84 MW = 9 656 GPU NVIDIA H100. 100 % du hardware = NVIDIA (USA) + Cloud Act. La souveraineté numérique revendiquée est un **leurre** : les données, les modèles et le contrôle restent soumis au droit américain.

---

## 9. RÉFÉRENCES

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

### Sources complémentaires (§8 - Infrastructure physique)

| Document | URL |
|----------|-----|
| EUDCA Sustainability Code | [eudca.org](https://eudca.org/resources/sustainability/) |
| EUDCA Energy & Water Committee | [eudca.org](https://eudca.org/resources/ewcc/) |
| EUDCA Data Centre Cooling Guide | [eudca.org](https://eudca.org/2025/06/12/sustainability/) |
| ADEME - Efficacité énergétique datacenter | [agirpourlatransition.ademe.fr](https://agirpourlatransition.ademe.fr/entreprises/bilan-environnemental/gerer-pollutions-et-risques/efficacite-energetique-datacenter) |
| NVIDIA Data Centre Liquid Cooling | [nvidia.com](https://www.nvidia.com/en-us/data-center/solutions/liquid-cooling/) |
| Cloud&watt - Efficacité datacenter (PUE) | [cloud-watt.com](https://www.cloud-watt.com/fr/wiki/efficacite-datacenter/) |
| Vicente & Associates - AI Data Center Power | [vcandmore.com](https://vcandmore.com/data-centers/ai-data-center-power-demands-unveiled-what-you-need-to-know/) |
| USGS - Water Use in Data Centers | [usgs.gov](https://www.usgs.gov/media/images/water-use-data-centers) |
| DCCEW - Measuring Data Centre PUE | [dccew.org](https://dccew.org/2025/10/06/measuring-data-centre-pue-and-challenges-of-data-centre-efficiency-metrics/) |
| Schneider Electric - WUE | [schneider-electric.com](https://www.se.com/ww/en/insights/sustainability/sustainability-research-institute/white-papers/wue-understanding-water-usage-effectiveness-in-data-centers/) |
| Les Échos - Data centers : l'eau, talon d'Achille | [lesechos.fr](https://www.lesechos.fr/industrie-services/services-technologiques/ia-les-data-centers-face-au-defi-de-leau-le-talon-dachille-du-boom-de-lintelligence-artificielle-2534289) |
| L'Usine Digitale - Un datacenter peut consommer l'eau de 2 500 habitants | [usine-digitale.fr](https://www.usine-digitale.fr/ledition-patient/ia-et-innovation-verte-un-datacenter-peut-consommer-l-eau-de-2-500-habitants-en-france-arretons-le-scenario-qui-pose-tout-simplement-questions.NjU3MzUwOA.html) |
| Journal du Net - Datacenter et refroidissement | [journaldunet.fr](https://www.journaldunet.fr/tech/14009954-2409-ia-et-datacenter-comment-la-technologie-transforme-le-schema-de-refroidissement-des-plateformes-numeriques/) |
| Lemonde - Eau et data centers | [lemonde.fr](https://www.lemonde.fr/les-decodeurs/article/2025/09/04/ia-et-eau-le-data-center-est-devenu-les-pieds-dans-l-eau_6499527_4355770.html) |
| RTL - L'eau, talon d'Achille de l'IA | [rtl.fr](https://www.rtl.fr/actu/economie-consommation/ia-et-eau-le-talon-d-achille-de-l-intelligence-artificielle-se-situe-a-la-sortie-des-data-centers-7943043700) |
| ETFs.Net - L'eau et l'IA | [etfs.net](https://www.etfs.net/2026/02/12/lia-artificielle-a-t-elle-vraiment-soif-exploring-the-thirsty-side-of-ai-technology/) |
| Engie - Datacenter : empreinte carbone et impact | [engie.com](https://www.engie.com/fr/economie-circulaire/entreprises-responsables/datacenter-empreinte-carbone-impact-environnemental) |
| EDF - Forfaits datacenter France | [edf.fr](https://www.edf.fr/entreprise/fr/affaires/france/forfait-data-center) |

### Sources nappe de la Craie et piézométrie Lille

| Document | URL |
|----------|-----|
| Piézométrie Lille (BSS000BFVM) - Hub'Eau/BRGM | [meteo-npdc.fr](https://meteo-npdc.fr/piezometrie/BSS000BFVM) |
| Piézométrie Lille (BSS000BDDQ) - Hub'Eau/BRGM | [meteo-npdc.fr](https://meteo-npdc.fr/piezometrie/BSS000BDDQ) |
| Piézométrie Lille (BSS000BEXS) - Hub'Eau/BRGM | [meteo-npdc.fr](https://meteo-npdc.fr/piezometrie/BSS000BEXS) |
| BRGM - Nappes d'eau souterraine mars 2026 | [brgm.fr](https://www.brgm.fr/fr/actualite/communique-presse/nappes-eau-souterraine-au-1er-mars-2026) |
| BRGM - Note nappe avril 2026 | [brgm.fr](https://www.brgm.fr/sites/default/files/documents/2026-04/communique-nappes-eau-souterraine-2026-04-01-note.pdf) |
| BRGM - Fonctionnement hydro-système craie sud Lille (RP-71378) | [infoterre.brgm.fr](http://infoterre.brgm.fr/rapports/RP-71378-FR.pdf) |
| BRGM - Modélisation nappe Craie Nord-Pas-de-Calais (RP-60217) | [infoterre.brgm.fr](http://infoterre.brgm.fr/rapports/RP-60217-FR.pdf) |
| Univ. Lille - Remontées nappe Craie bassin minier | [pepite-depot.univ-lille.fr](https://pepite-depot.univ-lille.fr/LIBRE/Th_Num/1989/50376-1989-303-1.pdf) |
| Préf. Pas-de-Calais - Remontée nappe phréatique | [pas-de-calais.gouv.fr](https://www.pas-de-calais.gouv.fr/index.php/Actions-de-l-Etat/Prevention-des-risques-majeurs/Connaissance-des-risques-dans-le-P-d-C/Les-risques-naturels/Inondation/La-remontee-de-la-nappe-phreatique) |

### Sources golf, TRI et risques inondation site

| Document | URL |
|----------|-----|
| Risques Ronchin (TRI, CatNat) | [villagesfrancais.fr](https://villagesfrancais.fr/commune/ronchin-59790/risques/) |
| Risques Lezennes (TRI, CatNat) | [villagesfrancais.fr](https://villagesfrancais.fr/commune/lezennes-59260/risques/) |
| Zones inondables Lille - PPRi | [floody.fr](https://floody.fr/zones-inondables-lille/) |
| Note historique crues Deûle - DREAL | [hauts-de-france.developpement-durable.gouv.fr](https://www.hauts-de-france.developpement-durable.gouv.fr/IMG/pdf/note_historique_crues_inondations_lille.pdf) |
| TRI Lille Lens - Phase 1 | [hauts-de-france.developpement-durable.gouv.fr](https://www.hauts-de-france.developpement-durable.gouv.fr/IMG/pdf/rapport_phase_1_tri_lille_lens.pdf) |
| Concertation Camp français - MEL | [lillemetropole.fr](https://www.lillemetropole.fr/communique-de-presse/camp-francais-centre-equestre-golf-complexe-moto-la-metropole-engage-une) |
| Concertation Camp français - Ville Ronchin | [ville-ronchin.fr](https://ville-ronchin.fr/concertation) |

### Sources bruit autoroute

| Document | URL |
|----------|-----|
| CBS MEL - Cartographie bruit stratégique (2014) | [readkong.com](https://fr.readkong.com/page/mise-a-jour-de-la-cartographie-de-bruit-strategique-cbs-9319599) |
| Arrêté préfectoral — classement A1/A27 (secteurs affectés) | [nord.gouv.fr](https://www.nord.gouv.fr/contenu/telechargement/11648/70352/file/Arrete_Pref_Nord_30-07-2010.pdf) |
| bruit.fr — Bruit routier, PNB, seuils | [bruit.fr](https://www.bruit.fr/droits-demarches/bruit-des-transports/bruit-routier) |
| LRF Lille — Études acoustiques complémentaires (état initial) | [cpdp.debatpublic.fr](https://cpdp.debatpublic.fr/cpdp-regl/sites/debat.regl/files/documents/rapport-lrf_lille-etat_initial-_etudes_acoustiques_complementaires-_23.12.14.pdf) |
| DIR Nord — Baisse de vitesse A27 Lesquin/Camphin | [dirnord.fr](http://www.dirnord.fr/baisse-de-vitesse-a27-lesquin-camphin-en-pevele-a1766.html) |
| Radar discriminant Lesquin A1 (90/80 km/h) | [applivoiture.fr](https://www.applivoiture.fr/radars-automatiques/lesquin-59810/radar-discriminant-lesquin-a1-sens-lille-vers-paris) |
| France 3 — Régulation vitesse A1 Lille-Dourges | [france3-regions.franceinfo.fr](https://france3-regions.franceinfo.fr/hauts-de-france/nord-0/a1-mise-en-place-de-la-regulation-de-vitesse-sur-une-portion-de-l-autoroute-entre-lille-et-paris-2626936.html) |
| Golf Lille Métropole - intérêt métropolitain (délib. MEL) | [lillemetropole.fr](https://www.lillemetropole.fr/sites/default/files/2024-12/Recueil_delib_T2_0.pdf) |
| Golf Ronchin sécheresse 2022 - BFMTV | [bfmtv.com](https://www.bfmtv.com/grand-lille/nord-comment-le-golf-de-ronchin-s-adapte-a-la-secheresse_AV-202208090213.html) |
| Golf Lille Métropole - ICI (sécheresse) | [ici.fr](https://www.ici.fr/infos/environnement/photos-le-golf-de-lille-metropole-face-a-la-secheresse-1659809767) |
| La Voix du Nord - Concertation 2025 | [lavoixdunord.fr](https://www.lavoixdunord.fr/1614703/article/2025-08-12/un-cyber-centre-au-complexe-moto-une-extension-du-golf-ronchin-la-concertation) |

---

*Document complémentaire au dossier d'opposition datacenter Camp Français - Septembre 2026*
