# BILAN CARBONE PRODUCTIVISTE — 1,3 GW DE DATACENTERS = 1 EPR + TOUT LE RESTE

**Objet** : Prendre au sérieux l'hypothèse « plusieurs datacenters totalisant 1,3 GW de charge IT » et en inférer **tous les prérequis** (centrale, réseau, câblage, GPU, travaux), leur **bilan carbone complet** et leur **coût financier**
**Date** : Septembre 2026
**Statut** : Document de travail — ordres de grandeur, hypothèses explicites, à affiner
**Méthode** : « productiviste » = on compte tout ce que le kWh utile exige, pas seulement le compteur du datacenter

---

## TABLE DES MATIÈRES

1. [L'équation de départ — et sa correction](#1-léquation-de-départ--et-sa-correction)
2. [Prérequis n°1 : la centrale](#2-prérequis-n1--la-centrale)
3. [Prérequis n°2 : le réseau et le câblage](#3-prérequis-n2--le-réseau-et-le-câblage)
4. [Prérequis n°3 : les machines (serveurs, GPU, onduleurs)](#4-prérequis-n3--les-machines-serveurs-gpu-onduleurs)
5. [Prérequis n°4 : les travaux et le foncier](#5-prérequis-n4--les-travaux-et-le-foncier)
6. [Bilan carbone productiviste](#6-bilan-carbone-productiviste)
7. [Bilan financier consolidé](#7-bilan-financier-consolidé)
8. [Effets de bord non comptés (ou mal comptés)](#8-effets-de-bord-non-comptés-ou-mal-comptés)
9. [Mise à l'échelle nationale — 63 sites, 109 Md€](#9-mise-à-léchelle-nationale--63-sites-109-md)
10. [Argumentaire — questions à poser](#10-argumentaire--questions-à-poser)
11. [Références](#11-références)

---

## 1. L'ÉQUATION DE DÉPART — ET SA CORRECTION

### 1.1 L'hypothèse proposée

> 1,3 GW de datacenters ≈ 1 EPR (1 600 MW × 0,8 de productif = 1 280 MW ≈ 1,3 GW)

L'EPR de Flamanville affiche ~1 600 MWe nets (1 650 MW bruts, 1 630 MW de référence AIEA). Avec un facteur de charge de 0,8, il livre en moyenne **1 280 MW**. L'équation est arithmétiquement juste **à une condition** : confondre la charge IT des datacenters avec leur soutirage réel.

### 1.2 La correction : le PUE change tout

Un datacenter ne soutire jamais seulement sa charge IT. Avec le PUE (Power Usage Effectiveness) :

| PUE | Soutirage pour 1,3 GW IT | Couverture par 1 EPR à 0,8 (1 280 MW) | Couverture par 1 EPR au Kp FR réel 0,68 (1 088 MW) |
|---|---|---|---|
| 1,3 (cible vertueuse) | 1,69 GW | 76 % | 64 % |
| 1,4 (réaliste neuf) | 1,82 GW | 70 % | 60 % |
| 1,5 (parent §8 : 126 MW pour 84 MW IT) | 1,95 GW | 66 % | 56 % |

**Premier résultat** : 1,3 GW IT à PUE 1,4-1,5 exige **1,8-2,0 GW soutirés**, soit **1,4 à 1,8 EPR** au facteur de charge français réel (Kp 2024 : ~67 %, cf. `generalites/electricite-france-nucleaire.md`). L'équation « 1,3 GW = 1 EPR » est donc **optimiste d'un facteur ~1,5**. Le besoin réel, c'est **2 EPR** (ou 1 EPR + le réseau pour le solde).

### 1.3 Mise à l'échelle annuelle

| Indicateur | 1,3 GW IT, PUE 1,4 | Repère France |
|---|---|---|
| Soutirage continu | 1,82 GW | ~3 % de la pointe hiver (~100 GW) |
| Énergie annuelle | **15,9 TWh/an** | ~3,5 % de la consommation nationale (~450 TWh) |
| Équivalent foyers | ~3,5 millions | L'EPR « alimente 2-3 millions de foyers » : un parc de 1,3 GW IT **mange un EPR entier** |
| Équivalent Camp Français maximaliste | ~15 sites de 84 MW IT | 15 × 22 ha = 330 ha de foncier |

---

## 2. PRÉREQUIS N°1 : LA CENTRALE

### 2.1 Ce que coûte un EPR (chiffres vérifiés 2025-2026)

| Poste | Valeur | Source |
|---|---|---|
| Puissance EPR Flamanville | ~1 600 MWe nets (1 650 bruts) | EDF / AIEA PRIS |
| Coût total Flamanville 3 | **23,7 Md€** (dont construction 15,6 Md€) | Cour des comptes, janv. 2025 |
| Dérive | ×7 vs devis 2006 (3,2-3,3 Md€), 12 ans de retard | Cour des comptes |
| Programme EPR2 (6 réacteurs) | **72,8 Md€2020** soit **~12,1 Md€/tranche** | EDF, CA déc. 2025 (audité DINN 2026) |
| Première mise en service EPR2 (Penly) | **2038**, suivantes tous les 12-18 mois | Conseil de politique nucléaire, mars 2025 |
| Soutien public EPR2 | Prêt bonifié ≥50 %, **CfD 40 ans ≤100 €2024/MWh**, partage de risques État/EDF | CPN mars 2025, notifié Commission UE nov. 2025 |

### 2.2 Le calendrier tue l'équation

Un datacenter se construit en **2-3 ans**. Un EPR en **12-17 ans** (Flamanville : chantier 2007, couplage déc. 2024, pleine puissance déc. 2025). Décision d'investissement EPR2 fin 2026 → premier électron 2038.

**Conséquence** : tout GW de datacenters mis en service **avant ~2038** ne sera PAS alimenté par du nouveau nucléaire. Il sera alimenté par le parc existant (déjà saturé en pointe et fragilisé l'été : **20,4 % d'indisponibilité le 12/08/2026**, cf. dossier électricité) + gaz + importations. Le « datacenter décarboné grâce au nouveau nucléaire » est un récit à **12 ans de décalage**.

### 2.3 Le productif réel d'un EPR en France

Le 0,8 de l'hypothèse est un plafond : Kp français 2019-2025 = 63-70 % (suivi de charge + grand carénage + aléas climatiques). À Kp 0,68, l'EPR livre **1 088 MW moyens**, pas 1 280. Et l'été, quand les datacenters consomment à plein (clim + IT), le parc perd 3-6 % de production (été 2026 : 4,1 TWh de gaz de compensation, spot à 122,8 €/MWh en août).

---

## 3. PRÉREQUIS N°2 : LE RÉSEAU ET LE CÂBLAGE

### 3.1 Raccordement : l'infrastructure invisible

| Composant | Ordre de grandeur | Délai | Coût |
|---|---|---|---|
| Sous-station 225/20 kV dédiée (site type 126 MW) | 1 poste + 2 km de liaison | 3-5 ans | **80-150 M€** (cf. parent §8.6) |
| ×15 sites pour 1,3 GW IT | 15 postes, ~30 km de liaisons HT | Idem, en parallèle | **1,2-2,2 Md€** |
| Renforcement amont RTE (lignes 400/225 kV, transfos) | Selon saturation régionale | 5-10 ans | Non chiffré ici — à exiger à RTE |
| Câblage interne DC (courants faibles + forts) | ~2 400 racks × km de TGBT, jeux de barres, fibre | Chantier | Inclus CAPEX DC |

### 3.2 Groupes de secours et onduleurs

Un datacenter ne tolère aucune coupure : chaque site porte ses groupes électrogènes (fioul/HVO, rubrique ICPE 3110) et ses chaînes ASI (batteries lithium, renouvelées tous les 8-10 ans). Pour 15 sites : ~15 × 20-40 groupes de 2-3 MVA = **300-600 groupes**, leurs cuves (~milliers de m³ de fioul), leurs émissions NOx/PM aux essais mensuels — **jamais comptées** dans le « bilan vert » de l'exploitant.

---

## 4. PRÉREQUIS N°3 : LES MACHINES (SERVEURS, GPU, ONDULEURS)

### 4.1 Combien de machines pour 1,3 GW IT ?

Base parent §8 : 2 414 racks pour 84 MW IT (4 GPU H100/rack). Extrapolation linéaire :

| Poste | 84 MW IT (1 site max) | 1,3 GW IT (×15,5) |
|---|---|---|
| Racks | 2 414 | **~37 400** |
| GPU H100 (4/rack) | 9 656 | **~150 000** |
| Coût GPU seuls (~30 k$/H100) | ~290 M$ | **~4,5 Md$ (~4,1 Md€)** |
| Serveurs complets (×2 du GPU, règle usuelle) | ~0,6 Md€ | **~8-9 Md€** |
| Renouvellement | Tous les **4-6 ans** (obsolescence IA) | **~2 Md€/an** de refresh permanent |

Le refresh est le point aveugle : la « centrale » matérielle se **reconstruit tous les 5 ans**, quand l'EPR se construit une fois pour 60 ans.

### 4.2 Carbone incorporé (embodied) — méthode et ordres de grandeur

Hypothèses de travail explicites (littérature constructeurs PCF 2024-2025 : un serveur bi-GPU ~3-6 tCO2e, un rack 8×H100 ~25-40 tCO2e avec réseau et ASI au prorata) :

| Poste | Hypothèse | Total 1,3 GW IT |
|---|---|---|
| 37 400 racks équipés | ~8 tCO2e/rack (serveurs + réseau + part ASI/GE) | **~300 000 tCO2e** |
| Bâtiments (15 × 77 000 m², béton/acier) | ~0,5 tCO2e/m² (bâtiment industriel) | **~580 000 tCO2e** |
| **Total incorporé initial** | | **~0,9 MtCO2e** |
| Renouvellement IT (5 ans) | 300 kt × 12 cycles sur 60 ans | **~3,6 MtCO2e / 60 ans** |

À comparer : la construction d'un EPR (béton ~500 000 m³, acier ~200 000 t) est estimée par l'ACV à **~0,5-1 MtCO2e** — du même ordre que **la seule première équipement IT**, avant tout refresh.

---

## 5. PRÉREQUIS N°4 : LES TRAVAUX ET LE FONCIER

| Poste | Ordre de grandeur | Source / base |
|---|---|---|
| Génie civil 2 EPR2 Penly (Eiffage, gros œuvre seul) | **>4 Md€** | Contrat Eiffage/EDF |
| Démarche « Grand Chantier » par site nucléaire | Logements, voiries, parkings, formation, 1 200 salariés + milliers d'intérimaires chantier | EDF Penly 2026 |
| Foncier datacenters (15 × 22 ha) | **~330 ha** artificialisés ou bloqués 20-30 ans | Parent §8 |
| Eau DC (adiabatique, 15 sites) | **~5 Mm³/an** (330 000 m³ × 15) | Parent §8.7 |
| Eau EPR (appoint circuit) | Ordre 1-2 Mm³/an par tranche en circuit fermé (aéroréfrigérant) | Ordres publiés EDF |
| Groupes froids, fluides (R1234ze…), tours | Fuites HFC : PRP × fuites annuelles 2-5 % | À inventorier par site |

---

## 6. BILAN CARBONE PRODUCTIVISTE

### 6.1 Facteurs d'émission retenus (ACV complètes, ordres admis)

| Source | gCO2e/kWh (cycle de vie) | Remarque |
|---|---|---|
| Nucléaire neuf (EPR, 60 ans, Kp 0,75) | **10-15** | Construction + cycle + démantèlement + déchets (médiane GIEC ~12) |
| Mix électrique FR 2025 | **~50-60** | Dominante nucléaire + hydraulique + fossile résiduel |
| Gaz CCGT (marginal d'été) | **~400-490** | Été 2026 : 4,1 TWh gaz pour compenser nucléaire ralenti + clim |
| Import marginal UE (pointe) | **~200-350** | Mix voisins (charbon/gaz DE-PL) |

### 6.2 Exploitation : trois scénarios pour 15,9 TWh/an

| Scénario | Facteur appliqué | Émissions/an | Commentaire |
|---|---|---|---|
| **A. « EPR dédié » (récit promoteur)** | 12 g | **~190 000 tCO2e/an** | Suppose un EPR neuf disponible — faux avant 2038 (§2.2) |
| **B. Mix FR moyen** | 55 g | **~875 000 tCO2e/an** | Le plus honnête pour un soutirage 24/7 base |
| **C. Marginal de tension (été canicule)** | 250 g (mix pointe/import/gaz) | **~4 MtCO2e/an** | Ce que coûte réellement le kWh **additionnel** quand le parc est à -20 % |

Le scénario C est le seul « productiviste » : le datacenter tourne **à plein quand le système est au plus fragile** (clim + IT l'été, pointe d'hiver le soir). L'été 2026 l'a démontré : +4-5 % de consommation → gaz + importations + spot à 487 €/MWh le 13/08.

### 6.3 Bilan 60 ans (durée de vie d'un EPR) — 1,3 GW IT maintenus

| Poste | Total 60 ans |
|---|---|
| Exploitation (scénario B, mix FR) | **~52 MtCO2e** |
| Incorporé IT initial + 11 refresh | **~3,6 MtCO2e** |
| Bâtiments DC (1 génération, 30 ans → ×2) | **~1,2 MtCO2e** |
| Construction EPR (1 tranche) | **~0,5-1 MtCO2e** |
| Groupes secours (essais + vrai secours) | Non chiffré — à ajouter |
| **Total productiviste** | **~57-58 MtCO2e** |

Soit l'équivalent de **~1 an d'émissions du transport routier français** (~90 Mt en 2024, à vérifier CITEPA) pour faire tourner 1,3 GW d'IA pendant 60 ans — avec de l'électricité « décarbonée ». Le paradoxe n'est qu'apparent : 16 TWh/an × 60 ans = 950 TWh, même à 55 g ça pèse 52 Mt.

### 6.4 Le rendement carbone du calcul (pourquoi c'est un gouffre)

Parent §4 : 1 lame 8×B200 = 140 000 tok/s pour 8 kW. À l'échelle 1,3 GW : ~20 milliards de tokens/s théoriques pour 52 Mt/60 ans. Rapporté à l'utilité (utilisation moyenne GPU cloud mesurée : **5 %**, Cast AI, cf. parent §1.3), **95 % de l'énergie sert à chauffer des GPU en attente**. Le premier gisement carbone n'est pas le PUE, c'est le **taux d'utilisation**.

---

## 7. BILAN FINANCIER CONSOLIDÉ

### 7.1 La stack complète pour 1,3 GW IT (neuf, France, 2026)

| Couche | Coût | Base |
|---|---|---|
| 1 EPR (part EPR2, 12,1 Md€/tranche) — ou 1,5 au réel | **12-18 Md€** | EDF déc. 2025 (§2.1) |
| Raccordements + renforcements (15 sites + amont) | **2-4 Md€** | 80-150 M€/site + amont RTE |
| 15 datacenters (2,5 Md€/site maximaliste 84 MW) | **~37 Md€** | Parent §8.9 |
| Équipement IT initial (serveurs + réseau) | **~8-9 Md€** | §4.1 |
| Refresh IT 60 ans (×12) | **~100 Md€** cumulés | §4.1 — le poste dominant |
| **TOTAL initial (hors refresh)** | **~60-68 Md€** | |
| **TOTAL 60 ans (avec refresh)** | **~160 Md€** | Soit ~7× Flamanville |

### 7.2 Qui paie ? (la question qui fâche)

| Coût | Payeur affiché | Payeur réel probable |
|---|---|---|
| EPR (prêt bonifié ≥50 %, CfD 40 ans ≤100 €/MWh) | EDF / État | **Contribuable** (garantie) + **consommateur** (CfD 100 € vs coût historique 60,3 €/MWh CRE 2026-2028 = +66 %) |
| Raccordements et renforcements | « Le projet » | **TURPE** : mutualisé sur tous les usagers du réseau |
| Datacenters et GPU | Opérateur privé | Opérateur — mais subventions, foncier décoté et exonérations à inventorier |
| Refresh GPU permanent | Opérateur | Opérateur — répercuté sur les prix du calcul (donc sur tous les clients, dont le public) |
| Inondations, eau, voiries, Grand Chantier | — | **Collectivités** |

Le CfD à 100 €/MWh (contre 60,3 €/MWh de coût complet historique) verrouille **pendant 40 ans** un prix supérieur de deux tiers au nucléaire actuel : chaque MWh « souverain » du nouveau nucléaire coûtera plus cher que le MWh actuel, **avant même d'ajouter le PUE et le refresh GPU**.

### 7.3 Coût du MWh utile de calcul

1 MWh IT à PUE 1,4 = 1,4 MWh soutirés à ~100 € (CfD) = **140 €/MWh IT**, hors amortissement DC (~37 Md€ / 950 TWh = ~39 €/MWh) et hors refresh (~100 €/MWh). Total : **~280 €/MWh de calcul utile** — contre ~60-120 €/MWh d'électricité nue. Le calcul IA « décarboné » coûte **3 à 5 fois** le prix de son électricité.

---

## 8. EFFETS DE BORD NON COMPTÉS (OU MAL COMPTÉS)

1. **Canicule croisée** : l'EPR perd de la puissance quand le DC en demande le plus (été 2026 : -20,4 % parc, clim +4-5 %). Dimensionner sur la moyenne annuelle = panne dimensionnelle.
2. **Eau cumulée** : 5 Mm³/an (DC) + appoint EPR + agriculture + nappe déjà haute/basse selon saison (cf. dossier nappe Craie) = conflit d'usage programmé.
3. **Déchets** : combustible usé (piscine La Hague saturée → nouvelle piscine 2040), serveurs (DEEE, terres rares, lithium ASI), béton amianté des friches.
4. **Foncier verrouillé** : 330 ha + emprises lignes/postes, 20-60 ans, pendant que le marché bureaux est à 8,8 % de vacance (Lille T2 2026).
5. **Compétences** : soudeurs nucléaires + techniciens DC + électriciens HT : même bassin de main-d'œuvre tendue, mêmes délais qui glissent ensemble.
6. **Géopolitique du refresh** : 150 000 GPU NVIDIA/TSMC tous les 5 ans = 12 fois la dépendance, pas une.
7. **Rebond (Jevons)** : chaque gain tok/kWh est réinvesti en modèles plus gros (cf. parent : Kimi K3 = 16×B200, 800 k$) — le bilan ne baisse jamais.

---

## 9. MISE À L'ÉCHELLE NATIONALE — 63 SITES, 109 MD€

### 9.1 Les faits vérifiés (2025-2026)

| Donnée | Valeur | Source |
|---|---|---|
| Annonce sommet IA (fév. 2025) | **109 Md€ privés** pour l'IA, surtout datacenters | Élysée ; LeMagIT 17/02/2025 |
| Sécurisé 10 mois après | ~90 Md€ sur 109, **48 projets** suppl. évalués | La Tribune (via Obs. multinationales) |
| Sites « clés en main » État | **63 sites** identifiés (carte confidentielle) | DGE (entreprises.gouv.fr) ; Décideurs 07/2026 |
| Projets recensés RTE fin 2025 | **~70 projets = 15 GW** cumulés horizon 2035 | Livre blanc France Datacenter |
| Conso parc FR | 5-10 TWh (2025) → **21-32 TWh (2035)** ; 300 DC = 10 TWh en 2022 (2 % conso FR) | France Datacenter ; RTE 2022 |
| Budget raccordement RTE | **53 Md€ sur 15 ans** (lignes 400 kV + postes) | LeMagIT/RTE 02/2025 |
| Délais raccordement actuels | **5-7 ans** ; instruction >2 ans sans garantie | France Datacenter / Equinix |
| Poids acteurs français | **<10 %** du poids économique du secteur | Thésée DataCenter |
| Leaders FR | Digital Realty 241 MW, Equinix 234 MW (US) ; OVH >1 Md€ CA 2025, Data4 | Hubblo/AEF ; Obs. multinationales |

### 9.2 Nouveaux projets emblématiques (Hauts-de-France en tête)

| Projet | Puissance | Investissement | Mise en service |
|---|---|---|---|
| Fouju (77), Campus AI MGX/Bpifrance/Nvidia/Mistral | **1,4 GW**, 12 DC, 70 ha | 2e site ~7,5 Md€ | Phase 1 en 2028 |
| Bosquel (80), Sesterce/SoftBank | **1 GW**, 64 ha, 16 modules | **10 Md€ bâtiment seul** (ratio 10 M€/MW), RTE 1 GW en 4 ans | — |
| Cambrai + Escaudain, Brookfield/Data4 | **700 MW** « AI factory » Nord, 2 500 emplois permanents | 30 Md€ (rehaussé de 20) | — |
| Béthune, Nebius (ex-Bridgestone) | 240 MW | ~8 Md€ | Phase 1 en 2026 |
| SoftBank (Dunkerque, Bosquel, Bouchain) | **5 GW** d'ici 2031 (dont 3,1 GW phase 1) | **75 Md€** (45 Md€ d'ici 2031 en Hauts-de-France) | 2031 |
| Microsoft (4 DC + Alsace) | — | 4 Md€ | — |

### 9.3 Le test productiviste à l'échelle nationale

**Puissance** : 15 GW IT à PUE 1,4 = **21 GW soutirés** = **13 à 16 EPR** au facteur de charge réel (1 088-1 280 MW/EPR). Il n'existe ni le programme nucléaire (6 EPR2 prévus, premier en 2038), ni le réseau (53 Md€ sur 15 ans, délais 5-7 ans), ni les chantiers pour absorber ça d'ici 2035. Le plan national suppose implicitement **gaz + importations** pendant 10 ans — exactement le scénario C du §6 (250 g/kWh marginal).

**Argent** : le ratio Bosquel (10 M€/MW **bâtiment seul**) donne 15 GW = **150 Md€ de gros œuvre**, avant GPU (~45 Md€ pour ~1,7 M de H100 équivalents), avant réseau (53 Md€ RTE), avant nucléaire (12 Md€/tranche × 13 = **156 Md€**), avant refresh (~1 100 Md€/60 ans). Les **109 Md€ annoncés sont un acompte** : la stack complète vaut **5 à 10 fois** ce montant. Qui paie le solde ? Cf. §7.2 : TURPE, CfD, collectivités.

**Souveraineté** : <10 % d'acteurs français, leaders US (Digital Realty, Equinix), GPU NVIDIA, fonds émirati MGX sur le projet amiral « souverain » de Fouju. Le §6 du parent s'applique ×63 : **63 bâtiments français = 63 dépendances**, pas 63 souverainetés.

**Carbone** : 21-32 TWh/an à 55 g (mix) = **1,2-1,8 MtCO2e/an** ; au marginal d'été (250 g) = **5-8 MtCO2e/an**. Plus l'incorporé : 63 sites × ~60 kt (bâtiment + première IT) ≈ **3,8 MtCO2e** initiales, avant refresh quinquennal.

---

## 10. ARGUMENTAIRE — QUESTIONS À POSER

1. Quel PUE **contractuel avec pénalités** ? (pas une cible)
2. Quelle source d'électrons **avant 2038**, année par année, avec facteurs d'émission **marginaux** ?
3. Qui paie les **2-4 Md€** de réseau, et quelle part en TURPE ?
4. Quel **taux d'utilisation GPU contractuel** (contre 5 % mesurés) ?
5. Quel plan **refresh** (masses, DEEE, coûts) sur 30 ans ?
6. Quel cumul **eau + chaleur + bruit** des 15 sites à l'échelle du territoire ?
7. Quel prix du MWh **tout compris** (CfD + PUE + amortissement + refresh) ?
8. Quelle **réversibilité** du foncier après 20-30 ans ?

---

## 10. RÉFÉRENCES

| Donnée | Source |
|---|---|
| EPR Flamanville : 1 600 MWe nets, couplage 21/12/2024, 100 % le 14/12/2025 (1 669 MW) | EDF ; TF1/AFP déc. 2025 ; AIEA PRIS (1630/1620/1650 MW) |
| Coût Flamanville : 23,7 Md€, rentabilité médiocre | Cour des comptes, janv. 2025 (via Le Monde 14/01/2025) |
| EPR2 : 72,8 Md€2020 pour 6 tranches, Penly 2038, CfD 40 ans ≤100 €2024/MWh, prêt ≥50 % | EDF 18/12/2025 ; CPN Élysée 17/03/2025 |
| Génie civil Penly : >4 Md€ (Eiffage) | Eiffage / EDF |
| Kp/Kd, canicule 20,4 %, gaz été 2026, spot 122,8 €/MWh, coût complet 60,3 €/MWh | `generalites/electricite-france-nucleaire.md` (RTE, CRE, Sfen, Franceinfo, France 24) |
| Racks, GPU, PUE, eau, bruit, coûts DC | `infrastructure-ia-gpu-souverainete.md` §8 |
| Utilisation GPU cloud 5 % | Cast AI, via parent §1.3 |

---

*Document de travail — les chiffres IT (incorporé/rack, refresh, PUE) sont des hypothèses de travail explicites à resserrer avec les PCF constructeurs et les CCTP des projets réels. Les chiffres nucléaires et réseau sont sourcés. Conclusion inchangée quelle que soit la marge : 1,3 GW IT = ~2 EPR au réel + ~60 Md€ initiaux + ~57 MtCO2e/60 ans + refresh perpétuel.*
