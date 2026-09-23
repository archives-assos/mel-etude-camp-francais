# Glossaire Technique — Vieillissement des Cuves de Réacteurs Nucléaires

---

## A

### Adjusted Reference Temperature (ART)
**Température de référence ajustée**. Température pseudo-ductile du matériau de la cuve du réacteur, ajustée en fonction de la fluence neutronique accumulée et de la composition chimique (cuivre, phosphore, nickel). C'est le paramètre clé pour évaluer la résistance à la fissuration fragile. Plus l'ART augmente, plus la matière devient fragile.

### Année Pleine Effet (EFPY — Effective Full Power Year)
Unité de mesure du temps d'irradiation cumulée. Une année pleine effet correspond à une année où le réacteur fonctionne à 100% de sa puissance nominale. Une année avec des arrêts ou des variations de puissance correspond à moins d'une EFPY. Facteur de conversion typique : 40 ans réels ≈ 32-35 EFPY (facteur ~0,80).

---

## B

### Beltline 4 (ceinture 4)
Zone de la paroi interne du réacteur pressure vessel (RPV) située à environ 200-250 mm sous la surface intérieure. C'est la zone où le flux neutronique est le plus intense et où l'embrittlement est maximal. Les capsules de surveillance sont placées à cette profondeur. C'est le point le plus critique pour l'évaluation de l'intégrité de la cuve.

### Benchmark (étalonnage)
Comparaison entre les résultats de calculs de fluence neutronique et des données expérimentales issues de programmes de surveillance ou de réacteurs témoins. Les benchmarks garantissent la validité des méthodes de calcul (RG 1.190 du NRC). Exemples : VENUS-1, OECD/NEA benchmarks.

---

## C

### Capsule de surveillance (surveillance capsule)
Échantillon de matériau (acier de type 4140 ou 4340) placé à l'intérieur du réacteur pour mesurer la fluence neutronique et l'embrittlement accumulés au fil du temps. Les capsules contiennent des éprouvettes Charpy (impact), des dosimètres de flux et des échantillons de composition chimique. Retirées périodiquement pour analyse. Norme ASTM E185-82.

### CEA (Commissariat à l'énergie atomique et aux énergies alternatives)
Organisme de recherche français qui réalise les calculs de fluence neutronique pour le compte d'EDF. Le CEA a développé le code **EFLUVE** (code 1D simplifié) pour les calculs de fluence par cycle de chaque unité, validé par comparaison avec le code 3D **TRIPOLI** (méthode Monte Carlo).

### Charpy (essai Charpy)
Essai de résilience par absorption d'énergie d'impact (éprouvette en V). Mesure la ténacité (résistance à la fissuration fragile) du matériau à une température donnée. L'essai Charpy est l'outil principal pour suivre l'embrittlement de la cuve du réacteur au fil du temps. La perte d'énergie d'impact indique le durcissement.

### Coefficient de plomb (lead factor)
Facteur multiplicatif appliqué à la fluence mesurée par une capsule de surveillance pour estimer la fluence à la paroi interne du réacteur. La capsule étant à ~200 mm sous la surface, la paroi interne (beltline 4) reçoit un flux plus intense. Le lead factor dépend de la géométrie du réacteur.

### Cuve du réacteur (Reactor Pressure Vessel — RPV)
Ensemble constitué de la cuve cylindrique, du couvercle (closure head) et des fonds. Composée d'acier bas-allié (généralement SA-508 classe 3) conçu pour résister à la pression, à la température et au flux neutronique. La cuve est soudée à la base de la centrale et **non remplaçable** en exploitation.

### Critère G (10 CFR Appendix G)
Réglementation américaine (NRC) définissant les exigences de résistance à la fissuration fragile pour la cuve du réacteur. Le critère G impose que la température de référence ajustée (RTNDT) ne dépasse pas une limite telle que la marge de résilience reste suffisante. En France, l'ASN applique des exigences équivalentes via le code ASN-IS (Implantation des Systèmes nucléaires).

---

## D

