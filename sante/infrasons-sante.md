# Infrasons et santé — synthèse sourcée

Document de référence. Compilation : 2026-10-14.

**Convention de citation.** Chaque affirmation chiffrée porte un renvoi `[n]` vers
la liste de sources (§9). Les références sont des documents vérifiables (OMS,
revues à DOI, normes) ; quand une donnée n'est disponible qu'en ligne via une
page de synthèse (Wikipédia), la source primaire d'origine est indiquée. Aucune
valeur n'est donnée sans source.

**Pondérations à ne pas confondre** : `dB SPL` (niveau physique), `dB(Z)`
(linéaire), `dB(A)`/`dB(C)` (pondérés audition), **`dB(G)`** (ISO 7196, spécifique
infrason 0,1–20 Hz). La pondération A efface tout sous 20 Hz et **n'est pas
valide pour l'infrason** `[3][6]`. Une même valeur « en dB » n'est comparable que
si la pondération est identique.

---

## 1. Définitions et repères

- **Infrasons** : sons de fréquence **< 20 Hz** (le plus souvent 0,1–20 Hz ;
  jusqu'à 0,001 Hz en géophysique) ; seuil défini par le standard
  ANSI/ASA S1.1-2013 `[8]`.
- **Basses fréquences (LFN)** : **20–200 Hz** (souvent 20–250 Hz) `[4][6]`.
- **20 Hz** = limite basse normale de l'audition ; un pur sinus reste identifiable
  jusqu'à **12 Hz** en conditions idéales et fort volume `[8]`.
- **< 10 Hz** : perception des **cycles isolés** et **sensation de pression sur le
  tympan** (pas d'un « son ») `[8]`.
- La sensibilité auditive décroît quand la fréquence baisse ; la plage dynamique
  se compresse, si bien qu'une **faible hausse de niveau** peut faire passer un
  infrason de « à peine audible » à « fort » `[8]`.
- **Variabilité interindividuelle** : environ **2,5 %** de la population aurait un
  seuil basses fréquences au moins **12 dB plus sensible** que la moyenne
  `[5]` (Leventhall 2004).
- L'air est un **très mauvais milieu** de transfert des vibrations basse fréquence
  vers le corps ; les effets graves supposent une **transmission mécanique**
  (siège, structure), pas seulement aérienne `[8]`.

### Seuils d'audition par bande de 1/3 d'octave — DIN 45 680 `[6]`

| Hz | 8 | 10 | 12,5 | 16 | 20 | 25 | 31,5 | 40 | 50 | 63 | 80 | 100 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Seuil (dB SPL) | 103 | 95 | 87 | 79 | 71 | 63 | 55,5 | 48 | 40,5 | 33,5 | 28 | 23,5 |

Lecture : entendre un **8 Hz** demande ~**103 dB SPL** ; un **20 Hz** ~**71 dB SPL**.

---

## 2. Sources d'infrasons

- **Naturelles** : vent, vagues (microbaroms ~0,2 Hz), orages, séismes, volcans,
  avalanches, météores, aurores `[8]`. Niveaux mesurés jusqu'à **~110 dB** par un
  vent de ~26 km/h `[4]`.
- **Animales (communication)** : baleines (10 Hz–31 kHz, jusqu'à ~117 dB, portée
  de centaines de km) ; éléphants (14–35 Hz, ~117 dB, ~10 km) ; rhinocéros
  (< 3 Hz) ; tigre (< 18 Hz) ; pigeons (navigation) `[8]`.
- **Anthropiques** : moteurs diesel, éoliennes, compresseurs, CVC, avions, trains,
  explosions et sonic booms, haut-parleurs de forte puissance `[4][8]` ; torches
  à méthane (« flares »), pic à **~17–20 Hz** `[4]`.

---

## 3. Effets physiologiques (fréquence × niveau × durée)

### 3.1 Études humaines

| Fréquence | Niveau | Durée | Effets observés | Source |
|---|---|---|---|---|
| 2–3 Hz | **160 dB** (transmis par le siège) | — | Ataxie motrice, nausée, troubles visuels, baisse de performance, difficultés de communication (essais 0,5–40 Hz, programme spatial US) | `[8]` |
| 5 et 10 Hz | 100 et 135 dB | 15 min | Fatigue, pression auriculaire, baisse de concentration, somnolence, sensation de vibration des organes internes | `[4]` |
| 7,5 Hz | 130 dB | 50 min | Somnolence, légère hausse de tension artérielle ; pas d'autre effet délétère | `[8]` (Borredon 1972) |
| 1–20 Hz | jusqu'à **144 dB SPL** | 8 min | Seulement inconfort auriculaire léger | `[8]` (Slarve & Johnson 1975) |
| — | ~100–120 dB | — | Céphalées, sensation de balancement, fatigue, acouphènes, difficultés respiratoires | `[4]` |
| 5 et 16 Hz | 95 dB | 5 min | Effet mesurable sur le **balancement corporel** (fonction vestibulaire) | `[4]` |
| 6 Hz | 80–90 dB | 28 nuits (essai contrôlé) | Aucun changement vertige / douleur thoracique / nausée / santé mentale | `[4]` |
| — | 115 dB | professionnelle | Aucune hausse significative des symptômes (chauffeurs poids lourds) | `[4]` |

### 3.2 Données animales (mécanismes)

Exposition in vivo/in vitro, souvent à forte dose ; extrapolation à l'humain
prudente `[3]` :

| Fréquence | Niveau | Cible | Effet | Source |
|---|---|---|---|---|
| 5 Hz | 130 dB | Cœur (rat) | Apoptose des cardiomyocytes | `[3]` |
| 8 Hz | 130 dB | Testicules (rat) | Baisse de la méthylation de l'ADN | `[3]` |
| 16 Hz | 120 dB | Système endocrinien (rat) | ↑ ACTH et cortisone, ↓ flux gastrique | `[3]` |
| 20 Hz | 163 dB | Cochlée (animal) | Dégénérescence des cellules ciliées externes | `[3]` |

### 3.3 Résonances internes (repères)

- Haut du torse : **50–100 Hz** → gêne et inconfort ; ACGIH recommande d'abaisser
  le niveau en cas d'inconfort `[4]`.
- Œil : **~18 Hz** (NASA) → illusions visuelles / « visions » `[8]`.
- Mythe du **« brown note »** (incontinence fécale) : **non démontré**
  (MythBusters : test à 5 Hz jusqu'à 153 dB, aucun effet) `[8]`.
- Cas rares/anecdotiques : pneumothorax près de subwoofers de concert ; mort
  subite (SADS) après exposition à de fortes basses en discothèque — lien
  **non prouvé** (verdict : causes naturelles) `[8]`.

### 3.4 Centres de données (« datacenters ») : données émergentes

La question est **peu étudiée** mais des sources existent. La revue de référence
est **Wheeler et al. (2026)** `[10]` : les sources d'ILFN d'un datacenter sont les
**ventilateurs de refroidissement**, les systèmes **CVC (HVAC)**, les
**générateurs de secours** (diesel) et les **transformateurs électriques**. Constat
central : **aucune étude publiée n'a mesuré le spectre infrason / basse fréquence
d'un datacenter en exploitation**, ni examiné les effets sanitaires chez les
travailleurs ou les riverains pour l'exposition sub-audible ; les auteurs appellent
à une caractérisation en **dB(G) et en réponse plate, de 1 à 200 Hz**, préalable à
toute norme de conception acoustique `[10]`. Point métrologique décisif : la
pondération **A** atténue de **plus de 26 dB à 63 Hz** et de **plus de 50 dB** dans
l'infrason, ce qui **sous-estime massivement** l'exposition réelle et explique en
partie pourquoi les plaintes sont mal objectivées `[10]`. En audible, le bruit
interne d'un datacenter peut atteindre **96 dB(A)** `[11]` ; les générateurs
industriels montent à **~105 dB** et les tours de refroidissement à **~70 dB(A) à
120 m** `[13]`. Les riverains rapportent céphalées, vertiges, nausées, troubles du
sommeil, douleurs auriculaires et hypertension `[13]` — **données déclaratives**,
non corrélées à des mesures `[10][13]` ; en Virginie, près d'un tiers des
datacenters se situent à moins de ~61 m (200 pieds) de zones résidentielles (`[14]`, cité
par `[13]`). Un cadre analytique a été proposé pour relier l'ILFN des datacenters
à des inégalités sanitaires `[12]`, mais il **n'a pas été évalué par les pairs**.

À retenir : les preuves spécifiques « infrason de datacenter » restent **faibles**
(une revue narrative, des rapports institutionnels, des plaintes), **sans mesure
quantitative in situ publiée à ce jour** ; il n'existe **aucune valeur limite propre
aux datacenters** — les référentiels du §5 s'appliquent par analogie `[10]`.

---

## 4. Effets psychologiques

- **La « gêne » (annoyance) est l'effet principal et le mieux documenté** `[4]`.
- Les **basses fréquences 25–63 Hz** et **30–80 Hz** pèsent plus sur la gêne que
  l'infrason pur ou les hautes fréquences `[4]`.
- Gêne corrélée à : fatigue, vertiges, mauvaise concentration, sensation de
  pression sur la tête `[4]`.
- **Expérience de concert « Infrasonic »** (Purcell Room, Londres, 31 mai 2003,
  ~700–750 personnes ; Angliss, Wiseman, O'Keeffe) : surimpression d'un ton de
  **17 Hz** proche du seuil d'audition. **22 %** des participants rapportent
  malaise, tristesse, frissons, dégoût ou peur, sans perception consciente
  `[8][9]`.
- Hypothèse **« fantômes »** : un 18,98 Hz résonnant avec l'œil pourrait expliquer
  certaines « apparitions » (Tandy & Lawrence 1998 ; Wiseman) `[8]`.
- **Sommeil** : perturbations rapportées subjectivement, contribution propre de
  l'infrason **non tranchée** `[4][7]`.
- **Anxiété, irritabilité, détresse** associées aux environnements riches en
  infrasons de forte intensité `[3]`.
- **Effet nocebo** : les croyances négatives envers l'infrason génèrent des
  symptômes réels ; les plaintes subjectives (autour des éoliennes) ne sont pas
  toujours confirmées par les mesures objectives (cortisol, VFC, actigraphie)
  `[3][7]`.
- Indicateur de risque de plainte : écart **C − A ≥ 20 dB** = spectre déséquilibré
  (beaucoup de basses fréquences) propice aux plaintes `[4]`.

---

## 5. Valeurs limites et normes

| Référentiel | Limite | Source |
|---|---|---|
| **ACGIH (US)** | **145 dB** par bande de 1/3 d'octave de 1 à 100 Hz ; **150 dB** en niveau global | `[4]` |
| **US (hygiène du travail)** | max **145 dB** (1–80 Hz) ; max global **150 dB** | `[8]` |
| **Russie (SanPiN)** | 2 Hz : 100 ; 4 Hz : 95 ; 8 Hz : 90 ; 16 Hz : 85 ; global 100 dB ; max 120 dB | `[8]` |
| **Danemark** | 85 dB(G) (infrason) ; LFN : 20 dB(A) nuit / 25 dB(A) jour (moyennés sur 10 min, 10–160 Hz) ; bureaux 30 dB ; autres 35 dB | `[6]` |
| **Allemagne (DIN 45 680)** | Critère d'identification : **C − A ≥ 20 dB** ; bruit tonal : ≤ 5 dB au-dessus du seuil (jour), 0 dB (nuit) ; bruit large bande : 35 dB(A) jour / 25 dB(A) nuit | `[6]` |
| **Suède (SOSFS 1996:7)** | Courbe critère 31,5–200 Hz (56 dB à 31,5 Hz → 32 dB à 200 Hz) | `[6]` |
| **Pays-Bas** | Courbe critère 10–200 Hz ; critère d'audibilité 20–100 Hz | `[6]` |
| **Pologne** | Courbe L<sub>A10</sub> 10–250 Hz | `[6]` |
| **OMS 1999** | « Pour un bruit à forte proportion de basses fréquences, une valeur guide encore plus basse est recommandée » | `[2]` |

---

## 6. Position de l'OMS

**Référence** : OMS Europe, *Environmental Noise Guidelines for the European
Region*, 2018 — ISBN 9789289053563, n° de référence
WHO/EURO:2018-3287-43046-60243 `[1]`.

Recommandations (`Lden` = jour-soir-nuit ; `Lnight` = nuit) `[1]` :

| Source | Niveau | Force | Source |
|---|---|---|---|
| Trafic routier | 53 dB Lden / 45 dB Lnight | Forte | `[1]` |
| Trafic ferroviaire | 54 dB Lden / 44 dB Lnight | Forte | `[1]` |
| Trafic aérien | 45 dB Lden / 40 dB Lnight | Forte | `[1]` |
| **Éoliennes** | **45 dB Lden** | **Conditionnelle** (aucune reco pour Lnight) | `[1]` |
| Bruit de loisirs | 70 dB LAeq,24h (moyenne annuelle, toutes sources de loisirs) | Forte | `[1]` |

À retenir :

1. **L'OMS ne fixe pas de valeur limite propre à l'infrason** ; ses valeurs portent
   sur le bruit environnemental **audible** global `[1]`.
2. Pour les **éoliennes**, la reco (45 dB Lden) est **conditionnelle** car le
   nombre d'études de qualité sur les effets propres de l'infrason / basses
   fréquences est insuffisant ; pas de reco pour la nuit `[1][7]`.
3. L'infrason éolien aux niveaux usuels **n'est pas reconnu** comme causant des
   effets sanitaires **directs** ; les effets sont attribués à la **gêne** et aux
   facteurs **psychologiques (nocebo)** `[7]`.
4. La base « bruit » OMS antérieure (1999) demandait déjà une valeur guide **plus
   basse** pour les bruits riches en basses fréquences `[2]`.

---

## 7. Ce qui est établi vs incertain

**Établi / consensuel**
- L'infrason devient perceptible (pression, vibration) à fort niveau : seuils
  élevés (ex. ~71 dB à 20 Hz, ~103 dB à 8 Hz) `[6]`.
- À très fort niveau (≈ ≥ 110–130 dB selon fréquence/durée) et surtout par
  **transmission mécanique** : inconfort, pression thoracique, nausées, vertiges,
  troubles de l'équilibre, baisse de performance `[3][4][8]`.
- La **gêne** est l'effet sanitaire le plus net aux niveaux environnementaux réels
  `[4][7]`.
- L'OMS ne retient **aucun effet direct** de l'infrason éolien aux niveaux usuels
  `[1][7]`.

**Contesté / incertain**
- Effets **sous** le seuil d'audibilité (ex. 6 Hz à 80–90 dB) : résultats nuls ou
  non reproductibles `[3][4]`.
- Contribution propre de l'infrason aux **troubles du sommeil** et à l'anxiété
  `[4][7]`.
- Robustesse des **modifications cérébrales** observées (souvent sans traduction
  comportementale) `[3]`.
- Rôle de l'infrason dans le **syndrome de La Havane** : hypothèse **non prouvée**
  `[3]`.
- Mécanismes fins (cellulaires) : surtout issus de modèles **animaux / in vitro**
  `[3]`.

**Mise en garde** : la plupart des effets « graves » proviennent d'essais à **très
haute intensité** ou par **contact mécanique**, non représentatifs des expositions
environnementales ordinaires `[4][8]`.

---

## 8. Comment vérifier

- Chaque `[n]` renvoie à la source listée en §9. Les revues `[3][4][7]` sont en
  accès libre (PMC) ; `[1][2]` sont des publications OMS téléchargeables ; `[5]`
  est indexée sur PubMed ; `[6]` est la comparaison officielle des méthodes
  nationales (Agence danoise de l'environnement).
- Pour les données agrégées issues de `[8]` (Wikipédia), la source primaire citée
  par l'article est indiquée entre parenthèses ; vérifier dans cet article.
- Toujours relever **la pondération** d'un niveau « en dB » (§ en-tête) : une
  valeur dB(A) sous 20 Hz n'est pas exploitable pour l'infrason `[3][6]`.

---

## 9. Références

1. OMS Bureau régional de l'Europe. *Environmental Noise Guidelines for the
   European Region.* Copenhague : OMS, 2018. ISBN 9789289053563 ;
   WHO/EURO:2018-3287-43046-60243.
   https://www.who.int/europe/publications/i/item/9789289053563
2. Berglund B, Lindvall T, Schwela DH (éd.). *Guidelines for Community Noise.*
   Genève : OMS, 1999. https://www.who.int/publications/i/item/a68672
3. Kapoor P, Yadav RB, Agrawal N, Gaur S, Arora R. *Infrasound in Biology and
   Medicine: Insights into Mechanisms, Health Outcomes and Research
   Perspectives — A Narrative Review.* Noise & Health. 2025;27(129):676-691.
   doi:10.4103/nah.nah_136_25 ; PMCID PMC12818516.
   https://pmc.ncbi.nlm.nih.gov/articles/PMC12818516/
4. Chiu SK, Brueck SE, Wiegand DM, Free HL, Echt H. *Evaluation of Low-Frequency
   Noise, Infrasound, and Health Symptoms at an Administrative Building and Men's
   Shelter: A Case Study.* Seminars in Hearing. 2023;44(4):503-520.
   doi:10.1055/s-0043-1769497 ; PMCID PMC10562056.
   https://pmc.ncbi.nlm.nih.gov/articles/PMC10562056/
5. Leventhall HG. *Low frequency noise and annoyance.* Noise & Health.
   2004;6(23):59-72. PMID 15273024.
   https://pubmed.ncbi.nlm.nih.gov/15273024/
6. Danish Environmental Protection Agency / National Environmental Research
   Institute. *Laboratory Evaluation of Annoyance of Low Frequency Noise*,
   chap. 4 « Assessment Methods for Low Frequency Noise » (méthodes danoise,
   allemande DIN 45 680, suédoise SOSFS 1996:7, polonaise, néerlandaise), 2002.
   https://www2.mst.dk/udgiv/publications/2002/87-7944-955-7/html/kap04_eng.htm
7. van Kamp I, van den Berg F. *Health Effects Related to Wind Turbine Sound:
   An Update.* Int. J. Environ. Res. Public Health. 2021;18(13):6849.
   PMCID PMC8430592. https://pmc.ncbi.nlm.nih.gov/articles/PMC8430592/
8. Wikipédia (article « Infrasound », consulté 2026-10-14) — page d'agrégation
   citant les études primaires suivantes : Borredon (1972) ; Slarve & Johnson
   (1975) ; Leventhall, Benton & Pelmear, *A Review of Published Research on Low
   Frequency Noise and its Effects* (Defra, 2003) ; essais NASA / programme
   spatial US (von Gierke) ; Tandy & Lawrence (1998) ; *MythBusters* (2005).
   https://en.wikipedia.org/wiki/Infrasound
9. Wiseman R, O'Keeffe C, Angliss S. *Infrasonic* / « Soundless Music » —
   expérience contrôlée, Purcell Room (Londres), 31 mai 2003. Rapportée par :
   *The Guardian*, 8 septembre 2003.
   https://www.theguardian.com/science/2003/sep/08/sciencenews.science ;
   voir aussi https://www.sarahangliss.com/infrasonic/
10. Wheeler MR, Everett B, Williamson SM, Prybutok V. *Infrasound and
    Low-Frequency Noise in Data Center Environments: A Narrative Review Toward
    Health-Protective Acoustic Design Standards.* Clean Technologies.
    2026;8(4):126. doi:10.3390/cleantechnol8040126.
    https://www.mdpi.com/2571-8797/8/4/126
11. Tao Y, Gao P. *Global data center expansion and human health: A call for
    empirical research.* Eco-Environment & Health. 2025;4(3):100157.
    doi:10.1016/j.eehl.2025.100157 ; PMCID PMC12273412.
    https://pmc.ncbi.nlm.nih.gov/articles/PMC12273412/
12. Pudina T. *Infrasonic and Low-Frequency Noise Exposure from Large Data
    Centers: A Proposed Analytical Framework.* Adams State University, 2026
    (**document non évalué par les pairs**).
    https://www.academia.edu/165875697/
13. Environmental and Energy Study Institute (EESI). *Communities Are Raising
    Noise Pollution Concerns About Data Centers.* 23 mars 2026 (source secondaire
    / note d'information). https://www.eesi.org/articles/view/communities-are-raising-noise-pollution-concernsabout-data-centers
14. Joint Legislative Audit and Review Commission (JLARC), Commonwealth de
    Virginie. *Report on Data Centers (Rpt598-2).* 2024.
    https://jlarc.virginia.gov/pdfs/reports/Rpt598-2.pdf

---

## 10. Lexique des unités et acronymes

### 10.1 Unités et notations

| Symbole | Signification | Remarque |
|---|---|---|
| **Hz** | hertz | Unité de fréquence : 1 Hz = 1 cycle par seconde |
| **kHz** | kilohertz | 1 kHz = 1 000 Hz |
| **dB** | décibel | Unité logarithmique de rapport de niveaux. Pour le son, niveau de pression acoustique relatif à **20 µPa** (référence à 1 kHz) |
| **dB SPL** | *Sound Pressure Level* (niveau de pression acoustique) | Niveau physique, souvent non pondéré ; à préciser avec la pondération |
| **dB(A)** | décibel pondéré A (noté aussi **dBA**) | Approxime la sensibilité de l'oreille aux niveaux faibles ; s'effondre sous 20 Hz → **non valide pour l'infrason** `[3][6]` |
| **dB(C)** | décibel pondéré C | Pondération plus plate, sert à capter l'énergie des basses fréquences |
| **dB(Z)** | décibel pondéré Z | Pondération « zéro » = **linéaire** (aucune pondération) |
| **dB(G)** | décibel pondéré G | ISO 7196, pondération **spécifique de l'infrason** (0,1–20 Hz) `[3][6]` |
| **dB(A),LF** (L<sub>pA,LF</sub>) | niveau basse fréquence pondéré A (méthode danoise) | Somme du spectre 10–160 Hz après corrections A nominales `[6]` |
| **Bande de 1/3 d'octave** | bande de tiers d'octave | Subdivision du spectre sonore autour d'une fréquence centrale `[6]` |
| **Lden** | *Level day-evening-night* | Niveau équivalent jour-soir-nuit, pénalités +5 dB (soir) et +10 dB (nuit) `[1]` |
| **Lnight** | *Level night* | Niveau équivalent nocturne (23 h–07 h) `[1]` |
| **LAeq,24h** | niveau acoustique équivalent pondéré A sur 24 h | Utilisé par l'OMS pour le bruit de loisirs `[1]` |
| **L<sub>A10</sub>** | courbe critère polonaise | Courbe de référence 10–250 Hz au-delà de laquelle un bruit basse fréquence est jugé gênant `[6]` |
| **C − A** | écart pondération C moins pondération A | **≥ 20 dB** = spectre riche en basses fréquences, propice aux plaintes `[4][6]` |
| **min** | minute(s) | Durée d'exposition |
| **%** | pourcentage | Part d'une population (2,5 % ; 22 %) |
| **km/h** | kilomètre par heure | Vitesse du vent (~26 km/h) `[4]` |
| **µPa** | micropascal | Unité de pression acoustique utilisée dans la définition du dB |

### 10.2 Acronymes, organismes et normes

| Sigle | Signification |
|---|---|
| **ACGIH** | *American Conference of Governmental Industrial Hygienists* — association américaine d'hygiène industrielle (valeurs limites) `[4]` |
| **ACTH** | *AdrenoCorticoTropic Hormone* — hormone corticotrope (stimule le cortisol) `[3]` |
| **ADN** | acide désoxyribonucléique (matériel génétique) `[3]` |
| **ANSI / ASA** | *American National Standards Institute* / *Acoustical Society of America* — définissent le seuil d'audibilité (ANSI/ASA S1.1-2013) `[8]` |
| **CVC** | chauffage, ventilation, climatisation (équivalent de *HVAC*) — source d'infrasons `[4][8]` |
| **Defra** | *Department for Environment, Food and Rural Affairs* — ministère britannique de l'environnement (rapport 2003) `[8]` |
| **DIN** | *Deutsches Institut für Normung* — organisme allemand de normalisation ; **DIN 45 680** = norme d'évaluation du bruit basse fréquence `[6]` |
| **DOI** | *Digital Object Identifier* — identifiant pérenne d'une publication |
| **EESI** | *Environmental and Energy Study Institute* — institut américain (note d'information sur le bruit des datacenters) `[13]` |
| **HVAC** | *Heating, Ventilation, and Air Conditioning* — voir **CVC** `[10]` |
| **ILFN** | *Infrasound and Low-Frequency Noise* — infrasons et bruit basse fréquence `[10]` |
| **ISBN** | *International Standard Book Number* — identifiant d'un livre/rapport `[1]` |
| **ISO** | *International Organization for Standardization* ; **ISO 7196** = pondération de fréquence pour l'infrason (dB(G)) `[3][6]` |
| **JLARC** | *Joint Legislative Audit and Review Commission* — commission d'audit de Virginie (rapport datacenters 2024) `[14]` |
| **LFN** | *Low Frequency Noise* — bruit basse fréquence (≈ 20–200 Hz) ; voir aussi **ILFN** `[4][6]` |
| **MDPI** | *Multidisciplinary Digital Publishing Institute* — éditeur de la revue *Clean Technologies* `[10]` |
| **NASA** | *National Aeronautics and Space Administration* — agence spatiale américaine (essais vibratoires) `[8]` |
| **OMS / WHO** | Organisation mondiale de la santé / *World Health Organization* ; **WHO/EURO** = son bureau régional pour l'Europe (réf. WHO/EURO:2018-…) `[1][2]` |
| **PMC / PMCID** | *PubMed Central* / son identifiant — archive de revues biomédicales en accès libre `[3][4][7]` |
| **PMID** | *PubMed identifier* — identifiant d'un article dans PubMed `[5]` |
| **SanPiN** | *Sanitarnyye pravila i normy* — « règles et normes sanitaires » (Russie) `[8]` |
| **SADS** | *Sudden Arrhythmic Death Syndrome* — mort subite d'origine rythmique `[8]` |
| **SOSFS** | *Socialstyrelsens författningssamling* — recueil de règlements du Conseil national suédois de la santé et du bien-être ; **SOSFS 1996:7** = recommandations bruit basse fréquence `[6]` |
| **SPL** | *Sound Pressure Level* — niveau de pression acoustique (voir dB SPL) `[3]` |
| **US** | *United States* — États-Unis `[8]` |
| **VFC** | variabilité de la fréquence cardiaque (en anglais *HRV*) — indicateur physiologique de stress `[3][7]` |
