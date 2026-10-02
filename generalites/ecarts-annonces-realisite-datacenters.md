# ÉCARTS ENTRE ANNONCES ET RÉALITÉ — DATACENTERS : EAU, ÉLECTRICITÉ, EMPLOIS, BRUIT

**Objet :** recenser, **cas par cas et avec source URL**, les datacenters dont les annonces initiales (communiqués, accords de développement, promesses d'investisseurs, études d'impact) contredisent la réalité constatée une fois l'exploitation lancée, sur **4 dimensions : eau, électricité, emploi, nuisances sonores**.
**Intrants :** recherches web externes (presse, statistiques nationales, rapports d'audit, décisions administratives) + corpus du dossier (`generalites/NuisancesSonores.md`, `dimensionnement-camp-francais.md`, `rapport-moyens-opposition.md`).
**Méthode :** chaque chiffre est assorti de sa source ; les chiffres non retrouvés sont marqués **[à confirmer]** et ne doivent pas être repris dans un argumentaire. Séparation stricte **fait sourcé / déduction** (§1.3).
**Date :** octobre 2026 — document de travail.

---

## TABLE DES MATIÈRES

1. [Méthode et limites de lecture](#1-méthode-et-limites-de-lecture)
2. [Eau](#2-eau)
3. [Électricité](#3-électricité)
4. [Emplois](#4-emplois)
5. [Nuisances sonores](#5-nuisances-sonores)
6. [Synthèse croisée — les quatre patterns récurrents](#6-synthèse-croisée--les-quatre-patterns-récurrents)
7. [Application au Camp Français — ce qu'il faut exiger](#7-application-au-camp-français--ce-quil-faut-exiger)
8. [Points à confirmer](#8-points-à-confirmer)
9. [Références](#9-références)

---

## 1. MÉTHODE ET LIMITES DE LECTURE

### 1.1 Définition de l'écart

| Type d'écart | Définition | Exemple du présent document |
|---|---|---|
| **A — Non-divulgation** | L'annonce initiale est chiffrée, la donnée réelle n'est jamais publiée (secret commercial, refus d'autorité) | The Dalles (Oregon), Meta Richland Parish (Louisiane) |
| **B — Surestimation** | Le chiffre réel est mesuré/publié et inférieur à l'annonce | Seine-Saint-Denis 1 600 → 500 postes ; Géorgie 5 471 → 1 641 emplois |
| **C — Dépassement** | Le chiffre réel est **supérieur** à l'annonce (impact négatif : consommation, part de marché) | Irlande 5 % → 23 % du mix électrique ; The Dalles 12 % → ~40 % de l'eau de la ville |
| **D — Divergence de mesure** | L'autorité et les riverains mesurent, et aboutissent à des valeurs inconciliables | Loudoun County (Virginie) : 55 dB norme / 70-80 dB relevés riverains / « jamais au-dessus » côté comté |
| **E — Glissement** | L'écart porte sur le périmètre ou la date, pas sur le nombre : annonce 2017, réalité 2026, périmètre modifié | Meta Louisiana : 2 GW → 5 GW, 500 → 1 000 emplois annoncés, données réelles toujours classées |

### 1.2 Niveau de preuve retenu

| Niveau | Nature | Poids dans l'argumentaire |
|---|---|---|
| **S1** | Statistique nationale officielle ou audit public (CSO Irlande, JLARC Virginie, audit Géorgie, CSO France) | **Utilisable tel quel** |
| **S2** | Presse d'investigation avec chiffres datés et rattachés à une source primaire (Oregonian, Reuters, AP, AFP, Sud Ouest) | Utilisable avec la source citée |
| **S3** | Déclaration d'un acteur (communiqué opérateur, déclaration d'élus, ONG) | À attribuer : « selon X » |
| **S4** | Mesure non normalisée (application smartphone, mesure associative) | **Jamais seule** — à réutiliser comme preuve de divergence (type D), pas comme valeur |

### 1.3 Limites de comparaison (à rappeler dans tout usage)

1. **Emplois :** « emplois directs », « emplois soutenus », « emplois créés pendant la construction » et « emplois permanents » sont des périmètres distincts. Les annonces additionnent souvent les trois, les bilans ne comptent que le dernier.
2. **Eau :** un WUE (L/kWh) ne se compare pas à un volume total ; un volume total ne se compare pas à un % de prélèvement municipal (poste le plus contraignant pour la collectivité).
3. **Bruit :** dB(A) à quelle distance, quel journal de mesure, quelle période ? Les valeurs du §5 ne sont **pas** interchangeables sans précision du protocole.
4. **Électricité :** « demande de raccordement », « capacité autorisée » et « énergie réellement consommée » sont trois grandeurs différentes (§3, cas WRI et xAI).

---

## 2. EAU

### 2.1 Cas documentés

| Site (opérateur) | Annonce | Réalité constatée | Type d'écart | Source (niveau) |
|---|---|---|---|---|
| **The Dalles, Oregon (Google)** | Consommation non communiquée : Google a invoqué le **secret commercial** pour refuser la publication | **12 %** de l'eau de la ville (2012) → **29 %** (2021, 355 M gallons) → **~1/3** (2024) → **~550 M gallons en 2025 ≈ 40 % de l'eau de la ville**. Google s'engage sur un stockage de 29 M$ « suffisant » | **A + C** | The Oregonian/OregonLive, 06/04/2026 [R1] (S2) |
| **Cerrillos, Chili (Google)** | ≈ **7,6 millions de litres/jour** d'eau potable prélevés sur une nappe en sécheresse depuis 10 ans | Autorisation **partiellement révoquée en février 2024** ; projet redessiné autour d'un refroidissement à air | **E** (le projet annoncé n'a pas survécu à l'instruction) | Reuters, 27/02/2024 [R2] (S2) |
| **Mesa, Arizona (Google)** | Accord de développement 2019 : **~1 M gal/j au lancement → ~4 M gal/j à plein** (ordre de grandeur d'une ville de 500 000 hab. à terme) | Aucune publication de la consommation réelle ; **poussée de résistance locale en 2021 en pleine sécheresse** | **A** | Accord de développement (compute-atlas) [R3] ; NBC News, 2021 [R4] (S2) |
| **Prineville, Oregon (Meta/Facebook)** — *contre-exemple* | Les sociétés annonçaient **800 gal/min** avant implantation | Facebook ne contracte que **100 gal/min**, soit **4,1 M gallons/an (2012)** pour une ville qui en consomme 495 M ; Meta : **117,5 M gal (2020)** sur un campus à terme de 4,6 M pi² | **B (sens inverse)** — annonce haute, réalité basse | The Bulletin / Deschutes River Alliance [R5] ; East Oregonian, 10/12/2021 [R6] (S2) |
| **Prineville, Oregon (Apple)** | Apple finance un stockage aquifère de 9 M$ pour sécuriser ses besoins | **27 M gallons (2016)** pour le seul 1er datacenter ≈ **près de 10 % de la production annuelle de la ville** (600 M gal) | **A** (le volume réel n'est pas déclaré à date récente) | AP / Seattle Times, 19/12/2018 [R7] (S2) |
| **Wissous / Pennes-Mirabeau (CyrusOne / Amazon / Telehouse) — France** | CyrusOne, opérant pour Amazon : consommation d'eau **« dérisoire », limitée à 850 m³/an**, soit « la consommation de sept habitations », « sans rejet extérieur » | **Bataille des chiffres** entre opposants et porteur de projet : aucune mesure contradictoire rendue publique ; l'urbaniste Cécile Diguet signale des **forages « plus ou moins déclarés »** en Essonne | **A** | Reporterre, 30/01/2024 [R42] (S2/S3) |
| **Aragón (Espagne) — AWS** | Trois datacenters AWS dans une des régions **les plus sèches d'Europe** | AWS reconnaît **jusqu'à 53,9 M litres/an par centre** ; collectif *Tu Nube Seca Mi Río* (« Ton nuage sèche ma rivière ») alors que des agriculteurs cherchent une indemnisation sécheresse | **C** (chiffre avancé puis débattu, pas révisé à la baisse) | EU Perspectives, 08/2026 [R50] (S2/S3) |
| **Toledo (Espagne) — Meta** | Projet de 1,1 Md$ | **>600 M litres/an** annoncés dans une zone **à risque de sécheresse** | **C** | DCD, 21/01/2025 [R49] (S2) |
| **Ordres de grandeur France / monde** *(repères, pas un écart)* | Moyennes publiées pour situer : hyperscale **760 M L/an ≈ une ville de 12 000 hab.** ; petit/moyen **25 M L/an ≈ 500 hab.** ; **25,5 M L/MW/an** (étude *Nature*) ; **45 % des datacenters mondiaux en bassins à risque** | Utilisables comme **bornes de raisonnement** quand un opérateur ne publie rien | — | Guide Ville de Demain, 04/2026 [R44] ; blog.datacenter-paris, 16/04/2026 [R53] (S3) |
| **Google (chiffres groupe)** | Communication « water positive » | Rapport environnemental : **28 milliards de litres prélevés/an**, dont **2/3 d'eau potable**, **+82 % entre 2018 et 2022** — Google a d'abord **refusé de fournir des chiffres site par site** aux journalistes | **C** (publication du groupe, **pas par site**) | Reporterre, 30/01/2024 [R42] (S2) ; LeMagIT, 22/12/2021 [R54] (S2) |

### 2.2 Ce que l'on retient (eau)

- **L'absence de publication est la règle, pas l'exception.** En Oregon, il n'existe *« aucune donnée agrégée sur la consommation d'eau des datacenters »* (document de travail de l'État, 27/03/2026) [R8] (S1) — la donnée n'existe pas, donc nul ne peut contester. **En France, c'est pareil** : la publication « reste soumise au bon vouloir des industriels », et des forages sont signalés « plus ou moins déclarés » en Essonne [R42] (S2).
- **Le curseur municipal est le bon indicateur** : un volume (M gallons) ne dit rien ; le **% de l'eau produite par la commune** dit tout (The Dalles : 12 % → 40 %).
- **Le contrepoids n'existe pas automatiquement** : Apple et Meta à Prineville ont dû financer des infrastructures de stockage/recharge aquifère *parce que* la ville était au plafond — c'est le mécanisme à exiger contractuellement.
- **Le cas chilien montre la fragilité des annonces d'eau** : quand l'autorité refuse, l'opérateur change de technologie. La promesse initiale n'était donc pas contraignante.
- **Repères français à défaut de données par site** : hyperscale ≈ **760 M L/an ≈ ville de 12 000 habitants** ; petit/moyen datacenter ≈ **25 M L/an ≈ 500 habitants** [R44] (S3) ; et un poste distinct à ne pas confondre avec le refroidissement : **la fabrication des puces** — selon l'hydroclimatologue Florence Habets (ENS/CNRS), les usines de microprocesseurs en Isère prélèvent « des millions de m³ d'eau chaque année » [R43] (S3).

---

## 3. ÉLECTRICITÉ

### 3.1 Cas documentés

| Site / territoire | Annonce / cadre affiché | Réalité constatée | Type d'écart | Source (niveau) |
|---|---|---|---|---|
| **Irlande (CSO)** | Politique de raccordement encadrée pour **limiter** la part des datacenters | Part des datacenters dans l'électricité comptée : **5 % (2015) → 21 % (2023) → 22 % (2024) → 23 % (2025)**, soit **7 663 GWh en 2025 (+10 % en un an)** | **C** | CSO Ireland, release 07/07/2026 [R9] (S1) |
| **États-Unis — files d'attente (WRI)** | Les demandes de raccordement reflètent le besoin réel | Requêtes **spéculatives et dupliquées** (« double counting ») auprès des DSO/TSO : une part de ces MW « fantômes » ne sera **jamais construite**, faussant les prévisions de charge de l'ensemble du réseau | **B** (surévaluation des besoins) | WRI Insights [R10] (S1) |
| **Virginie (JLARC)** | L'industrie soutient la croissance sans impact majeur sur les ménages | Demande électrique **+180 % d'ici 2035/2040** ; **+37 $/mois** sur la facture résidentielle moyenne d'ici 2040 ; exonération fiscale **928 M$ (exercice 2023) → 1,9 Md$ (exercice 2025)** | **C** | JLARC Report 598 [R11] (S1) ; Governing [R12] (S2) |
| **Memphis / Southaven (xAI Colossus)** | Raccordement approuvé par la TVA : **150 MW** | **69 turbines à combustion** installées (3 → 18 → 27 → 57 → 69), tirage d'environ **2 GW de puissance gaz**, soit ~13× la capacité de raccordement approuvée — l'écart est absorbé **hors réseau** | **C + A** | Bloomberg Graphics [R13] ; Daily Helmsman [R14] (S2) |
| **Richland Parish, Louisiane (Meta + Entergy)** | 3 turbines CC de **2 260 MW** (déc. 2024) ; « Meta paie l'intégralité des coûts » ; **>2 Md$ d'économies** pour les clients | **7 centrales gaz supplémentaires** mises en accélération réglementaire (avril 2026), puis projet porté à **5 GW** (juillet 2026) ; un rapport-conseil du PSC estime que **les résidents subventionnent une partie** de la consommation ; **550 M$ de ligne de transport** portés par les clients ; **Meta a refusé de communiquer consommation et emploi réels** (vote du PSC, août 2026) | **A + E + C** | Entergy, 06/12/2024 [R15] ; Fox8/Louisiana, 15/04/2026 [R16] ; Sierra Club / Wired [R17] ; NOLA.com, 12/08/2026 [R18] (S2) |
| **Pays-Bas — Amsterdam / Haarlemmermeer** | Moratoire communal (2019, levé en 2020 avec des exigences d'efficacité : PUE 1,2 neuf / 1,3 existant), moratoire national hyperscale de 9 mois (fév. 2022, seuils **>10 ha et >70 MW**), nouvelles restrictions d'Amsterdam en décembre 2023 | **Contournement par découpage** : projet Microsoft/Pure DC (3 tours de 85 m) autorisé car **chaque tour isolée passe sous le seuil hyperscale** alors que l'ensemble consomme **78 MW** ; le nombre total de datacenters des Pays-Bas est **inférieur en 2025 (187) à 2019 (189)** — le moratoire a déplacé la demande, pas réduit le besoin | **D + E** | Dutch Brief, 16/05/2026 [R46] ; DCD, 18/09/2026 [R45] ; DCD, 17/02/2022 [R48] (S2) |
| **Amsterdam-Zuidoost (Pays-Bas) — Equinix** | Permis de construire accordé : **4 tours de 60 m, 80 MW de raccordement, 779 GWh/an** une fois complet | **Le réseau ne suit pas** : les sous-stations TenneT nécessaires ne sont **pas attendues avant 2036** — « l'autorisation administrative précède largement la réalité physique du raccordement » | **E** | DCmag, 09/07/2026 [R47] (S2) |
| **Allemagne — stratégie nationale (18/03/2026)** | Capacité **×2 en 5 ans**, **×4 pour l'IA** (gouvernement fédéral) | Étude citée par les mêmes ministères : la capacité **va de toute façon tripler** (**5 000 à 5 500 MW**) sans aide supplémentaire — l'annonce décrit une trajectoire déjà engagée | **B** (surestimation du besoin d'intervention publique) | Berlin Gazette, 09/07/2026 [R51] (S3) |
| **Espagne / Union européenne** | Encadrement : nouveau décret espagnol — **1 MW renouvelable construit dans les 18 mois par MW de demande supplémentaire**, sous peine de perdre le raccordement ; échelle de durabilité UE (étiquetage dès **15/08/2027**) | Le cadre répond à un constat de l'UE : les datacenters consomment **~3 % de l'électricité de l'Union** et cette part est attendue en hausse ; jusqu'à présent l'UE se limite au **reporting et à l'étiquetage, sans objectif énergétique contraignant** | **C** (part en hausse) + limite de l'engagement | EU Perspectives, 08/2026 [R50] (S1/S2) |
| **CNDCP — Pacte eau européen** | **74 opérateurs** (AWS, Google, Equinix, CyrusOne…) s'engagent à descendre à **0,4 L/kWh (WUE) d'ici 2040** | Engagement **volontaire** : la source ne mentionne ni sanction ni obligation de publication **site par site** → l'atteinte de l'objectif n'est pas vérifiable par un tiers | **A** (mesure non produite) | DCD [R52] ; LeMagIT, 22/12/2021 [R54] (S2/S3) |

### 3.2 Ce que l'on retient (électricité)

- **Trois grandeurs, trois écart-types :** demande déposée (surestimée, WRI) < capacité autorisée (trompeuse, xAI : 150 MW) < consommation réelle (non publiée, Louisiane).
- **Le réseau n'est pas la seule voie** : quand le raccordement est plafonné, l'opérateur peut construire sa production *in situ* (xAI : 69 turbines). Le plafond Enedis d'un territoire n'est donc **pas** un garant de l'impact réel — c'est un garde-fou seulement si le régime ICPE/turbines est lui-même encadré.
- **Le « client modèle » devient un coût socialisé** : le motif du bas prix promis (Louisiane, Virginie) est systématiquement relié à une facture résidentielle en hausse côté contrôleur (JLARC : +37 $/mois ; PSC : subvention indirecte).

---

## 4. EMPLOIS

### 4.1 Cas documentés

| Site / territoire | Annonce | Réalité constatée | Écart | Source (niveau) |
|---|---|---|---|---|
| **Seine-Saint-Denis (FR)** | **1 600 postes annoncés** par les promoteurs | **500 seulement auraient été créés** — sénateur David Ros (PS, Essonne), auteur d'une proposition de loi : les opérateurs « tournent les chiffres de manière assez utile » | **−69 %** | Sud Ouest / AFP, 01/06/2026 [R19] (S2) |
| **Île-de-France — densité d'emploi** | Le datacenter serait un site d'emploi | **15 à 20 salariés** pour ce qu'un entrepôt logistique emploie à **300-400** à emprise équivalente ; **1 emploi par tranche de 24 M€** d'investissement (Loup Cellard) ; La Courneuve : **700 emplois (usine Eurocopter) → 36** pour la même emprise | **B** | Sud Ouest [R19] ; La Dauphiné, 04/06/2026 [R20] (S2) |
| **France — bilan national** | **93 Md€** annoncés au sommet *Choose France* (juin 2026) pour **15 000 emplois** ; filière : **50 000 emplois directs et indirects pour 300 centres** (rapport du Sénat, févr. 2026) | Ratios affichés par l'annonce elle-même : **6,2 M€/emploi** (Choose France) et **167 M€/centre** (filière) — aucun bilan d'effectifs réels publié à ce stade | **A** (bilan non produit) | La Dauphiné [R20] ; Sud Ouest [R19] (S2/S3) |
| **Géorgie (audit étatique)** | **5 471 emplois** promis contre aides fiscales | **1 641 emplois réellement recensés**, soit **−70 %** ; **289 000 $ d'exonérations par emploi créé** | **−70 %** | Audit de l'État de Géorgie [R21] (S1) |
| **Virginie (JLARC / Governing)** | « 74 000 emplois soutenus » par l'industrie (2023) | **~50 emplois par facilité** (typique) ; **1 610 emplois en exercice 2025** pour **1,9 Md$** d'exonérations = **1,2 M$/emploi** | **B** | JLARC [R11] ; Governing [R12] (S1/S2) |
| **États-Unis (Brookings, 10/08/2026)** | L'emploi local est le bénéfice principal | Création d'emplois **surestimée d'un facteur 3** ; **100-200 emplois permanents par comté**, concentrés dans 10-20 % des comtés ; **aucun effet mesurable sur les salaires médians** ; **+2 à +5 %** sur les prix de l'immobilier résidentiel | **B (×3)** | Brookings [R22] (S1) |
| **Orangeburg, NY (JPMorgan)** | Bâtiment promettant **5 emplois** | **1 seul emploi créé** pour **77 M$** d'exonération fiscale ; Genesee County : **11 M$/emploi** ; Virginie : « plus d'1 Md$ → 150 emplois » | **B** | syracuse.com / audit [R23] (S1/S2) |
| **Luleå, Suède (Meta/Facebook)** | Rapport Business Sweden : **30 000 emplois** induits | Enquête Yle : **56 personnes en 2020**, **~90 aujourd'hui** | **−99,7 %** | Nordic Labour Journal / Yle [R24] (S2) |
| **Memphis, Tennessee (xAI)** | **300 emplois** annoncés (2024) | **32 postes** publiés | **−89 %** | Memphis Flyer [R25] (S2) |
| **Richland Parish, Louisiane (Meta)** | **500 emplois** à l'exploitation (Sierra Club citant Meta) → portés à **1 000 postes permanents** avec l'extension à 5 GW (juil. 2026) ; Entergy annonce **44 emplois permanents** pour ses propres centrales | **Effectif réel non communiqué** : le PSC a **refusé d'exiger à Meta de dévoiler le nombre d'emplois** et sa consommation (vote partisan, août 2026) | **A** | Sierra Club [R17] ; WAFB, 13/07/2026 [R26] ; NOLA.com, 12/08/2026 [R18] (S2) |
| **Fouju, France (campus IA MGX/Mistral/Nvidia)** | **300 à 500 emplois** pour la phase 1 (livraison 2028) | Opposition locale (FNE 77) : « la valeur économique du projet est discutable » ; **613 groupes électrogènes** et 680 circuits de refroidissement comme impacts avancés | **[à suivre]** | AFP / France 24, 05/06/2026 [R27] (S2/S3) |
| **Rantigny, Oise (SCI Alyssa / Realwave Group)** | Dossier d'enquête publique : projet estimé **>4 Md€**, **~100 emplois directs** ; projet jumeau à Lachelle : **150 emplois directs annoncés** | **Porteur de projet opaque** : SCI Alyssa → Realwave Group, SAS parisienne créée le **06/11/2024 au capital de 999 €** ; **l'exploitant final reste inconnu** (« se présentera quand le permis sera purgé de recours ») ; **300 habitants sur 2 524** à la réunion du 19/08/2026 | **A** (aucun engagement opposable : ni exploitant, ni bilan possible) | Parlons Business, 26/08/2026 [R37] (S2) |
| **Châteauroux / Étrechet, Indre (Google)** | **8 à 10 bâtiments sur 195 ha** ; **200 emplois** avancés ; chaleur fatale « redistribuée à la filière agricole (serres) » (maire) ; promesse de vente liant la collectivité jusqu'au **05/07/2030** | Opposition : « **mirage des promesses de création d'emplois** » (Cyrielle Chatelain, groupe écologiste à l'Assemblée) ; consommation électrique avancée **≈ celle du département de l'Indre** ; **200 manifestants** le 30/06/2026 ; le maire reconnaît que Google « ne créera pas 5 000 emplois » ; travaux pas avant **2029** | **A** (promesse non contractualisée, bilan impossible avant 2029+) | France 3, 29/05/2026 [R38] et 01/07/2026 [R39] ; Le Monde, 30/05/2026 [R40] (S2) |
| **Les Pennes-Mirabeau, B.-d.-R. (Telehouse)** | Permis de construire accordé en **février 2026** (avis MRAe du dossier, voir `README` §PDF) | **« Une quinzaine [d'emplois] probablement »** ; 18 mois d'excavation de **150 000 t de roche** ; l'ARS répond aux opposants que le bassin de l'étang de Berre « est déjà fortement pollué » ; recours de la commune de Saint-Victoret déposé le **18/04/2026** | **—** (annonce basse, pas encore d'écart mesurable) | France 3, 19/04/2026 [R41] (S2/S3) |
| **Lleida, Catalogne (Espagne)** | Le secteur promet des emplois qualifiés et un « ancrage industriel » | **Première ville espagnole à interdire les datacenters** (janv. 2025) : maire Fèlix Larrosa — « ils ne créent pas assez d'emplois qualifiés et ne contribuent pas à l'économie locale » ; refus de changer la destination d'un sol rural acheté par une entreprise ; le consultant Colliers qualifie ces arguments de « désinformation » | **B** (bilan municipal vs promesse sectorielle) | DCD, 21/01/2025 [R49] (S2/S3) |

### 4.2 Ce que l'on retient (emplois)

1. **Le taux d'écart observé va de −69 % (Seine-Saint-Denis) à −99,7 % (Luleå)** ; l'audit d'État le plus favorable (Géorgie) constate encore **−70 %**.
2. **Le ratio opposable à une collectivité est simple et documenté** : 15-20 emplois par site (Cellard), ~50 emplois par facilité (JLARC), **1 emploi / 24 M€** (Cellard), **1 emploi / 11 à 77 M$** d'aides (NY).
3. **La qualité d'emploi est l'argument de repli de l'industrie** (Telehouse : « dix fois moins d'emplois qu'un entrepôt, dix fois mieux en qualité », 80 % de CDI selon le sénateur Ros) — argument recevable, mais **sans effet sur la quantité annoncée**.
4. **Le schéma est toujours le même** : promesse chiffrée avant autorisation → donnée réelle indisponible pendant 3 à 5 ans → bilan produit par un tiers (audit, presse, parlement) et jamais par l'opérateur.
5. **L'écart devient un fait politique** : au moins **10 villes** (dont Marseille, Bordeaux, Le Bourget) portaient des candidatures municipales opposées aux datacenters en mars 2026, motivées par « pollution, chaleur et manque d'emploi » [R35] ; les collectifs de riverains se structurent à l'échelle nationale [R34]. L'écart annonce/réalité n'est plus un débat technique, c'est un argument électoral.

---

## 5. NUISANCES SONORES

### 5.1 Cas documentés

| Site | Annonce / cadre applicable | Réalité constatée | Type d'écart | Source (niveau) |
|---|---|---|---|---|
| **Ashburn, Virginie (CloudHQ)** | Projets d'implantation en zone d'activité, impacts jugés maîtrisés | **Relevé à 90 dB(A)** (application de mesure, mars 2026) par des riverains à plusieurs miles du site ; plaintes formelles | **D** (mesure S4 : valeur indicative, divergence avérée) | NBC News / News4, 23/03/2026 [R28] (S2/S4) |
| **Loudoun County, Virginie (Vantage II)** | Ordonnance du comté : **55 dB(A)** | Riverains : **70-80 dB(A)** avec des turbines ; **les relevés du comté « ne dépassent jamais » le seuil** — deux protocoles, deux conclusions inconciliables ; procédure contentieuse ouverte | **D** | Washingtonian, 02/10/2025 [R29] (S2/S4) |
| **Memphis / Southaven (xAI)** | Respect de l'ordonnance bruit de la municipalité | Recours de l'**NAACP** et plainte pour **bruit continu de type « moteur de jet »** ; action en justice pour manquement à l'ordonnance ; l'installation s'est étendue de 3 à **69 turbines** | **C + B** | WMC TV (recours NAACP) [R30] ; Bloomberg [R13] (S2) |
| **Wissous, Essonne (CyrusOne PAR1)** | Dossier ICPE en enquête publique 2021 ; autorisation d'exploitation ; expansion Phase 2 → **49,5 MW**, Phase 3 → **60 MW** | Contentieux engagé **depuis 2021** par *Wissous Notre Ville*, France Nature Environnement et Data for Good au titre du **bruit et des chaleurs** ; **la Cour administrative d'appel de Versailles a autorisé la poursuite de l'expansion en avril 2026** ; les élus redoutent **2 lignes 225 kV** passant à proximité des habitations | **E** (périmètre croît malgré le contentieux) | Courthouse News, 06/06/2026 [R31] (S2) ; fiche projet CyrusOne [R32] (S3) |
| **Fouju, Essonne (campus IA)** | Dossier d'enquête publique | **613 groupes électrogènes de secours** à essais réguliers et **680 circuits de refroidissement** cités par l'opposition comme sources de bruit/pollution ; pas de réemploi de chaleur annoncé | **A** | AFP / France 24, 05/06/2026 [R27] (S3) |
| **Rantigny, Oise (SCI Alyssa / Realwave)** | Réunion publique du 19/08/2026 (300 personnes, 1 habitant sur 8) | Titre même de la réunion rapporté par la presse : **« Vous allez nous mettre un radiateur qui fait du bruit ! »** — l'objet du débat est la **chaleur fatale + bruit** du groupe de refroidissement ; aucune étude acoustique contradictoire rendue publique à ce stade | **A** | Parlons Business, 26/08/2026 [R37] (S2) |
| **Les Pennes-Mirabeau / Saint-Victoret, B.-d.-R. (Telehouse)** | Permis accordé fév. 2026, projet présenté comme conforme | Nuisances alléguées : **18 mois de terrassement (150 000 t de roche)**, chaleur fatale, risques sanitaires ; réponse de l'ARS citée par les opposants : *« ici vous êtes déjà fortement pollués, donc un peu plus, un peu moins… »* ; recours déposé le **18/04/2026** | **D** (les autorités sanitaires ne contestent pas l'impact, elles le relativisent) | France 3, 19/04/2026 [R41] (S2/S3) |
| **Référence technique (France)** | Seuils applicables : **70 dB(A) de jour / 60 dB(A) de nuit en limite de propriété** (ICPE) et **émergence 5 dB(A) jour / 3 dB(A) nuit** (art. R.1336-5) | Modélisation du dossier : sans traitement acoustique, **~70 dB(A) chez le riverain à 100 m** pour un hyperscale ; les façades rayonnantes dégradent autant que les équipements de toiture | — (norme, pas un écart) | `generalites/NuisancesSonores.md` [R33] (S3) |

### 5.2 Ce que l'on retient (bruit)

- **Il n'existe aucun cas dans le corpus où l'opérateur a publié des mesures contestées par personne.** Le seul chiffre « dur » du côté riverain (90 dB) vient d'une **application grand public (S4)** ; le seul chiffre « dur » du côté autorité (jamais au-dessus de 55 dB) vient du **propriétaire du référentiel**. L'écart est donc d'abord **un écart de protocole**.
- **Conséquence pratique : la preuve doit être produite avant l'exploitation**, par un tiers désigné communément (mesure de référence ISO 1996-2, point en limite de propriété, jour + nuit), sinon aucun des deux camps ne pourra jamais prouver son chiffre.
- **Le bruit industriel apparaît quand la puissance augmente** : les trois cas US (CloudHQ, Vantage, xAI) sont des sites dont la capacité a été **étendue après la première autorisation** — c'est le mécanisme à surveiller au Camp Français (phases).

---

## 6. SYNTHÈSE CROISÉE — LES QUATRE PATTERNS RÉCURRENTS

### 6.1 Grille de lecture

| # | Pattern | Mécanisme | Dimension(s) | Exemple type |
|---|---|---|---|---|
| **P1** | **Annonce chiffrée, mesure jamais produite** | Secret commercial / refus d'une autorité / obligation inexistante | Eau, Emplois, Électricité | The Dalles ; Meta Louisiane ; Oregon (« aucune donnée agrégée ») |
| **P2** | **Promesse pluriannuelle non contractualisée** | Communiqué d'accord de développement sans clause de résultat ni clause de retour d'aides | Emplois, Eau | Géorgie (−70 %) ; Seine-Saint-Denis (−69 %) ; Mesa (M gal/j) |
| **P3** | **Extension progressive post-autorisation** | Phases successives, ajouts de turbines/salles, chaque phase présentée comme « nouvelle » | Bruit, Électricité, Eau | xAI (3 → 69 turbines) ; CyrusOne (27 → 60 MW) ; Loudoun |
| **P4** | **Divergence de protocole de mesure** | Autorité et riverains ne mesurent pas de la même manière ; la preuve arrive après l'exploitation | Bruit, Électricité | Loudoun (55 vs 70-80 dB) ; files de raccordement (WRI) |

### 6.2 Ce qui distingue les rares cas « vert »

| Site | Pourquoi l'écart est faible | Ce qui a fait la différence |
|---|---|---|
| **Meta/Apple — Prineville (eau)** | Volume réel publié chaque année ; recharge aquifère financée | Publication volontaire de la WUE + obligation de la ville au plafond |
| **CSO Irlande (électricité)** | Statistique publique annuelle depuis 2015 | **Obligation légale de comptage et de publication** — l'annoncé est vérifiable |

→ **Le facteur déterminant n'est pas la bonne volonté de l'opérateur : c'est l'obligation de publication.**

### 6.3 Lecture France / Europe : les écarts sont en amont

| Observation | Ce qu'elle implique | Sources |
|---|---|---|
| **Peu de sites français sont en exploitation pleine** : Google Châteauroux (travaux pas avant 2029), Fouju (phase 1 en 2028), Rantigny (permis non purgé) | En France, l'écart n'est **pas encore mesurable** : on est dans le **P1 / P2** (promesse non contractualisée, bilan impossible), pas dans le **B** (surestimation prouvée) | [R38] [R39] [R27] [R37] |
| **Le seul écart français chiffré est celui de la Seine-Saint-Denis** (1 600 → 500 postes), établi par un élu, pas par un organisme public | Il manque en France **un équivalent de l'audit de Géorgie ou du JLARC** : personne ne produit de bilan opposable | [R19] vs [R21] [R11] |
| **Les Pays-Bas montrent que l'encadrement crée ses propres écarts** : moratoires nationaux + découpage en tours sous le seuil → le contournement est structurel | Exiger un **seuil de puissance par site agrégé**, pas par bâtiment | [R46] [R47] [R45] |
| **L'Espagne et l'UE traitent le problème par la réglementation** (1 MW renouvelable par MW de demande ; étiquetage UE 2027) ; l'Allemagne par l'annonce de capacité | Trois réponses différentes au même diagnostic : **la donnée manquante partout** | [R50] [R51] |
| **Les engagements sectoriels européux sont volontaires** (Pacte eau CNDCP : 0,4 L/kWh en 2040, 74 opérateurs) | Un objectif sans obligation de mesure site par site **ne produit pas d'écart vérifiable — il produit du non-savoir** | [R52] [R54] |

---

## 7. APPLICATION AU CAMP FRANÇAIS — CE QU'IL FAUT EXIGER

### 7.1 Ce que le dossier MEL permet déjà de caler (rappel)

| Poste | Valeur du dossier | Source interne |
|---|---|---|
| Raccordement | **40 MVA (≈ 38 MW actifs)** pour **l'ensemble des 130 ha** | `sources/mel/lettre d'engagement enedis.md`, art. 2 |
| Emploi au ratio du MANUEL | **1 emploi / 6 MW** → ≈ **6 emplois directs** si tout le 40 MVA partait au datacenter | `MANUEL-dimensionnement-datacenter.md` |
| Bruit applicable | 70/60 dB(A) ICPE + émergence 5/3 dB(A) | `generalites/NuisancesSonores.md` |
| Horizon | **2030** (lettre d'engagement), échéance de la lettre **19/12/2026** | délib. 25-B-0573 |

### 7.2 Les six exigences dérivées des patterns P1 à P4

| # | Exigence | Pattern visé | Formulation type |
|---|---|---|---|
| **E1** | **Publication annuelle des volumes d'eau prélevés**, en m³ **et** en % de la production de la commune | P1, P2 | « L'exploitant transmet chaque année à la MEL et met à disposition du public les volumes prélevés et leur part dans la production communale. » |
| **E2** | **Engagement chiffré d'emplois permanents, avec clause de retour des aides** en cas d'écart > 20 % à 5 ans | P2 | Clôturer l'écart type Géorgie (−70 %) / Seine-Saint-Denis (−69 %) au niveau contractuel, pas déclaratif. |
| **E3** | **Plafond de puissance par phase** et interdiction d'augmentation sans nouvelle autorisation | P3 | Ne pas reproduire le cas xAI (150 MW autorisés / ~2 GW réels) ni CyrusOne (27 → 60 MW par phases successives). |
| **E4** | **Campagne de mesures acoustiques de référence avant travaux**, puis 3 et 12 mois après mise en service, à l'initiative d'un bureau indépendant mandaté par la collectivité, en limite de propriété, ISO 1996-2 (jour + nuit) | P4 | C'est la seule façon d'éviter le scenario Loudoun : aucune des deux parties ne peut alors contester le protocole. |
| **E5** | **Publication de la répartition exacte des 40 MVA** entre datacenter et autres usages du secteur 130 ha | P1 | Sans ce chiffre, impossible de comparer aux cas ci-dessus (tout l'écart porte sur le périmètre). |
| **E6** | **Mesures de contrôle indépendantes** (consommation électrique réelle, bruit, eau) **financées par le pétitionnaire mais choisies par la collectivité** | P1, P4 | Réponse directe au refus Meta de communiquer consommation et emploi au PSC de Louisiane [R18]. |

### 7.3 Ce qu'il ne faut **pas** faire

- Ne pas reprendre à son compte le chiffre « 50 000 emplois pour 300 centres » (filière) : il est **non daté, non méthodologique, non opposable**.
- Ne pas opposer une mesure de bruit smartphone (type 90 dB à Ashburn) comme valeur : elle ne résiste à aucun contre-expertise (niveau S4).
- Ne pas comparer un % (The Dalles) et un volume (Mesa) sans convertir.

---

## 8. POINTS À CONFIRMER

1. **Effectif réel permanent du datacenter Meta d'Odense (Danemark)** — annonce 150 emplois permanents + 2 000 en construction (2017) ; effectif réel non retrouvé dans les sources consultées.
2. **Emplois réellement créés à Fouju (Essonne)** — la phase 1 n'est livrée qu'en 2028 ; le bilan n'existe pas encore. Suivre l'enquête publique et le rapport de l'enquêteur.
3. **Consommation d'eau réelle du campus Google de Mesa (Arizona)** — aucune publication retrouvée (cas type P1, mais le chiffre exact reste à établir).
4. **Chandler, Arizona (CyrusOne) — ordonnance bruit** : plaintes riverains et pétition de 300 signatures signalées en veille, **URL de la source primaire non rédigée ici** → ne pas citer sans vérification.
5. **Valeurs exactes des relevés du comté de Loudoun** (protocole, points de mesure, périodes) — nécessaires pour qualifier l'écart 55 / 70-80 dB.
6. **Rapport du Sénat de février 2026** (50 000 emplois / 300 centres) : retrouver le texte intégral pour citer la méthodologie.
7. **Présence d'une clause de retour d'aides** dans les accords de développement français (Géorgie / Virginie) — vérifier sur un accord type publié.
8. **Rantigny (Oise) — identité de l'exploitant final et du porteur réel** (Realwave Group, SAS de 999 € de capital) et **modalités de calcul des ~100 emplois directs** annoncés dans l'étude d'impact — source à refaire sur le dossier d'enquête lui-même [R37].
9. **Châteauroux / Étrechet — volume d'eau et part exacte du raccordement électrique** : les chiffres circulant (« consommation ≈ département de l'Indre ») sont des affirmations d'opposants rapportées par la presse, **à ne pas utiliser comme fait** tant qu'aucune pièce du dossier ne les confirme [R39].
10. **Espagne (Aragón, Toledo) — chiffres AWS/Meta** : les volumes (53,9 M L/an, 600 M L/an) proviennent de déclarations d'entreprise reprises par la presse, à confirmer sur les demandes d'autorisation [R49] [R50].

---

## 9. RÉFÉRENCES

**Eau**
- [R1] The Oregonian / OregonLive — *More Oregon water for Google's data centers, more concern over secrecy*, 06/04/2026 — https://www.oregonlive.com/silicon-forest/2026/04/more-oregon-water-for-googles-data-centers-more-concern-over-secrecy.html
- [R2] Reuters — *Chile partially pulls Google data center permit, seeks tougher environmental review*, 27/02/2024 — https://www.reuters.com/world/americas/chile-partially-pulls-google-data-center-permit-seeks-tougher-environmental-2024-02-27
- [R3] Compute Atlas — Google Redhawk / Mesa (Arizona), accord de développement — https://www.compute-atlas.com/facilities/google-redhawk-mesa-az
- [R4] NBC News — *Drought-stricken communities push back against data centers*, 2021 — https://www.nbcnews.com/tech/internet/drought-stricken-communities-push-back-against-data-centers-n1271344
- [R5] The Bulletin / Deschutes River Alliance — *Facebook uses 4.1M gallons of water annually*, 10/08/2012 — https://www.deschutesriver.org/in-the-media/facebook-uses-4-1m-gallons-of-water-annually
- [R6] East Oregonian — *Meta seeks ways to boost water reserves in Crook County*, 10/12/2021 — https://eastoregonian.com/2021/12/10/meta-seeks-ways-to-boost-water-reserves-in-crook-county
- [R7] AP / Seattle Times — *Apple pledges nearly $9M to help Oregon town store water*, 19/12/2018 — https://www.seattletimes.com/seattle-news/northwest/apple-pledges-nearly-9m-to-help-oregon-town-store-water
- [R8] Oregon Department of Energy — *Data Centers and Water Dialogue (Draft)*, 27/03/2026 — https://www.oregon.gov/energy/get-involved/Documents/2026-03-27-Data-Centers-and-Water-Dialogue-Draft.pdf

**Électricité**
- [R9] CSO Ireland — *Data Centres Metered Electricity Consumption 2025*, 07/07/2026 (5 % en 2015, 23 % en 2025, 7 663 GWh) — https://www.cso.ie/en/releasesandpublications/ep/p-dcmec/datacentresmeteredelectricityconsumption2025/keyfindings — et release 2023 (5 % → 21 %) : https://www.cso.ie/en/releasesandpublications/ep/p-dcmec/datacentresmeteredelectricityconsumption2023/keyfindings/
- [R10] WRI — *Insights : US data centers, electricity demand and interconnection queues* — https://www.wri.org/insights/us-data-centers-electricity-demand
- [R11] JLARC (Virginia) — *Report 598 : Data Centers in Virginia* — https://jlarc.virginia.gov/pdfs/reports/Rpt598.pdf
- [R12] Governing — *How Virginia's booming data center industry fell short on jobs* — https://governing.com/govs/article/how-virginias-booming-data-center-industry-fell-short-on-jobs
- [R13] Bloomberg Graphics — *xAI Memphis turbines / pollution* — https://www.bloomberg.com/graphics/2025-xai-memphis-turbines-pollution/
- [R14] Daily Helmsman — recours NAACP / bruit xAI Southaven, 26/03/2026 — https://dailyhelmsman.com/2026/03/26/263453/
- [R15] Entergy — *Entergy Louisiana to power Meta's data center in Richland Parish*, 06/12/2024 — https://www.entergy.com/news/entergy-louisiana-power-meta-s-data-center-in-richland-parish
- [R16] Fox 8 / WVUE — *Seven power plants fast-tracked for Meta data center*, 15/04/2026 — https://www.fox8live.com/2026/04/15/seven-new-power-plants-meta-data-center-northern-louisiana-fast-tracked
- [R17] Sierra Club — *In Rural Louisiana, Meta's New Data Center Promises Growth—But at What Cost?* — https://www.sierraclub.org/sierra/rural-louisiana-meta-s-new-data-center-promises-growth-what-cost
- [R18] NOLA.com — *Meta won't have to turn over job, electric information after Louisiana regulators override judge*, 12/08/2026 — https://www.nola.com/news/meta-won-t-have-to-turn-over-job-electric-information-after-louisiana-regulators-override-judge/article_69105eda-826d-476c-9b01-b911afcdbe64.html

**Emplois**
- [R19] Sud Ouest / AFP — *Île-de-France : les data centers, des infrastructures gourmandes en énergie mais avares en emplois*, 01/06/2026 — https://www.sudouest.fr/ile-de-france/ile-de-france-les-data-centers-des-infrastructures-gourmandes-en-energie-mais-avares-en-emplois-29309407.php
- [R20] La Dauphiné — *Un raccordement facile mais peu d'emplois créés : la France, nouvel eldorado des datacenters ?*, 04/06/2026 — https://www.ledauphine.com/economie/2026/06/01/un-raccordement-facile-mais-peu-d-emplois-crees-la-france-nouvel-eldorado-des-datacenters
- [R21] Synthèse de l'audit de l'État de Géorgie (5 471 → 1 641 emplois, 289 k$/emploi) — https://thecounterstory.com/70-percent-shortfall-how-georgias-data-centers-failed-to-deliver-on-jobs-tax-breaks/
- [R22] Brookings — *New evidence on data center employment effects*, 10/08/2026 — https://www.brookings.edu/articles/new-evidence-on-data-center-employment-effects/
- [R23] syracuse.com — *$77 million tax break created just 1 job, NY data center auditors say*, 07/2025 — https://www.syracuse.com/business/2025/07/77-million-tax-break-created-just-1-job-ny-data-center-auditors-say.html
- [R24] Nordic Labour Journal (d'après Yle) — *Facebook gets green light in Denmark but at what cost* — https://www.nordiclabourjournal.se/facebook-gets-green-light-in-denmark-but-at-what-cost/html
- [R25] Memphis Flyer — *Colossus*, 11/12/2024 : « While xAI promised the community 300 jobs, they currently list just 32 positions — most of them hourly, contractual roles in administrative support » — https://www.memphisflyer.com/colossus/
- [R26] WAFB — *Meta more than doubles size of Louisiana AI data center in massive $50 billion expansion*, 13/07/2026 — https://www.wafb.com/2026/07/13/gov-landry-meta-formally-announce-louisiana-data-centers-historic-expansion
- [R27] AFP / France 24 — *France's data centre ambitions bump up against rural fears* (Fouju), 05/06/2026 — https://www.france24.com/en/live-news/20260605-france-s-data-centre-ambitions-bump-up-against-rural-fears

**Bruit**
- [R28] NBC Washington / News4 — *Neighbors raise concerns about noisy data center in Loudoun*, 23/03/2026 — https://www.nbcwashington.com/news/local/northern-virginia/neighbors-raise-concerns-about-noisy-data-center-in-loudoun/4080249/
- [R29] Washingtonian — *Data center noise has Loudoun County residents talking*, 02/10/2025 — https://washingtonian.com/2025/10/02/data-center-noise-loudoun-county-residents/
- [R30] WMC TV — *NAACP sues Southaven over XAI data center noise* — https://www.wmc-tv.com/news/naacp-sues-southaven-over-xai-data-center-noise/article_e40a4e70-9797-11f0-a4e2-ebca1e4bd3e9.html
- [R31] Courthouse News — *France boosts data center expansion amid pushback from residents* (Wissous / CyrusOne), 06/06/2026 — https://www.courthousenews.com/france-boosts-data-center-expansion-amid-pushback-from-residents
- [R32] CyrusOne — Data sheet PAR1 Wissous (27 MW à terme, arrivées 225 kV, 60 MVA) — https://www.cyrusone.com/hubfs/Website%20Documents%202025/CyrusOne%20-%20PAR1%20-%20French.pdf-1.pdf
- [R33] Corpus du dossier — `generalites/NuisancesSonores.md` (CIDB/Bruit.fr, Gamba Acoustique : ~70 dB(A) à 100 m sans traitement ; seuils ICPE et R.1336-5)

**Contexte France (opposition, emplois, projet)**
- [R34] ZDNet — *Opposés à l'implantation de datacenters, les collectifs de riverains s'organisent*, 25/06/2026 — https://www.zdnet.fr/actualites/opposes-a-limplantation-de-datacenters-les-collectifs-de-riverains-sorganisent-497655.htm
- [R35] Reuters — *Backlash against data centres is spilling into French municipal election races*, 13/03/2026 — https://www.reuters.com/sustainability/climate-energy/backlash-against-data-centres-is-spilling-into-french-municipal-election-races-2026-03-13
- [R36] Courthouse News [R31] et Le Monde (en) — *France strives to keep up in global data-center race as opposition mounts*, 27/07/2026 (Rexecode : 210 Md€ d'investissements d'ici 2035) — https://www.lemonde.fr/en/economy/article/2026/07/27/france-strives-to-keep-up-in-global-data-center-race-as-opposition-mounts_6755896_19.html

**France — cas par cas (eau, emploi, bruit)**
- [R37] Parlons Business — *À Rantigny, dans l'Oise, un projet de data center à 4,5 milliards d'euros divise un village de 2 500 habitants*, 26/08/2026 (SCI Alyssa / Realwave Group, capital 999 €, ~100 emplois directs, réunion du 19/08/2026, projet jumeau de Lachelle) — https://parlons-business.fr/decryptages/rantigny-data-center-oise-consultation-publique
- [R38] France 3 Centre-Val de Loire — *Google prépare un data center géant en France, pourquoi le projet divise fortement* (Étrechet/Châteauroux : 195 ha, 8-10 bâtiments, promesse de vente jusqu'au 05/07/2030), 29/05/2026 — https://france3-regions.franceinfo.fr/centre-val-de-loire/indre/pourquoi-le-premier-data-center-de-google-en-france-divise-3359485.html
- [R39] France 3 Centre-Val de Loire — *« Non au technofascisme »… 200 personnes se mobilisent contre un projet de data center* (30/06/2026, 200 emplois contestés, conso ≈ département de l'Indre) — https://france3-regions.franceinfo.fr/centre-val-de-loire/non-au-technofascisme-google-ton-data-on-en-veut-pas-200-personnes-se-mobilisent-contre-un-projet-de-data-center-3379165.html
- [R40] Le Monde — *A Châteauroux, la contestation contre le projet de data center de Google s'organise*, 30/05/2026 — https://www.lemonde.fr/economie/article/2026/05/30/a-chateauroux-la-contestation-contre-le-projet-de-data-center-de-google-s-organise_6695249_3234.html
- [R41] France 3 PACA / France Télévisions — *« Vous êtes déjà fortement pollués… » : un projet de data center déclenche la résistance d'élus et de riverains* (Les Pennes-Mirabeau / Saint-Victoret : PC février 2026, recours 18/04/2026, ~15 emplois, 150 000 t de roche), 19/04/2026 — https://france3-regions.franceinfo.fr/provence-alpes-cote-d-azur/bouches-du-rhone/marseille/vous-etes-deja-fortement-pollues-donc-un-peu-plus-un-peu-moins-un-projet-de-data-center-declenche-la-resistance-d-elus-et-de-riverains-3337127.html
- [R42] Reporterre — *Data centers : leur consommation d'eau va exploser*, 30/01/2024 (CyrusOne/Amazon : 850 m³/an annoncés ; Google : 28 Mdm de litres/an, +82 % 2018-2022 ; forages « plus ou moins déclarés » en Essonne) — https://reporterre.net/Data-centers-leur-consommation-d-eau-va-exploser
- [R43] franceinfo / OnVousRépond Climat — *Les data centers consomment beaucoup d'énergie, mais qu'en est-il de leurs besoins en eau ?*, 28/04/2026 (Florence Habets, ENS-CNRS : fabrication des puces en Isère, « des millions de m³ »/an) — https://www.franceinfo.fr/environnement/onvousrepond-climat/les-data-centers-consomment-beaucoup-d-energie-mais-qu-en-est-il-de-leurs-besoins-en-eau-onvousrepond-climat_7813781.html
- [R44] Ville de Demain — *Guide du data center : impact environnemental — eau, énergie, chaleur*, 04/2026 (hyperscale : 760 M L/an ≈ 12 000 hab. ; petit/moyen : 25 M L/an ≈ 500 hab. ; 45 % des datacenters mondiaux en bassins à risque) — https://www.ville-demain.com/wp-content/uploads/2026/04/guide-data-center-impact-environnemental-eau-energie-chaleur-2026.pdf
- [R53] blog.datacenter-paris — *Datacenter : 25,5 M litres d'eau/MW, comment réduire en 2026*, 16/04/2026 (chiffre attribué à une étude *Nature* ; rappel du rejet du projet de loi encadrant les datacenters au motif que le numérique représenterait 0,02 % des prélèvements économiques en France) — https://blog.datacenter-paris.com/datacenter-25-5-m-litres-d-eau-mw-comment-reduire-en-2026
- [R54] LeMagIT — *Pourquoi il devient critique d'évaluer l'usage de l'eau dans le datacenter*, 22/12/2021 (Google refuse les chiffres site par site ; pacte eau européen CNDCP) — https://www.lemagit.fr/conseil/Pourquoi-il-devient-critique-devaluer-lusage-de-leau-dans-le-datacenter

**Europe (hors France)**
- [R45] DataCenterDynamics — *The ongoing impact of Amsterdam's data center moratorium*, 18/09/2026 (moratoire 2019-2020, PUE 1,2/1,3, 187 datacenters NL en 2025 vs 189 en 2019) — https://www.datacenterdynamics.com/en/analysis/the-ongoing-impact-of-amsterdams-data-center-moratorium/
- [R46] Dutch Brief — *Microsoft to build massive data centre in Amsterdam despite bans*, 16/05/2026 (3 tours de 85 m, 78 MW, découpage sous le seuil hyperscale) — https://www.dutchbrief.com/p/microsoft-to-build-massive-data-centre-in-amsterdam-despite-bans
- [R47] DCmag (FR) — *Equinix obtient le permis de construire pour un méga data center à Amsterdam*, 09/07/2026 (4 tours de 60 m, 80 MW, 779 GWh/an, sous-stations TenneT attendues **en 2036**) — https://dcmag.fr/equinix-obtient-le-permis-de-construire-pour-un-mega-data-center-a-amsterdam-mais-devra-se-montrer-patient
- [R48] DataCenterDynamics — *Dutch government halts hyperscale data centers, pending new rules*, 17/02/2022 (seuils >10 ha et >70 MW, moratoire national de 9 mois) — https://www.datacenterdynamics.com/en/news/dutch-government-halts-hyperscale-data-centers-pending-new-rules
- [R49] DataCenterDynamics — *Spain's city of Lleida bans data centers*, 21/01/2025 (maire Fèlix Larrosa : manque d'emplois qualifiés, énergie et eau ; Meta Toledo >600 M L/an en zone à risque) — https://www.datacenterdynamics.com/en/news/spains-city-of-lleida-bans-data-centers
- [R50] EU Perspectives — *Can Spain build AI infrastructure without running dry?*, 08/2026 (AWS Aragón : 53,9 M L/an par centre ; décret espagnol 1 MW renouvelable/18 mois par MW ; UE ≈ 3 % de la demande électrique ; étiquetage UE dès 15/08/2027) — https://euperspectives.eu/2026/08/can-spain-build-ai-infrastructure-without-running-dry
- [R51] Berlin Gazette — *Are Data Centers Factories? Industrial promises and socio-ecological losses*, 09/07/2026 (stratégie nationale allemande du 18/03/2026 : ×2 capacité en 5 ans, ×4 pour l'IA ; étude prévoyant ×3 soit 5 000-5 500 MW ; ~3 000 datacenters ; 15 Md€ investis l'an dernier dont la moitié par des sociétés US) — https://berlinergazette.de/are-data-centers-factories-industrial-promises-and-socio-ecological-losses
- [R52] DataCenterDynamics — *European operators plan to cut water use to 400ml per kWh by 2040* (CNDCP : 74 opérateurs signataires, objectif WUE 0,4 L/kWh en 2040) — https://www.datacenterdynamics.com/en/news/european-operators-plan-to-cut-water-use-to-400ml-per-kwh-by-2040

---

*Document de travail — octobre 2026. Tous les chiffres des §2 à §5 sont sourcés par une référence [R##] dont l'URL figure au §9 ; les éléments sans source sont explicitement marqués [à confirmer] et ne doivent pas être utilisés dans un argumentaire. Les niveaux de preuve (§1.2) doivent accompagner toute reprise du document.*