### DORA / DORT (Discrete Ordinates Transport)
Code de calcul de transport neutronique utilisé pour calculer les flux neutroniques dans le système réacteur. DORT (avec la bibliothèque de sections efficaces BUGLE) est le code standard pour les calculs de fluence au vaisseau (RG 1.190 du NRC). Il résout l'équation de transport aux différences finies discrètes.

### Dpa (Displacements Per Atom)
Nombre de déplacements d'atomes dans le réseau cristallin du matériau dus aux collisions avec des neutrons. Mesure alternative de la dégradation des matériaux. 1 dpa = 1 atome déplacé par atome cible. Utilisé pour quantifier les dommages par irradiation.

---

## E

### EFLUVE
Code de calcul de fluence neutronique développé par le CEA pour le compte d'EDF. Code 1D simplifié, rapide et efficace pour les calculs par cycle de chaque unité du parc. Validé par comparaison avec les résultats du code 3D TRIPOLI (méthode Monte Carlo). EFLUVE est l'outil principal pour le suivi de la fluence dans le parc français.

### Effective Full Power Year (EFPY / année pleine effet)
Voir **Année Pleine Effet**.

### Embrittlement par fluence neutronique (neutron irradiation embrittlement)
Phénomène de durcissement et de fragilisation des aciers bas-alliés soumis au flux neutronique dans un réacteur nucléaire. Les neutrons provoquent des déslocations et la formation de précipités (sulfures, carbures, phases métalliques intermétalliques) qui réduisent la ductilité et la ténacité du matériau. Se manifeste par l'augmentation du RTNDT (température de transition ductile-fragile).

### ETC (Embrittlement Trend Curve)
Courbe de tendance d'embrittlement qui relie la fluence neutronique au décalage de la température de transition ductile-fragile (ΔRTNDT). Basée sur les données des capsules de surveillance (ASTM E185-82). L'ETC permet de prédire l'état futur de la cuve en fonction de la fluence accumulée. Le modèle RG 1.99 (NRC) est la référence.

---

## F

### Fluence neutronique (neutron fluence)
Quantité totale de neutrons rapides (E > 1 MeV) traversant une surface donnée, intégrée dans le temps. Unité : n/cm² (neutrons par centimètre carré). Mesurée ou calculée au ceinture 4 de la cuve. Valeurs typiques : 4-7×10¹⁹ n/cm² pour 40 ans d'exploitation. Plus la fluence est élevée, plus l'embrittlement est important.

### Fluence de conception (Design Life Fluence — DLF)
Fluence neutronique maximale prévue à la fin de la durée de vie de conception du réacteur. Pour les réacteurs français de 900 MWe (3 boucles) : ~6,5-7×10¹⁹ n/cm² à 40 ans. Pour les 1300 MWe (4 boucles) : ~4,5×10¹⁹ n/cm² à 40 ans. La fluence de conception détermine la taille de la cuve et le gap d'atténuation.

### Flux neutronique (neutron flux)
Nombre de neutrons rapides par cm² et par seconde dans le réacteur. Différent de la fluence (qui est intégrée dans le temps). Le flux est très élevé dans le cœur (~10¹⁴-10¹⁵ n/cm²/s) et diminue de plusieurs décennies (~10⁴×) lorsqu'il atteint la cuve du réacteur.

