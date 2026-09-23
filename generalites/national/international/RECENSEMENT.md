# Recensement des projets de data centers en France (2026)

**Source** : [Le Guide : Data Center — Carte](https://guidedatacenter.fr/carte)  
**Date d'extraction** : 16 septembre 2026  
**Période couverte** : Projets annoncés à fin mai 2026  
**Méthodologie** : Données croisées entre The Heron Collective / Catapulte (Challenges n°925), Hubblo (étude Ademe), et Le Nuage était sous nos pieds.

---

## Vue d'ensemble

| Indicateur | Valeur |
|---|---|
| **Total projets référencés** | 65 |
| **En construction** | 18 |
| **En instruction** | 14 |
| **Annoncés** | 6 |
| **Potentiel** | 27 |
| **Projets sans opérateur identifié** | 21 / 65 (32%) |
| **Surface terrain renseignée** | 45 / 65 (69%) |
| **Surface bâtiment renseignée** | 26 / 65 (40%) |
| **Puissance renseignée** | 44 / 65 (68%) |
| **Au moins 1 champ technique** | 55 / 65 (85%) |
| **Total projet (après recoupement)** | **70** |

---

## Recoupement

Le recensement a été croisé avec :
- [travail-industrie.com](https://travail-industrie.com/blog/article-titre/carte-data-centers-france-regions-implantations) — vue régionale FLAP-D
- [Liste citoyenne] — Dunkerque 2 sites, Quaëdypre, La Chapelle d'Armentière, Douai, Bouchain, Hornaing, Escaudain, E-Valley, Rantigny, Lachelle, friche Ynsect, 2 DC Bethune, 2 DC Maubeuge
- [DCmag carte](https://carte.dcmag.fr) — DCmag opérationnels
- [LaFibre.info](https://lafibre.info/datacenter/carte-des-projets-de-data-centers-en-cours) — 48 projets avancés
- [DCD](https://www.datacenterdynamics.com) — SoftBank Bouchain 400 MW, Eclairion 330 MW

### Projets trouvés dans d'autres sources mais absents de la carte guidatacenter.fr (65)

| Projet | Opérateur | Commune | Puissance | Source |
|---|---|---|---|---|
| **Bouchain** | SoftBank | Bouchain (Nord) | **400 MW** | DCD, EDF AMI (2026) |
| **La Chapelle d'Armentière** | Non identifié | La Chapelle d'Armentière (Nord) | Non publiée | La Voix du Nord (juil 2026) |
| **Lachelle** | PKM Logistique | Lachelle (Oise) | ~300 MW | actu.fr (aoû 2026) |
| **H&DC Dardilly** | H&DC | Dardilly (69) | 18 MW | LaFibre.info |
| **EDF Creys-Mépieu** | EDF CEI | Creys-Mépieu (Isère) | Non publiée | EDF (jul 2026) |

---

## Répartition par région

| Région | Projets | % |
|---|---|---|
| Île-de-France | 26 | 40.0% |
| Hauts-de-France | 12 | 18.5% |
| Auvergne-Rhône-Alpes | 7 | 10.8% |
| Grand Est | 6 | 9.2% |
| Normandie | 4 | 6.2% |
| Occitanie | 3 | 4.6% |
| Provence-Alpes-Côte d'Azur | 3 | 4.6% |
| Pays de la Loire | 1 | 1.5% |
| Centre-Val de Loire | 1 | 1.5% |
| Bourgogne-Franche-Comté | 1 | 1.5% |
| Nouvelle-Aquitaine | 1 | 1.5% |

---

## Répartition par département (top 10)

| Département | Projets |
|---|---|
| Essonne | 8 |
| Nord | 6 |
| Val-de-Marne | 5 |
| Seine-Saint-Denis | 4 |
| Pas-de-Calais | 3 |
| Moselle | 3 |
| Rhône | 3 |
| Bouches-du-Rhône | 3 |
| Seine-et-Marne | 3 |

---

## Opérateurs identifiés (≥2 projets)

| Opérateur | Projets |
|---|---|
| Data4 | 4 |
| Eclairion | 3 |
| Digital Realty | 3 |
| H&DC | 2 |
| NDC | 2 |
| DataOne | 2 |
| Equinix | 2 |
| Segro | 2 |
| Goodman | 2 |
| Colt | 2 |

---

## Fichiers disponibles

| Fichier | Description |
|---|---|
| `ANALYSE_ENERGETIQUE.md` | DC vs tous usages électrifiables (DC + transport + industrie + H2) vs production |
| `INVESTISSEMENTS_2023_2026.md` | Chronologie des investissements (SoftBank 75Md€, Brookfield 30Md€, etc.) |
| `projets_dc_france.csv` | Recensement complet (70 projets) |
| `projets_dc_france.json` | Version JSON structurée (70 projets) |
| `RECOUPEMENT.md` | Tableau de recoupement complet |
| `RECENSEMENT.md` | Ce document de synthèse |

---

## Notes méthodologiques

- Les marqueurs sont placés au centre de la commune annoncée, pas à l'emplacement exact des terrains.
- Un statut « annoncé » ou « potentiel » ne garantit pas la réalisation du projet.
- Deux projets annoncés (Prologis en Île-de-France et Sesterce dans le Grand Est) ne figurent pas sur la carte faute de localisation précise.
- 21 projets sur 65 n'ont pas d'opérateur identifié publiquement.
- Le site recense les projets en instruction, en attente d'autorisation ou en construction, en plus des ~350 sites existants.
- Les données de surface, bâtiment et puissance ont été collectées via recherche web (articles de presse, communiqués opérateurs, documents réglementaires MRAe/Enquêtes publiques, sites des opérateurs). Les champs vides indiquent une absence de données publiques fiables.

### Sources techniques principales
- DataOne (dataone.eu), Digital Realty, Equinix, CloudHQ, NTT, Colt, Data4, Goodman, Segro, OpCore sites officiels
- MRAe (mrae.developpement-durable.gouv.fr) et Registre Numérique (registre-numerique.fr) pour les autorisations
- Challenges / DCmag / La Libre Info / France 3 pour les articles de presse
- EDF, BSO, Ardian communiqués de presse

### Sources
- The Heron Collective & Catapulte, « 65 projets de data centers sur dix ans », *Challenges* n°925, 25 juin 2026
- Hubblo, contribution à l'étude Ademe « Prospective d'évolution des consommations des centres de données en France de 2024 à 2060 »
- Le Nuage était sous nos pieds (association marseillaise)
- Fond de carte : contours administratifs IGN / data.gouv.fr (licence ouverte)
- **RTE** — Bilan Électrique 2025, SDDR 2025, Les data centers en chiffres clés

---

## Autonomie Énergétique — Synthèse

### France — Électricité (2025)

| Indicateur | Valeur |
|---|---|
| Production totale | **547,5 TWh** (bas-carbone 95,2%) |
| Consommation brute | **446,1 TWh** |
| Export net (record) | **92,3 TWh** (Italie 26,2, Al/Belg 23,1, GB 22,6, Suisse 20,1) |
| Capacité installée | 164,5 GW |

### Tableau de croisement — Tous usages électrifiables (scénario rapide RTE 2035)

| Usage | 2025 | 2030 | 2035 | % prod. 2035 |
|---|---|---|---|---|
| Industrie | ~106 TWh | ~113 TWh | ~135 TWh | 23% |
| Transport (VE + PL) | ~5-6 TWh | ~15-20 TWh | ~61 TWh | 10% |
| Data Centers | ~5 TWh | 15-20 TWh | ~28 TWh | 5% |
| Hydrogène | <1 TWh | ~15 TWh | ~25 TWh | 4% |
| Résidentiel/Tertiaire | ~195 TWh | ~210 TWh | ~220 TWh | 38% |
| Chauffage (PAC) | ~40 TWh | ~45 TWh | ~50 TWh | 9% |
| **TOTAL consommation** | ~446 TWh | ~451-510 TWh | ~580 TWh | 100% |

### Réponses aux questions clés

| Question | Réponse |
|---|---|
| La France a-t-elle assez d'électricité pour les DC seuls ? | **Oui, largement** — 28 TWh = 5% de la prod. |
| L'excédent actuel couvre la demande DC ? | **Oui, 3x** — 92 TWh d'export = 3x les 28 TWh projetés |
| L'excédent couvre DC + Transport ? | **Oui, mais juste** — ~89 TWh vs surplus ~92 TWh |
| L'excédent couvre DC + Transport + Industrie + H2 ? | **Non** — ~249 TWh vs surplus ~92 TWh |
| France en surcapacité ? | **Oui aujourd'hui**, mais surplus s'érode si électrification lente |
| Vrai frein ? | **Raccordement réseau (3-7 ans)**, pas la production |
| RTE — DC consomment réellement ? | **15-20%** de la puissance signée |
| RTE — Projets industriels signés ? | ~30 GW, mais **15% lancés seulement** |

### Le paradoxe

> **La France n'a PAS besoin de plus de production pour les data centers. Elle a besoin de PLUS DE DEMANDE** (électrification transport + industrie) pour absorber son surplus actuel de ~92 TWh. Les DC sont un client bienvenu, pas un problème énergétique. Le vrai défi : accélérer l'électrification pour utiliser un surplus qui s'érode.

> *"Il n'y a aucun projet de data center qui attend son raccordement au réseau. C'est plutôt le réseau qui attend son projet."* — **Thomas Veyrenc**, DG RTE, La Tribune, déc. 2025

### RTE — 3 constats (Bilan Prévisionnel 2025)

1. 📊 **Surcapacité transitoire** : 547 TWh produits pour 446 TWh consommés. Excédent « durera 2-3 ans ».
2. ⚠️ **Frein = raccordement** : Délais 3-7 ans pour un raccordement 400 kV. 85% des projets industriels n'ont pas lancé les travaux.
3. 🎯 **L'électrification est le levier** : Trajectoire rapide = 580 TWh en 2035 (nécessite volonté politique forte).

### PPE3 (12 fév. 2026) — Cadre cible

| Cible | Valeur |
|---|---|
| Nucléaire | 380-420 TWh/an (2030-2035) |
| Éolien offshore | 15-18 GW (2035) |
| Solaire | 65-90 GW (2035) |
| H2 (électrolyse) | 4,5 GW (2030), 8 GW (2035) |
| Consommation électrique | 555-615 TWh (2035) |

### Sources énergie
- RTE Bilan Électrique 2025 (25 fév. 2026), Bilan Prévisionnel 2025-2035 (23 déc. 2025)
- RTE Électrification des transports (25 juin 2026), Les data centers en chiffres clés (6 mars 2026)
- Enedis Prospective 2035-2050, CRE SDDR 2025, SDES Chiffres clés énergie 2025
- PPE3 (Décret 12 fév. 2026), Strategie-Plan gouv Réindustrialisation 2035
- Reuters (9 fév. 2026), La Tribune (déc. 2025)
