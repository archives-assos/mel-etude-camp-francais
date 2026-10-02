# LES ONZE NUISANCES D'UN DATACENTER

**Objet :** développer, un par un, les **11 nuisances** retenues pour argumenter sur les projets de datacenter : perte de terres agricoles, recul de la biodiversité, tension réseau au détriment des usagers, hausse de températures, pollution sonore, pollution lumineuse, polluants éternels (PFAS), consommation électrique, ressources en eau fragilisées, peu d'emplois créés, mensonges sur la souveraineté numérique.
**Intrants :** corpus général `generalites/` (`NuisancesSonores.md`, `refroidissement-generalisation-300MW.md`, `ecarts-annonces-realisite-datacenters.md` — déjà sourcé, cité par ses [R##]) + recherches externes dédiées ([N##] ci-contre).
**Méthode :** par nuisance → **mécanisme** / **chiffres sourcés** / **cadre réglementaire français** / **levier opposable**. Tout chiffre porte une source ; ce qui n'en a pas est marqué **[à confirmer]** et ne doit pas être repris.
**Date :** octobre 2026 — document de travail.

---

## TABLE DES MATIÈRES

1. [Perte de terres agricoles](#1-perte-de-terres-agricoles)
2. [Recul de la biodiversité](#2-recul-de-la-biodiversité)
3. [Tension sur le réseau électrique au détriment des usagers](#3-tension-sur-le-réseau-électrique-au-détriment-des-usagers)
4. [Hausse des températures autour du datacenter](#4-hausse-des-températures-autour-du-datacenter)
5. [Pollution sonore](#5-pollution-sonore)
6. [Pollution lumineuse](#6-pollution-lumineuse)
7. [Polluants éternels (PFAS)](#7-polluants-éternels-pfas)
8. [Consommation électrique](#8-consommation-électrique)
9. [Ressources en eau fragilisées](#9-ressources-en-eau-fragilisées)
10. [Peu d'emplois créés](#10-peu-demplois-créés)
11. [Mensonges sur la souveraineté numérique](#11-mensonges-sur-la-souveraineté-numérique)
12. [Cadre Union européenne](#12-cadre-union-européenne)
13. [Grille de synthèse](#13-grille-de-synthèse)
14. [Exigences à poser (recap)](#14-exigences-à-poser-recap)
15. [Points à confirmer](#15-points-à-confirmer)
16. [Références](#16-références)

---

## 1. PERTE DE TERRES AGRICOLES

### 1.1 Mécanisme

Le datacenter est une **surface imperméabilisée massive, monobloc, sans valeur agricole résiduelle** : plateau bétonné, parking de sécurité, zone de délestage, emprise des lignes de raccordement. Contrairement à une usine, il ne crée pas de tissu économique local susceptible de compenster la perte de sol.

### 1.2 Chiffres sourcés

| Projet | Emprise | Source |
|---|---|---|
| **Google — Étrechet / Châteauroux (36)** | **195 ha**, soit « **279 terrains de football** » (élus écologistes) ; 8 à 10 bâtiments ; RTE construit **90 km de ligne** pour 300 M€ | France 24 / AFP, 12/06/2026 [N20] ; France 3, 29/05/2026 → `ecarts-...` [R38] |
| **Campus IA — Fouju (77)** | Projet en **zone maraîchère** : les opposants opposent à la datacenterisation l'usage agricole des parcelles (« filière de transformation alimentaire ») | France 3, 01/07/2026 [R39] ; France 24, 05/06/2026 [R27] |
| **Le Bosquel — Somme** | Campus IA SoftBank sur **46 ha de terres agricoles** | ZDNet, 25/06/2026 → `ecarts-...` [R34] |
| **Offre publique de l'État** | **63 sites industriels « propices »**, soit **~1 200 ha — « l'équivalent d'une ville comme Versailles »** | AOC, 10/05/2026 [N19] |
| **Lleida (Catalogne)** | Une entreprise avait acheté un **sol rural** ; la municipalité a **refusé le changement de destination** — et interdit les datacenters | DCD, 21/01/2025 → `ecarts-...` [R49] |
| **Île-de-France** | **Plus de 160 datacenters** concentrent **>70 % des infrastructures françaises** (Institut Paris Region) — artificialisation concentrée sur le foncier disponible | Sud Ouest / AFP, 01/06/2026 → `ecarts-...` [R19] |

### 1.3 Cadre réglementaire français

- **Objectif national de zéro artificialisation nette** (loi Climat et Résilience 2021, codifiée au code de l'urbanisme) — **URL Légifrance [à confirmer]**.
- **Loi du 15 avril 2026** : extension aux datacenters du régime dérogatoire de **« projet d'intérêt national majeur »** (PINM) — c'est précisément la porte qui **contourne** le contrôle foncier communal [N19].
- **SDAGE / ZNIEFF / servitudes de passage de ligne** : le raccordement haute tension emporte sa propre emprise foncière et ses servitudes, à instruire avec le document d'urbanisme.

### 1.4 Levier opposable

Exiger le **recalibrage au plus près** (surface bâtie utile vs emprise totale), la **remise en état agronomique** en fin d'exploitation, et contester le bénéfice PINM au motif que le projet **ne répond pas à un impératif de souveraineté** (recommandation n° de la commission d'enquête, §11).

---

## 2. RECUL DE LA BIODIVERSITÉ

### 2.1 Mécanisme

Trois volets : **(i)** destruction/disjonction d'habitats sur emprise fermée ; **(ii)** nuisances de fonctionnement (lumière nocturne, bruit, chaleur, chocs de l'air rejeté) qui dégradent la faune environnante **sans emprise** ; **(iii)** prélèvements hydriques qui assoiffent les milieux.

### 2.2 Chiffres et cas sourcés

| Élément | Donnée | Source |
|---|---|---|
| **Lumière nocturne vs faune** | Le décret français vise explicitement « **l'atteinte à la faune, à la flore et aux écosystèmes** » par l'éclairage artificiel | Décret du 27/12/2018, Legifrance [N7] |
| **Eau** | **45 % des datacenters mondiaux** sont situés dans des **bassins à forte pression sur l'eau** | Guide Ville de Demain, 04/2026 → `ecarts-...` [R44] |
| **Chaleur** | Élévation de température locale mesurée (§4) → stress thermique sur la faune végétale périphérique | ASU [N1] ; Cambridge [N3] |
| **Fouju** | Opposition : **613 groupes électrogènes** à essais et **680 circuits de refroidissement** évoqués comme risques ; **pas de réemploi de chaleur** annoncé par le maire | France 24, 05/06/2026 → `ecarts-...` [R27] |

### 2.3 Levier opposable

1. **Dérogation espèces protégées L.411-1 / L.411-2** : gage de retard de 12-24 mois si les études chiroptères ne sont pas fournies **avant** le dépôt du permis.
2. **Plan de continuité écologique** exigé (corridors, haies, toiture végétalisée, hors-zones d'agrégation).
3. **Interdiction des essais de groupes électrogènes nocturnes et en période de reproduction** (voir §5 et §7).

---

## 3. TENSION SUR LE RÉSEAU ÉLECTRIQUE AU DÉTRIMENT DES USAGERS

### 3.1 Mécanisme

La puissance prélevée par les datacenters est **une ressource rare disputée** : elle fait monter les coûts de réseau, retarde le raccordement d'autres usagers, et peut être socialisée sur les factures résidentielles quand le régulateur valide des investissements « client modèle ».

### 3.2 Chiffres sourcés

| Territoire | Constat | Source |
|---|---|---|
| **Virginie (États-Unis)** | Demande électrique **+180 % d'ici 2035/2040** ; facture résidentielle **+37 $/mois d'ici 2040** (rapport législatif JLARC) | JLARC Rpt598 → `ecarts-...` [R11] ; Governing [R12] |
| **Louisiane (États-Unis)** | Un rapport-conseil du régulateur (PSC) estime que **les résidents subventionnent une partie** de la consommation ; **550 M$ de ligne de transport** supportés par les clients ; Meta a **refusé de dévoiler sa consommation** au PSC | Sierra Club/Wired [R17] ; NOLA.com, 12/08/2026 [R18] |
| **France** | **RTE a réservé 15 GW** de capacité de raccordement à des projets de datacenters = **24 % de la puissance du parc nucléaire français**, dont **seulement 9 %** profiteraient à des acteurs européens | Commission d'enquête AN, rapport enregistré le 08/07/2026 → Silicon.fr [N15] ; ChannelNews [N16] ; Vie publique [N14] |
| **Île-de-France** | Le Grand Port Maritime de Marseille concentre des besoins électriques **« équivalents à ceux de plus de 200 000 foyers »** (délibération municipale d'oct. 2023) | AOC, 10/05/2026 [N19] |
| **Pays-Bas** | Le raccordement n'existe pas : pour Equinix Amsterdam, les sous-stations TenneT nécessaires **ne sont pas attendues avant 2036** — la puissance devient le facteur limitant **y compris pour les autres usagers** | DCmag, 09/07/2026 → `ecarts-...` [R47] |
| **Irlande** | Part des datacenters dans l'électricité comptée : **5 % (2015) → 23 % (2025)** — plus que les ménages urbains (18 %) et ruraux (10 %) réunis | CSO Ireland → `ecarts-...` [R9] |
| **Files d'attente (États-Unis)** | Requêtes **spéculatives et dupliquées** : une part des MW demandés n'existera pas, mais gonfle les prévisions **au détriment des priorités de raccordement** | WRI → `ecarts-...` [R10] |
| **Argument opposé (à connaître)** | Entergy affirme que ses clients seront **épargnés d'une hausse de ~5 $/mois** au Mississippi dès juillet 2026 et reverseront **2,8 Md$ en 20 ans** en Louisiane — c'est **la thèse de l'opérateur**, à opposer avec les chiffres du PSC ci-dessus | Entergy (page corporate) [N22] |

### 3.3 Levier opposable

- Exiger le **chiffrage complet du raccordement** (qui paie la hausse de puissance, qui paie le renforcement RTE) et non l'annonce d'économies promises par l'exploitant.
- S'appuyer sur la recommandation de la commission d'enquête : **moratoire sur les datacenters ne répondant pas à un impératif de souveraineté** et **contrôle public renforcé du déploiement** [N15] [N14].

---

## 4. HAUSSE DES TEMPÉRATURES AUTOUR DU DATACENTER

### 4.1 Mécanisme

Un datacenter **ne consomme pas** d'énergie : il la **convertit en chaleur**, 100 % de la charge IT devenant de la chaleur à évacuer (`generalites/refroidissement-generalisation-300MW.md` §1). Les aérorefigérants rejettent un air **+5 à +12 °C** au-dessus de l'ambiant, formant un panache qui descend le vent sur les quartiers voisins.

### 4.2 Chiffres sourcés

| Étude | Résultat | Portée | Source |
|---|---|---|---|
| **Arizona State University (Phoenix)** — *première mesure directe in situ* | Température de l'air aval **+0,7 à +0,9 °C en moyenne**, **jusqu'à +2,2 °C** ; détection **jusqu'à ~500 m** (voire ~800 m / ⅓ de mile) ; l'air rejeté est **+8 à +14 °C** au-dessus de l'ambiant ; chaleur d'1 datacenter **> celle de 40 000 foyers** | air ambiant des quartiers résidentiels | ASU News, 18/05/2026 [N1] ; revue ASME *J. Eng. Sustain. Bldgs. Cities* [N2] |
| **Université de Cambridge** — pré-relecture (preprint) | Sur **>6 000 datacenters** et 20 ans d'imagerie satellite : température de surface **+2 °C en moyenne** après mise en service, **jusqu'à +9,1 °C** en cas extrême ; effet détecté **jusqu'à ~10 km** ; **340 M de personnes** concernées ; confirmation d'une anomalie de **+2 °C en Aragon** (Espagne) non présente dans les provinces voisines | température de surface à l'échelle régionale | CNN, 30/03/2026 [N3] ; The Independent, 31/03/2026 [N23] |
| **Slough (Royaume-Uni)** — plus grand hub d'Europe (~30-40 sites) | Hausse **~+2 °C en moyenne, jusqu'à +9 °C** dans le périmètre immédiat ; station météo la plus proche du tech park : **36,7 °C** alors que le centre-ville atteint 36,2 °C puis 34,7 °C la veille | ressenti et mesure locale | The Guardian, 26/06/2026 [N4] |
| **Contre-point honnête** | L'Uptime Institute reconnaît le phénomène mais estime que **la chaleur résiduelle reste aujourd'hui un contributeur mineur** de l'îlot de chaleur urbain ; mitigations : conception, matériaux, végétalisation | — | Uptime Institute [N5] |
| **Revendication locale (non mesurée)** | Opposants à Châteauroux avancent une hausse **de 2 à 7 °C** en extérieur dû à la climatisation | **annonce d'opposants** → à ne pas utiliser comme mesure | France 3, 01/07/2026 → `ecarts-...` [R39] |

### 4.3 Cadre et levier

- Le dossier français traite la chaleur fatale comme une **ressource à valoriser** (promesse de serres à Châteauroux [R39], réemploi « à confirmer » à Fouju [R27]) — jamais comme une **nuisance à mesurer**.
- **Levier :** exiger une **campagne de mesures de température de l'air avant/après mise en service** (points aval, 100/250/500 m, jour + nuit d'été), protocole aligné sur ASU/N2, **financée par le pétitionnaire mais choisie par la collectivité** — voir `ecarts-...` §7.2 E6.
- **Levier technique :** refroidissement **adiabatique/DLC** (moins de chaleur rejetée en air) et **obligation de réemploi de la chaleur fatale** (sinon engagement nul).

---

## 5. POLLUTION SONORE

### 5.1 Ce qui émet

Pas les serveurs (confinés) : **chillers, pompes, CTA, aérorefigérants de toiture**, **groupes électrogènes de secours** (essais mensuels, jusqu'à **130 dB(A)** non isolés) et, pour l'IA, **infrasons** de basse fréquence (<20 Hz) qui traversent les parois. → `generalites/NuisancesSonores.md` §1-§2 (sources CIDB/Bruit.fr, ia-info.fr).

### 5.2 Chiffres sourcés

| Cas | Valeur | Source |
|---|---|---|
| **Modèle de conception (non traité)** | **~70 dB(A) chez le riverain à 100 m** en pleine charge sans traitement ; un hyperscale à 100 m = un edge à 20 m | Gamba Acoustique → `generalites/NuisancesSonores.md` [R33] |
| **Ashburn, Virginie (CloudHQ)** | **90 dB(A)** relevés par des riverains (application grand public, mars 2026) | NBC/News4 → `ecarts-...` [R28] (niveau S4) |
| **Loudoun County (Vantage II)** | Ordonnance **55 dB(A)** vs relevés riverains **70-80 dB(A)** ; les relevés du comté **ne dépassent jamais** le seuil | Washingtonian → `ecarts-...` [R29] |
| **Memphis / Southaven (xAI)** | Recours de l'**NAACP** pour bruit continu type « moteur de jet » ; **69 turbines** installées | WMC TV [R30] ; Bloomberg [R13] |
| **Wissous (CyrusOne)** | Contentieux **bruit + chaleur** depuis 2021 ; la CAA de Versailles a autorisé l'extension en avril 2026 | Courthouse News → `ecarts-...` [R31] |
| **Rantigny (Oise)** | Titre de la réunion publique : *« Vous allez nous mettre un radiateur qui fait du bruit ! »* | Parlons Business → `ecarts-...` [R37] |

### 5.3 Cadre réglementaire français

| Régime | Seuil | Source |
|---|---|---|
| **ICPE** | **70 dB(A) jour / 60 dB(A) nuit en limite de propriété** | `generalites/NuisancesSonores.md` §3 (décret n° 2006-1099) |
| **Bruit de voisinage (art. R.1336-5 CSP)** | **Émergence 5 dB(A) jour / 3 dB(A) nuit** | idem ; art. L.571-1 CSP |
| **Infrasons / émergence** | Devoir d'évaluation spécifique, pas de seuil simple | `generalites/NuisancesSonores.md` §2 |

### 5.4 Levier opposable

**Mesure de référence avant travaux** (ISO 1996-2, limite de propriété, jour + nuit), puis **T+3 et T+12 mois**, bureau indépendant choisi par la collectivité → `ecarts-...` §7.2 E4. Sans cela, on retombe dans le scénario Loudoun : deux protocoles, deux vérités.

---

## 6. POLLUTION LUMINEUSE

### 6.1 Mécanisme

Un datacenter fonctionne **24 h/24** avec des espaces de sécurité (parkings, cours de livraison, façades, caméras) éclairés **« en force »** : DarkSky décrit une logique de **« brute force lighting »** — « si un espace n'est pas activement utilisé par des humains, il ne doit pas être éclairé comme un stade » [N6].

### 6.2 Recommandations techniques sourcées (DarkSky, 04/06/2026) [N6]

| Levier | Exigence recommandée |
|---|---|
| Éviter la surenchère | Niveau minimal strictement nécessaire |
| **Coupure à 80°** | Aucun flux au-dessus de l'horizon |
| **Détection de présence + gradation** | Forte baisse en fin de nuit |
| **Température de couleur ≤ 3000 K** | Limiter la lumière bleue (skyglow + rythme circadien) |
| **Niveaux d'éclairement** | Parkings : **2 lux** ; zones de transaction **10 lux** avant couvre-feu, **2 lux** après |
| Référence technique | **IES RP-43-22** |
| Preuve d'efficacité | Tucson (Arizona) : rétrofit LED + gradation → **−7 % de skyglow** alors que la ville grandissait |

### 6.3 Cadre réglementaire français (opposable tel quel)

**Décret n° 2018-1157 du 27 décembre 2018** relatif à la prévention, à la réduction et à la limitation des nuisances lumineuses — Legifrance : https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000037864346 [N7]

- **Couvre-feux** (extinction ou baisse obligatoire selon les usages et les zones).
- **Limite de lumière émise vers le ciel** : **ULR (Upward Light Ratio) < 1 %** dans la plupart des cas.
- **Interdiction des UV**, exigences de **non-éblouissement** et de **température de couleur maîtrisée**.
- **Champs d'application** : éclairage extérieur des **bâtiments non résidentiels** (y compris lumière intérieure vers l'extérieur et façades), **parkings non couverts**, **éclairage de chantier**, parcs et jardins — donc **le site d'un datacenter est dedans**.
- **Zones différenciées** : zones bâties, hors zones bâties, zones naturelles (annexe de l'art. R.583-4) et **sites d'observation astronomique** (11 sites protégés).
- **Obligation d'information** : le propriétaire doit fournir aux agents les éléments permettant de **vérifier la conformité** [N8].
- La loi de 2013 a par ailleurs **interdit l'allumage de 1 h à 7 h** des façades et vitrines commerciales (elle a sauvé l'équivalent de la consommation de **750 000 ménages** et **200 M€/an**) → The Times, 30/06/2013 [N24].

### 6.4 Levier opposable

**Cahier des charges acoustique-lumière** à joindre au permis : ULR < 1 %, CCT ≤ 3000 K, couvre-feu (ex. extinction à 23 h sauf présence détectée), 2 lux en parking, plan d'éclairage justifié point par point, et **relevé nocturne contradictoire à T+3 mois**. En l'absence de telles mesures, la nuisance est **non mesurable après coup** — même schéma que pour le bruit (§5.4).

---

## 7. POLLUANTS ÉTERNELS (PFAS)

### 7.1 Les trois voies d'exposition

1. **Refroidissement liquide** : les fluides de **refroidissement en immersion diphasique** sont, selon des chercheurs de Microsoft eux-mêmes cités par Food & Water Watch, **des PFAS** (« two-phase immersion fluids are PFAS ») [N11].
2. **Climatisation / froids industriels** : fluides frigorigènes de la famille des **HFO** (hydrofluorooléfines, type Opteon de Chemours) — liaisons carbone-fluorine = PFAS [N12].
3. **Extinction incendie et semi-conducteurs** : mousse anti-incendie et fabrication des puces sont des sources connues de PFAS [N12] [N13].

### 7.2 Chiffres sourcés

| Donnée | Chiffre | Source |
|---|---|---|
| Volume potentiel | « Un datacenter hyperscale peut contenir **des centaines de cuves**, soit **des dizaines de milliers de litres de fluide diélectrique** » (lettre de 17 ONG à l'EPA) | Fortune, 18/09/2026 [N9] ; The Guardian, 27/07/2026 [N10] |
| Émissions | À chaque **ouverture de cuve pour maintenance**, « de grandes quantités de PFAS s'évaporent dans le datacenter puis dans l'atmosphère » (entreprise citée) ; jusqu'à **~2 100 L/an** par cuve estimés par un collectif | Food & Water Watch, 07/2026 [N11] ; CPEO, 29/06/2026 [N25] |
| Production en hausse | **Daikin, Arkema (France), Chemours** augmentent leur production de PFAS **grâce à la demande des datacenters et des semi-conducteurs** ; **50 à 67 %** du chiffre d'affaires de Chemours (5,8 Md$) vient des PFAS | Fortune [N9] |
| Contamination de l'eau liée au site | Un datacenter **Amazon en Oregon** a conclu un **accord collectif de 20,5 M$** : son processus de refroidissement aurait concentré des **eaux usées riches en nitrates**, contaminant des puits privés (fausses couches, insuffisances rénales, cancers allégués) | EHN, 01/02/2026 [N13] |
| Rejet liquide (blowdown) | Purges contenant **sels, inhibiteurs, biocides, métaux lourds, réfrigérants, PFAS** ; la chaleur **concentre** les contaminants | EHN [N13] |
| Revendication locale | À Fouju, l'opposition craint des **PFAS issus des 680 systèmes de refroidissement** | France 24, 05/06/2026 → `ecarts-...` [R27] |

### 7.3 Ce qu'il faut savoir (nuances obligatoires)

- **L'opérateur répond que c'est une boucle fermée** : Chemours affirme qu'il n'y a « pas d'émission de cheminée » et que les fuites (**émissions fugitives**) sont faibles [N10].
- **Les analysts indépendants nuancent** : EESI estime que la pollution directe sur site est **« difficile à évaluer et probablement limitée »**, mais que la pollution industrielle en **amont** (usines de production) est bien réelle et affecte les riverains de ces usines [N12].
- **L'Arcticle clé** : le passage à l'immersion diphasique est **vendu comme la réponse à la consommation d'eau** — c'est donc **un arbitrage eau ↔ PFAS**, pas une suppression d'impact (§9) [N9] [N10].

### 7.4 Cadre et levier

- **Cadre UE** : règlement (UE) n° **2024/573** sur les gaz à effet de serre fluorés (f-gas, **remplace le règlement 517/2014**), visant à réduire les **fuites de fluides frigorigènes** → EUR-Lex [N32] ; lecture technique → UBA / agence allemande de l'environnement [N26].
- **Leviers à exiger** : (i) **inventaire et déclaration des fluides** (famille chimique, tonnage, GWP, présence de PFAS) ; (ii) **interdiction des systèmes en immersion diphasique PFAS** sur site ; (iii) **dates de fin de vie et filière d'élimination** (incinération) contractuellement ; (iv) **déclaration des essais d'extinction**.

---

## 8. CONSOMMATION ÉLECTRIQUE

### 8.1 Chiffres sourcés

| Périmètre | Donnée | Source |
|---|---|---|
| **Monde (AIE)** | Consommation des datacenters **×2 d'ici 2030** ; l'IA représenterait **40 %** de cet appétit avant la fin de la décennie | AIE, citée par AOC, 10/05/2026 [N19] |
| **Union européenne** | Les datacenters représentent **~3 % de la demande électrique de l'UE**, part attendue en hausse | EU Perspectives, 08/2026 → `ecarts-...` [R50] |
| **France (Arcep)** | **+8 %** de consommation électrique des datacenters en 2023 — **alors que les autres secteurs tertiaires baissaient** — et **+19 %** de prélèvement d'eau (essentiellement potable) | Arcep, citée par AOC [N19] |
| **France (Ademe)** | Les usages numériques des Français pourraient faire **quadrupler** la consommation électrique des datacenters **d'ici 2035** | Ademe, citée par France 24, 12/06/2026 [N20] |
| **France (réservations RTE)** | **15 GW réservés** à des projets de datacenters = **24 % du parc nucléaire** | Commission d'enquête AN [N15] [N16] |
| **Châteauroux** | Puissance attendue **1,2 à 1,3 GW**, soit **plus que la consommation électrique annuelle du département de l'Indre** | Jérémie Godet (élu régional), cité par France 24 [N20] |
| **Marseille** | Besoins du Grand Port Maritime **équivalents à >200 000 foyers** | Délibération municipale oct. 2023, citée par AOC [N19] |
| **Irlande** | **23 %** de l'électricité comptée (2025) | CSO → `ecarts-...` [R9] |

### 8.2 Le point de vigilance (à ne pas omettre)

L'argumentaire officiel repose sur le **mix décarboné (95 %)** français [N20]. Réponse : **décarboné ≠ disponible et ≠ indolore** — les 15 GW réservés concurrencent directement les autres usages (§3), et la chaleur résiduelle n'est pas réinjectée (§4).

### 8.3 Levier opposable

- Exiger la **part exacte de raccordement** affectée au datacenter et la **répartition par usage** du site (datacenter, logistique, bureaux…), souvent non publiée → `ecarts-...` E5.
- Exiger **PUE et WUE contractuels**, avec pénalité si dépassement (référence : PUE < 1,3 exigé aux Pays-Bas pour les neufs [R45]).
- S'appuyer sur **l'encadrement espagnol** : **1 MW renouvelable construit dans les 18 mois par MW de demande**, à défaut perte du raccordement [R50].

---

## 9. RESSOURCES EN EAU FRAGILISÉES

### 9.1 Chiffres sourcés (synthèse)

| Donnée | Chiffre | Source |
|---|---|---|
| **Curseur municipal le plus parlant** | The Dalles (Oregon) : Google passe de **12 % (2012) à ~40 % de l'eau de la ville** (~550 M gallons en 2025) ; données tenues secrètes au nom du secret commercial | The Oregonian, 06/04/2026 → `ecarts-...` [R1] |
| **France — tendance** | **+19 %** de prélèvement d'eau des datacenters en 2023, essentiellement **eau potable** | Arcep via AOC [N19] |
| **Ordres de grandeur** | Hyperscale ≈ **760 M L/an ≈ ville de 12 000 hab.** ; petit/moyen ≈ **25 M L/an ≈ 500 hab.** ; **25,5 M L/MW/an** (étude *Nature* citée) | Guide Ville de Demain [R44] ; blog datacenter-paris [R53] |
| **Arbitrage eau ↔ PFAS** | Passer à l'immersion diphasique **réduit l'eau mais charge en PFAS** (§7) | Fortune [N9] ; Guardian [N10] |
| **Zones à risque** | **45 % des datacenters mondiaux** en bassins à pression élevée sur l'eau ; Amazon Aragón : **53,9 M L/an par centre** dans l'une des régions les plus sèches d'Europe ; Meta Toledo : **>600 M L/an** en zone à risque sécheresse | Guide Ville de Demain [R44] ; EU Perspectives [R50] ; DCD [R49] |
| **Absence de donnée en France** | « La publication des chiffres relatifs à la consommation d'eau reste soumise au **bon vouloir des industriels** » ; forages en Essonne « **plus ou moins déclarés** » | Reporterre, 30/01/2024 → `ecarts-...` [R42] |

### 9.2 Cadre et levier

- Seuls les cas **contractuels** ont produit un résultat : à Prineville, Apple et Meta ont financé un **stockage aquifère** parce que la ville était au plafond (`ecarts-...` §2.2).
- **Leviers** : publication annuelle des volumes **en m³ et en % de la production communale** (`ecarts-...` E1) ; **plafond de prélèvement contractuel** ; **obligation de boucle fermée** (0 prélèvement d'eau potable en régime normal) ; **mesure des eaux de purge (blowdown)** au titre de la pollution (§7).

---

## 10. PEU D'EMPLOIS CRÉÉS

### 10.1 Chiffres sourcés (les plus solides)

| Cas | Annonce | Réalité | Source |
|---|---|---|---|
| **Seine-Saint-Denis** | **1 600 postes** annoncés par les promoteurs | **500 seulement** auraient été créés (sénateur David Ros) | Sud Ouest / AFP, 01/06/2026 → `ecarts-...` [R19] |
| **Géorgie (États-Unis)** | **5 471 emplois** contre aides fiscales | **1 641** (**−70 %**) ; **289 000 $ d'exonérations par emploi** | Audit de l'État [R21] |
| **Virginie** | « 74 000 emplois soutenus » (2023) | **~50 emplois par facilité** ; **1,9 Md$** d'exonérations pour **1 610 emplois** (exercice 2025) = **1,2 M$/emploi** | JLARC / Governing [R11] [R12] |
| **Brookings (2026)** | L'emploi local est le bénéfice clé | Surestimation **×3** ; **100-200 emplois permanents par comté** ; **aucun effet** sur les salaires médians ; **+2 à +5 %** sur les prix de l'immobilier | Brookings [R22] |
| **Empreinte au sol** | — | **15 à 20 salariés** pour un datacenter là où un entrepôt logistique en emploie **300-400** ; **1 emploi par 24 M€** investis | Loup Cellard, sociologue [R19] [R20] |
| **Luleå (Suède)** | **30 000 emplois** (rapport Business Sweden) | **56 personnes en 2020**, ~90 aujourd'hui | Nordic Labour Journal / Yle [R24] |
| **xAI Memphis** | **300 emplois** | **32 postes** publiés | Memphis Flyer [R25] |
| **France — projection** | **93 Md€** annoncés (Choose France) pour **15 000 emplois** | Soit **6,2 M€/emploi annoncé**, sans bilan public à ce stade | La Dauphiné [R20] |
| **Projets en cours (annoncés, non vérifiés)** | Châteauroux **200 emplois** ; Rantigny **~100** ; Lachelle **150** ; Pennes-Mirabeau **~15** ; Fouju **300-500** | **Aucun bilan possible avant 2028-2029** | `ecarts-...` §4 [R37] [R38] [R41] [R27] |

### 10.2 Levier opposable

**Clause de retour des aides** en cas d'écart > 20 % à 5 ans (`ecarts-...` §7.2 E2) + **publication des effectifs permanents réels** (ET, pérennes, hors chantier) et non « emplois soutenus ».

---

## 11. MENSONGES SUR LA SOUVERAINETÉ NUMÉRIQUE

### 11.1 Ce qu'on promet vs ce que dit le contrôle

**Argument de vente** : construire des datacenters en France = « construire la souveraineté numérique ». **Diagnostiques officiels** : c'est précisément l'inverse quand l'opérateur, le financeur et le contrôle des données restent extra-européens.

### 11.2 Chiffres sourcés

| Donnée | Chiffre | Source |
|---|---|---|
| **Réservations électriques attribuées** | **15 GW réservés** à des projets de datacenters = **24 % du parc nucléaire** — dont **seulement 9 %** à des acteurs **européens** | Commission d'enquête AN, rapport du 08/07/2026 → Silicon.fr [N15] ; ChannelNews [N16] ; Vie publique [N14] |
| **Hébergement des données** | **70 % des données françaises** hébergées sur des clouds **surtout américains** ; **83 %** à l'échelle européenne ; **7 entreprises françaises sur 10** préfèrent une solution américaine (début 2024) | Institut Montaigne, via I'MTech, 07/01/2026 [N17] |
| **Part européenne en recul** | La part des acteurs européens dans le cloud est passée de **27 % (2017) à 15 % (2026)** | Commission d'enquête AN → Vie publique, 17/07/2026 [N14] |
| **Dépenses publiques** | **~70 % des dépenses publiques en infrastructures numériques** finissent chez Amazon, Microsoft ou Google (rapport Cour des comptes du 31/10/2025) ; **1 à 1,5 Md€** de dépendance chiffrée chez les grands éditeurs américains ; **~80 %** des achats de l'Ugap chez des sociétés américaines | L'Essentiel de l'Éco, 03/11/2025 [N21] ; ChannelNews [N16] |
| **Clouds « souverains » de l'État** | L'usage interministériel des clouds souverains **plafonne à 5 %** | Anne Le Hénanff, prononcé du 13/01/2026, Vie publique [N27] |
| **Label** | L'Anssi a accordé **SecNumCloud à Google Cloud** (via S3NS) — le label « garantit la protection contre le Cloud Act » selon Google lui-même | franceinfo, 03/07/2022 [N18] |
| **Cloud Act** | Google reste une **société américaine** soumise aux demandes d'accès de la justice américaine **même si les données sont en France** ; « **peu importe où est situé le data center, ce qui compte c'est qui le contrôle** » | franceinfo [N18] ; citation via AOC [N19] |
| **Contradiction citée en France** | « La **contradiction majeure** à vouloir construire la souveraineté numérique en accueillant Google à bras ouverts » (Jérémie Godet, élu régional) | France 24, 12/06/2026 [N20] |
| **Cadre juridique accéléré** | Loi du **15 avril 2026** étendant aux datacenters le régime dérogatoire de **projet d'intérêt national majeur** — « au bénéfice d'opérateurs extra-européens » | AOC, 10/05/2026 [N19] |
| **Lobbying** | **35 M€/an** de lobbying des GAFAM auprès de l'UE, **+50 % en 5 ans** | Commission d'enquête → ChannelNews [N16] |

### 11.3 La chaîne du mensonge, en trois temps

1. **« On héberge en France »** → localisation ≠ contrôle : le **Cloud Act** s'applique à l'entreprise, pas au bâtiment [N18].
2. **« C'est du souverain »** → seuls des **services certifiés SecNumCloud** échappent, et le label a été étendu à un opérateur américain [N18].
3. **« C'est de l'industrie française »** → **9 %** seulement de la capacité réservée profite à des acteurs européens [N15].

### 11.4 Levier opposable

- **Exiger la qualification du bénéficiaire réel** (nationalité du bailleur de fonds, exploitant, client final des données) pour tout projet présentée comme « souverain ».
- S'appuyer sur la recommandation de la commission d'enquête : **moratoire sur les datacenters ne répondant pas à un impératif de souveraineté** + **contrôle public renforcé** [N15] [N14].
- Exiger **SecNumCloud** et une clause de protection contre le Cloud Act pour toute donnée publique hébergée sur le site.

---

## 12. CADRE UNION EUROPÉENNE

### 12.1 Ce que l'UE impose déjà (en vigueur)

| Texte | Objet | Ce que ça change pour un projet | Source |
|---|---|---|---|
| **Directive (UE) 2023/1791** (recast EED), art. 12 + Annexe VII | Obligation annuelle de **reporting énergie + eau** pour tout datacenter **≥ 500 kW de puissance IT installée** ; publication d'un jeu d'informations ; habilitation de la Commission à proposer **standards de performance minimaux et labellisation** | Le haut de la filière **déjà déclarant** : les KPI existent, ils sont opposables comme référence de marché | EUR-Lex [N33] ; Commission UE [N28] |
| **Règlement délégué (UE) 2024/1364** (14/03/2024) | 1ʳᵉ phase du **schéma de notation commun** : KPI et méthodologie (PUE, WUE, ERF, REF, chaleur réemployée, température de consigne…) versés à la **base de données européenne** | Rapport annuel au **15 mai** (premier au 15/09/2024) ; **données individuelles non publiées** — seuls les agrégats UE/État le sont (et rien si moins de 3 DC dans une catégorie) | EUR-Lex [N29] |
| **Base de données européenne** + analyse de la Commission (rapport juillet 2025 sur les données 2024) | Premier état des lieux consolidé ; FAQ et points nationaux mis à jour (dernière version 28/07/2026) | Preuve qu'un **référentiel commun de mesures** est déjà opérationnel | Commission UE [N28] ; rapport d'analyse [N34] |
| **Règlement (UE) 2024/573 (f-gas)** | Fluides frigorigènes : réduction des fuites, plafonds de GWP, interdictions progressives | Cadrage des **fluides de climatisation** (§7.4) | EUR-Lex [N32] |
| **Règlement (UE) 2019/424** (écoconception serveurs) | Exigences d'efficacité sur **serveurs et stockage** — cadre transféré sous l'ESPR (UE) 2024/1781 | Équipements IT neufs : exigences minimales à la mise sur le marché | EUR-Lex [N35] |
| **Directive (UE) 2024/1275** (EPBD recast) | Bâtiments non résidentiels neufs **zéro émission** à l'horizon 2030, solaire, systèmes techniques du bâtiment | Applicable au **bâtiment** datacenter s'il entre dans le champ | EUR-Lex [N36] |
| **PFAS — restriction REACH universelle** | Proposition ECHA (janv. 2023) couvrant toute la famille chimique | Toucherait fluides diphasiques et frigorigènes si adoptée | **statut au 2026 [à confirmer]** |

### 12.2 Ce qui se prépare (à suivre)

| Détail | Échéance / statut | Source |
|---|---|---|
| **Data Centre Energy Efficiency Package** : projet de règlement instaurant le **schéma de notation UE** pour DC + lancement du travail sur les **standards de performance minimaux** | Call for feedback UE du **26/03 au 23/04/2026** ; texte à venir | Commission UE [N28] |
| **CADA — Cloud and AI Development Act**, proposition **COM(2026) 502 du 03/06/2026** : **tripler la capacité de datacenters de l'UE en 5-7 ans**, simplification/accélération des permis, « **zones d'accélération** » (art. 10, avec préférence pour les sites brownfield et la réemploi de chaleur fatale), accès à l'énergie, l'eau, la terre et le financement, cadre de souveraineté cloud à **4 niveaux de garantie** pour les pouvoirs publics | **Proposition uniquement** — procédure législative en cours (avis CDE du 23/09/2026) ; ne pas citer comme loi adoptée | Commission UE [N30] ; Parlement européen, Legislative Train [N31] |

### 12.3 Ce que l'UE NE réglemente PAS (limites)

- **Pas de seuil de bruit ni de pollution lumineuse** au niveau UE → reste national (ICPE 70/60 dB(A), décret du 27/12/2018) → §5.3, §6.3.
- **Pas d'autorisation d'implantation ni de moratoire** : l'urbanisme et le foncier restent nationaux (en France : régime PINM, §1.3).
- **Eau** : aucune régulation spécifique aux DC — uniquement le droit commun (directive-cadre eau, SQE) ; le WUE n'est qu'un **KPI déclaratif**, pas un plafond → §9.
- **Le reporting UE n'est pas directement opposable au cas par cas** : données individuelles non publiées, agrégats seulement → s'en servir comme **exigence de preuve** (12.4), pas comme outil de contestation publique.
- **Chaleur locale, PFAS sur site, emplois, souveraineté** : hors champ du reporting UE → cadres nationaux et §4, §7, §10, §11.

### 12.4 Levier opposable (usage du cadre UE)

1. **Exiger la preuve d'inscription** du projet dans la base de données européenne (ou l'expliquer si < 500 kW IT) et la **remise annuelle du reporting** (KPI PUE/WUE/ERF/REF) comme pièce du dossier.
2. **Caler les exigences contractuelles sur les KPI du règlement 2024/1364** (mêmes définitions, même méthodologie) : évite la divergence de protocole (schéma P4 d'`ecarts-...`) et rend les pénalités vérifiables.
3. **Suivre le rating scheme et les standards minimaux à venir** : anticiper le haut de classe plutôt que subir le futur seuil.
4. **Sur le CADA** : documenter la demande à l'inverse du texte (accélération des permis) — exiger que toute « zone d'accélération » soit conditionnée à une **évaluation d'impact social et environnemental** (demande déjà portée par le CDE, avis du 23/09/2026 [N31]).

---

## 13. GRILLE DE SYNTHÈSE

| # | Nuisance | Échelle | Délai d'apparition | Opposabilité actuelle | Source pivote |
|---|---|---|---|---|---|
| 1 | Terres agricoles | **Définitive** (imperméabilisation) | À la construction | Forte (PLU, SDAGE, ZAN) — **faiblie par le PINM** | [N19] [N20] |
| 2 | Biodiversité | Locale (site + périphérie) | Immédiate, puis cumulative | Forte (L.411-1/L.411-2) si études fournies **avant** permis | `ecarts-...` [R34] |
| 3 | Tension réseau / usagers | **Territoriale → national** | Dès la réservation de puissance | Moyenne (délibérations, régulateur) | [N15] [R11] |
| 4 | Températures | **500 m à 10 km** selon méthode | Dès la mise en service | Faible aujourd'hui (aucune mesure obligatoire) | [N1] [N3] |
| 5 | Bruit | **100 m à ~1 km** | Immédiate | Forte (ICPE 70/60, émergence 5/3) | `NuisancesSonores.md` |
| 6 | Lumineuse | Périphérie nocturne | Immédiate | **Forte : décret 27/12/2018 déjà applicable** | [N7] |
| 7 | PFAS | Site + chaîne amont | Différée (cumul) | Faible (données opérateur, boucle fermée invoquée) | [N9] [N12] |
| 8 | Consommation électrique | Régionale/nationale | Dès la demande de raccordement | Moyenne (avis RTE, régulateur) | [N15] [N19] |
| 9 | Eau | Communale (curseur % municipal) | Sècheresse révélatrice | **Faible : pas de publication obligatoire en France** | [R1] [R42] |
| 10 | Emplois | Local | Bilan à 3-5 ans | Moyenne (clause de retour d'aides possible) | [R19] [R21] |
| 11 | Souveraineté | **Nationale** | Immédiate (thématique) | Forte (rapport parlementaire, propositions) | [N15] [N14] |

**Lecture :** les nuisances **1, 5, 6, 11** sont opposables dès aujourd'hui ; les nuisances **4, 7, 9** sont les plus difficiles à prouver **parce que la mesure n'est pas obligatoire** — d'où les exigences du §14.

---

## 14. EXIGENCES À POSER (RECAP)

Reprises de `generalites/ecarts-annonces-realisite-datacenters.md` §7.2, complétées par les axes de ce document :

| # | Exigence | Axe(s) |
|---|---|---|
| **E1** | Publication annuelle des volumes d'eau **en m³ et en % de la production communale** | 9 |
| **E2** | Engagement chiffré d'emplois permanents + **clause de retour des aides** (écart > 20 % à 5 ans) | 10 |
| **E3** | **Plafond de puissance par phase**, interdiction d'extension sans nouvelle autorisation | 3, 8 |
| **E4** | **Campagne acoustique ISO 1996-2** avant travaux, à T+3 et T+12 mois, bureau indépendant | 5 |
| **E5** | Publication de la **puissance de raccordement par phase** et de sa **répartition par usage** du site | 3, 8 |
| **E6** | Mesures de contrôle (eau, bruit, **température**) financées par le pétitionnaire **mais choisies par la collectivité** | 4, 5, 9 |
| **E7** *(nouveau)* | **Plan d'éclairage nocturne** conforme au décret du 27/12/2018 (ULR < 1 %, CCT ≤ 3000 K, couvre-feu, 2 lux en parking) + relevé contradictoire à T+3 mois | 6 |
| **E8** *(nouveau)* | **Inventaire des fluides** (PFAS/f-gas, tonnage, fin de vie) et **interdiction de l'immersion diphasique PFAS** | 7 |
| **E9** *(nouveau)* | **Qualification du bénéficiaire réel** (bailleur, exploitant, client des données) et clause SecNumCloud / Cloud Act pour toute donnée publique | 11 |
| **E10** *(nouveau)* | **Recalibrage foncier** (surface bâtie utile vs emprise) + **remise en état agronomique** contractuelle ; refus du régime PINM si le projet ne répond pas à un impératif de souveraineté | 1, 2 |

---

## 15. POINTS À CONFIRMER

1. **URL Légifrance exacte** de l'objectif de zéro artificialisation nette (art. L.101-1 CRDU) — à ne pas citer sans vérification.
2. **Chiffre de chaleur revendiqué à Châteauroux (+2 à +7 °C)** : affirmation d'opposants, **aucune mesure** → ne pas utiliser comme fait.
3. **Rapport de la commission d'enquête du 8 juillet 2026** : récupérer le texte intégral (18 propositions, 29 selon une autre reprise — **les deux chiffres circulent**) pour citer exactement.
4. **Rapport Cour des comptes du 31/10/2025** : retrouver le document original (la donnée des 70 % vient ici d'un relais presse, niveau S3).
5. **Contradiction mesurée sur la chaleur** : ASU (air, +0,7 à +2,2 °C) vs Cambridge (surface satellite, +2 °C moyen) vs Uptime (« contributeur mineur ») — les trois coexistent ; **ne pas présenter un seul chiffre comme définitif**.
6. **Volumes PFAS réels** : les tonnages cités viennent d'ONG ou d'estimations de constructeurs, **jamais d'un inventaire réglementaire public**.
7. **Éclairage du site** : vérifier si le PC impose le décret de 2018 (il s'applique par droit commun, mais **les mesures de conformité ne sont pas systématiquement contrôlées**).
8. **Statut de la restriction PFAS (REACH)** : la proposition universelle d'ECHA (janv. 2023) est-elle adoptée en 2026 ? Vérifier avant tout usage comme cadre opposable (§12.1).
9. **CADA** : suivre l'évolution de la proposition COM(2026) 502 (adoption, contenu des articles 7 et 10) — **ne citer qu'à son statut réel** (§12.2).

---

## 16. RÉFÉRENCES

**Chaleur**
- [N1] ASU News — *Turning down the heat from data centers*, 18/05/2026 — https://news.asu.edu/20260518-environment-and-sustainability-turning-down-heat-data-centers
- [N2] ASME *Journal of Engineering for Sustainable Buildings and Cities* — *Data Center Waste Heat as an Emerging Urban Thermal Hazard: First Field Measurements…* — https://asmedigitalcollection.asme.org/sustainablebuildings/article/7/2/024501/1233035/Data-Center-Waste-Heat-as-an-Emerging-Urban
- [N3] CNN — *Data centers are creating 'heat islands' and warming the land around them by up to 16 degrees*, 30/03/2026 — https://www.cnn.com/2026/03/30/climate/data-centers-are-having-an-underrported
- [N4] The Guardian — *'Slough is like an experiment': Europe's largest datacentre hub leaves town sweltering*, 26/06/2026 — https://www.theguardian.com/environment/2026/jun/26/slough-is-like-an-experiment-europes-largest-datacentre-hub-leaves-town-sweltering
- [N5] Uptime Institute — *Data centers face new scrutiny over heat island effect* — https://journal.uptimeinstitute.com/data-centers-face-new-scrutiny-over-heat-island-effect/
- [N23] The Independent — *Data centers are creating 'heat islands'… warming them by up to 16 degrees*, 31/03/2026 — https://www.independent.co.uk/climate-change/ai-data-center-heat-islands-usage-climate-b2949418.html

**Lumière**
- [N6] DarkSky International — *Data center light pollution | DarkSky's statement on responsible development*, 04/06/2026 — https://darksky.org/news/data-center-light-pollution-darkskys-statement-on-responsible-development
- [N7] Légifrance — Décret n° 2018-1157 du 27 décembre 2018 relatif à la prévention, à la réduction et à la limitation des nuisances lumineuses — https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000037864346
- [N8] DarkSky International — *France Adopts National Light Pollution Policy* (rappel des obligations, y compris information du propriétaire) — https://darksky.org/news/france-light-pollution-law-2018
- [N24] The Times — *Put that light out! France orders cities to go dark at night*, 30/06/2013 (interdiction 1 h-7 h, 750 000 ménages, 200 M€/an) — https://www.thetimes.com/travel/destinations/europe-travel/france/paris/put-that-light-out-france-orders-cities-to-go-dark-at-night-tv6ptnrttgb

**PFAS**
- [N9] Fortune — *Data centers are swapping water for forever chemicals to keep AI cool*, 18/09/2026 (rapport ChemSec ; Daikin/Arkema/Chemours ; lettre de 17 ONG à l'EPA) — https://www.fortune.com/2026/09/18/data-centers-ai-compute-pfas-forever-chemicals-water
- [N10] The Guardian — *US environmental groups urge EPA to reject new PFAS to cool datacenters*, 27/07/2026 (réponse Chemours : « boucle fermée ») — https://www.theguardian.com/us-news/2026/jul/27/pfas-datacenter-cooling-epa
- [N11] Food & Water Watch — *Toxic Mixture: Data Centers Turn to PFAS For Cooling*, 07/2026 — https://www.foodandwaterwatch.org/wp-content/uploads/2026/07/FSW_2607_DataCenterPFAS.pdf
- [N12] Environmental and Energy Study Institute (EESI) — *Data Centers Are Contributing to PFAS Forever Chemical Pollution* — https://www.eesi.org/articles/view/data-centers-are-contributing-to-pfas-forever-chemical-pollution
- [N13] EHN — *AI Data Center Health Impacts*, 01/02/2026 (accord collectif Amazon Oregon 20,5 M$ ; composition du blowdown) — https://www.ehn.org/ai-data-center-health-impacts
- [N25] CPEO — *Forever Chemicals at Data Centers*, 29/06/2026 — https://cpeo.org/pubs/ForeverDataCenters.pdf
- [N26] Umweltbundesamt (DE) — *Climate-friendly Air-Conditioning with Natural Refrigerants* (règlement F-gas UE 517/2014) — https://www.umweltbundesamt.de/system/files/medien/376/dokumente/climate-friendly_air-conditioning_with_natural_refrigerants_factsheet.pdf

**Réseau, souveraineté, cadre français**
- [N14] Vie publique — *Quelles pistes pour renforcer la souveraineté numérique de la France ?*, 17/07/2026 (rapport de commission d'enquête du 08/07/2026 ; part européenne 27 % → 15 %) — https://www.vie-publique.fr/en-bref/304051-quelles-pistes-pour-renforcer-la-souverainete-numerique-de-la-france
- [N15] Silicon.fr — *29 propositions pour reconquérir la souveraineté numérique*, 17/07/2026 (15 GW réservés = 24 % du parc nucléaire ; 264 Md€ de cloud achetés par les Européens aux États-Unis ; moratoire proposé) — https://www.silicon.fr/business-1367/open-source-moratoire-sur-les-data-centers-29-propositions-pour-reconquerir-la-souverainete-numerique-228300
- [N16] ChannelNews — *Zoom sur la dépendance numérique de la France par une commission d'enquête parlementaire*, 16/07/2026 (9 % de capacité à des acteurs européens ; 1-1,5 Md$ ; ~80 % des achats Ugap ; 35 M€ de lobbying) — https://www.channelnews.fr/zoom-sur-la-dependance-numerique-de-la-france-par-une-commission-denquete-parlementaire-158042
- [N17] I'MTech (Institut Mines-Télécom) — *Preserving French digital sovereignty: the "critical move"*, 07/01/2026 (Institut Montaigne : 70 % des données françaises et 83 % européennes sur cloud américain) — https://imtech.imt.fr/en/2026/01/07/preserving-french-digital-sovereignty-the-critical-move
- [N18] franceinfo — *Google Cloud : souveraineté non garantie malgré des serveurs désormais en France*, 03/07/2022 (Cloud Act, SecNumCloud) — https://www.radiofrance.fr/franceinfo/podcasts/nouveau-monde/nouveau-monde-du-dimanche-03-juillet-2022-8741802
- [N19] AOC (Jérémy Bousquet, juriste) — *Méga data centers : la souveraineté numérique contre l'écologie*, 10/05/2026 (loi du 15/04/2026 PINM ; Arcep +8 % / +19 % ; AIE ×2 d'ici 2030, IA 40 % ; Marseille 200 000 foyers ; 348 datacenters recensés) — https://aoc.media/analyse/2026/05/10/mega-data-centers-la-souverainete-numerique-contre-lecologie
- [N20] France 24 / AFP — *En France, l'arrivée d'énormes centres de données bouscule les territoires*, 12/06/2026 (Ademe ×4 d'ici 2035 ; Châteauroux 1,2-1,3 GW > Indre ; RTE 90 km / 300 M€ ; « contradiction majeure » souveraineté) — https://www.france24.com/fr/info-en-continu/20260612-en-france-l-arriv%C3%A9e-d-%C3%A9normes-centres-de-donn%C3%A9es-bouscule-les-territoires
- [N21] L'Essentiel de l'Éco — *Souveraineté numérique : la France à la dérive*, 03/11/2025 (relais du rapport Cour des comptes du 31/10/2025 : ~70 % des dépenses publiques chez AWS/Microsoft/Google) — https://lessentieldeleco.fr/4151-souverainete-numerique-la-france-a-la-derive
- [N27] Vie publique — Prononcé d'Anne Le Hénanff, 13/01/2026 (usage interministériel des clouds souverains ≈ 5 %) — https://www.vie-publique.fr/discours/301739-anne-le-henanff-13012026-numerique
- [N22] Entergy — *Data centers and Entergy customers* (argumentaire de l'opérateur : 2,8 Md$ de bénéfices clients en 20 ans) — https://www.entergy.com/datacenters/louisiana

**Cadre Union européenne**
- [N28] Commission européenne (DG ENER) — *Energy performance of data centres* (art. 12 EED, base de données européenne, règlement délégué 2024/1364, Data Centre Energy Efficiency Package, call for feedback rating scheme 26/03–23/04/2026, FAQ du 28/07/2026) — https://energy.ec.europa.eu/topics/energy-efficiency/energy-efficiency-targets-directive-and-rules/energy-efficiency-directive/energy-performance-data-centres_en
- [N29] EUR-Lex — Règlement délégué (UE) **2024/1364** du 14/03/2024, 1ʳᵉ phase du schéma commun de notation des datacenters (≥ 500 kW IT, rapports au 15 mai, KPI PUE/WUE/ERF/REF) — https://eur-lex.europa.eu/eli/reg_del/2024/1364/oj
- [N30] Commission européenne — *Cloud and AI Development Act (CADA)*, proposition **COM(2026) 502** du 03/06/2026 (tripler la capacité DC de l'UE en 5-7 ans, permis, zones d'accélération, 4 niveaux de souveraineté) — https://digital-strategy.ec.europa.eu/en/policies/cloud-and-ai-development-act
- [N31] Parlement européen — Legislative Train, *Cloud and AI development act* (procédure en cours ; avis du CDE INT/1126-EESC-2026-01043, adopté le 23/09/2026, propose de conditionner les zones d'accélération à une évaluation d'impact social et environnemental) — https://www.europarl.europa.eu/legislative-train/theme-a-new-plan-for-europe-s-sustainable-prosperity-and-competitiveness/file-cloud-and-ai-development-act
- [N32] EUR-Lex — Règlement (UE) **2024/573** du 07/02/2024 relatif aux gaz à effet de serre fluorés (f-gas, remplace le règlement 517/2014) — https://eur-lex.europa.eu/eli/reg/2024/573/oj
- [N33] EUR-Lex — Directive (UE) **2023/1791** du 13/09/2023 sur l'efficacité énergétique (recast), art. 12 + Annexe VII (reporting des datacenters) — https://eur-lex.europa.eu/eli/dir/2023/1791/oj
- [N34] Publications Office de l'UE — rapport de la Commission, *analysis of the data submitted in the 2024 reporting period* (juillet 2025) — https://op.europa.eu/en/publication-detail/-/publication/83be4c3e-5c79-11f0-a9d0-01aa75ed71a1/language-en
- [N35] EUR-Lex — Règlement (UE) **2019/424** : exigences d'écoconception pour les serveurs et produits de stockage de données (cadre transféré sous l'ESPR 2024/1781) — https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32019R0424
- [N36] EUR-Lex — Directive (UE) **2024/1275** du 24/04/2024 sur la performance énergétique des bâtiments (recast) — https://eur-lex.europa.eu/eli/dir/2024/1275/oj

**Corpus général (sources internes)**
- `generalites/NuisancesSonores.md` — sources techniques bruit (CIDB/Bruit.fr, Gamba Acoustique, infrasons), seuils ICPE et R.1336-5
- `generalites/refroidissement-generalisation-300MW.md` — 100 % de la charge IT → chaleur à évacuer, WUE/PUE
- `generalites/ecarts-annonces-realisite-datacenters.md` — cas sourcés annonce/réalité (références [R##])

---

*Document de travail — octobre 2026. Portée **générale** (aucun site particulier) : applicable à tout projet de datacenter en France. Chaque chiffre des §1 à §12 porte une référence [N##] (URL au §16), une référence [R##] (`ecarts-annonces-realisite-datacenters.md` §9) ou une source interne du corpus `generalites/`. Les éléments marqués **[à confirmer]** et les revendications non mesurées (§4, §15) ne doivent pas être utilisés comme faits.*