### Fracture Toughness (résistance à la fissuration fragile)
Mesure de la capacité d'un matériau à résister à la propagation d'une fissure. Exprimée en MPa·√m (KIC) ou en J (énergie d'impact Charpy). L'embrittlement par fluence neutronique réduit la fracture toughness. Si la fracture toughness descend en dessous d'un seuil critique, la cuve peut rompre fragilement sous contrainte thermique ou mécanique.

---

## G

### Gap d'atténuation (water gap / attenuation gap)
Espace entre le bord du cœur (fuel assembly) et la paroi interne du réacteur pressure vessel. Rempli d'eau (modérateur). L'eau atténue (réduit) le flux neutronique avant qu'il n'atteigne la cuve. Plus le gap est large, plus l'atténuation est forte. Facteur clé : les réacteurs 1300 MWe ont un gap plus large que les 900 MWe → fluence au vaisseau plus faible.

### Grande Ceinture (outer beltline / beltline 4)
Synonyme de ceinture 4. Zone la plus externe de la zone critique de la cuve. L'embrittlement y est maximal car c'est la première surface interne exposée au flux neutronique.

---

## H

### Head (couvercle de cuve)
Partie supérieure amovible du réacteur pressure vessel. Le couvercle est soumis aux mêmes contraintes de fluence que la cuve, mais est remplaçable (contrairement à la cuve elle-même). Le Flamanville EPR a nécessité l'autorisation ASN pour l'utilisation de son couvercle (contraintes de fabrication).

### H2 (hydrogène)
Dans le contexte de l'embrittlement, l'hydrogène peut être absorbé par l'acier de la cuve lors de réactions radiolytiques dans l'eau du circuit primaire. L'hydrogène ambiant peut causer la fragilisation par hydrogène (hydrogen embrittlement), un phénomène distinct de l'embrittlement par fluence neutronique mais qui peut interagir avec celui-ci.

---

## I

### Irradiation (irradiation neutronique)
Exposition d'un matériau au flux neutronique dans le réacteur. L'irradiation provoque des dommages au réseau cristallin (dislocations, vacants, précipités). L'intégralité de l'irradiation est mesurée par la fluence (n/cm²).

### IRSN (Institut de radioprotection et de sûreté nucléaire)
Institut français d'expertise pour la sûreté nucléaire, dépendant du CEA (fusionné avec l'ASN le 1er janvier 2025 sous le nom ASNR). L'IRSN réalise les évaluations techniques indépendantes pour l'ASN, notamment les études de fluence et d'embrittlement.

---

## K

### KIC (Fracture Toughness — Critical Stress Intensity Factor)
Seuil critique de résistance à la fissuration fragile. Si le facteur d'intensité de contrainte (K) dépasse KIC, la fissure se propage de manière fragile. L'embrittlement par fluence réduit KIC, rendant la cuve vulnérable à la rupture sous contrainte thermique ou mécanique.

---

## N

### Neutron damage (dommages par neutrons)
Terme général désignant tous les effets délétères de l'irradiation neutronique sur les matériaux : durcissement, embrittlement, gonflement (swelling), migration d'objets gazeux (helium, hydrogène), changement de propriétés mécaniques. Dans le contexte des cuves de réacteurs, c'est principalement l'embrittlement qui est le facteur limitant.

### NRC (Nuclear Regulatory Commission)
Commission de réglementation nucléaire des États-Unis. Le NRC a établi le cadre réglementaire pour la gestion de l'embrittlement des cuves (10 CFR Part 50, Appendices G et H, Regulatory Guide 1.99). Les méthodes NRC servent de référence internationale.

### NUREG (Nuclear Regulatory Commission - Generic)
Série de rapports du NRC fournissant des orientations réglementaires. Exemples pertinents : NUREG-1801 (Generic Aging Lessons Learned), NUREG-2191 (GALL-SLR Report pour 60-80 ans), NUREG/CR-6115 (benchmarks PWR/BWR).

---

## P

### PTS (Pressurized Thermal Shock — Choc Thermique Pressurisé)
Phénomène transitoire où la cuve du réacteur est soumise simultanément à une pression interne élevée et un gradient thermique important (refroidissement brutal). Le PTS est un mécanisme de rupture potentiellement catastrophique si la cuve est embrittée. Le screening PTS (10 CFR 50.61) vérifie que la probabilité de PTS reste acceptable tout au long de la vie de la cuve. L'embrittlement par fluence réduit la marge PTS.

---

## R

