# Data Centers en Europe — Recensement Existant

**Date** : 17 septembre 2026  
**Sources** : EUDCA 2026, CBRE Q2 2026, Knight Frank, MLQ.ai, CIL Strategy, ResearchAndMarkets

---

## Vue d'ensemble — Europe

| Indicateur | Valeur |
|---|---|
| **Capacité IT live 2025** | **14 784 MW** (EUDCA/Pb7 Research) |
| **Capacité live 2026** | **12 416 MW** (Knight Frank) / **13 GW** build (CBRE) |
| **Installations référencées** | **1 355 existants** + 240 upcoming (ResearchAndMarkets) |
| **Capacité 2030 projetée** | **52,2 GW** (CIL Strategy) |
| **Investissements cumulés 2026-2031** | **176 Md€** |
| **Capacité par habitant** | ~40 MW/m habitant (vs 120-140 MW/m US) |
| **Consommation électrique** | ~4-5% de l'électricité européenne |
| **Prix moyen colocation** | 1,39 PUE (EUDCA) |

---

## Répartition par Type (2025)

| Type | Europe (MW) | EU27 (MW) |
|---|---|---|
| **Enterprise** | 3 101 | 2 602 |
| **Colocation** | 5 020 | 3 570 |
| **Hyperscale (owned)** | 3 654 | 2 347 |
| **Scale colocation** | 3 009 | 2 697 |
| **TOTAL** | **14 784** | **11 216** |

> *Source : EUDCA State of European Data Centres 2026, Pb7 Research*

---

## Top Marchés par Capacité Colocation (MW)

| Rang | Marché | Pays | 2024 | 2025 | 2026F | CAGR 2024-31 |
|---|---|---|---|---|---|---|
| 1 | **London** | UK | 1 155 | 1 228 | 1 333 | 8,5% |
| 2 | **Frankfurt** | Germany | 830 | 1 023 | 1 273 | **17,4%** |
| 3 | **Amsterdam** | Netherlands | 639 | 666 | 778 | 12,5% |
| 4 | Paris | France | 400+ | — | — | ~20% |
| 5 | Dublin | Ireland | 350+ | — | — | ~14% |
| 6 | Stockholm | Sweden | 99 | 104 | 122 | 6,3% |
| 7 | Vienna | Austria | 46 | 48 | 55 | 14,3% |
| 8 | Brussels | Belgium | 48 | 57 | 61 | 12,8% |

> *FLAP-D (Frankfurt, London, Amsterdam, Paris, Dublin) = 5 278 MW colocation (2024)*

---

## Par Région (2024)

| Région | Capacité colocation (MW) | Part |
|---|---|---|
| **FLAP-D countries** | **5 278** | 72% |
| **Nordics** | 866 | 12% |
| **CEE (Central & Eastern)** | 690 | 9% |
| **South Europe** | 682 | 9% |
| **Other** | 155 | 2% |

> *Source : EUDCA 2026, Pb7 Research*

---

## Croissance par Pays (CAGR 2025-30)

| Pays | CAGR | Part capacité ajoutée |
|---|---|---|
| **Germany** | 23,6% | 15,1% |
| **UK** | 21,6% | 17,8% |
| **France** | 20,8% | 9,3% |
| **Nordics** | 23,0% | 23,7% |
| **Rest of Europe** | 22,2% | 25,5% |
| **Ireland** | 14,5% | 5,2% |
| **Netherlands** | 12,0% | 3,3% |
| **TOTAL Europe** | **20,6%** | 100% |

> *Source : CIL Strategy Consultants, European data centre market 2026*

---

## Top Opérateurs Europe

| Opérateur | Pays | Type | Capacité |
|---|---|---|---|
| **Digital Realty** | US | Colocation | 1re position Europe |
| **Equinix** | US | Colocation | 2e position Europe |
| **NTT** | Japan | Colocation | 3e position |
| **Interxion (Digital Realty)** | Netherlands | Colocation | — |
| **Telehouse (KDDI)** | Japan | Colocation | — |
| **Data4** | France | Colocation | France #1 |
| **Global Switch** | Hong Kong | Colocation | — |
| **Amazon AWS** | US | Hyperscale | Ireland, Germany, Spain |
| **Microsoft Azure** | US | Hyperscale | Ireland, Germany, Netherlands |
| **Google** | US | Hyperscale | Belgium, Netherlands |
| **Meta** | US | Hyperscale | Denmark, Sweden, Norway |

