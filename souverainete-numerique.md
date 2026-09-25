# SOUVERAINETÉ NUMÉRIQUE — DATACENTER CAMP FRANÇAIS

**Objet** : Reprendre les arguments de `infrastructure-ia-gpu-souverainete.md` (§2, §3, §6) et les développer en doctrine applicable au projet Camp Français (Lezennes / Lesquin / Ronchin)
**Date** : Septembre 2026
**Statut** : Document de travail
**Document parent** : [infrastructure-ia-gpu-souverainete.md](infrastructure-ia-gpu-souverainete.md) — les chiffres GPU, HBM, CoWoS et cas modèles n'y sont pas répétés, ils y sont référencés

---

## TABLE DES MATIÈRES

1. [Reprise des acquis](#1-reprise-des-acquis--ce-que-dit-déjà-le-dossier)
2. [Définition opérationnelle](#2-définition-opérationnelle--5-couches-de-souveraineté)
3. [Cadre juridique](#3-cadre-juridique--pourquoi-héberger-en-france-ne-suffit-pas)
4. [Chaîne de dépendance technique](#4-chaîne-de-dépendance-technique--où-se-joue-vraiment-la-souveraineté)
5. [Opérateurs et niveaux](#5-opérateurs-et-niveaux--qui-peut-héberger-souverain)
6. [Le paradoxe Camp Français](#6-le-paradoxe-camp-français--bâtiment-français--système-américain)
7. [Cahier des charges souverain](#7-cahier-des-charges--ce-quexiger-si-le-projet-se-fait)
8. [Alternatives](#8-alternatives--souverain-sans-construire)
9. [Argumentaire d'opposition](#9-argumentaire-dopposition--questions-et-pièces-à-exiger)
10. [Références](#10-références)

---

## 1. REPRISE DES ACQUIS — CE QUE DIT DÉJÀ LE DOSSIER

### 1.1 Arguments repris du document parent (sans modification)

| Argument parent | § | Contenu repris tel quel |
|---|---|---|
| CLOUD Act (US, 2018) | §3.1 | Toute entreprise US doit livrer les données, **peu importe le lieu de stockage** |
| Témoignage Microsoft France | §3.1 | Juin 2025, devant le Sénat : **impossible de garantir** la non-transmission aux autorités US |
| 4 niveaux de souveraineté | §3.2 | Niveau 1 (cloud US en UE, exposition élevée) → Niveau 4 (100 % européen, exposition nulle) |
| Acteurs niveau 4 | §3.3 | OVHcloud (SecNumCloud, 46 DC), Scaleway (seul EU avec Blackwell B300), 3DS Outscale (SecNumCloud 3.2), IONOS, Hetzner |
| CADA (UE) | §3.4 | Adopté 03/06/2026, en vigueur **04/08/2026**, objectif **tripler** la capacité DC européenne, permis accéléré |
| Contrat CE 180 M€ | §3.5 | Avril 2026 : cloud souverain des institutions UE attribué à **4 européens** (OVHcloud, Scaleway, Clever Cloud, DEEP) |
| Si opérateur US vs européen | §3.6 | US = pas de SecNumCloud, marchés publics UE bloqués ; EU = SecNumCloud 3.2 possible, marchés ouverts |
| Dépendance NVIDIA/TSMC | §2 | >80 % accélérateurs NVIDIA, CUDA lock-in 17 ans, toute la chaîne passe par Taïwan |
| Huawei = pas une option EU | §6.3 | 60 % d'un H100, CANN immature, indisponible hors Chine |
| Verdict parent | §8.10 (6) | 9 656 GPU NVIDIA H100 = 100 % hardware US → la souveraineté revendiquée est un **leurre** |

### 1.2 Ce qui manquait — et que ce document développe

1. **Définition** : la MEL invoque la « souveraineté numérique » (concertation, mai 2026) sans dire de quelle couche elle parle (foncier ? opérateur ? puces ?).
2. **Droit** : articulation CLOUD Act / FISA 702 / RGPD / Data Act / SecNumCloud 3.2 / CADA — conditions concrètes d'éligibilité.
3. **Technique** : la dépendance ne s'arrête pas aux GPU — HBM, CoWoS, NVLink/InfiniBand, CUDA/ROCm, ASML (seul levier européen réel).
4. **Test local** : grille d'évaluation appliquée au projet Camp Français (7 tests).
5. **Exigences** : clauses minimales à imposer dans la consultation « cession de charges » si le projet se poursuit.

---

## 2. DÉFINITION OPÉRATIONNELLE — 5 COUCHES DE SOUVERAINETÉ

Un datacenter n'est souverain que si **les 5 couches** sont maîtrisées. Le bâtiment seul (couche 1) ne suffit pas.

| Couche | Question | Situation typique Camp Français si opérateur US + NVIDIA | Souverain ? |
|---|---|---|---|
| **1. Foncier / bâti / énergie** | Qui possède le sol, le bâtiment, le raccordement ? | Foncier MEL (public FR), raccordement RTE/Enedis (FR) | ✅ partiel |
| **2. Hardware** | Qui fabrique puces, serveurs, réseau ? | NVIDIA (US) + TSMC (TW) + SK Hynix/Samsung/Micron (KR/US) | ❌ |
| **3. Logiciel / firmware** | Qui contrôle hyperviseur, orchestration, pilotes, CUDA ? | CUDA, vSphere/ESXi ou stack hyperscaler (US) | ❌ |
| **4. Opérateur / données** | Qui exploite, qui peut être contraint de livrer ? | Si AWS/Azure/Google ou filiale US → CLOUD Act | ❌ si US |
| **5. Compétences / réversibilité** | Qui sait exploiter, sortir, auditer ? | Dépendance aux roadmaps et certifications US | ⚠️ |

**Règle** : le niveau de souveraineté d'un projet = **le maillon le plus faible**. Un bâtiment français exploité par un opérateur US sur puces US avec stack US = **niveau 1**, pas niveau 4.

---

## 3. CADRE JURIDIQUE — POURQUOI HÉBERGER EN FRANCE NE SUFFIT PAS

### 3.1 Le conflit de lois au cœur du dossier

| Texte | Portée | Effet concret sur Camp Français |
|---|---|---|
| **CLOUD Act** (US, 2018) | Oblige toute société US à remettre les données sur mandat US, **où qu'elles soient** | Un DC à Lezennes opéré par AWS/Azure/Google (ou filiale) reste saisissable depuis Washington |
| **FISA 702** (US) | Surveillance des non-Américains hors US, programmes type PRISM | Données MEL / entreprises hébergées = interceptables sans notification |
| **RGPD** (UE) | Interdit tout transfert sans base légale + garanties | Transférer vers un opérateur soumis au CLOUD Act = violation potentielle (jurisprudence Schrems II) |
| **Data Act** (UE, applicable 2025) | Encadre l'accès des gouvernements aux données industrielles | Conflit frontal avec le CLOUD Act : l'opérateur doit choisir quelle loi violer |
| **NIS2 / DORA** (UE) | Exigences cyber et résilience opérateurs critiques | Un opérateur non-EU complique l'audit et la notification |

### 3.2 Le témoignage qui verrouille le débat

> En juin 2025, le directeur juridique de Microsoft France a confirmé **sous serment devant le Sénat** qu'il ne pouvait pas garantir que les données européennes ne seraient pas transmises aux autorités américaines.

Conséquence : toute promesse contractuelle (« vos données restent en France ») d'un opérateur US est **juridiquement inopposable** à un ordre US. Seule la **structure capitalistique et technique** (niveau 3-4) protège, pas la clause.

### 3.3 SecNumCloud 3.2 (ANSSI) — le seul filtre crédible

| Exigence | Contenu | Pourquoi c'est discriminant |
|---|---|---|
| Capital et contrôle EU | Pas de contrôle extra-européen, pas de veto US | Exclut AWS, Azure, Google même « régions France » |
| Immunité extraterritoriale | Prouver l'absence de soumission à une loi extra-EU | Exclut les licences tech US avec clause d'audit US |
| Hébergement + exploitation en UE | Données, supervision, support : UE uniquement | Exclut le support 24/7 depuis les US/Inde sous contrôle US |
| Réversibilité / audit ANSSI | Audit, pentest, plan de sortie | Seuls OVHcloud, 3DS Outscale (qualifiés) et équivalents passent |

Sans SecNumCloud, l'étiquette « souverain » n'a **aucune valeur opposable** pour des données publiques ou critiques.

### 3.4 CADA — Cloud & AI Development Act (UE, en vigueur 04/08/2026)

| Point | Détail | Impact Camp Français |
|---|---|---|
| Objectif | **Tripler** la capacité DC européenne d'ici 2030 | La MEL peut s'inscrire dedans — mais la Commission privilégiera les projets niveau 3-4 |
| Guichet unique + permis accéléré | Par État membre | Accélération possible, **pas de dispense** d'étude d'impact ni de dérogation espèces |
| Classification 4 niveaux | Reprise des niveaux §3.2 du parent | Les marchés publics UE exigeront niveau 3-4 → un DC niveau 1-2 à Lezennes serait **inéligible** aux clients publics |
| Conditionnalité probable | Énergie bas-carbone, chaleur fatale, PUE | Le dossier actuel (PUE 1,35–1,5, pas de valorisation chaleur démontrée) est fragile |

### 3.5 GAIA-X, ESCC — utiles mais non suffisants

Labels d'interopérabilité et de transparence, **pas des preuves d'immunité juridique**. Un DC « GAIA-X compliant » opéré par un hyperscaler US reste soumis au CLOUD Act.

---

## 4. CHAÎNE DE DÉPENDANCE TECHNIQUE — OÙ SE JOUE VRAIMENT LA SOUVERAINETÉ

Reprise du §2 du parent, élargie au-delà des GPU.

| Maillon | Monopole | Levier européen ? | Risque Camp Français |
|---|---|---|---|
| **GPU / accélérateurs** | NVIDIA >80 %, CUDA 17 ans | ❌ Aucun GPU IA EU à l'échelle | Prix +20-30 % spot, allocations verrouillées par hyperscalers |
| **Mémoire HBM3/HBM3e** | SK Hynix, Samsung, Micron (100 % vendue 2026) | ❌ | Délais 36-52 semaines H100/H200 |
| **Empaquetage CoWoS** | TSMC uniquement, saturé jusqu'à mi-2027 | ❌ | B200 : 3-7 mois si prioritaire, sinon file d'attente |
| **Fonderie ≤7 nm** | TSMC N3/N4 ; SMIC bloqué 7 nm sans EUV | ⚠️ ASML (NL) = **seul levier EU** (monopole EUV mondial) mais ne fabrique pas de puces | Toute la chaîne passe par Taïwan |
| **Interconnexion** | NVLink/NVSwitch, InfiniBand (NVIDIA/Mellanox) | ❌ (Ethernet ouvert = alternative partielle) | Lock-in réseau intra-cluster |
| **Logiciel** | CUDA (NVIDIA), CANN (Huawei) ; ROCm (AMD, ouvert mais en retard) | ⚠️ Mistral (modèles), BSC/RISC-V (recherche), pas de stack complète | Migrer hors CUDA = réécrire tout le pipeline |
| **Modèles** | Open weights EU (Mistral) vs US vs CN (DeepSeek, Kimi, Qwen) | ✅ atout EU réel | Mais l'inférence tourne sur hardware US |

**Lecture** : l'Europe tient **un bout de la chaîne** (ASML, modèles ouverts, opérateurs niveau 4) et **zéro bout décisif** (fonderie avancée, HBM, GPU, CUDA). Construire un bâtiment à Lezennes ne change **aucun** de ces maillons. La seule souveraineté achetable à court terme, c'est **l'opérateur + la certification + la réversibilité**.

---

## 5. OPÉRATEURS ET NIVEAUX — QUI PEUT HÉBERGER SOUVERAIN

### 5.1 Grille rappelée et précisée (parent §3.2–3.3)

| Niveau | Montage | CLOUD Act | SecNumCloud | Exemples | Éligible marchés publics UE sensibles ? |
|---|---|---|---|---|---|
| **1** | Hyperscaler US, région EU | Élevée | Impossible | AWS, Azure, GCP standard | Non |
| **2** | Filiale EU dédiée, maison mère US | Moyenne-élevée | Non (sauf montage ad hoc, jamais équivalent 3.2) | AWS ESC, Azure Deutschland | Non / marginal |
| **3** | Opérateur EU + techno US sous licence | Réduite (résiduelle : licences, firmware, support) | Possible sous conditions strictes | S3NS (Google/Thales), Bleu (Microsoft/Orange) | Oui, avec réserves |
| **4** | 100 % EU, pas de contrôle US | Nulle | Oui (si audit ANSSI) | OVHcloud, Scaleway, 3DS Outscale, Clever Cloud, DEEP, IONOS | Oui |

### 5.2 Focus acteurs français niveau 4 (complété)

| Acteur | GPU IA dispo (2026) | Certifs | Points forts | Limites à vérifier pour Camp Français |
|---|---|---|---|---|
| **Scaleway** (Iliad) | H100, H200, **B300** (seul EU) | GAIA-X, SecNumCloud en cours | Seul EU sur Blackwell récent, clusters dédiés possibles | SecNumCloud non encore complet : exiger calendrier |
| **OVHcloud** | H100, L40S, A10 | **SecNumCloud**, HDS, ISO 27001 ; 46 DC, 1,6 M clients | Maturité, Roubaix à 15 km (mutualisation) | Pas de B200/B300 en 2026 : trajectoire GPU à contractualiser |
| **3DS Outscale** (Dassault) | Bare metal NVIDIA | **SecNumCloud 3.2** (depuis 2025) | Le plus certifié pour données critiques | Capacité GPU IA limitée : dimensionner tôt |
| **Clever Cloud / DEEP** | Cloud EU, GPU variables | Co-titulaires contrat CE 180 M€ | Agilité, ancrage EU | Capacité hyperscale à démontrer |

### 5.3 Niveau 3 : vigilance

S3NS et Bleu réduisent l'exposition mais conservent une **dépendance technologique US** (mises à jour, firmware, roadmap, support niveau 3). Pour des données MEL critiques ou santé, exiger niveau 4. Pour du calcul IA banalisé non sensible, niveau 3 peut suffire — **à condition de le dire explicitement** au lieu de parler de « souveraineté » en général.

---

## 6. LE PARADOXE CAMP FRANÇAIS — BÂTIMENT FRANÇAIS = SYSTÈME AMÉRICAIN

### 6.1 Les 7 tests de souveraineté appliqués au projet

| # | Test | Question à la MEL / au candidat | Réponse connue (sept. 2026) | Verdict |
|---|---|---|---|---|
| 1 | **Opérateur** | Niveau 1-4 ? Maison mère ? | Consultation « cession de charges » : **opérateur inconnu** | ❓ À exiger |
| 2 | **Certification** | SecNumCloud 3.2 exigé ? Calendrier ? | Non mentionné | ❌ |
| 3 | **Hardware** | GPU NVIDIA ? Part US du BOM ? | Scénarios parent = 100 % NVIDIA | ⚠️ dépendance assumée, non compensée |
| 4 | **Logiciel** | Stack CUDA ? Hyperviseur ? Support hors UE ? | Non documenté | ❓ |
| 5 | **Données** | Quelles données (MEL ? clients privés ?) ? Localisation supervision ? | Non documenté | ❓ |
| 6 | **Réversibilité** | Sortie en combien de mois ? Format ? Coût ? | Non documenté | ❌ |
| 7 | **Territoire** | Chaleur fatale, emplois, fiscalité locale vs 22 ha bloqués 20-30 ans | Pas de valorisation chaleur démontrée ; 20-70 emplois permanents | ⚠️ |

**Bilan** : 0 test passé sur 7. Invoquer la souveraineté dans cet état, c'est vendre la **couche 1 (foncier)** comme si c'était les couches 1-5.

### 6.2 Le précédent qui doit alerter : contrat CE 180 M€

La Commission a choisi **4 européens** pour son propre cloud. Si la MEL confie 22 ha à un opérateur US ou non certifié, Lille sera **moins exigeante que Bruxelles pour ses propres données** — intenable politiquement et juridiquement pour tout hébergement de données publiques.

### 6.3 Souveraineté et taille : le contresens

Le parent (§8) montre que le site peut porter 80-187 MW IT (2 414 racks, 9 656 H100, 9,5-24 ExaFLOPS) — soit 5-12 % d'un Colossus. Or :

- Plus le site est gros, plus le BOM US (GPU, HBM, réseau) est massif → **plus la dépendance est profonde**.
- Plus le site est gros, plus le foncier public est immobilisé longtemps → **moins la collectivité garde de marges de manœuvre**.
- La puissance (126-150 MW totaux = ville de 100 000 hab., sous-station 225 kV à 80-150 M€, 3-5 ans) fait du projet un **otage du raccordement** : celui qui finance le raccordement impose ses conditions.

Un « grand » datacenter non souverain, c'est une **grande dépendance**, pas une grande souveraineté.

---

## 7. CAHIER DES CHARGES — CE QU'EXIGER SI LE PROJET SE FAIT

Clauses minimales à inscrire dans la consultation, faute de quoi retirer le mot « souverain » du dossier.

| Bloc | Clause minimale | Preuve exigible |
|---|---|---|
| **Opérateur** | Niveau 4 ; aucun contrôle extra-UE ; supervision et support 100 % UE | Kbis, organigramme capitalistique, liste sites supervision |
| **Certification** | SecNumCloud 3.2 (ou engagement daté + pénalités) ; HDS si santé | Certificat ANSSI ou lettre d'engagement + audit |
| **Hardware** | Inventaire BOM avec origine ; pas de firmware avec backdoor contractuelle US ; pièces 10 ans | BOM + lettres fournisseurs |
| **Logiciel** | Stack auditable ; pas de télémétrie hors UE sans consentement ; code source séquestré | Matrice flux + contrat séquestre |
| **Données** | Chiffrement clés MEL ; pas de réplication hors UE ; journal d'accès | Architecture + HSM |
| **Réversibilité** | Sortie ≤ 6 mois, formats ouverts, coûts plafonnés, test annuel | Plan de sortie + test |
| **Territoire** | PUE ≤ 1,3 contractualisé ; chaleur fatale valorisée (golf, bâtiments) ; eau en boucle fermée ; emplois et fiscalité chiffrés | Engagements + pénalités |
| **Transparence** | Publication des pièces (hors secrets protégés) au registre numérique | Bordereau de versement |

Sans ces pièces, l'argument « souveraineté » est **irrecevable** en concertation et fragile devant le juge administratif (erreur manifeste d'appréciation de l'intérêt public majeur, cf. conditions L.411-2).

---

## 8. ALTERNATIVES — SOUVERAIN SANS CONSTRUIRE

Reprise et développement du phasage parent (§6.4) : la souveraineté s'achète **d'abord en capacité**, pas en béton.

| Option | Contenu | Délai | Souveraineté | Coût vs 500 M€-3,2 Md€ construction |
|---|---|---|---|---|
| **A. Cluster dédié existant** | Louer du B200/H100 chez Scaleway/OVHcloud (Roubaix à 15 km, Strasbourg, Vitry) | Semaines | Niveau 4 immédiat si bon opérateur | 10-50× moins cher à court terme |
| **B. Contrat pluriannuel capacitaire** | Réserver 1-5 MW souverains avec clause SecNumCloud | 2027-2028 | Contractuelle + audit | Marginal vs raccordement 225 kV (80-150 M€) |
| **C. Mutualisation MEL** | Cloud MEL existant + extension niveau 4 pour données critiques | Mois | Progressive, réversible | Faible |
| **D. Construction différée** | Ne construire que si A-C saturés ET cahier §7 tenu | 2028-2030+ | À démontrer | Évite 22 ha bloqués 30 ans pour rien |

La question à poser en concertation : **pourquoi construire 22 ha avant d'avoir saturé un rack souverain existant à 15 km ?**

---

## 9. ARGUMENTAIRE D'OPPOSITION — QUESTIONS ET PIÈCES À EXIGER

### 9.1 Six angles prêts à l'emploi

1. **Leurre** : 9 656 GPU NVIDIA + CLOUD Act = pas de souveraineté sans opérateur niveau 4 certifié. Exiger le nom de l'opérateur et son niveau.
2. **Inéligibilité** : sans SecNumCloud 3.2, le site est exclu des marchés publics UE sensibles (CADA) — quel client public viendra ?
3. **Précédent CE** : Bruxelles choisit 4 européens pour 180 M€ ; Lille ferait moins bien sur 22 ha ?
4. **Témoignage Sénat** : Microsoft France avoue ne pas pouvoir garantir la non-transmission — que vaut une promesse d'un opérateur US à Lezennes ?
5. **Dépendance croissante** : chaque MW ajouté = plus de BOM US, plus de CUDA, moins de sortie possible. La taille aggrave, elle ne protège pas.
6. **Foncier otage** : 22 ha publics bloqués 20-30 ans + raccordement 80-150 M€ + 3-5 ans pour un opérateur non souverain = perte sèche.

### 9.2 Dix questions pour le registre de concertation

1. Quel opérateur (nom, maison mère, niveau 1-4) ?
2. SecNumCloud 3.2 exigé ? Calendrier et pénalités ?
3. Part US du BOM (GPU, HBM, réseau, logiciel) ?
4. Supervision et support : quels pays ?
5. Données MEL hébergées ? Lesquelles ? Clés détenues par qui ?
6. Plan de sortie (durée, formats, coûts) ?
7. PUE contractuel, eau (WUE), chaleur fatale : chiffres et pénalités ?
8. Pourquoi construire avant de louer du capacitaire souverain existant (Roubaix) ?
9. Clients publics visés : lesquels acceptent du non-SecNumCloud ?
10. Publication intégrale des pièces au registre numérique : quand ?

### 9.3 Pièces à demander (contrôle des pièces promoteur)

- Règlement de consultation « cession de charges » + critères de notation (poids de la souveraineté ?)
- Engagements SecNumCloud / CADA / réversibilité
- BOM prévisionnel et contrats GPU
- Étude raccordement RTE/Enedis (coût, délai, qui paie)
- Engagements PUE/WUE/chaleur fatale

---

## 10. RÉFÉRENCES

### 10.1 Reprises du parent (ne pas dupliquer, s'y reporter)

- GPU, HBM, CoWoS, délais, prix : parent §1
- NVIDIA vs Huawei, CUDA vs CANN : parent §2
- Niveaux, acteurs, CADA, contrat CE 180 M€ : parent §3
- Recommandations opérateur EU + phasage : parent §6
- Chiffrage 22 ha (racks, MW, eau, bruit) : parent §8
- URLs : parent §9 (neuralwired, sourcebyspec, cfr.org, awesomeagents, bontrain.fr, fromeuropewithlove.eu, genee.tech, scaleway.com, corporate.ovhcloud.com, parlons.cloud)

### 10.2 Cadre à verser au dossier

| Texte | Lien |
|---|---|
| CLOUD Act et souveraineté (bontrain.fr) | https://bontrain.fr/ressources/cloud-act-donnees-europeennes |
| 4 niveaux de souveraineté cloud | https://www.fromeuropewithlove.eu/fr/blog/quatre-niveaux-souverainete-cloud-guide-ctos-europeens |
| CADA (Cloud & AI Development Act) | https://www.genee.tech/blog/cloud-ai-development-act-cada-ue-data-centers-souverainete-aout-2026 |
| Cloud Act vs FISA | https://www.parlons.cloud/cloud-act-fisa-et-lillusion-du-datacenter-en-france/ |
| Scaleway GPU instances | https://www.scaleway.com/en/gpu-instances/ |
| OVHcloud — cloud souverain (consortium) | https://corporate.ovhcloud.com/en/newsroom/news/ovhcloud-deep-clever-cloud-consortium/ |
| ADEME — 5 scénarios data centers, souveraineté et CO₂ | Dossier `generalites/sources/textes/Consommation électrique des data centers _ 5 scénarios pour demain - ADEME Infos.html` |

---

*Document complémentaire au dossier d'opposition datacenter Camp Français — Septembre 2026. À lire avec `infrastructure-ia-gpu-souverainete.md` (technique) et `rapport-moyens-opposition.md` (stratégie).*
