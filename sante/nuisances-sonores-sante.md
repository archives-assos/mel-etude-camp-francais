# Nuisances sonores et santé — synthèse sourcée

Document de référence. Compilation : 2026-10-14.

Document complémentaire de `infrasons-sante.md` (même méthode, même conventions) ;
l'accent y est mis sur les infrasons, ici sur le bruit audible.

**Convention de citation.** Chaque affirmation chiffrée porte un renvoi `[n]` vers
la liste de sources (§10). Les références sont des documents vérifiables (OMS,
agences publiques, revues à DOI, normes, textes réglementaires). Quand une donnée
n'est disponible qu'en ligne, l'URL officielle est donnée. Aucune valeur n'est
donnée sans source.

**Pondérations à ne pas confondre** : `dB SPL` (niveau physique), `dB(Z)`
(linéaire), `dB(A)` (pondéré audition, noté aussi `dBA`) et `dB(C)` (plus plat,
capter les basses fréquences). La pondération A sous-estime fortement le bruit
sous 100 Hz ; dès que l'écart C − A dépasse 10 dB, une analyse en fréquence est
recommandée `[2]`. Une valeur « en dB » n'est comparable qu'à pondération égale.

---

## 1. Définitions et repères

- **Son / bruit** : il n'existe **pas de différence physique** entre les deux ; le
  bruit est défini comme un **son indésirable** (perception) `[2]`.
- **Nuisance sonore** : ensemble des effets indésirables (gêne, perturbation du
  sommeil, de la parole, effets physiologiques) sur la santé et le bien-être `[2]`.
- **Domaine audible** : environ **20 Hz – 20 000 Hz** chez l'auditeur jeune et
  sans déficit `[2]`. Sous 20 Hz : infrasons (voir document `infrasons-sante.md`).
- **dB (décibel)** : échelle logarithmique ; pour le son, niveau relatif à
  **20 µPa** `[2]`. Les niveaux ne s'additionnent **pas arithmétiquement** `[2]`.
- **Indicateurs de gêne/bruit** `[1][2]` :
  - **LAeq,T** : niveau équivalent pondéré A moyenné sur une durée T (bruit continu) ;
  - **LAmax** : niveau maximal d'un événement (bruit impulsionnel) ;
  - **SEL / LAE** : niveau d'exposition sonore d'un événement isolé ;
  - **Lden** : 24 h avec pénalités **+5 dB** (soir) et **+10 dB** (nuit) ;
  - **Lnight** : niveau équivalent nocturne (8 h, ≈ 23 h–07 h).
- **Règle d'énergie** (*equal energy*) : à durée double, un événement de +3 dB
  apporte la même énergie `[2]`.
- L'effet sanitaire **le plus net** aux niveaux environnementaux réels est la
  **gêne** (`annoyance`) `[2]`.
- **Gestion** : principes de **précaution**, **pollueur-payeur** et réduction
  **à la source** `[2]`.

---

## 2. Sources de bruit

- **Transports** (source dominante) : routier, **ferroviaire**, **aérien** `[1][2]`.
- **Industrie**, **chantiers / BTP**, **voisinage** (appareils, ventilation),
  **loisirs** (concerts, discothèques, écouteurs, sons amplifiés), **éoliennes** `[2][9]`.
- Repères d'exposition (UE) `[2]` :
  - ≈ **40 %** de la population exposée au bruit routier **> 55 dB(A)** de jour ;
  - ≈ **20 %** exposée à **> 65 dB(A)** ;
  - **> 30 %** exposée la nuit à **> 55 dB(A)** (perturbant le sommeil).
- Bilan européen (au-dessus des seuils de la directive « bruit ») `[4][5]` :

| Source | Population exposée à des niveaux nocifs (Lden) |
|---|---|
| Bruit routier | **113 millions** |
| Bruit ferroviaire | 22 millions |
| Bruit aérien | 4 millions |
| Bruit industriel | 1 million |

### 2.1 Cas particulier : centres de données (« datacenters »)