### RTNDT (Reference Temperature, Nil-Ductility Transition)
Température de référence de transition ductile-fragile. Température en dessous de laquelle le matériau se fracture de manière fragile (faible absorption d'énergie Charpy) et au-dessus de laquelle il se déforme de manière ductile. L'embrittlement par fluence augmente le RTNDT. Le RTNDT à la ceinture 4 est le paramètre le plus critique pour la sûreté de la cuve.

### Regulatory Guide 1.99 (RG 1.99)
Guide réglementaire du NRC décrivant les méthodes acceptables pour calculer l'embrittlement par irradiation neutronique des matériaux de cuve. Version révisée 2. Définit :
- La méthode de corrélation fluence-RTNDT (Equation A)
- Le programme de surveillance (ASTM E185-82)
- Les critères de fin de vie (RTNDT limite)
- Les procédures de prédiction

### Regulatory Guide 1.190 (RG 1.190)
Guide du NRC pour les méthodes de calcul et de dosimétrie de la fluence neutronique dans les cuves de réacteurs. Définit les méthodes acceptables de calcul de fluence (DORT, TRIPOLI, etc.) et les exigences de benchmark. Essentiel pour la validation des calculs de fluence.

---

## S

### Surveillance program (programme de surveillance)
Programme systématique de placement, retrait et analyse des capsules de surveillance dans le réacteur. Objectif : mesurer la fluence réelle et prédire l'embrittlement futur. Le programme est défini par l'appendice H du NRC (10 CFR 50 App H). En France, il est géré par EDF sous supervision ASN/IRSN.

### Sécurité d'exploitation (operating margins)
Marge de sécurité entre les conditions d'exploitation actuelles et les limites de sûreté (PTS, RTNDT, pression, température). L'embrittlement réduit ces marges. Les restrictions opérationnelles peuvent être imposées si la marge devient insuffisante (ex : limitation de la puissance, restrictions de transitoires).

---

## T

### TAS (Test Assurance System)
Système de surveillance de la température dans le réacteur. Partie intégrante du programme de surveillance de la cuve. Les capteurs de température au voisinage de la ceinture 4 permettent de calculer les contraintes thermiques et de vérifier les marges PTS.

### Thermal-hydraulic analysis (analyse thermo-hydraulique)
Analyse du comportement de l'eau de refroidissement dans le réacteur (écoulement, chaleur, pressions). Particulièrement importante pour le PTS (choc thermique pressurisé) car les gradients thermiques dans la cuve dépendent des conditions thermo-hydrauliques du circuit primaire.

---

## V

### VENUS-1 (benchmark)
Réacteur-test utilisé pour le benchmark des calculs de fluence neutronique (RG 1.190). Le VENUS-1 est un petit réacteur de recherche dont la géométrie est bien caractérisée. Les résultats de calcul de fluence pour VENUS-1 servent à valider les méthodes DORT/TRIPOLI avant application aux réacteurs de puissance.

### Vessel integrity (intégrité de la cuve)
État de la cuve du réacteur en termes de résistance mécanique, de résistance à la fissuration fragile, de tenue à la pression et à la température. L'intégrité de la cuve est le facteur limitant ultime de la durée de vie d'un réacteur. Elle est évaluée par les méthodes ci-dessus (fluence, RTNDT, PTS screening, surveillance).

---

## Tableaux Récapitulatifs

### Table 1 : Paramètres Clés par Palier

| Paramètre | 900 MWe (3 boucles) | 1300 MWe (4 boucles) | 1450 MWe (N4) | EPR (1650) |
|---|---|---|---|---|
| **Fluence conception (40 ans)** | ~7×10¹⁹ n/cm² | ~4.5×10¹⁹ n/cm² | ~4×10¹⁹ n/cm² | Nouvelle conception |
| **Fluence 60 ans (est.)** | ~10×10¹⁹ n/cm² | ~7×10¹⁹ n/cm² | ~6×10¹⁹ n/cm² | — |
| **RTNDT shift max (est.)** | ~60-80°F | ~30-50°F | ~25-40°F | — |
| **Age limite ASN** | 50 ans | 50+ ans | 50+ ans | 60 ans |
| **Risk failure at 60 ans** | 6-9% | ~2-3% | <2% | — |
| **Gap eau cœur→cuve** | Court (~300 mm) | Long (~450 mm) | Moyen | Long |
| **Code fluence EDF** | EFLUVE (1D) | EFLUVE (1D) | EFLUVE (1D) | EFLUVE + TRIPOLI |
| **Capsules de surveillance** | ASTM E185-82 | ASTM E185-82 | ASTM E185-82 | ASTM E185-82 |
| **Méthode NRC** | RG 1.99 Rev 2 | RG 1.99 Rev 2 | RG 1.99 Rev 2 | RG 1.99 Rev 2 |

### Table 2 : Évolution de la RTNDT avec la Fluence

| Fluence (10¹⁹ n/cm²) | ΔRTNDT 900 MWe (~°F) | ΔRTNDT 1300 MWe (~°F) |
|---|---|---|
| 4 | ~20-25 | ~10-15 |
| 6 | ~30-40 | ~15-25 |
| 8 | ~40-55 | ~20-35 |
| 10 | ~50-70 | ~30-45 |
| 12 | ~60-80 | ~35-50 |
| 14 | ~70-90 | ~40-60 |

*(Estimations basées sur l'équation RG 1.99, pour des matériaux avec ~0,35% Cu, 1% Ni)*

### Table 3 : Organismes et Codes

| Organisme | Rôle | Codes/Documents |
|---|---|---|
| **ASN / ASNR** | Autorité de sûreté nucléaire (France) | Décisions, Cahiers #07, arrêtés |
| **EDF** | Exploitant du parc nucléaire | EFLUVE, visites décennales, PSR |
| **CEA** | Recherche, calculs de fluence | EFLUVE, TRIPOLI (Monte Carlo) |
| **IRSN / ASNR** | Expertise indépendante | Évaluations, rapports IRSN |
| **NRC (USA)** | Réglementation de référence | RG 1.99, RG 1.190, 10 CFR 50 |
| **IAEA** | Standards internationaux | Safety Standards, PLIM Symposia |
| **WENRA** | Harmonisation européenne | WENRA Guidelines on LTO |
| **Framatome** | Concepteur des réacteurs | Spécifications, codes de calcul |
| **ASTM** | Normes des matériaux | E185-82 (surveillance), E900-15 (ETC) |

### Table 4 : Chronologie Réglementaire (France)

| Date | Événement |
|---|---|
| 1973 | Début construction des premiers réacteurs 900 MWe |
| 1977 | Mise en service du 1er réacteur CP0 (Bugey 2) |
| 1980 | Début de l'exploitation massive (37 réacteurs 1976-1985) |
| 1985 | Premier examen de 20 ans (durée initiale autorisée) |
| 2000 | Allongement à 40 ans décidé |
| 2006 | Autorisation 3e PSR pour 1300 MWe (+10 ans) |
| 2007 | Début construction EPR Flamanville 3 |
| 2010 | Premier 4e PSR pour 900 MWe |
| 2015 | 3e PSR 1300 MWe (2015-2024) |
| 2020 | Fermeture Fessenheim (2 réacteurs) |
| 2021 | ASN autorise 900 MWe au-delà de 40 ans (50 ans) |
| 2024 | Raccordement EPR Flamanville 3 au réseau (déc.) |
| 2025 | ASN autorise 1300 MWe au-delà de 40 ans (juil.) |
| 2026 | 4e PSR 1300 MWe commence (Paluel 1) |
| 2027 | Début construction EPR2 (Penly) |
| 2030 | Fin des 4e PSR 900 MWe |
| 2035-2040 | Fin des 4e PSR 1300 MWe |

---

## Références

- NRC Regulatory Guide 1.99 Rev 2 — Radiation Embrittlement of Reactor Vessel Materials
- NRC Regulatory Guide 1.190 — Calculational and Dosimetry Methods for Determining PV Neutron Fluence
- NRC 10 CFR Part 50, Appendix G — Fracture Toughness Requirements
- NRC 10 CFR Part 50, Appendix H — Reactor Vessel Material Surveillance Program Requirements
- ASN — Cahiers #07, 1300 MWe Nuclear Reactors Beyond 40 Years (14 janv. 2026)
- IAEA — PLIM Symposium 2007 (Bezdikian Panel, French PLM Strategy)
- OECD/NEA — CIELO Addendum (neutron cross-sections)
- World Nuclear Association — Nuclear Power in France (avril 2026)
- CEA/EDF — Code EFLUVE (fluence calculation)
- EDF — Bilan Électrique 2025, Programme EPR2
- ORNL — Reactor Pressure Vessel Characterization Methods
- Politico — Nuclear phase-out debate (août 2026)
