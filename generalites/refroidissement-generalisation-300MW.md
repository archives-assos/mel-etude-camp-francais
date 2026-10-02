# GÉNÉRALISATION DU REFROIDISSEMENT — SITE DE BASE 300 MW

**Objet :** passer des fiches technologiques (`refroidissement.md`) à un **dimensionnement de site complet**, en extrapolant les 4 familles (air, Direct-to-Chip, immersion monophasique, immersion diphasique) à une **capacité globale de refroidissement de 300 MW**.

**Base de calcul :** `P_IT = 300 MW` ≈ `300 MWth` de chaleur à évacuer (≈ 100 % de la puissance IT devient de la chaleur).
Point de référence du corpus : Google Saint-Ghislain = **60 ha pour ~300 MW** (`DATACENTER.md`).

**Abaque calibré** sur le modèle 22 ha de `infrastructure-ia-gpu-souverainete.md` §8 (Air : 78 MW — Liquid : 187 MW) — reproduction exacte des deux bornes, donc extrapolation linéaire valide.

---

## TABLE DES MATIÈRES

1. [Hypothèses et règles de calcul](#1-hypothèses-et-règles-de-calcul)
2. [Capacité globale de refroidissement — 300 MW](#2-capacité-globale-de-refroidissement--300-mw)
3. [Surface du bâtiment IT + refroidissement](#3-surface-du-bâtiment-it--refroidissement)
4. [Bruit](#4-bruit)
5. [Eau](#5-eau)
6. [Fuite de caloporteur](#6-fuite-de-caloporteur)
7. [Synthèse multicritère](#7-synthèse-multicritère)
8. [Références](#8-références)

---

## 1. HYPOTHÈSES ET RÈGLES DE CALCUL

### 1.1 Constantes

| Paramètre | Valeur | Origine |
|---|---|---|
| Charge IT / chaleur à évacuer | **300 MW** | Base imposée |
| Heures/an | 8 760 h | Standard |
| Énergie IT annuelle | **2 628 GWh/an** | 300 × 8 760 |
| Coefficient de constructibilité | **0,35** du site | `MANUEL-dimensionnement` §Paramètres |
| Data halls / constructible | **0,73** | `MANUEL` §2.1 |
| SMCC / constructible | 0,05 | `MANUEL` §2.1 |
| Plant refroidissement / constructible | **0,10** | `MANUEL` §2.1 |
| Marge installée (pertes annexes + N+1) | ×1,05 à 1,15 | Hypothèse de conception |

### 1.2 Densités de charge dans les salles (calibrées sur le corpus)

| Technologie | Densité rack/cuve | kW/rack | **kW/m² de data hall** | Contrôle |
|---|---|---|---|---|
| Air (allées confinées, adiabatique) | 1 rack / 25 m² | 35 kW | **1,40** | `MANUEL` §2.2 A → 22 ha = 78,4 MW ✅ |
| Direct-to-Chip (DLC) | 1 rack / 18 m² | 60 kW | **3,33** | `MANUEL` §2.2 B → 22 ha = 186,6 MW ✅ |
| Immersion monophasique | 1 cuve / 12–15 m² | 100–120 kW | **6–8** ⚠️ | Hypothèse (cuve + allées d'exploitation) |
| Immersion diphasique | 1 cuve / 20–25 m² | 250 kW ⚠️ | **10–15** | Hypothèse (cuves DataTank >250 kW, `refroidissement.md` §4) |

> ⚠️ = hypothèse de travail à confirmer chez le fournisseur. Les deux premières lignes sont issues du tableur validé.

### 1.3 Formules de généralisation

```
S_data_halls  = P_IT(kW) / densité(kW/m²)
S_constructible = S_data_halls / 0,73
S_plant_cooling = S_constructible × 0,10
S_SMCC          = S_constructible × 0,05
S_site          = S_constructible / 0,35

Énergie refroidissement = P_IT × (PUE − 1)
Fluides (mouvement)     = Être déduit de Q/(c_p·ΔT) et de la hauteur manométrique
Eau (m³/an)             = Énergie IT (kWh) × WUE (L/kWh) / 1000
L_p(r)                  = L_p(100) − 20·log₁₀(r/100)   [divergence sphérique, ISO 9613-2]
```

---

## 2. CAPACITÉ GLOBALE DE REFROIDISSEMENT — 300 MW

### 2.1 Ce qu'il faut réellement rejeter

| Poste | Puissance | Commentaire |
|---|---|---|
| Chaleur IT | 300,0 MW | ≈ 100 % de la charge IT |
| Pertes électriques internes (onduleurs, transfos, CCF) | +5 à +10 % | À intégrer au plant |
| Apports solaires / parois (hall) | +1 à +3 % | Toiture, vitrages |
| **Capacité installée à prévoir** | **315 à 345 MWth** | Arrondi de conception |
| Redondance N+1 (pompes, dry-coolers, CDU) | +10 à +15 % | Un module de secours plein |

### 2.2 Énergie refroidissement selon la technologie (PUE de `refroidissement.md` §2)

| Technologie | PUE | Surplus MW (300 MW IT) | Surplus GWh/an | Gain vs air 1,40 |
|---|---|---|---|---|
| Air classique | 1,40 – 1,80 | 120 – 240 | 1 051 – 2 102 | référence |
| Air adiabatique (mixte) | 1,30 – 1,39 | 90 – 117 | 788 – 1 025 | −30 à −50 % |
| **Direct-to-Chip** | **1,10 – 1,15** | **30 – 45** | **263 – 394** | **−75 à −85 %** |
| Immersion monophasique | 1,03 – 1,08 | 9 – 24 | 79 – 210 | −90 % |
| Immersion diphasique | 1,02 – 1,04 | 6 – 12 | 53 – 105 | −95 % |

**Règle de généralisation :** sur un site 300 MW, **chaque centième de PUE = 3 MW de raccordement évité = 26,3 GWh/an ≈ 2,6 M€/an** (au prix spot ~100 €/MWh). Passer de l'air (1,40) au DLC (1,12) = **84 MW de raccordement RTE en moins** — souvent le vrai facteur bloquant du raccordement, avant même le coût.

### 2.3 Équipements à installer pour 300 MW

| Technologie | Équipement principal | Nombre (hors N+1) | Nombre avec N+1 |
|---|---|---|---|
| **Air** | CTA/CRAH 20–40 m³/s | **520 – 1 040** | **600 – 1 200** |
| Air | Aérocondenseur 1–2 MW | 150 – 300 | 175 – 345 |
| **DLC** | CDU au sol 1,3 MW (Vertiv XDU) | **231** | **266** |
| DLC | CDU au sol 2,5 MW (Schneider/Motivair) | **120** | **138** |
| DLC | Dry-cooler 1 MW | 300 – 345 | 345 – 400 |
| Immersion mono | Cuves 100–120 kW | 2 500 – 3 000 | +10 % |
| Immersion diphasique | Cuves 250 kW | **1 200** | 1 380 |
| Toutes liquid | Dry-cooler 1 MW | 300 – 345 | 345 – 400 |

*CDU : `refroidissement.md` §1 (1,3 MW/unité Vertiv) et §5 (200 kW → 2,5 MW Schneider).*

### 2.4 Énergie de mouvement des fluides (pleine charge, T_ext = 35 °C)

| Technologie | Fluides volumiques | Pompes/ventilateurs | Justification |
|---|---|---|---|
| Air | Air à 12 K de ΔT : **20 700 m³/s (74,7 Mm³/h)** + tours | **16 – 26 MW** | `ṁ = Q/(c_p·ΔT)` ; fans CTA 500–800 W/(m³/s) |
| DLC | Eau-glycol : 8,3 m³/s à ΔT 10 K | **9 – 15 MW** | Pompes 4,4 MW à 40 mCE (3–6 MW) + fans dry-cooler 6–9 MW |
| Immersion mono | Huile en recirculation (faible Δp) | **7 – 12 MW** | Convection naturelle dominante + fans dry-cooler |
| Immersion diphasique | Changement de phase, pompes minimales | **7 – 11 MW** | `refroidissement.md` §2 : pompes « beaucoup moins » |

> Le gain liquid vient surtout de la **suppression du mouvement d'air en salle** (−10 à −15 MW), pas de la suppression des ventilateurs de rejet extérieur (6–9 MW, incompressibles pour toute technologie à dry-cooler).
> À la moyenne annuelle (free cooling 4–6 mois en France), ces puissances tombent de **40 à 60 %**.

---

## 3. SURFACE DU BÂTIMENT IT + REFROIDISSEMENT

### 3.1 ABAQUE PRINCIPAL — 300 MW

| Technologie | kW/m² | **S data halls** | **S plant refroidissement** | S SMCC | **S constructible** | **S SITE** | Emprise bâtie IT+cool |
|---|---|---|---|---|---|---|---|
| **Air** | 1,40 | **214 300 m²** | **29 400 m²** | 14 700 m² | 293 500 m² | **83,9 ha** | **25,8 ha** |
| **DLC** | 3,33 | **90 100 m²** | **12 300 m²** | 6 200 m² | 123 400 m² | **35,3 ha** | **10,9 ha** |
| **Immersion mono** | 6–8 | **37 500 – 50 000 m²** | **5 100 – 6 900 m²** | 2 600 – 3 400 m² | 51 400 – 68 500 m² | **14,7 – 19,6 ha** | **4,5 – 6,0 ha** |
| **Immersion diphasique** | 10–15 | **20 000 – 30 000 m²** | **2 700 – 4 100 m²** | 1 400 – 2 100 m² | 27 400 – 41 100 m² | **7,8 – 11,7 ha** | **2,7 – 3,6 ha** |

### 3.2 Ratios de généralisation (à réutiliser pour toute puissance)

| Technologie | **m² de data hall / MW** | **ha de site / MW** | Nb de halls de 14 000 m² |
|---|---|---|---|
| Air | **714** | 0,280 | 15 |
| DLC | **300** | 0,118 | 6 – 7 |
| Immersion mono | **143** | 0,056 | 3 |
| Immersion diphasique | **83** | 0,033 | 2 |

### 3.3 Champ de rejet extérieur (dry-cooler / aérocondenseur)

```
Surface ≈ 40 à 60 m² par MW refroidi
Pour 300 MW → 12 000 à 18 000 m² (1,2 à 1,8 ha) au sol
```

*Contrôle : `infrastructure-ia-gpu-souverainete.md` §8.3 → 0,5 ha d'aérocondenseurs pour ~100 MW = 50 m²/MW ✅*

⚠️ **Point de vigilance DLC/immersion :** le coefficient `plant = 0,10 × constructible` ne loge que 12 300 m² (DLC) alors qu'il faut 12 000–18 000 m² de dry-coolers. En DLC, le champ de rejet **dépasse le plant alloué** → l'implanter **en toiture** ou ajouter **+2 à +6 % de surface constructible**. C'est un arbitrage classique : toiture = chère mais pas d'emprise au sol.

### 3.4 Contrôles de cohérence

| Référence | Surface / puissance | Lecture |
|---|---|---|
| Google Saint-Ghislain (`DATACENTER.md`) | 60 ha / 300 MW = **5,0 MW/ha** | Situé **entre air (3,6) et DLC (8,5)** → site mixte/hybride calibré |
| Camp Français, scénario A (`infra` §8.4) | 22 ha / 78,4 MW = 3,6 MW/ha | ✅ Identique à l'abaque air |
| Camp Français, scénario B (`infra` §8.4) | 22 ha / 186,6 MW = 8,5 MW/ha | ✅ Identique à l'abaque DLC |
| Projet Rantigny / Lachelle (`national/RECOUPEMENT.md`) | ~300 MW annoncés | → exiger **35 à 84 ha** selon technologie retenue |

**Règle d'or :** un site 300 MW annoncé sans surface précise est non vérifiable. Exiger systématiquement `S_site ≥ 0,12 ha/MW × P` (liquide) ou `≥ 0,28 ha/MW × P` (air).

---

## 4. BRUIT

### 4.1 Mise en échelle

Ancre du corpus : hyperscale 84 MW → **65–72 dB(A) à 100 m non traité** (`infra` §8.9) ; 50 MW → **110 dB(A) champ proche** (`optimisation-datacenter` §5).

Loi d'échelle : `ΔL = 10·log₁₀(P₂/P₁)` → 84 → 300 MW = ×3,57 = **+5,5 dB**

```
L_p(100 m) non traité, site 300 MW ≈ 70 + 5,5 ≈ 75,5 dB(A)
Modèle : L_p(r) = 75,5 − 20·log₁₀(r/100)
```

### 4.2 Niveaux calculés à 300 MW

| Distance | **Non traité** | Traité −15 dB | Traité −20 dB |
|---|---|---|---|
| 50 m | **81,5 dB(A)** | 66,5 | 61,5 |
| 100 m | **75,5 dB(A)** | 60,5 | 55,5 |
| 200 m | **69,5 dB(A)** | 54,5 | 49,5 |
| 300 m | **66,0 dB(A)** | 51,0 | 46,0 |
| 500 m | **61,5 dB(A)** | 46,5 | 41,5 |
| 800 m | **57,4 dB(A)** | 42,4 | 37,4 |
| 1 000 m | **55,5 dB(A)** | 40,5 | 35,5 |
| 2 000 m | **49,5 dB(A)** | 34,5 | 29,5 |

### 4.3 Ce qu'exige réellement la réglementation

| Seuil | Valeur | Source |
|---|---|---|
| ICPE — limite de propriété | **70 dB(A) jour / 60 dB(A) nuit** | Arrêté préfectoral |
| Émergence régime général | **5 dB(A) jour / 3 dB(A) nuit** | Décret n° 2006-1099 |
| Émergence zone résidentielle (PLU) | **6 dB(A) jour / 4 dB(A) nuit** | `optimisation-datacenter` §5 |
| OMS | 53 dB(A) sur 24 h / 45 dB(A) nuit | Recommandation |

**Règle opérationnelle déduite de la formule d'émergence :**
pour respecter une émergence de 3 dB(A), **le niveau du datacenter seul doit rester ≤ niveau ambiant résiduel**.

```
L_ajout ≤ L_ambiant  (pour émergence ≤ 3 dB)
→ si L_ambiant nuit = 45 dB(A) : le site doit émettre ≤ 45 dB(A) au récepteur
```

### 4.4 Atténuation exigée selon la distance au premier récepteur (ambiant nuit 45 dB(A))

| Distance récepteur | Niveau non traité | **Atténuation requise (émergence 3 dB)** | Faisabilité |
|---|---|---|---|
| 50 m | 81,5 dB(A) | **36,5 dB** | 🔴 Impossible → **recul obligatoire** |
| 100 m | 75,5 dB(A) | **30,5 dB** | 🔴 Hors d'atteinte (< 25 dB réalistes) |
| 200 m | 69,5 dB(A) | **24,5 dB** | 🔴 Très difficile |
| 300 m | 66,0 dB(A) | **21,0 dB** | 🟠 Faisable avec encoffrement lourd |
| 500 m | 61,5 dB(A) | **16,5 dB** | 🟢 Réaliste (traitement standard poussé) |
| 800 m | 57,4 dB(A) | **12,4 dB** | 🟢 Standard |
| 1 000 m | 55,5 dB(A) | **10,5 dB** | 🟢 Standard + modération vitesse |
| 2 000 m | 49,5 dB(A) | **4,5 dB** | 🟢 Modération suffit |

**Conclu :** pour **300 MW non traités, aucune distance < 200 m n'est recevable** ; avec un traitement acoustique de **15–20 dB**, la conformité devient atteignable à **≈ 400–500 m**. En dessous de 300 m, seule la **réduction de capacité** ou le **recul foncier** fonctionnent.

### 4.5 Levers d'atténuation disponibles

| Levier | Gain | Coût / limite |
|---|---|---|
| Encoffrement des dry-coolers / aérocondenseurs | 8 – 15 dB | CAPEX majeur, perte de charge → +énergie |
| Silencieux aérauliques + pièges à son CTA | 5 – 10 dB | Pression statique supplémentaire |
| Réduction de vitesse (variateurs) la nuit | 3 – 6 dB | Faible coût, gain immédiat |
| Merlon de terre végétalisé | 5 – 10 dB (LF) | Seule solution efficace en **infrasons** |
| Ceinture végétale multi-strates | 3 – 5 dB | Espace, temps de croissance |
| Fausses façades / modification de l'effet « bunker » | 3 – 8 dB (côté façade) | `NuisancesSonores.md` §1 (étude CIDB) |
| Réduction du nombre d'unités (N sans N+1 partagé) | −1,5 dB | Compromis disponibilité |

**Alerte infrasons :** les basses fréquences (< 20 Hz) sont **quasi non atténuées par l'air** (α ≈ 0,001 dB/km) et **non mesurées par la réglementation standard (≥ 125 Hz)**. Aucun recul ne protège : il faut traiter **à la source** (silencieux LF, découplage anti-vibration, merlon). → `NuisancesSonores.md` §2.

**Cumul :** toujours additionner avec les sources existantes (ex. autoroute A1 à 65–75 dB(A) Lden sur le site Camp Français) — l'émergence se calcule sur le **niveau total**.

---

## 5. EAU

### 5.1 Consommation annuelle (WUE, ISO 30134-3 — base énergie IT = 2 628 GWh/an)

| Technologie | WUE (L/kWh) | **m³/an** | Piscines olympiques (2 500 m³) | Équiv. habitants (150 m³/hab/an) |
|---|---|---|---|---|
| Tour évaporative classique | 1,5 – 2,5 | **3 940 000 – 6 570 000** | **1 576 – 2 628** | **26 300 – 43 800** |
| **Air adiabatique** (défaut) | 0,3 – 0,8 | **788 000 – 2 102 000** | **315 – 841** | **5 300 – 14 000** |
| Centrale : 0,55 L/kWh | 0,55 | **1 445 000** | **578** | **9 600** |
| **Direct-to-Chip** | 0,05 – 0,15 | **131 000 – 394 000** | **52 – 158** | **880 – 2 630** |
| Immersion (dry-cooler uniquement) | 0 – 0,05 | **0 – 131 000** | **0 – 52** | **0 – 880** |
| **Boucle fermée sèche (dry)** | **0** | **0** | **0** | **0** |

*Formule : `Eau (m³/an) = Énergie IT (MWh) × 1 000 × WUE / 1 000` (`MANUEL` §2.5).*

### 5.2 Point critique : le débit de pointe, pas la moyenne annuelle

```
Moyenne annuelle (adiabatique 1,45 Mm³/an) = 165 m³/h
Facteur estival ×3 à ×5 → DÉBIT DE CONCEPTION ÉTÉ = 500 à 800 m³/h
```

| Dimensionnement | Valeur adiabatique 300 MW | Conséquence |
|---|---|---|
| Adduction / diamètre de tuyau | **500–800 m³/h en juillet** | ≈ **DN 250–300 à 2–3 m/s** |
| Stockage tampon | 2 000 – 5 000 m³ | Lisser les pointes, sécuriser l'été |
| Point de rejet / bassin | ≈ 165 m³/h moyen (continu) | ≈ consommation moyenne d'une **commune de 12 000 hab** |
| Interconnexion | Adduction **+** secours camion-citerne | Si nappe non mobilisable |

⚠️ **Nappe de la Craie (Camp Français)** : nappe < 5 m, déjà sollicitée, pics de remontée en mars → **captage quasi impossible**. Le WUE de 0,55 n'est défendable que si l'eau est **acheminée**, pas prélevée sur place (`infra` §8.7).

### 5.3 Arbitrage eau ↔ énergie

| Option | Eau | Énergie refroidissement (300 MW) | Surface rejet |
|---|---|---|---|
| Évaporative | 6,6 Mm³/an | PUE la plus basse en été, mais **+eau** | la plus petite |
| Adiabatique partielle | 1,45 Mm³/an | bon compromis | moyenne |
| **Dry (boucle fermée)** | **0** | +5 à +15 % vs adiabatique | **+20 à +40 %** de dry-coolers |

**Règle :** la **surface de rejet et l'eau sont un arbitrage direct** — supprimer l'eau (WUE 0) fait grossir le champ de dry-coolers de 20 à 40 %, soit +2 400 à 5 400 m² sur un site 300 MW.

**Le DLC rend le WUE ≈ 0 quasi gratuit :** l'eau sort des serveurs à **45–50 °C** (`refroidissement.md` §2) → un dry-cooler suffit toute l'année en France, sans compresseur, sans évaporation.

---

## 6. FUITE DE CALOPORTEUR

### 6.1 Inventaire de fluide par technologie (300 MW)

| Technologie | Fluide | Charge (L/kW) ⚠️ | **Volume total site** | Conductivité | Risque électrique |
|---|---|---|---|---|---|
| Air (adiabatique) | Eau + traitements | 1 – 2 | **300 – 600 m³** (bassins + tuyauteries) | Élevée | Moyen (CTA) |
| **DLC** | **Eau déionisée + glycol 20–30 %** | 0,5 – 1,5 | **150 – 450 m³** | **Conductrice** 🔴 | **Élevé — sur composants sous tension** |
| Immersion monophasique | Huile PAO / ester biosourcé | 5 – 10 | **1 500 – 3 000 m³** | Diélectrique | Nul |
| Immersion diphasique | HFO (fluoré) | 4 – 8 | **1 200 – 2 400 m³** | Diélectrique | Nul |

⚠️ Hypothèses de charge à valider chez le fournisseur (ordres de grandeur classiques de l'industrie : DLC 0,5–1,5 L/kW ; immersion 5–10 L/kW).

### 6.2 Scénarios de fuite — DLC (le vrai risque, cf. `refroidissement.md` §1 « point noir »)

| Scénario | Volume relâché | Temps avant isolement | Dégât | Prérequis de conception |
|---|---|---|---|---|
| Rupture plaque froide / tuyau rack | **5 – 30 L** | < 10 s (connecteurs anti-goutte QD) | 1 rack, arrêt local | Bac de rétention par armoire, détecteur de fuite sous plancher |
| Rupture manifold de rack | **50 – 300 L** | 10 – 30 s | Allée entière, plancher | Bac de rétention d'allée, plancher étanche |
| **Rupture collecteur de hall** | **15 – 45 m³** | 30 s à 1 min | Hall hors service | ⚠️ Débit ≈ **1,4 m³/s par hall** (50 MW / ΔT 10 K) → valves d'isolement rapides **par zone** |
| Rupture principal plant | **40 – 100 m³** | 1 – 2 min | Site partiellement à l'arrêt | Cuvelage global, vanne automatique amont |

**Dimensionnement du bac de rétention :**
```
V_bac ≥ V boucle de la zone + (débit × temps de manœuvre) + 20 % marge
Exemple hall 50 MW : V_boucle ≈ 15–30 m³ + 1,4 m³/s × 60 s = 84 → bac ≥ 100–120 m³/hall
```

### 6.3 Conséquences à traiter

| Dimension | Constat | Mesure |
|---|---|---|
| **Électrique** | Eau glycolée **conductrice** sur composants sous tension → arc court-circuit (`refroidissement.md` §1) | Détecteur de fuite par zone, coupure rack < 10 s, QD anti-goutte, **double barrière** au CDU (échangeur à plaques = séparation boucles) |
| **Environnemental** | Glycol propylénique : peu toxique, mais **DBO5 très élevée** → ne jamais verser en ruissellement pluvial | Cuvelage étanche des salles, regards à limon, **interdiction de rejet** → enlèvement par prestataire |
| **Opérationnel** | Perte de charge → arrêt des racks servis par la boucle | Redondance N+1 des pompes, boucles segmentées (6 halls indépendants) |
| **Chimique** | Analyse annuelle pH + conductivité pour garder les inhibiteurs actifs (`refroidissement.md` §1) | Boucle d'analyse en continu + rapport annuel |
| **As-tu de maintenance** | Filtres à sédiments à remplacer **tous les 6 à 12 mois** (sinon microcanaux cuivre obstrués) | Stock pièces + accès CDU en allée technique |

### 6.4 Scénarios — immersion

| Technologie | Scénario | Risque dominant | Mesure |
|---|---|---|---|
| Monophasique (Submer, GRC) | Fuite de cuve / extraction serveur | **Pollution sol**, glisse, perte de fluide | Bac de rétention sous chaque cuve ou cuvelage de hall, gants + bacs de manipulation, station d'égouttement (`refroidissement.md` §3) |
| Monophasique | 💰 Valeur du stock | **1 500 – 3 000 m³ × 5–15 €/L ≈ 7 à 45 M€** ⚠️ | Assurance, inventaire fluide, contrat de re-fourniture |
| **Diphasique (LiquidStack)** | Micro-fuite sur joints de couvercle | **Évaporation du fluide HFO → perte financière immédiate + émission atmosphérique** (`refroidissement.md` §3) | Contrôle d'étanchéité continu, condensation rapide avant ouverture, détection de pression |
| Diphasique | Réglementaire | Fluides fluorés surveillés (sous-produits **TFA**), GWP faible mais PFAS sous surveillance | Clause de retrait du fluide, plan de substitution vers eau/huile |

### 6.5 Matrice de synthèse « fuite »

| | **Air** | **DLC** | **Immersion mono** | **Immersion diphasique** |
|---|---|---|---|---|
| Volume en jeu | 300–600 m³ | 150–450 m³ | 1 500–3 000 m³ | 1 200–2 400 m³ |
| Dégât immédiat | ⚠️ Moyen | 🔴 **Élevé (court-circuit)** | 🟠 Sol + logistique | 🔴 **Fluide cher, perte instantanée** |
| Risque riverain | Faible | Faible si cuvelé | Moyen (sol) | Moyen (air) |
| Coût de remplacement fluide | Faible | **~0,15–0,7 M€** | **7–45 M€** | **Très élevé (fluorescents)** |
| Détection | Standard | **Critique** | Standard | **Critique (pression)** |
| Maintenance fluide | Filtres 6–12 mois, pH/an | Filtres 6–12 mois, pH/an | Filtres huile 12–24 mois, huile > 10 ans | Étanchéité couvercle en continu |

---

## 7. SYNTHÈSE MULTICRITÈRE — SITE 300 MW

| Critère | **Air** | **DLC** | **Immersion mono** | **Immersion diphasique** |
|---|---|---|---|---|
| PUE | 1,40 – 1,80 | 1,10 – 1,15 | 1,03 – 1,08 | 1,02 – 1,04 |
| Surplus refroidissement | 120 – 240 MW | **30 – 45 MW** | 9 – 24 MW | 6 – 12 MW |
| Raccordement évité vs air | — | **84 MW** | 111 MW | 117 MW |
| **S data halls** | **214 300 m²** | **90 100 m²** | **37 500–50 000 m²** | **20 000–30 000 m²** |
| **S plant refroidissement** | **29 400 m²** | **12 300 m²** | **5 100–6 900 m²** | **2 700–4 100 m²** |
| **Surface site** | **83,9 ha** | **35,3 ha** | **14,7–19,6 ha** | **7,8–11,7 ha** |
| Emprise IT + cooling | 25,8 ha | 10,9 ha | 4,5–6,0 ha | 2,7–3,6 ha |
| Équipement clé | 600–1 200 CTA | 138–266 CDU | 2 500–3 000 cuves | 1 380 cuves |
| Fluides (mouvement) | 16 – 26 MW | 9 – 15 MW | 7 – 12 MW | 7 – 11 MW |
| **Bruit non traité à 100 m** | 75,5 dB(A) | 75,5 dB(A) | ~71 dB(A) ⁺ | ~71 dB(A) ⁺ |
| Atténuation pour 3 dB à 100 m | **30,5 dB** 🔴 | **30,5 dB** 🔴 | ~26 dB 🔴 | ~26 dB 🔴 |
| **Distance réelle de conformité** (−20 dB) | **≈ 500 m** | **≈ 500 m** | **≈ 350–400 m** | **≈ 350–400 m** |
| **Eau (m³/an)** | **0,79–2,10 M** | **0,13–0,39 M** | **0–0,13 M** | **0–0,13 M** |
| Débit de pointe été (adiab.) | **500–800 m³/h** | 45–225 m³/h | < 75 m³/h | < 75 m³/h |
| **Volume caloporteur** | 300–600 m³ | **150–450 m³** | **1 500–3 000 m³** | **1 200–2 400 m³** |
| Risque de fuite | Faible | 🔴 **Court-circuit** | 🟠 Sol + stock 7–45 M€ | 🔴 **Fluide cher + émission** |
| Verdict 300 MW | 🔴 **Ne scale pas** (surface + CTA) | 🟢 **Standard IA retenu** | 🟢 Compact, poste hydrique nul | 🟠 Performant mais fluide régulé |

> ⁺ Estimation : immersion ⇒ **suppression des ventilateurs de serveurs** (moins de bruit en salle), mais **champ de dry-coolers identique** en extérieur → gain modest de 3 à 5 dB(A) sur le site global, aucun sur la façade des dry-coolers. À confirmer par étude acoustique.

### 7.1 Les 5 règles de généralisation

1. **Surface :** `S_site = P(MW) × 0,28 ha` (air) ou `× 0,12 ha` (liquid) — un site 300 MW annonce facilement **35 à 84 ha** ; vérifier la cohérence annoncée/surface.
2. **Bruit :** à 300 MW, **aucun récepteur < 200 m n'est recevable sans recul** ; avec traitement 15–20 dB, conformité à **≈ 400–500 m** ; sous 300 m, seule la réduction de capacité fonctionne.
3. **Eau :** WUE 0 = +20 à +40 % de surface de dry-coolers ; le **débit de pointe d'été (×3–×5)** conditionne l'adduction, pas la moyenne annuelle.
4. **Fuite :** le risque n'est pas le volume mais la **conductivité** (DLC sur composants sous tension) et la **valeur du stock** (immersion : 7 à 45 M€ de fluide). Cuvelage + isolement par zone obligatoires.
5. **Énergie :** sur 300 MW, **1 centième de PUE = 3 MW de raccordement = 2,6 M€/an** → le PUE devient un critère de **raccordement réseau**, pas seulement de facture.

### 7.2 Points à confirmer (hypothèses marquées ⚠️)

- Densité kW/m² en immersion (mono 6–8, diphasique 10–15) — à valider sur plans fournisseurs.
- Charge en fluide L/kW (DLC 0,5–1,5 ; immersion 5–10).
- Valeur unitaire du fluide d'immersion (5–15 €/L) → impact CAPEX/assurance direct.
- Nombre exact de modules N+1 (redondance retenue : N+1 complet ou N+1 partagé).

---

## 8. RÉFÉRENCES

**Fiches sources du dossier**
- `generalites/refroidissement.md` — 5 acteurs, 4 technologies, fluides, maintenance, PUE
- `generalites/optimisation-datacenter-parametres.md` — §2 PUE, §5 bruit, §9 WUE, §10 chaleur fatale
- `generalites/NuisancesSonores.md` — sources, réglementation, infrasons, ISO 9613-2
- `generalites/DATACENTER.md` — Google Saint-Ghislain, 60 ha / 300 MW
- `infrastructure-ia-gpu-souverainete.md` §8 — modèle calibré 22 ha (78 / 187 MW), eau, bruit
- `MANUEL-dimensionnement-datacenter.md` — coefficients de surface, densités rack, formules WUE
- `generalites/dimensionnement-datacenter-entrainement-frontiere.md` — Colossus 150 → 300 MW
- `generalites/national/RECOUPEMENT.md` — Rantigny / Lachelle ~300 MW

**Normes citées**
- ISO 30134-2 (PUE), ISO 30134-3 (WUE), ISO 9613-2 (propagation acoustique)
- Décret n° 2006-1099 (bruit de voisinage), régime ICPE (70/60 dB(A) en limite de propriété)

---

*Document de travail — septembre 2026. Abaque extrapolé depuis `refroidissement.md` et calibré sur le modèle 22 ha ; hypothèses marquées ⚠️ à confirmer auprès des fabricants avant usage réglementaire.*