Les datacenters sont une source de bruit **industrielle continue**, en forte
croissance. **Production** : les émissions proviennent des **ventilateurs**
(serveurs et refroidissement), des **unités de climatisation (CVC)**, des
**groupes froid** (*chillers*) et **tours de refroidissement**, des
**transformateurs** et surtout des **groupes électrogènes diesel** (essais de
mise en charge et secours) `[15][17]`. **Niveaux** : à l'intérieur, le bruit peut
atteindre **≈ 96 dB(A)** `[16]` ; en zone froide (*cold aisle*), l'exposition
professionnelle **dépasse fréquemment 85 dB(A)** avec des **pics > 100 dB** `[15]` ;
à l'extérieur, les groupes électrogènes montent à **≈ 105 dB** et les tours de
refroidissement à **≈ 70 dB(A) à 120 m** `[17]`. **Nuisances** : les riverains
rapportent gêne, perte de sommeil, céphalées, vertiges, nausées, douleurs
auriculaires et hypertension `[17]` — **plaintes déclaratives**, non corrélées à
des mesures `[15][17]` ; en Virginie, près d'un tiers des datacenters se situent à
moins de **~61 m (200 pieds)** de zones résidentielles `[18]`. Limite de
connaissance importante : une **revue narrative (2026)** souligne que les
**mesures publiées du spectre complet d'un datacenter en exploitation restent
absentes**, que la pondération A **sous-estime** la composante basse fréquence
(pour l'infrason, voir `infrasons-sante.md` §3.4) et qu'**aucune norme propre aux
datacenters n'existe** `[15]`. En milieu de travail, une exposition **> 85 dB(A)
sur 8 h** fait basculer dans le régime de **protection auditive** (§6.4) `[12][15]`.

À retenir : nuisance **continue de voisinage** doublée d'un **risque auditif
professionnel** ; preuves encore **limitées** (une revue narrative et des rapports
institutionnels), **sans valeur limite spécifique** — les référentiels du §6
s'appliquent `[15]`.

---

## 3. Effets auditifs (sur l'oreille)

- **Perte auditive induite par le bruit** = élévation du seuil d'audition `[2]`.
  Survenue **d'abord en hautes fréquences (3 000–6 000 Hz)**, maximum vers
  **4 000 Hz** ; avec le niveau et la durée, elle atteint des fréquences plus
  basses (jusqu'à 2 000 Hz) `[2]`.
- **Pas de surdité attendue** à **LAeq,8h ≤ 75 dB(A)**, même en exposition
  professionnelle prolongée `[2]`.
- Bruit **environnemental et de loisirs** : **LAeq,24h ≤ 70 dB(A)** sans surdité
  pour la **grande majorité** des personnes, même sur une vie entière `[2]`.
- **Pics impulsionnels** (jouets, pétards, armes) : **jamais > 140 dB** chez
  l'adulte, **> 120 dB** chez l'enfant (mesuré à 100 mm de l'oreille) `[2]`.
- **Loisirs sonores** : concerts/discothèques dépassent souvent **100 dB LAeq** ;
  patrons exposés < 5 fois/an à 100 dB LAeq sur 4 h, et **LAmax toujours < 110 dB** `[2]`.
- **Écouteurs** : équivalent **≤ 70 dB(A) LAeq,24h**, soit **≤ 85 dB(A) LAeq pour
  1 h/jour** `[2]`.
- **Acouphènes** (sifflements) souvent associés `[2]`.
- **Charge mondiale** : **≈ 1,5 milliard** de personnes vivent avec une perte
  auditive ; **≈ 430 millions** nécessitent une rééducation ; **> 1 milliard** de
  jeunes sont exposés à un risque évitable par pratiques d'écoute à risque `[13]`.
- L'altération auditive due au bruit se **modélise** (norme **ISO 1999**) et se
  **mesure** au poste de travail (norme **ISO 9612**) `[14]`.

---

## 4. Effets non auditifs

### 4.1 Sommeil

- Effets mesurables dès **≈ 30 dB LAeq** ; plus le bruit de fond est fort, plus la
  perturbation est marquée `[2]`.
- **Chambre à coucher** : **≤ 30 dB LAeq** (bruit continu) et éviter les
  événements **> 45 dB LAmax** `[2]` ; fenêtre ouverte, l'extérieur devrait rester
  **≤ 45 dB LAeq** `[2]`.
- Effets **primaires** (endormissement difficile, éveils, changement de stades du
  sommeil, ↑ tension/pouls) et **secondaires** (fatigue, humeur, performance) `[2]`.
- **OMS – Lignes directrices bruit nocturne** : cible **40 dB Lnight** à
  l'extérieur ; **55 dB** comme **objectif intermédiaire** `[3]`.
- Le **bruit basse fréquence** (ventilation) perturbe repos et sommeil **à bas
  niveau** `[2]`.

### 4.2 Appareil cardiovasculaire

- Expositions prolongées : risque accru d'**hypertension** et de **cardiopathie
  ischémique** ; effets **démontrés** pour le trafic routier et aérien à
  **LAeq,24h de 65–70 dB(A)** `[2]`.
- Association **plus forte pour la cardiopathie ischémique** que pour
  l'hypertension, mais incréments faibles appliqués à de grandes populations `[2]`.
- **Mécanismes** : bruit → réaction de stress → activation du système nerveux
  **sympathique**, hormones de stress, **stress oxydant**, dysfonction
  endothéliale → HTA, infarctus, AVC `[7]`.
- Revue de synthèse des effets auditifs et **non auditifs** : gêne, perturbation
  du sommeil, somnolence diurne, effets cardiovasculaires, cognition `[6]`.

### 4.3 Cognition et apprentissage (enfants)

- Le bruit dégrade les tâches **cognitives complexes** (lecture, attention,
  résolution de problèmes, mémorisation) `[2]`.
- Écoles proches d'aéroports : **retard d'acquisition de la lecture**, moindre
  persistance, altération motivationnelle ; **élévation du stress et de la
  tension artérielle au repos** `[2]`.
- Au niveau européen : **≈ 12 000 enfants** présenteraient des troubles
  d'apprentissage imputables au bruit aérien `[4]`.

### 4.4 Gêne, stress et santé mentale

- La **gêne est l'effet principal** et le mieux documenté `[2]`.
- À niveau égal, l'**avion gêne plus** que la route, elle-même plus que le
  **rail** ; la gêne dépend aussi de facteurs **non acoustiques** (source,
  contexte, contrôle perçu) `[2][8]`.
- Le bruit **> 80 dB(A)** peut réduire les comportements d'aide et augmenter
  l'agressivité `[2]`.
- **Santé mentale** : le bruit **ne cause pas directement** une maladie mentale
  mais pourrait **accélérer** des troubles latents ; données **non conclusives** `[2]`.

---

## 5. Relations dose-réponse

- Le **pourcentage de personnes fortement gênées (%HA)** croît avec le niveau
  **Lden** ; les **fonctions dose-réponse** de référence (route, rail, avion)
  sont établies par Miedema & Oudshoorn `[8]`.
- Ces fonctions **exposition-réponse** (gêne, perturbation du sommeil, incidence
  de la cardiopathie ischémique) servent de base aux évaluations sanitaires de
  l'OMS et de l'Agence européenne pour l'environnement `[1][4]`.
- La corrélation exposition–gêne est **plus forte au niveau du groupe** qu'au
  niveau individuel `[2]`.

---

## 6. Valeurs guides et limites

### 6.1 OMS — Lignes directrices bruit environnemental (2018) `[1]`

| Source | Lden | Lnight | Force |
|---|---|---|---|
| Trafic routier | 53 dB | 45 dB | Forte |
| Trafic ferroviaire | 54 dB | 44 dB | Forte |
| Trafic aérien | 45 dB | 40 dB | Forte |
| Éoliennes | 45 dB | — | Conditionnelle |
| Bruit de loisirs | 70 dB LAeq,24h (moyenne annuelle) | — | Forte |

### 6.2 OMS — *Guidelines for Community Noise* (1999) `[2]`

| Environnement | Effet critique | Valeur guide |
|---|---|---|
| Zones de vie extérieures | Gêne sérieuse / modérée (jour-soir) | **55 / 50 dB LAeq** (16 h) |
| Intérieur logement (jour) | Intelligibilité, gêne | **35 dB LAeq** (16 h) |
| Chambre à coucher (nuit) | Perturbation du sommeil | **30 dB LAeq** (8 h) ; **45 dB LAmax** |
| Extérieur chambre (fenêtre ouverte) | Sommeil | **45 dB LAeq** (8 h) ; 60 dB LAmax |
| Salles de classe | Intelligibilité | **35 dB LAeq** (pendant le cours) |
| Hôpital (chambre, nuit) | Sommeil | **30 dB LAeq** (8 h) ; **40 dB LAmax** |
| Zones industrie/commerce/circulation | Perte auditive | **70 dB LAeq** (24 h) ; 110 dB LAmax |
| Concerts, festivals | Perte auditive (patrons) | **100 dB LAeq** (4 h) ; 110 dB LAmax |
| Baladeurs/écouteurs | Perte auditive | **85 dB LAeq** (1 h) ; 110 dB LAmax |
| Impulsions (jouets, pétards, armes) | Perte auditive | **crête 140 dB** (adultes) / **120 dB** (enfants, à 100 mm) |

Repères : pas de surdité attendue **≤ 75 dB LAeq,8h** ; gêne sérieuse rare
**< 55 dB LAeq**, gêne modérée rare **< 50 dB LAeq** (jour) `[2]`.

### 6.3 OMS — Bruit nocturne en Europe (2009) `[3]`

- **Cible** : **40 dB Lnight** à l'extérieur (protège les groupes vulnérables,
  dont les enfants) ; **objectif intermédiaire : 55 dB** `[3]`.

### 6.4 Bruit au travail

| Référentiel | Valeur limite | Source |
|---|---|---|
| **UE — Directive 2003/10/CE** | valeurs **déclenchant l'action** : 80 dB(A) / 112 Pa (basse), 85 dB(A) / 140 Pa (haute) ; **valeur limite d'exposition** : **87 dB(A) / 200 Pa** (protection auditive incluse) | `[10]` |
| **NIOSH (US)** | **85 dB(A)** en moyenne pondérée sur 8 h (REL), **taux d'échange 3 dB** | `[12]` |
| **OSHA (US)** | **90 dB(A)** sur 8 h (PEL), **taux d'échange 5 dB** | `[12]` |

### 6.5 France

- **Émergence** en zone à émergence réglementée (bruit de voisinage) : **5 dB(A)**
  en période diurne (7 h–22 h) et **3 dB(A)** en période nocturne (22 h–7 h) `[11]`.
- **Émergence spectrale** (Code de la santé publique, R. 1336-8) : **7 dB** dans
  les bandes d'octave **125 Hz et 250 Hz**, **5 dB** dans celles de **500 Hz,
  1 000 Hz, 2 000 Hz et 4 000 Hz** `[11]`.
- **ICPE** : bruit ne devant pas dépasser **70 dB(A)** le jour et **60 dB(A)** la
  nuit en limite de propriété (arrêté du 23 janvier 1997) `[11]`.
- Bruit des activités de loisirs amplifiées : niveau moyen limité (102 dB(A) /
  118 dB(C) selon les cas) et information du public `[11]`.

### 6.6 Union européenne — Directive « environnement » 2002/49/CE

- Impose l'évaluation/gestion du bruit environnemental via les indicateurs
  **Lden** et **Lnight**, et des **cartes stratégiques de bruit** (notamment
  agglomérations ≥ 100 000 habitants et grandes infrastructures) `[9]`.

---

## 7. Charge sanitaire (Europe)

Chiffres de l'Agence européenne pour l'environnement, à partir des seuils de la
directive bruit (55 dB Lden / 50 dB Lnight) `[4][5]` :

| Indicateur | Valeur annuelle |
|---|---|
| Personnes exposées à des niveaux nocifs | **> 100 millions** |
| Nouveaux cas de cardiopathie (ischémique) | **48 000** |
| Décès prématurés | **12 000** |
| Forte gêne chronique | **22 millions** |
| Forte perturbation chronique du sommeil | **6,5 millions** |
| Troubles d'apprentissage (enfants, aérien) | **12 000** |
| Années de vie en bonne santé perdues (DALY) | **≈ 1 million** |

À retenir : la **gêne et la perturbation du sommeil** représentent l'essentiel de
la charge de morbidité liée au bruit, devant la cardiopathie ischémique `[4]`.

---

## 8. Établi vs incertain

**Établi / consensuel**
- Lien **niveau × durée → perte auditive** (relation reconnue, modélisée par
  ISO 1999) `[2][14]`.
- **Perturbation du sommeil** et **gêne** : effets les mieux documentés et les
  plus prévalents `[2][4]`.
- Association du bruit des transports avec **hypertension** et **cardiopathie
  ischémique**, maximale pour la cardiopathie `[2][6][7]`.
- **Effets sur la cognition des enfants** exposés (bruit aérien) `[2][4]`.

**Contesté / incertain**
- **Forme exacte** des relations dose-réponse aux **faibles niveaux** et seuils
  d'apparition `[2]`.
- Lien bruit → **santé mentale** : données **non conclusives** `[2]`.
- **Effets combinés** de sources multiples : pas de consensus sur un modèle de
  gêne **totale** `[2]`.
- **Incertitudes méthodologiques** : couverture partielle des cartes, données par
  bandes de 5 dB, extrapolation de fonctions génériques `[4]`.

**Mise en garde** : les indicateurs énergétiques (**LAeq**) ne suffisent pas ;
il faut **aussi** suivre les maxima (**LAmax**) et le **nombre d'événements**,
surtout la nuit `[2][3]`.

---

## 9. Comment vérifier

- Chaque `[n]` renvoie à la source listée en §10.
- Sources **primaires** : OMS `[1][2][3]`, textes réglementaires UE/France
  `[9][10][11]`, agences (EEA `[4][5]`, NIOSH/OSHA `[12]`, OMS `[13]`), normes
  `[14]`.
- Sources **de revue** (accès libre PMC) : `[6][7]` ; article fondateur `[8]`.
- Toujours relever **la pondération** et **l'indicateur** d'un niveau « en dB » :
  LAeq, Lden, Lnight, LAmax et dB(A) ne sont pas interchangeables `[1][2]`.

---

## 10. Références

1. OMS Bureau régional de l'Europe. *Environmental Noise Guidelines for the
   European Region.* Copenhague : OMS, 2018. ISBN 9789289053563 ;
   WHO/EURO:2018-3287-43046-60243.
   https://www.who.int/europe/publications/i/item/9789289053563
2. Berglund B, Lindvall T, Schwela DH (éd.). *Guidelines for Community Noise.*
   Genève : OMS, 1999. https://www.who.int/publications/i/item/a68672
   (texte intégral : https://ruidos.org/Noise/WHO_Noise_guidelines_summary.html)
3. OMS Bureau régional de l'Europe. *Night Noise Guidelines for Europe.*
   Copenhague : OMS, 2009. ISBN 9789289041737.
   https://www.who.int/europe/publications/i/item/9789289041737
4. Agence européenne pour l'environnement (AEE / EEA). *Health risks caused by
   environmental noise in Europe.* EEA Briefing no. 21/2020, 14 déc. 2020.
   ISBN 978-92-9480-296-5 ; doi:10.2800/64834.
   https://www.eea.europa.eu/en/analysis/publications/health-risks-caused-by-environmental-noise-in-europe
5. Agence européenne pour l'environnement (AEE / EEA). *Environmental noise in
   Europe — 2020.* EEA Report No 22/2019.
   https://www.eea.europa.eu/publications/environmental-noise-in-europe
6. Basner M, Babisch W, Davis A, et al. *Auditory and non-auditory effects of
   noise on health.* The Lancet. 2014;383(9925):1325-1332.
   doi:10.1016/S0140-6736(13)61613-X ; PMCID PMC3988259.
   https://pubmed.ncbi.nlm.nih.gov/24183105/
7. Münzel T, Gori T, Babisch W, Basner M. *Cardiovascular effects of
   environmental noise exposure.* European Heart Journal. 2014;35(13):829-836.
   doi:10.1093/eurheartj/ehu030 ; PMCID PMC3971384.
   https://pmc.ncbi.nlm.nih.gov/articles/PMC3971384/
8. Miedema HME, Oudshoorn CGM. *Annoyance from transportation noise:
   relationships with exposure metrics DNL and DENL and their confidence
   intervals.* Environmental Health Perspectives. 2001;109(4):409-416.
   doi:10.1289/ehp.01109409 ; PMCID PMC1240284.
   https://pubmed.ncbi.nlm.nih.gov/11335190/
9. Parlement européen et Conseil. *Directive 2002/49/CE relative à l'évaluation
   et à la gestion du bruit dans l'environnement* (END). JO L 189, 18.7.2002.
   https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32002L0049
10. Parlement européen et Conseil. *Directive 2003/10/CE concernant les
    prescriptions minimales de sécurité et de santé relatives à l'exposition des
    travailleurs aux risques dus au bruit.* JO L 42, 15.2.2003.
    https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32003L0010
11. France. *Code de la santé publique*, art. R. 1336-4 à R. 1336-8 (bruits de
    voisinage) ; *arrêté du 23 janvier 1997* (limitation des bruits des ICPE) ;
    *arrêté du 20 août 2015*. https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000035425936
12. NIOSH / OSHA (US). NIOSH *Criteria for a Recommended Standard: Occupational
    Noise Exposure* (REL 85 dB(A), 8 h, taux 3 dB) ; OSHA 29 CFR 1910.95
    (PEL 90 dB(A), 8 h, taux 5 dB).
    https://www.cdc.gov/niosh/noise/prevent/understand.html ;
    https://www.osha.gov/noise
13. OMS. *Deafness and hearing loss* — aide-mémoire, 2024.
    https://www.who.int/news-room/fact-sheets/detail/deafness-and-hearing-loss
14. ISO. *ISO 1999* (estimation de l'altération auditive due au bruit) ;
    *ISO 9612* (mesure de l'exposition au bruit en milieu de travail).
    https://www.iso.org/standard/6759.html ;
    https://www.iso.org/standard/41718.html
15. Wheeler MR, Everett B, Williamson SM, Prybutok V. *Infrasound and
    Low-Frequency Noise in Data Center Environments: A Narrative Review Toward
    Health-Protective Acoustic Design Standards.* Clean Technologies.
    2026;8(4):126. doi:10.3390/cleantechnol8040126.
    https://www.mdpi.com/2571-8797/8/4/126
16. Tao Y, Gao P. *Global data center expansion and human health: A call for
    empirical research.* Eco-Environment & Health. 2025;4(3):100157.
    doi:10.1016/j.eehl.2025.100157 ; PMCID PMC12273412.
    https://pmc.ncbi.nlm.nih.gov/articles/PMC12273412/
17. Environmental and Energy Study Institute (EESI). *Communities Are Raising
    Noise Pollution Concerns About Data Centers.* 23 mars 2026 (source secondaire
    / note d'information). https://www.eesi.org/articles/view/communities-are-raising-noise-pollution-concernsabout-data-centers
18. Joint Legislative Audit and Review Commission (JLARC), Commonwealth de
    Virginie. *Report on Data Centers (Rpt598-2).* 2024.
    https://jlarc.virginia.gov/pdfs/reports/Rpt598-2.pdf

---

## 11. Lexique des unités et acronymes

### 11.1 Unités et notations

| Symbole | Signification | Remarque |
|---|---|---|
| **Hz** | hertz | Unité de fréquence : 1 Hz = 1 cycle par seconde `[2]` |
| **kHz** | kilohertz | 1 kHz = 1 000 Hz |
| **dB** | décibel | Pour le son, niveau relatif à **20 µPa** ; échelle logarithmique `[2]` |
| **dB(A)** / **dBA** | décibel pondéré A | Pondération approchant l'oreille aux niveaux faibles ; **sous-estime les basses fréquences** `[2]` |
| **dB(C)** | décibel pondéré C | Pondération plus plate (basses fréquences) `[2]` |
| **dB(Z)** | décibel pondéré Z | Pondération « zéro » = **linéaire** |
| **dB SPL** | *Sound Pressure Level* | Niveau de pression acoustique (à préciser avec la pondération) |
| **µPa** | micropascal | Unité de pression acoustique du dB (référence 20 µPa) |
| **Pa** | pascal | Unité de pression ; pics de la directive bruit au travail (112/140/200 Pa) `[10]` |
| **LAeq,T** | niveau équivalent pondéré A sur T | Moyenne énergétique, bruit continu `[2]` |
| **LAmax** | niveau maximal pondéré A | Pertinence pour les événements isolés `[2]` |
| **SEL / LAE** | *Sound Exposure Level* | Énergie d'un événement isolé, ramenée à 1 s `[2]` |
| **Lden** | *Level day-evening-night* | 24 h ; pénalités **+5 dB** (soir) et **+10 dB** (nuit) `[1]` |
| **Lnight** | *Level night* | Niveau équivalent nocturne (8 h, ≈ 23 h–07 h) `[1][3]` |
| **%HA** | *% Highly Annoyed* | Pourcentage de personnes **fortement gênées** `[8]` |
| **C − A** | écart pondération C − A | **> 10 dB** = spectre riche en basses fréquences → analyse en fréquence recommandée `[2]` |
| **Émergence** | différence bruit ambiant − bruit résiduel | Cadre français : 5/3 dB(A) jour/nuit ; spectrale 7/5 dB `[11]` |
| **DALY** | *Disability-Adjusted Life Year* | Année de vie corrigée de l'incapacité (charge de morbidité) `[4]` |
| **dBA** | voir **dB(A)** | Écriture anglophone de dB(A) |

### 11.2 Acronymes, organismes et normes

| Sigle | Signification |
|---|---|
| **AEE / EEA** | Agence européenne pour l'environnement / *European Environment Agency* `[4][5]` |
| **BTP** | bâtiment et travaux publics (chantiers = source de bruit) `[2]` |
| **CSP** | Code de la santé publique (France) — art. R. 1336-4 à R. 1336-8 `[11]` |
| **CVC** | chauffage, ventilation, climatisation (anglais *HVAC*) — source de bruit des bâtiments et datacenters `[15]` |
| **DALY** | voir §11.1 (année de vie corrigée de l'incapacité) `[4]` |
| **dB(A) / dBA** | voir §11.1 `[2]` |
| **DOI** | *Digital Object Identifier* — identifiant pérenne d'une publication |
| **EESI** | *Environmental and Energy Study Institute* — institut américain (note sur bruit des datacenters) `[17]` |
| **END** | *Environmental Noise Directive* — directive 2002/49/CE sur le bruit dans l'environnement `[9]` |
| **HTA** | hypertension artérielle `[2][7]` |
| **ICPE** | installation classée pour la protection de l'environnement (France) `[11]` |
| **ISBN** | *International Standard Book Number* — identifiant d'un livre/rapport `[1]` |
| **ISO** | *International Organization for Standardization* — **ISO 1999** (perte auditive), **ISO 9612** (mesure au travail) `[14]` |
| **JLARC** | *Joint Legislative Audit and Review Commission* — commission d'audit de Virginie (rapport datacenters 2024) `[18]` |
| **IHD / cardiopathie ischémique** | *Ischaemic Heart Disease* — maladie coronarienne `[4][7]` |
| **Lden / Lnight** | voir §11.1 `[1]` |
| **NIHL** | *Noise-Induced Hearing Loss* — perte auditive induite par le bruit `[2]` |
| **NIOSH** | *National Institute for Occupational Safety and Health* (US) — REL 85 dB(A)/8 h `[12]` |
| **OMS / WHO** | Organisation mondiale de la santé / *World Health Organization* `[1][2][3]` |
| **OSHA** | *Occupational Safety and Health Administration* (US) — PEL 90 dB(A)/8 h `[12]` |
| **PEL** | *Permissible Exposure Limit* — valeur limite réglementaire (OSHA) `[12]` |
| **PMC / PMCID** | *PubMed Central* / son identifiant — archive en accès libre `[6][7][8]` |
| **REL** | *Recommended Exposure Limit* — valeur recommandée (NIOSH) `[12]` |
| **SEL / LAE** | voir §11.1 (niveau d'exposition sonore d'un événement) `[2]` |
| **SPL** | *Sound Pressure Level* — voir dB SPL `[2]` |
| **TWA** | *Time-Weighted Average* — moyenne pondérée dans le temps (exposition sur 8 h) `[12]` |
| **UE / EU** | Union européenne / *European Union* `[9][10]` |
| **US** | *United States* — États-Unis `[12]` |
| **ZER** | zone à émergence réglementée (France) `[11]` |
