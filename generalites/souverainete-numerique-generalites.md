# SOUVERAINETÉ NUMÉRIQUE — GUIDE GÉNÉRALISTE

**Objet** : doctrine réutilisable pour évaluer la souveraineté de tout projet cloud / datacenter / IA, sans référence à un site particulier
**Date** : Septembre 2026
**Statut** : Document de travail — généraliste
**Documents liés** : doctrine GPU et puissance de calcul (pénurie HBM/CoWoS, coûts, délais — voir dossier technique du projet)

---

## TABLE DES MATIÈRES

1. [Définition](#1-définition--ce-que-souverain-veut-dire)
2. [Les 5 couches](#2-les-5-couches-de-souveraineté)
3. [Cadre juridique](#3-cadre-juridique) (dont 3.6 : loi russe — précédent technique, pas modèle ; 3.7 : autres lois nationales)
4. [Chaîne technique](#4-chaîne-de-dépendance-technique)
5. [Niveaux d'hébergement](#5-niveaux-dhébergement-1--4)
6. [Grille d'évaluation générique](#6-grille-dévaluation-générique--10-tests)
7. [Clauses types de cahier des charges](#7-clauses-types-de-cahier-des-charges)
8. [Arbre de décision : louer vs construire](#8-arbre-de-décision--louer-vs-construire)
9. [Idées reçues](#9-idées-reçues-fréquentes)
10. [Références](#10-références)

---

## 1. DÉFINITION — CE QUE « SOUVERAIN » VEUT DIRE

La souveraineté numérique = la capacité d'un acteur (État, collectivité, entreprise) à **choisir, contrôler et révoquer** les conditions de traitement de ses données et de son calcul, sans dépendre d'une autorisation étrangère.

Elle se mesure sur trois axes :

| Axe | Question | Exemple d'échec |
|---|---|---|
| **Juridique** | Qui peut légalement exiger mes données ? | Hébergeur soumis à une loi extraterritoriale (CLOUD Act) |
| **Technique** | Puis-je fonctionner si un fournisseur coupe ? | Stack CUDA sans alternative, firmware non auditable |
| **Économique** | Puis-je sortir à coût et délai raisonnables ? | 30 ans de bail + raccordement dédié + formats fermés |

Un projet n'est souverain que s'il passe les trois axes. Le bâtiment seul ne valide aucun des trois.

---

## 2. LES 5 COUCHES DE SOUVERAINETÉ

| Couche | Contenu | Exemples de dépendance |
|---|---|---|
| **1. Foncier / bâti / énergie** | Sol, bâtiment, raccordement électrique, fibre, eau, refroidissement | Bail longue durée, sous-station dédiée financée par le public, PUE non contractuel |
| **2. Hardware** | GPU, CPU, mémoire HBM, stockage, réseau, onduleurs | NVIDIA, TSMC, SK Hynix / Samsung / Micron, Mellanox |
| **3. Logiciel / firmware** | Hyperviseur, orchestration, pilotes, CUDA/ROCm, OS, télémétrie | CUDA, stack hyperscaler, support niveau 3 hors UE |
| **4. Opérateur / données** | Qui exploite, supervise, détient les clés, où sont les sauvegardes | Maison mère extra-UE, supervision 24/7 hors UE |
| **5. Compétences / réversibilité** | Qui sait exploiter, auditer, migrer, former | Équipe 100 % prestataire, documentation fermée, formats propriétaires |

**Règle du maillon faible** : le niveau global = le niveau de la couche la plus basse. Un bâtiment national + opérateur étranger + puces étrangères = projet non souverain.

---

## 3. CADRE JURIDIQUE

### 3.1 Conflit de lois : le point central

| Texte | Portée | Effet pratique |
|---|---|---|
| **CLOUD Act** (US, 2018) | Toute société US doit remettre les données sur mandat US, **où qu'elles soient stockées** | Un datacenter en Europe opéré par une société US reste saisissable depuis les US |
| **FISA 702** (US) | Surveillance des non-Américains hors US | Interception possible sans notification à la personne concernée |
| **RGPD** (UE) | Interdit les transferts sans base légale ni garanties suffisantes | S'appuyer sur un opérateur soumis au CLOUD Act expose à une violation (logique Schrems II) |
| **Data Act** (UE, applicable 2025) | Encadre l'accès des gouvernements et tiers aux données industrielles | Conflit frontal : l'opérateur peut devoir choisir quelle loi violer |
| **NIS2 / DORA** (UE) | Exigences cyber, résilience, notification pour opérateurs critiques et secteur financier | Un opérateur hors UE complique audit, notification et contrôle |

### 3.2 Fait établi : les promesses contractuelles ne protègent pas

> En juin 2025, le directeur juridique de Microsoft France a confirmé **sous serment devant le Sénat** qu'il ne pouvait pas garantir que les données européennes ne seraient pas transmises aux autorités américaines.

Conséquence : seule la **structure** (capital, contrôle, technique, localisation de la supervision) protège. Aucune clause « vos données restent en Europe » signée par une société soumise au CLOUD Act n'est opposable à un ordre américain.

### 3.3 SecNumCloud (ANSSI) — le filtre de référence en France

| Exigence | Pourquoi c'est discriminant |
|---|---|
| Capital et contrôle européens, sans veto extra-européen | Exclut les hyperscalers US même en « région France » |
| Démonstration d'immunité extraterritoriale | Exclut les licences tech avec clause d'audit ou de mise à jour imposée depuis hors UE |
| Hébergement, supervision et support en UE | Exclut le support 24/7 externalisé hors UE sous contrôle extra-européen |
| Audit ANSSI, pentest, plan de sortie | Vérifiable, renouvelable, opposable |

Sans certification de ce type, le mot « souverain » n'a **aucune valeur opposable** pour des données publiques, critiques ou de santé (voir aussi HDS pour la santé, ISO 27001 pour l'hygiène de base — nécessaires mais non suffisantes).

### 3.4 CADA — Cloud & AI Development Act (UE, en vigueur 04/08/2026)

| Point | Détail |
|---|---|
| Adoption / entrée en vigueur | Adopté 03/06/2026, publié 15/07/2026, en vigueur **04/08/2026** |
| Objectif | **Tripler** la capacité datacenter européenne d'ici 2030 |
| Mécanisme | Guichet unique par État membre, permis accéléré — **sans dispense** d'étude d'impact ni de droit de l'environnement |
| Classification | 4 niveaux de souveraineté (cf. §5) — les marchés publics sensibles exigeront les niveaux 3-4 |
| Conditionnalité attendue | Énergie bas-carbone, efficacité (PUE), valorisation de la chaleur fatale, sobriété hydrique |

### 3.5 GAIA-X et labels d'interopérabilité

Utiles pour la portabilité et la transparence, **insuffisants** comme preuve d'immunité juridique. Un service « GAIA-X compliant » opéré par une société soumise au CLOUD Act reste soumis au CLOUD Act.

### 3.6 Loi russe sur l'autonomie numérique (« internet souverain », Runet) — précédent technique, pas modèle

> Ajoutée à titre documentaire : le contexte géopolitique européen n'est pas celui de la Russie, et la doctrine du présent guide reste celle de l'État de droit (droits fondamentaux, contrôle juridictionnel, proportionnalité). La loi russe est citée comme **précédent technique** — le seul État à avoir légiféré et testé une déconnexion nationale — pas comme modèle politique.

| Point | Contenu |
|---|---|
| **Texte** | Loi fédérale n° 90-FZ du 01/05/2019 modifiant les lois « Sur les communications » et « Sur l'information, les technologies de l'information et la protection de l'information » (projet n° 608767-7) |
| **Calendrier** | Douma 16/04/2019, Conseil de la Fédération 22/04/2019, signature 01/05/2019, entrée en vigueur **01/11/2019**, DNS national pleinement exigible au **01/01/2021** |
| **Motif officiel** | Exposé des motifs : répondre au « caractère agressif » de la stratégie cyber américaine de 2018 ; garantir le fonctionnement du Runet en cas de menace extérieure ou d'urgence |
| **Pilotage** | Ministère du numérique (MoC) + **Roskomnadzor** : surveillance des menaces, gestion **centralisée** du routage en cas de menace, instructions aux opérateurs |
| **Mesures** | Registre des points d'échange (IXP) agréés ; boîtiers **DPI/TSPU** fournis par l'État et installés chez les FAI (filtrage, blocage, reroutage) ; contrôle du trafic transfrontalier ; **DNS national** ; **exercices annuels** obligatoires de déconnexion |
| **Tests** | Exercices avec les grands opérateurs 15/06–15/07/2021, déclarés concluants par les autorités (durée et portée exactes non publiées) |
| **Critiques documentées** | HRW, RSF, Internet Society : blocage **extrajudiciaire et opaque**, « menace » non définie, faisabilité d'une isolation complète contestée (dizaines d'IXP, centaines d'opérateurs internationaux), atteintes à la liberté d'expression et à la vie privée |

**Socle connexe (pour mémoire)** : localisation des données personnelles (loi 152-FZ), obligations de conservation (lois dites « Iarovaïa »), politique de substitution aux importations logicielles/matérielles. Chaque brique renforce l'autonomie technique **au prix d'un contrôle étatique direct** — l'inverse du modèle européen visé ici (certification indépendante type ANSSI, réversibilité client, labels ouverts).

**Quatre modèles comparés** :

| Modèle | Logique | Levier | Coût affiché |
|---|---|---|---|
| **US** (CLOUD Act, FISA 702) | Projection extraterritoriale du droit | Juridiction sur les sociétés US où qu'elles opèrent | Perte de confiance des clients étrangers |
| **UE** (RGPD, CADA, SecNumCloud) | Protection + certification + marché | Norme opposable, audit indépendant | Lenteur, fragmentation, dépendance hardware persistante |
| **CN** (Grand pare-feu, contrôle des opérateurs) | Filtrage dès la conception, opérateurs concentrés | Architecture fermée native | Isolement, coût d'innovation |
| **RU** (90-FZ, Runet) | Autonomie de repli + contrôle centralisé | DPI d'État, DNS national, exercices | Opacité, contestation technique, atteintes aux libertés |

**Enseignement réutilisable** : l'autonomie de routage (IXP maîtrisés, DNS redondant, exercices de résilience) est une brique légitime de toute doctrine — l'UE la traite via NIS2 et la résilience des infrastructures critiques, **avec garanties juridictionnelles**, ce que la loi russe ne prévoit pas.

### 3.7 Autres lois nationales traitant l'autonomie numérique — panorama comparé

> Même avertissement qu'en 3.6 : ces textes sont cités pour outiller l'analyse (ce que chaque État juge critique et avec quels instruments), pas pour importer leurs arbitrages politiques.

| Pays | Texte(s) | Dates clés | Objet autonomie numérique | Instrument distinctif |
|---|---|---|---|---|
| **Chine** | Loi cybersécurité (CSL) ; Loi sécurité des données (DSL) ; Loi protection des informations personnelles (PIPL) | CSL en vigueur 01/06/2017 ; DSL adoptée 10/06/2021, en vigueur 01/09/2021 ; PIPL adoptée 20/08/2021, en vigueur 01/11/2021 | Triptyque : sécurité des réseaux + classification des données (« importantes », « cœur ») + droits personnels ; extraterritorialité revendiquée (DSL art. 2, PIPL art. 3) | Localisation pour opérateurs d'infrastructures critiques (CIIO) ; **évaluation de sécurité CAC** avant tout transfert transfrontalier ; Grand pare-feu antérieur comme infrastructure de filtrage |
| **Inde** | Digital Personal Data Protection Act (DPDP Act) + DPDP Rules | Loi promulguée 11/08/2023 ; règles notifiées 14/11/2025 (mise en œuvre phasée 2026-2027) | Droits des personnes + obligations des « data fiduciaries », amendes jusqu'à 250 crores ₹ (~27 M€) | Transferts autorisés **sauf liste noire** notifiée par l'État (approche permissive inversée) ; localisation sectorielle maintenue (ex. paiements, banque centrale RBI) |
| **France** | Loi **SREN** (sécuriser et réguler l'espace numérique) | Promulguée 21/05/2024 | Décline DSA/DMA/Data Act en droit interne, **en avance** sur le Data Act pour le cloud | Interdiction des crédits cloud ouverts et des ventes liées infra/logiciel ; extension du champ de la loi de 1978 au pistage depuis hors UE ; pouvoirs ARCOM |
| **Allemagne** | Loi sécurité IT 2.0 (IT-Sicherheitsgesetz 2.0) | Adoptée mai 2021 | Renforce le BSI et les obligations des infrastructures critiques (KRITIS) | Contrôle des composants critiques télécoms (clause Huawei 5G) ; label de sécurité C5 du BSI pour le cloud |
| **États-Unis** | CLOUD Act + FISA 702 (cf. 3.1) ; CHIPS & Science Act | CLOUD Act 2018 ; CHIPS promulgué 08/2022 (~52 Md$ semi-conducteurs) | Projection juridique extraterritoriale **+** reshoring industriel (fonderies Arizona/Ohio, R&D) | Le seul État à combiner contrainte sur les données mondiales **et** subventions massives au hardware |

**Lecture transversale** :

1. Tous les grands États lient désormais **données + infrastructures + hardware** dans un même raisonnement — la doctrine des 5 couches (§2) n'est pas une invention européenne.
2. Deux familles : **contrôle des flux** (CN, RU, IN-sectoriel : où vont les données ?) vs **contrôle des acteurs** (UE : qui opère, avec quelle certification ?) vs **projection + reshoring** (US : mon droit suit mes sociétés, mes usines reviennent).
3. Le modèle UE/FR reste le seul à faire de la **certification indépendante et de la réversibilité client** le cœur du dispositif plutôt que le filtrage ou l'interdiction — c'est ce qui rend SecNumCloud, CADA et SREN directement utilisables dans un cahier des charges sans changer de régime politique.

---

## 4. CHAÎNE DE DÉPENDANCE TECHNIQUE

| Maillon | Situation 2026 | Levier européen existant ? |
|---|---|---|
| **GPU / accélérateurs** | NVIDIA >80 % du marché, CUDA standard depuis 17 ans | Non à l'échelle (recherche : RISC-V, BSC) |
| **Mémoire HBM3/HBM3e** | SK Hynix, Samsung, Micron — 100 % vendue pour 2026 | Non |
| **Empaquetage avancé (CoWoS)** | TSMC uniquement, saturé jusqu'à mi-2027 | Non |
| **Fonderie ≤7 nm** | TSMC (TW) ; SMIC plafonné à 7 nm sans EUV | Partiel : **ASML (NL)** détient le monopole mondial des machines EUV — levier majeur mais indirect (ne fabrique pas de puces) |
| **Interconnexion intra-cluster** | NVLink / NVSwitch / InfiniBand (écosystème NVIDIA) | Partiel : Ethernet ouvert comme alternative, moins performant à iso-périmètre |
| **Stacks logicielles** | CUDA (NVIDIA) dominant ; ROCm (AMD) ouvert mais en retard ; CANN (Huawei) hors Europe | Partiel : modèles ouverts européens (ex. Mistral), écosystème open source |
| **Modèles IA** | US, chinois et européens coexistent en open weights | Oui : atout européen réel côté modèles, mais l'inférence tourne sur hardware non européen |

**Lecture** : l'Europe tient des bouts décisifs en **amont lointain** (ASML) et en **aval logiciel** (modèles ouverts, opérateurs), et presque rien au **milieu** (fonderie avancée, HBM, GPU, CUDA). Construire un bâtiment ne déplace aucun de ces maillons. La souveraineté achetable à court terme, c'est : **opérateur + certification + réversibilité + sobriété énergétique contractualisée**.

Repères chiffrés (détail dans le document parent) : délais H100/H200 de 36-52 semaines en 2026, prix spot +20-30 %, normalisation attendue 2028-2029, capex hyperscalers 600-630 Md$ en 2026.

---

## 5. NIVEAUX D'HÉBERGEMENT 1 → 4

| Niveau | Montage | Exposition extraterritoriale | SecNumCloud envisageable ? | Exemples types |
|---|---|---|---|---|
| **1 — Cloud étranger en Europe** | Serveurs en UE, société étrangère | Élevée | Non | Hyperscalers US en offre standard |
| **2 — Filiale locale dédiée** | Filiale européenne, maison mère étrangère | Moyenne-élevée | Non (ou équivalence fragile) | Offres « souveraines » de groupes étrangers |
| **3 — Opérateur européen + techno étrangère sous licence** | Société européenne, briques étrangères licenciées | Réduite mais résiduelle (firmware, mises à jour, support) | Oui sous conditions strictes | Co-entreprises type S3NS (Google/Thales), Bleu (Microsoft/Orange) |
| **4 — 100 % européen** | Capital, contrôle, exploitation et support en Europe | Nulle (à périmètre constant) | Oui (si audit ANSSI) | OVHcloud, Scaleway, 3DS Outscale, Clever Cloud, DEEP, IONOS |

Exemples datés (sept. 2026) : OVHcloud (SecNumCloud, HDS, 46 datacenters), Scaleway (seul européen avec Blackwell B300, SecNumCloud en cours), 3DS Outscale (SecNumCloud 3.2 depuis 2025). Contrat de référence : la Commission européenne a attribué en avril 2026 un contrat de **180 M€** pour son cloud à **quatre fournisseurs européens** (OVHcloud, Scaleway, Clever Cloud, DEEP).

**Usage recommandé** : données critiques / publiques / santé → niveau 4. Calcul banalisé non sensible → niveau 3 acceptable **si dit explicitement**. Niveau 1-2 + étiquette « souverain » = contradiction à relever systématiquement.

---

## 6. GRILLE D'ÉVALUATION GÉNÉRIQUE — 10 TESTS

À appliquer à tout projet, avant de parler de souveraineté.

| # | Test | Question | Preuve attendue |
|---|---|---|---|
| 1 | Opérateur | Niveau 1-4 ? Maison mère ? Pays de la supervision ? | Organigramme capitalistique, liste des sites de supervision |
| 2 | Certification | Quelle certification ? Calendrier ? Pénalités ? | Certificat ou engagement daté + audit |
| 3 | Hardware | Origine des puces, mémoire, réseau ? Part étrangère du BOM ? | BOM avec pays d'origine |
| 4 | Logiciel | Stack, hyperviseur, télémétrie, support niveau 3 : quels pays ? | Matrice des flux + contrats de support |
| 5 | Données | Quelles données ? Chiffrement ? Clés détenues par qui ? Réplication où ? | Architecture + HSM + journal d'accès |
| 6 | Réversibilité | Sortie en combien de mois, quels formats, quel coût ? Test annuel ? | Plan de sortie + test documenté |
| 7 | Énergie | PUE contractuel ? Électricité bas-carbone ? Secours ? | Engagements + pénalités, pas des intentions |
| 8 | Eau et chaleur | WUE ? Boucle fermée ? Chaleur fatale valorisée où ? | Chiffres + débouchés contractualisés |
| 9 | Territoire | Emplois, fiscalité, durée d'immobilisation du foncier ? | Bilan net, pas brut |
| 10 | Transparence | Pièces publiées (hors secrets protégés) ? | Bordereau de publication |

**Seuil** : si les tests 1, 2, 5 et 6 ne sont pas passés, le mot « souverain » ne doit pas figurer dans la communication du projet.

---

## 7. CLAUSES TYPES DE CAHIER DES CHARGES

| Bloc | Clause minimale | Preuve |
|---|---|---|
| Opérateur | Niveau 3 ou 4 selon sensibilité ; aucun contrôle extra-européen pour le niveau 4 ; supervision et support en UE | Kbis, organigramme, liste des sites |
| Certification | Certification visée, date, pénalités de retard ; audit annuel | Certificat ou lettre d'engagement |
| Hardware | Inventaire BOM avec origine ; maintenance UE ; pièces 10 ans | BOM + lettres fournisseurs |
| Logiciel | Stack auditable ; pas de télémétrie hors UE sans consentement ; séquestre du code/binaires critiques | Matrice flux + contrat de séquestre |
| Données | Chiffrement, clés détenues par le client, pas de réplication hors UE, journal d'accès | Architecture + HSM |
| Réversibilité | Sortie ≤ 6 mois, formats ouverts, coûts plafonnés, test annuel | Plan + test |
| Énergie / eau / chaleur | PUE et WUE plafonds contractuels ; chaleur valorisée ; boucle fermée si zone tendue | Engagements + pénalités |
| Transparence | Publication des pièces non couvertes par un secret protégé | Bordereau |

---

## 8. ARBRE DE DÉCISION — LOUER VS CONSTRUIRE

```
Besoin de calcul souverain ?
├─ Ponctuel / < 1 MW → LOUER du capacitaire existant niveau 3-4
├─ Durable 1-5 MW → CONTRAT pluriannuel capacitaire + clause certification
├─ Durable > 5 MW ET saturation démontrée du locatif
│   ├─ Foncier disponible + énergie + eau + acceptabilité → CONSTRUIRE (cahier §7)
│   └─ Sinon → MUTUALISER (extension d'un site existant niveau 4)
└─ Données non sensibles → niveau 3 + réversibilité suffisent, pas besoin de béton dédié
```

Principe : la souveraineté s'achète **d'abord en capacité contractualisée**, ensuite seulement en béton. Construire avant d'avoir saturé l'existant, c'est immobiliser du foncier et du capital pour aggraver la dépendance (chaque MW = BOM étranger supplémentaire).

---

## 9. IDÉES REÇUES FRÉQUENTES

| Idée reçue | Réponse |
|---|---|
| « Serveurs en France = souverain » | Non. Si l'opérateur est soumis au CLOUD Act, la localisation ne protège pas. |
| « Filiale française d'un groupe US = souverain » | Non : niveau 2, exposition moyenne-élevée, pas de SecNumCloud équivalent. |
| « Label d'interopérabilité = souverain » | Non : GAIA-X et labels équivalents attestent la portabilité, pas l'immunité juridique. |
| « GPU européens disponibles » | Non à l'échelle en 2026. Le choix réel : NVIDIA (US) ou AMD (US) via opérateur européen. |
| « Plus grand = plus souverain » | Inverse : plus grand = BOM étranger plus massif + foncier immobilisé plus longtemps = dépendance plus profonde. |
| « La construction crée la souveraineté » | Non : elle crée du bâtiment. La souveraineté vient de l'opérateur, de la certification et de la réversibilité. |

---

## 10. RÉFÉRENCES

| Ressource | Lien |
|---|---|
| CLOUD Act et souveraineté (bontrain.fr) | https://bontrain.fr/ressources/cloud-act-donnees-europeennes |
| 4 niveaux de souveraineté cloud | https://www.fromeuropewithlove.eu/fr/blog/quatre-niveaux-souverainete-cloud-guide-ctos-europeens |
| CADA (Cloud & AI Development Act) | https://www.genee.tech/blog/cloud-ai-development-act-cada-ue-data-centers-souverainete-aout-2026 |
| Cloud Act vs FISA | https://www.parlons.cloud/cloud-act-fisa-et-lillusion-du-datacenter-en-france/ |
| Scaleway GPU instances | https://www.scaleway.com/en/gpu-instances/ |
| OVHcloud — cloud souverain (consortium) | https://corporate.ovhcloud.com/en/newsroom/news/ovhcloud-deep-clever-cloud-consortium/ |
| ADEME — 5 scénarios data centers, souveraineté et CO₂ | `generalites/sources/textes/Consommation électrique des data centers _ 5 scénarios pour demain - ADEME Infos.html` |
| Loi RU 90-FZ « internet souverain » (analyse) | https://merlin.obs.coe.int/article/8603 |
| Loi RU 90-FZ (critique HRW) | https://www.hrw.org/news/2019/10/31/russia-new-law-expands-government-control-online |
| Tests de déconnexion Runet 2021 (Reuters) | https://www.reuters.com/technology/russia-disconnected-global-internet-tests-rbc-daily-2021-07-22 |
| DSL Chine (texte officiel NPC) | http://www.npc.gov.cn/englishnpc/c2759/c23934/202108/t20210823_385168.html |
| PIPL Chine (texte officiel) | https://en.spp.gov.cn/2021-12/29/c_948419.htm |
| DPDP Act Inde (MeitY/PIB, règles 2025) | https://www.pib.gov.in/PressReleasePage.aspx?PRID=2190655&lang=2&reg=3 |
| Loi FR SREN (analyse Orrick) | https://www.jdsupra.com/legalnews/the-sren-law-5-things-to-know-about-new-8726737 |

---

*Guide généraliste — réutilisable pour tout projet. Les chiffres GPU détaillés (délais, prix, HBM, CoWoS) sont dans la doctrine technique du dossier.*
