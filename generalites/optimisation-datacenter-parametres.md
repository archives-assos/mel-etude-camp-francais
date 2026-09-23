# Paramètres d'optimisation du dimensionnement d'un datacenter

> Dernière mise à jour : septembre 2026
> Sources citées dans le texte. Vérification recommandée sur les originaux.

---

## Table des matières

1. [Distance backbone et connectivité fibre](#1-distance-backbone-et-connectivité-fibre)
2. [Refroidissement et efficacité énergétique](#2-refroidissement-et-efficacité-énergétique)
3. [Consommation énergétique et scénarios prospectifs](#3-consommation-énergétique-et-scénarios-prospectifs)
4. [Groupes électrogènes et énergie de secours](#4-groupes-électrogènes-et-énergie-de-secours)
5. [Nuisances sonores et réglementation](#5-nuisances-sonores-et-réglementation)
6. [Coûts informatiques (CAPEX/OPEX)](#6-coûts-informatiques-capexopex)
7. [Disponibilité et niveaux de service](#7-disponibilité-et-niveaux-de-service)
8. [Taille des modèles et densité GPU](#8-taille-des-modèles-et-densité-gpu)
9. [Consommation d'eau (WUE)](#9-consommation-deau-wue)
10. [Valorisation de la chaleur fatale](#10-valorisation-de-la-chaleur-fatale)
11. [Synthèse des fourchettes clés](#11-synthèse-des-fourchettes-clés)

---

## 1. Distance backbone et connectivité fibre

### Types d'interconnexion datacenter (DCI)

| Type DCI | Distance typique | Latence | Usage | Technologies |
|---|---|---|---|---|
| Campus | ≤ 5 km | Très faible | Regroupement bâtiments | ToR, DWDM local |
| Métropolitain | ≤ 100 km | Faible | Zones de disponibilité régionales | DWDM, amplification minimale |
| Longue distance | > 500 km | Plus élevée | Réplication géo-ronde | EDFA/Raman, DWDM |
| Sous-marin | Centaines de km | Variable | Intercontinentale | Câbles sous-marins, amplification |

*Source : zoneactu.fr, 2026 [1]*

### Contraintes physiques de la fibre optique

- Atténuation fibre monomode : **0,4 dB/km à 1 310 nm** et **~0,2 dB/km à 1 550 nm** (valeurs nominales nouvelles fibres)
- Fibres installées depuis >15 ans : **0,35 à 0,45 dB/km à 1 550 nm** mesurés en déploiement réel
- Liaisons intra-bâtiment <300 m : fibre multimode, émetteurs-récepteurs SR
- Liaisons campus/métro 1-80 km : fibre monomode, optiques LR/ER/ZR
- Au-delà de 80 km : technologie cohérente avec amplification
- Migration 100G → 400G → 800G réduit les limites : le 400G SR8 ne couvre que **30 m sur fibre multimode OM4** (contre 100 m en 100G)

*Source : 100gmodules.com, 2026 [2]*

### Capacité et dimensionnement

- Le coût de l'extraction de nouvelles fibres est dominé par la **main-d'œuvre et les travaux de génie civil**, pas par le verre
- Fibre installée aujourd'hui achemine le trafic pendant **15 à 25 ans** ; les émetteurs-récepteurs seront remplacés 3-4 fois
- Recommandation : concevoir l'infrastructure permanente de manière généreuse (≥30% capacité noire supplémentaire) et la couche enfichable de manière économique
- Seuil économique DWDM vs CWDM : DWDM quand >18 canaux ou >80 km ou débits ≥100G par canal
- 400G ou 800G comme référence par port en 2026

*Source : 100gmodules.com, 2026 [2]*

### Réseau backbone OVHcloud

- OVHcloud exploite un réseau backbone mondial avec fibre noire en propre
- Objectif : 100% des interconnexions DC ↔ PoP en fibre propre
- Infrastructure DWDM déployée pour interconnexions longue distance
- Connectivité directe (OVHcloud Connect) : de 200 Mbps à fibre dédiée 10 Gbps

*Source : OVHcloud, 2026 [3]*

### Résilience et survie des DC distribués

- Augmenter la survivabilité de 0 à 0,5 n'augmente la latence que de **0,7 ms max** sur les WAN réalistes
- Survivabilité de 0,8 atteinte avec seulement **3,6 ms** de latence max
- Au-delà de 0,94 de survivabilité, chaque gain de 2% peut augmenter la latence de **46%** (chemins très longs vers nœuds isolés)

*Source : Cnam, SSCC-GC14 [4]*

### Fibre Nexloop (France)

- Réseau national : **38 000 km** de fibre optique, **130+ points de présence**
- Architecture hors axes historiques pour redondance réelle (chemins physiquement distincts)
- Backbone souterrain, routes alternatives, supervision 24h/24

*Source : Nexloop, 2026 [5]*

---

## 2. Refroidissement et efficacité énergétique

### Indicateur PUE (Power Usage Effectiveness)

Le PUE mesure le rapport entre l'énergie totale du datacenter et l'énergie effectivement consommée par les équipements informatiques. Un PUE de 1,0 serait idéal (toute l'énergie pour l'IT). En pratique :

| Technologie | PUE typique | Capacité par rack | Idéal pour |
|---|---|---|---|
| Air (allées confinées) | 1,36 – 1,39 | 15-20 kW | Cloud standard, stockage |
| Free-chilling (eau) | 1,24 – 1,27 | 20-40 kW | Sites tempérés |
| Direct-to-Chip (DLC) | 1,10 – 1,20 | Jusqu'à 80 kW | IA modérée, hybridation |
| Immersion cooling | < 1,05 – 1,10 | 100+ kW | HPC, IA intensive |

*Sources : ADEME/Critical Building, 2026 [6] ; Sirenergies, 2026 [7]*

### Performances mesurées en France

- Groupes froids à air : **PUE 1,36-1,39**
- Groupes froids à condensation eau + free-chilling : **PUE 1,24-1,27**
- Gain supplémentaire de **7%** possible avec compresseurs TurboCor
- Le DLC (refroidissement liquide direct) affiche les **meilleures performances** parmi les technologies étudiées

*Source : ADEME/Critical Building, 2026 [6]*

### PUE benchmarks hyperscale

- Google : PUE annuel moyen 2024 de **1,09** sur sa flotte mondiale
- NREL ESIF : PUE de **1,028** avec système thermosiphon
- Pour chaque centième de PUE en moins sur un site de 50 MW → **des centaines de milliers d'euros** d'économie annuelle

*Sources : orelnienergie.com, 2026 [8] ; score-grp.com, 2026 [9]*

### Température de consigne

- Serveurs maintenus idéalement entre **18°C et 27°C** (25°C recommandé)
- Passer de 18°C à 25°C en allées chaudes réduit les besoins en refroidissement mécanique et élargit la fenêtre de free cooling
- Le free cooling actif en France : **4 à 6 mois** selon la région (contre 8 000+ h/an en Scandinavie)

*Sources : Sirenergies, 2026 [7] ; mission-open-data.fr, 2026 [10]*

### Impact du refroidissement sur les coûts de construction

| Composant | Installation standard | Installation IA |
|---|---|---|
| Refroidissement par MW | ~1,8 M$ (air) | 4,5-5,2 M$ (liquide) |
| Part mécanique dans le budget | ~22% | ~33% |

*Source : Turner & Townsend, 2025-2026, cité par axis-intelligence.com [11]*

### Technologies émergentes

- **Immersion cooling** : serveurs plongés dans un fluide diélectrique, jusqu'à **100+ kW/rack**
- **Free cooling avancé** : combinaison dry cooler + boucle eau tempérée
- **IA pour gestion thermique** : optimisation en temps réel des consignes
- **Groupes froids à fluides alternatifs** : réduction GWP

*Source : ADEME/Critical Building livrable 3, 2026 [6]*

---

## 3. Consommation énergétique et scénarios prospectifs

### Situation actuelle France

- Consommation datacenters France : **10 TWh/an** (2,2% des 449 TWh nationaux en 2025)
- Équivalent de la consommation de **9 à 10 agglomérations >100 000 habitants**
- Demandes de raccordement RTE : **~9 GW** (équivalent 7 réacteurs nucléaires)
- **352 datacenters** en activité en France (recensement ADEME 2026)

*Source : ADEME Infos, 2026 [12]*

### Scénarios ADEME (janvier 2026) — 5 trajectoires jusqu'en 2060

L'ADEME a publié 5 scénarios prospectifs :

1. **Génération frugale** : sobriété maximale, dénumérisation, moratoire sur nouvelles constructions
2. **Coopérations territoriales** : développement concerté avec les territoires, normes sans moratoire, usages prioritaires santé/environnement
3. **Technologies vertes** : innovation technologique et souveraineté numérique
4. **Pari réparateur** : compensation des impacts par la technologie
5. **Tendanciel** : scénario de référence

**Résultats clés du scénario tendanciel** :
- Usages français multipliés par **3,7 d'ici 2035**
- **2/3 de la consommation à l'étranger** (mix électriques plus carbonés)
- En 2060 : consommation varie d'une **division par 2 à une multiplication par 7**
- Chaleur fatale récupérable : **4 à 13 TWh nets en 2035** (via liquid cooling notamment)
- Seules des politiques de sobriété permettent d'atteindre le zéro émission nette en 2050
- L'étude est consultable sur la librairie ADEME : « Prospective d'évolution des consommations des data centers à court, moyen et long terme de 2024 à 2060 »

*Source : ADEME Infos, 2026 [12]*

### Projections européennes et mondiales

- RTE estime que la consommation liée aux centres de données pourrait **tripler en 15 ans** (10 TWh → 19-28 TWh en 2035)
- En 2035 : **~4% de la consommation électrique nationale**
- AIE : consommation mondiale datacenters de **415 TWh en 2024** → **945 TWh en 2030** (plus que doubler)
- Les USA représentent 45%, la Chine 25%, l'Europe 15% du total mondial

*Sources : Banque des Territoires/Autorité concurrence, 2026 [13] ; AIE, 2025 [14]*

### Projections Belgique (BCG/Plateforme GIEC)

- 2024 : **3 TWh/an** (4% de la consommation belge)
- 2035 : **7 à 16 TWh/an** (multiplication par 2 à 5)
- 2050 : **11 à 34 TWh/an** (5% à 15% de la consommation nationale)

*Source : Plateforme wallonne GIEC, 2025 [15]*

### Contraintes de raccordement en France

- RTE a réservé **~18 GW** pour environ 80 projets (mai 2026)
- Demandes cumulées : **28,6 GW**
- Délais de raccordement : **2 à 7 ans**
- Projets individuels de **100 à 200 MW** deviennent courants

*Source : France Épargne/Cushman & Wakefield, 2026 [16]*

---

## 4. Groupes électrogènes et énergie de secours

### Architecture de redondance

| Configuration | Signification | Exemple (4 MW IT) | Tier correspondant |
|---|---|---|---|
| N | Capacité de base, pas de backup | 4 × 1 MW | Tier I |
| N+1 | Une unité supplémentaire | 5 × 1 MW (4 suffisent) | Tier II / Tier III |
| 2N | Deux chemins indépendants pleine capacité | 2 × 4 MW | Tier IV |
| 2N+1 | 2 chemins + 1 unité supplémentaire | 2 × 4 MW + 1 spare | Tier IV hyperscale |

*Source : asogenset.com, 2026 [17]*

### Spécifications techniques

| Paramètre | Valeur typique |
|---|---|
| Gamme de puissance par unité | 500 kVA à 4 MVA (mono) ; jusqu'à 10 MVA (multi-GE synchronisés) |
| Démarrage et tension nominale | **10 à 15 secondes** après détection de panne |
| Niveau acoustique (container GE) | 75 dBA à 1 m / 65 dBA à 7 m / **55 dBA en limite de propriété** |
| Autonomie carburant | 8 h à 72 h selon cuve intégrée |
| Résistance au feu | REI 60 / REI 120 |
| Fonctionnement température | -30°C à +50°C |
| Conformité | CE, ISO 8528, NFPA 110, IEC 60034 |

*Sources : AIROPTA, 2026 [18] ; letonpower.com, 2026 [19]*

### Norme de puissance DCC vs ESP

- **DCC (Data Center Continuous)** : fonctionnement continu à 100% puissance nominale, heures illimitées — **requis pour datacenters**
- **ESP (Emergency Standby Power)** : max 200 h/an, facteur charge <70% — inadapté aux datacenters
- La certification DCC garantit conformité Tier III/IV

*Source : letonpower.com, 2026 [19]*

### Autonomie carburant par Tier

- Tier III : **minimum 12 heures** à pleine charge IT (souvent spécifié)
- Tier IV / hyperscale : **72 à 96 heures** selon profil de risque et logistique
- Stockage carburant : cuves surélevées ou belly tanks, double paroi, système de polissage du diesel
- Redondance des contrats de livraison et des chemins d'alimentation carburant

*Source : asogenset.com, 2026 [17]*

### Impact des charges non-linéaires

- Les serveurs et redresseurs UPS génèrent des **harmoniques** qui augmentent les pertes et l'échauffement des enroulements
- Recommandation : générateur à **faible impédance** (surdimensionné de **1,2 à 1,5×** la capacité nominale)
- Moteur avec excitation PMG (aimants permanents) pour réponse transitoire

*Sources : Kyson, 2026 [20] ; letonpower.com, 2026 [19]*

### Délais d'approvisionnement (2026)

- Transformateur sur socle : **68 à 113 semaines**
- Groupe électrogène : **60 à 100 semaines**
- Tableau moyenne tension : **38 à 63 semaines**
- Hausse des prix depuis 2021 : groupes électrogènes **+33%**, équipements refroidissement **+32%**, transformateurs **+29%**

*Source : Cushman & Wakefield, 2026 [16]*

---

## 5. Nuisances sonores et réglementation

### Sources sonores d'un datacenter

- Systèmes de refroidissement (principale source)
- Groupes électrogènes de secours
- Ventilateurs et CTA (centrales de traitement d'air)
- Transformateurs électriques

**Niveaux de puissance sonore** :
- Datacenter hyperscale 50 MW : **~110 dB(A)** émis par les refroidisseurs (en champ proche)
- Datacenter edge 2 MW : **~100 dB(A)** émis
- Chez les riverains à 100 m (hyperscale sans traitement) : **~70 dB(A)**
- Émergence sonore résidentielle urbaine : **25 à 35 dB(A)**

*Sources : Gamba, 2026 [21] ; Vibiscus, 2026 [22]*

### Réglementation française

**Décret bruit de voisinage** (Code de la Santé Publique, décret n°2006-1099) :

| Niveau ambiant mesuré | Émergence max. jour | Émergence max. nuit |
|---|---|---|
| > 35 dBA et < 45 dBA | 6 dBA | 4 dBA |
| > 45 dBA | 5 dBA | 3 dBA |

**ICPE (Installations Classées)** :
- Limite de propriété : **70 dB(A) jour / 60 dB(A) nuit** (arrêté préfectoral)
- Valeurs souvent inférieures imposées selon contexte

**Seuils OMS recommandés** :
- **53 dB(A)** sur 24h (effets néfaste sur santé)
- **45 dB(A)** en période nocturne

*Sources : Venathec, 2026 [23] ; Acoustique BSEC, 2026 [24]*

### Zones et émergences PLU

| Zone réceptrice | Émergence max. jour | Émergence max. nuit |
|---|---|---|
| Naturelle | 5 dBA | 3 dBA |
| Résidentielle | 6 dBA | 4 dBA |
| Commerciale/artisanale | 7 dBA | 5 dBA |

*Source : Acoustique BSEC, 2026 [24]*

### Infrasons : la nuisance invisible

Les datacenters génèrent des composantes sonores dans le domaine des infrasons (**< 20 Hz**), inaudibles pour l'oreille humaine mais physiquement perceptibles. Ce phénomène est particulièrement documenté depuis 2025-2026 aux États-Unis et en France.

**Sources d'infrasons** :
- Systèmes de refroidissement massifs (compresseurs, ventilateurs grande échelle)
- Groupes électrogènes diesel (marqués en basses fréquences 50-250 Hz, avec composantes < 20 Hz)
- Turbines à gaz pour centres de données hors réseau
- Transformateurs et onduleurs (vibrations structurelles à 100 Hz et harmoniques)

**Propagation** :
- Les basses fréquences traversent les murs, vitrages et écrans végétaux avec une facilité que les hautes fréquences n'ont pas
- Un data center hyperscale peut être audible jusqu'à **3 km** pour les grandes installations
- Les sonomètres pondérés en dB(A) sont calibrés sur la sensibilité moyenne de l'oreille et **ignorent largement le grave** → un riverain peut souffrir d'une gêne réelle alors que la mesure réglementaire reste conforme

**Effets sanitaires rapportés** :
- Troubles du sommeil, maux de tête, fatigue chronique, anxiété, hypertension
- Nauseés, vertiges
- Étude *Frontiers in Climate* (février 2026) : premiers résultats sur « Data Center Alley » en Virginie — exposition chronique associée à des atteintes cardiovasculaires, cognitives et psychiques
- Bibliothèque nationale de médecine US : infrasons > 100 dB pouvant affecter la fonction cardiaque dès 1 heure d'exposition
- Infrasons cités comme cause potentielle du « syndrome de La Havane »

**Cadre réglementaire (lacune)** :
- La réglementation française (ICPE, bruit de voisinage) couvre les fréquences **≥ 125 Hz** pour l'émergence spectrale
- Les fréquences < 125 Hz (et donc les infrasons < 20 Hz) **ne sont pas mesurées dans le cadre réglementaire standard**
- Seule une mesure en **tiers d'octave étendu** permet de les quantifier
- Plusieurs comtés américains (Maryland, Pennsylvanie) commencent à intégrer l'infrason dans les délibérations de zonage

**Témoignages France** :
- **Wissous** (Essonne) : extension data center AWS à quelques dizaines de mètres d'une crèche et de deux écoles
- **Le Bourget** (Seine-Saint-Denis) : projet Segro avec 33 groupes électrogènes, pétition 18 000 signatures (commune 15 000 hab.)
- **Rovaltain** (Drôme) : collectif citoyen contre projet supercalculateur IA
- **Loudoun** (Virginie) : demande électrique +166% entre 2021-2025

*Sources : developpez.com/EESI, 2026 [28] ; Les Numériques, 2026 [29] ; lasonotheque.org, 2026 [30] ; Referentiel-acoustique, 2026 [31]*

### Solutions de réduction acoustique

- Isolation en **laine de roche M0** et mousse mélamine dans containers GE
- Silencieux d'admission/échappement
- Ventelles et écrans acoustiques
- Conception aéraulique optimisée (pièges à son, gaines traitées)
- Containers GE atteignant **55 dBA en limite de propriété** (isolement -40 dB)

*Sources : AIROPTA, 2026 [18] ; Gantha, 2025 [25]*

---

## 6. Coûts informatiques (CAPEX/OPEX)

### Coûts de construction par MW (2026)

| Type d'installation | CAPEX/MW | Observations |
|---|---|---|
| Shell & core standard | **$10,7-11,3 M** | Moyenne mondiale, refroidissement air |
| AI-optimisé + liquid cooling | **$12-15 M** | Prime +7-10% structure |
| Facility + aménagement IT (hors GPU) | **$15-25 M** | Inclut PDU, infra de rack |
| Full stack avec GPU | **$30-45 M** | Inclut serveurs, réseau, stockage |
| Campus 1 GW | **$15-20 B total** | Infrastructure uniquement |

*Sources : JLL/Turner & Townsend, 2026 [11] ; Cushman & Wakefield, 2026 [16]*

### Ventilation des coûts de construction

| Poste | Part du budget | Remarques |
|---|---|---|
| Infrastructure électrique | 21-48% | +60% prix tableaux distrib. depuis 2021 |
| Refroidissement (liquid) | 22-33% | $4,5-5,2M/MW vs $1,8M air |
| Gros œuvre + site | 17% | |
| Provisions pour aléas | 2e rang | Incertitude supply chain |
| Sécurité, incendie, réseau | ~7% | |
| Acquisition terrain | 7% | |

*Source : Cushman & Wakefield, 2026 [16]*

### Coût par GPU par an (TCO annualisé)

| Composant | H100/an | B300/an |
|---|---|---|
| Dépréciation GPU (4 ans) | $18 750 | $28 125 |
| Dépréciation facility (10 ans) | $2 500 | $3 500 |
| Énergie ($0,10/kWh) | $5 110 | $7 300 |
| Refroidissement O&M | $1 200 | $2 100 |
| Personnel & opérations | $2 500 | $2 500 |
| Dépréciation réseau | $1 800 | $2 800 |
| **Total** | **$31 860** | **$46 325** |

*Source : ClusterBid, 2026 [26]*

### Prix de location GPU (break-even)

- H100 : **$5,21-6,20/GPU-hour** à 70% d'utilisation (break-even)
- Le spot H100 actuel ($2,50-3,50) est **sous le coût de remplacement**
- B300 : plancher durable à **$4,50-6,50/GPU-hour**

*Source : ClusterBid, 2026 [26]*

### Hausse des coûts en France

- **+21%** du coût par MW depuis Q4 2024 (Cushman & Wakefield)
- Moyenne Amérique du Nord : **$17,6M/MW** ≈ **15,15M€/MW**
- Projet SoftBank France : **14,5M€/MW** (3,1 GW dans les Hauts-de-France)

*Source : France Épargne/Cushman & Wakefield, 2026 [16]*

### Coût du foncier électrifié

- **$584 000/MW** en moyenne sur les marchés américains principaux (depuis début 2026)
- Hausse de **51% en un an**
- **+35%** par rapport à la moyenne quinquennale

*Source : Cushman & Wakefield, 2026 [16]*

---

## 7. Disponibilité et niveaux de service

### Niveaux Uptime Institute

| Tier | Disponibilité | Temps d'arrêt max/an | Architecture alimentation |
|---|---|---|---|
| Tier I | 99,671% | ~29 heures | N, sans redondance |
| Tier II | 99,741% | ~22 heures | Redondance composants, chemin unique |
| Tier III | 99,982% | **~1,6 heure** | N+1, maintenabilité concourante |
| Tier IV | 99,995% | **~0,5 heure** | 2N ou 2(N+1), tolérance aux fautes |

*Sources : asogenset.com, 2026 [17] ; letonpower.com, 2026 [19]*

### Disponibilité réseau vs survie

- Sur un WAN réaliste, **80% des racks restent opérationnels** après toute panne unique avec une latence max de seulement **3,6 ms** supplémentaires
- La disponibilité des données ne se limite pas à la disponibilité du serveur : il faut inclure la redondance des chemins réseau, la réplication et la sauvegarde

*Source : Cnam, SSCC-GC14 [4]*

---

## 8. Taille des modèles et densité GPU

### Densité de puissance par rack

| Type de charge | Puissance par rack | Refroidissement requis |
|---|---|---|
| Informatique standard | 5-15 kW | Air |
| IA modérée | 20-40 kW | Air optimisé / hybride |
| IA intensive (H100/B300) | 40-130+ kW | **Liquid cooling obligatoire** |
| Rack B300 NVL72 (72 GPU × 1000W) | **~72 kW** | DLC ou immersion |
| Roadmap 2027 | **~1 MW/rack** | Immersion |

*Sources : gainam.com, 2026 [27] ; clusterbid.com, 2026 [26]*

### Exigences par type de workload

**Entraînement (Training)** :
- Milliers de GPU couplés par interconnexion haute bande passante (InfiniBand NDR400/NDR800)
- Densité maximale imposée par la latence inter-GPU
- Coût/MW vers le haut de la fourchette
- Network fabric : $80-150M pour un cluster 25 000 GPU

**Inférence (Inference)** :
- Parallélisme « embarrassant », moins sensible à la latence inter-GPU
- Sites distribués plus proches des utilisateurs
- Densité rack plus faible, refroidissement moins coûteux
- Coût/MW vers le bas de la fourchette

*Source : gainam.com, 2026 [27]*

### Ordres de grandeur GPU

| GPU | Prix unitaire | Consommation | Rack type |
|---|---|---|---|
| H100 | ~$30 000 | ~700W | 40-60 kW/rack |
| B300 | ~$45 000 | ~1000W | 60-130 kW/rack |
| B300 NVL72 | — | 72 GPU × 1000W | **~72 kW/rack** |

*Source : clusterbid.com, 2026 [26]*

### Ratio GPU/Facility

- Le CAPEX GPU est **5 à 8× supérieur** au CAPEX facility
- Les GPU représentent **40-60% du CAPEX all-in**
- Durée de vie GPU : **3-5 ans** (contre 10-14 ans pour la facility)

*Sources : gainam.com, 2026 [27] ; clusterbid.com, 2026 [26]*

---

## 9. Consommation d'eau (WUE)

- Un datacenter de taille moyenne (10 MW) peut consommer **50 à 100 millions de litres d'eau par an** avec système adiabatique actif
- Systèmes à circuit fermé réduisent drastiquement cette consommation
- Le WUE (Water Usage Effectiveness) est l'indicateur à suivre quand le refroidissement mobilise de l'évaporation
- Aux USA : **17 milliards de gallons** consommés directement par les datacenters en 2023
- Hyperscalers : **16 à 33 milliards de gallons/an d'ici 2028** (Berkeley Lab 2024)

*Sources : mission-open-data.fr, 2026 [10] ; score-grp.com, 2026 [9]*

---

## 10. Valorisation de la chaleur fatale

- Directive européenne 2023/1791 : datacenters ≥1 MW doivent analyser les possibilités de valorisation de la chaleur fatale
- En France : obligation de raccordement à un réseau de chaleur **si disponible à proximité**
- Potentiel France : **109,5 TWh** de chaleur fatale (UIOM, stations d'épuration, datacenters) — ADEME 2015/2017
- Solution Neutral-IT : besoins ECS baissent de **30 à 60%** grâce à la chaleur des datacenters
- Récupération possible : jusqu'à **96% de la chaleur produite** dans les systèmes optimisés

*Sources : orelnienergie.com, 2026 [8] ; mission-open-data.fr, 2026 [10]*

---

## 11. Synthèse des fourchettes clés

| Paramètre | Fourchette | Source principale |
|---|---|---|
| PUE (air) | 1,36 – 1,39 | ADEME [6] |
| PUE (water free-chilling) | 1,24 – 1,27 | ADEME [6] |
| PUE (DLC) | 1,10 – 1,20 | ADEME [6] |
| PUE (immersion) | < 1,05 – 1,10 | orelnienergie [8] |
| CAPEX shell standard/MW | $10,7-11,3 M | JLL/T&T [11] |
| CAPEX all-in AI/MW | $30-45 M | Epoch AI/ClusterBid [26][27] |
| Coût an H100/an | ~$32 000 | ClusterBid [26] |
| Coût an B300/an | ~$46 000 | ClusterBid [26] |
| Latence DCI campus | ≤ 5 km, très faible | zoneactu [1] |
| Latence DCI métro | ≤ 100 km, faible | zoneactu [1] |
| Émergence sonore nuit (résidentiel) | 4 dBA max | Décret 2006-1099 [23] |
| Bruit limite ICPE (nuit) | 60 dB(A) | Arrêté 1997 [23] |
| Infrasons (fréquences < 20 Hz) | Non couverts par réglementation standard | developpez.com [28] |
| Niveau sonore hyperscale (sans traitement) | 96 dB(A) en fonctionnement | Les Numériques [29] |
| Portée auditive grandes installations | Jusqu'à 3 km | lasonotheque.org [30] |
| Autonomie GE Tier III | ≥ 12 h | asogenset [17] |
| Autonomie GE Tier IV | 72-96 h | asogenset [17] |
| Densité rack IA | 40-130+ kW | gainam [27] |
| WUE datacenter 10 MW (adiabatique) | 50-100 M L/an | mission-open-data [10] |
| Chaleur fatale récupérable 2035 | 4-13 TWh | ADEME [13] |
| Consommation France 2025 | 10 TWh | ADEME [12] |
| Projection France 2035 (tendanciel) | ×3,7 | ADEME [13] |

---

## Références

1. zoneactu.fr — « Connecter les datacenters pour un cloud toujours disponible », 2026
2. 100gmodules.com — « Conception de réseaux optiques : guide en 5 étapes », 2026
3. OVHcloud — « Réseau backbone : transport sécurisé de vos données », 2026
4. Cnam — « Latency Versus Survivability in Geo-Distributed DCs », SSCC-GC14
5. Nexloop — « IA, datacenters et résilience : pourquoi l'interconnexion est devenue stratégique », 2026
6. ADEME/Critical Building — « Refroidissement des datacenters : technologies utilisées en France, potentiel d'économies », 2026
7. Sirenergies — « Techniques pour refroidir un data center », 2026
8. orelnienergie.com — « PUE data center : efficacité énergétique, free cooling et récupération de chaleur », 2026
9. score-grp.com — « Free cooling en datacenter : limites et bonnes pratiques », 2026
10. mission-open-data.fr — « Refroidissement Data Center Eau », 2026
11. axis-intelligence.com — « AI Data Center Cost per MW: 2026 Benchmarks by Tier », 2026
12. ADEME Infos — « Consommation électrique des data centers : 5 scénarios pour demain », janvier 2026 (source consultée en HTML : `sources/textes/Consommation électrique des data centers _ 5 scénarios pour demain - ADEME Infos.html`)
13. Banque des Territoires — « Datacenters : une frugalité bonne pour la concurrence et… », 2026 (cite l'étude ADEME)
14. AIE — « Data Centres and Data Transmission Networks », 2025
15. Plateforme wallonne GIEC — « Lettre 39/40 », 2025
16. France Épargne/Cushman & Wakefield — « Data centers : coûts de construction en hausse de 21% », 2026
17. asogenset.com — « Data Center Generator Redundancy: N+1 vs 2N Guide », 2026
18. AIROPTA — « Container Groupe Électrogène Sur Mesure », 2026
19. letonpower.com — « Technical Specifications for Data Center Diesel Generators », 2026
20. Kyson — « Guide d'évaluation des groupes électrogènes diesel pour centres de données », 2026
21. Gamba — « Quel est l'impact du bruit des data centers pour le voisinage », 2026
22. Vibiscus — « Bruit data center : comment réduire les nuisances sonores », 2026
23. Venathec — « Étude d'impact acoustique des data centers », 2026
24. Acoustique BSEC — « Zone industrielle et conformité PLU acoustique », 2026
25. Gantha — « Maîtriser les enjeux acoustiques des data centers », 2025
26. ClusterBid — « AI Data Center Construction CAPEX 2026 », 2026
27. gainam.com — « AI Data Center Cost Per MW: Budgeting a 2026 GPU Facility », 2026
28. developpez.com/EESI — « Les centres de données IA émettent des infrasons inaudibles et indétectables aux sonomètres », 2026
29. Les Numériques — « Le bruit invisible des datacenters IA rend les riverains malades », 2026
30. lasonotheque.org — « Data centers IA : le grondement qui réveille les voisins », 2026
31. Referentiel-acoustique — « Bruit des équipements CVC : réglementation, obligations et solutions », 2026