---

## Contexte Énergétique

| Indicateur | 2025 | 2030 |
|---|---|---|
| **Capacité live** | 12-13 GW | 20-25 GW |
| **Investissements annuels** | €35-40 Md€/an | — |
| **Hyperscale self-build** | 4,3 GW | 5,6 GW+ |
| **Neocloud signings H1 2026** | 420 MW | — |
| **PUE moyen colocation** | 1,39 | — |
| **WUE moyen colocation** | 0,31 L/kWh | — |
| **Chauffage récupéré** | >10% (Germany) | 20% (Germany 2028) |

---

## Tensions Réseau

- **Power availability** = critère #1 pour les nouveaux sites
- **Délais raccordement** : 3-5 ans dans FLAP-D, plus courts en Nordics
- **Éolien/renouvelable** domine en Scandinavie (Norce, Suède, Danemark)
- **Allemagne** : loi heat reuse (10% min 2026, 20% d'ici 2028)
- **EU Green Deal** : EED oblige réchauffage >1 MW

---

---

## Puissance de Calcul (estimés)

**Méthode** : Conversion MW → TFLOPS (÷1000 = GFLOPS) basée sur le type d'installation
- Facteur hyperscale AI (AWS/Azure/GCP/Meta) : ~2 GFLOPS/MW
- Facteur colocation (Equinix, Digital Realty) : ~2 GFLOPS/MW
- Facteur enterprise : ~1 GFLOPS/MW
- Voir `./TFLOPS_REFERENCE.md` pour la méthodologie complète

| Indicateur | Valeur |
|---|---|
| **Puissance de calcul totale** | **~12 PFLOPS** (12 000 GFLOPS) |
| **Puissance FP8 estimée** | ~24 PFLOPS (24 000 GFLOPS) |
| **Puissance effective estimée** | **~7-10 PFLOPS** (7 000-10 000 GFLOPS) |
| **Comparaison Frontier** (1,1 EFLOPS) | ~1% de la puissance Frontier |
| **EU vs US (ratio GFLOPS)** | ~7% de la puissance US (~12 PFLOPS vs 162 PFLOPS) |

> *L'Europe a une capacité de calcul estimée ~7x inférieure aux US en GFLOPS. Le mix colocation traditionnel (PUE 1,39) est moins dense en GPU que les hyperscale US.*

---

## Sources

## Sources

- [EUDCA — State of European Data Centres 2026](https://www.eudca.org/new-2026-state-of-european-data-centres)
- [CBRE — Europe Data Centres Q2 2026](https://mktgdocs.cbre.com/2299/905ebeb3-1144-4e23-b11c-0ba30b7f537e-824468076/Europe_Data_Centres_Figures_Q2.pdf)
- [Knight Frank — Global Forecast 2026](https://content.knightfrank.com/research/2960/documents/en/data-centres-global-forecast-report-2026-12620.pdf)
- [CIL Strategy — European DC Market 2026](https://cil.com/media/i2lfhyaz/cil-strategy-consultants-european-data-centre-market-2026.pdf)
- [MLQ.ai — Data Centers in Europe](https://aidatacenterindex.com/continents/europe)
- [ResearchAndMarkets — Europe DC Database](https://www.globenewswire.com/news-release/2025/02/07/3022891/28124/en/europe-data-center-database-2025-detailed-analysis-of-1355-existing-240-upcoming-data-centers-across-20-countries.html)
- [Statista — DC by Country](https://www.statista.com/statistics/1661029/number-of-data-centers-united-states-by-state)

---

## Fichiers

| Fichier | Description |
|---|---|
| `EU_datacenters_existant.csv` | 47 installations répertoriées |
| [`EU_datacenters_existant.csv`](./EU_datacenters_existant.csv) | CSV complet |
