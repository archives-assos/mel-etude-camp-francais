# Synthèse TFLOPS → GFLOPS — Data Centers Mondiaux

**Date** : 17 septembre 2026  
**Méthode** : Conversion MW → TFLOPS (÷1 000 = GFLOPS) (voir `./TFLOPS_REFERENCE.md`)

---

## Résumé par Région

| Région | MW live | TFLOPS | TFLOPS/MW | Ratio US |
|---|---|---|---|---|
| **États-Unis** | ~57 GW | **~162 PFLOPS** | 2 000-2 500 | 100% |
| **Europe** (dont France ~18 GW signés) | ~12-13 GW | **~12 PFLOPS** | 1 500-2 200 | 7% |
| **Chine** | ~37 GW | **~8 PFLOPS** | 1 500-2 000 | 5% |
| **Monde** | ~200+ GW | **~400+ PFLOPS** | — | — |

> *Note : La France (~18 GW signés, projets DC France) est incluse dans le total Europe. La capacité live UE est ~12-13 GW ; la France "signée" (projets) dépasse la capacité live UE totale, mais les projets ne sont pas encore opérationnels.*

---

## Top 20 Data Centers par TFLOPS (estimés)

| # | Installation | Opérateur | Pays | MW | PFLOPS |
|---|---|---|---|---|---|
| 1 | Southaven | xAI | US | 2 000 | ~5 PFLOPS |
| 2 | Colossus 1 | xAI | US | 1 401 | ~3,5 PFLOPS |
| 3 | Altoona Campus | Meta | US | 1 401 | ~3,5 PFLOPS |
| 4 | Colossus 2 | xAI | US | 1 200 | ~3 PFLOPS |
| 5 | Prineville | Meta | US | 1 289 | ~3,2 PFLOPS |
| 6 | Fort Worth | Meta | US | 729 | ~1,8 PFLOPS |
| 7 | Mesa | Meta | US | 701 | ~1,8 PFLOPS |
| 8 | DeKalb | Meta | US | 673 | ~1,7 PFLOPS |
| 9 | Las Vegas Core | Switch | US | 495 | ~1,2 PFLOPS |
| 10 | Las Vegas 5 | Switch | US | 495 | ~1,2 PFLOPS |
| 11 | Quincy Azure | Microsoft | US | 622 | ~1,6 PFLOPS |
| 12 | AWS Ohio | Amazon | US | 1 010 | ~2,5 PFLOPS |
| 13 | AWS Salem | Amazon | US | 1 000 | ~2,5 PFLOPS |
| 14 | Ashburn | Vantage | US | 590 | ~1,5 PFLOPS |
| 15 | Gigafactory | Tesla | US | 500 | ~1,3 PFLOPS |
| 16 | Iron Mountain | Iron Mountain | US | 400 | ~1 PFLOPS |
| 17 | AWS Indiana | Amazon | US | 800 | ~2 PFLOPS |
| 18 | AWS Oregon | Amazon | US | 250 | ~0,6 PFLOPS |
| 19 | Council Bluffs | Google | US | 250 | ~0,6 PFLOPS |
| 20 | CoreWeave | CoreWeave | US | 100 | ~0,25 PFLOPS |

> *Facteur : 2 500 TFLOPS/MW pour hyperscale AI (Meta, xAI, AWS, Azure).*

---

## Top Opérateurs par TFLOPS (estimés)

| Rang | Opérateur | MW (disclose) | PFLOPS | Hyperscale AI? |
|---|---|---|---|---|
| 1 | **Amazon AWS** | 50 828 | ~127 PFLOPS | ✅ |
| 2 | **Google** | 23 763 | ~59 PFLOPS | ✅ |
| 3 | **Meta** | ~10 000+ | ~25 PFLOPS | ✅ |
| 4 | **xAI** | 2 898 | ~7,2 PFLOPS | ✅ |
| 5 | **Switch** | ~990 | ~2,5 PFLOPS | ❌ (colocation) |
| 6 | **CoreWeave** | ~100+ | ~0,25 PFLOPS+ | ✅ |
| 7 | **Microsoft** | ~622+ | ~1,6 PFLOPS+ | ✅ |
| 8 | **Iron Mountain** | ~400 | ~1 PFLOPS | ❌ |
| 9 | **Aligned** | 3 155 | ~7,9 PFLOPS | ❌/✅ |
| 10 | **Equinix** | ~10 000+ | ~15 PFLOPS | ❌ (colocation) |

> *AWS et Google dominent la puissance de calcul installée. Les opérateurs colocation (Equinix, Switch) sont moins denses en GPU mais plus diversifiés.*

---

## Facteurs de Conversion par Type d'Opérateur

| Type d'opérateur | TFLOPS/MW (BF16) | TFLOPS/MW (FP8) | GPU dominant | Exemple |
|---|---|---|---|---|
| **Hyperscale AI** (Meta, Google, AWS) | 2 500 | 5 000 | H100/H200/B200 | Prineville, Colossus |
| **Neocloud** (CoreWeave, Crusoe) | 2 500 | 5 000 | H100/H200 | CoreWeave Edison |
| **Colocation** (Equinix, Digital Realty) | 1 500 | 3 000 | Mix (moins dense) | Equinix London |
| **Telecom** (China Telecom, Orange) | 1 500 | 3 000 | Mix traditionnel | China Telecom Hangzhou |
| **Enterprise** | 1 000 | 2 000 | CPU/GPU mix | Datacenter enterprise |
| **Huawei Ascend** (Chine) | ~1 500* | ~3 000* | Ascend 910C | GDS, Chindata |

> *\* Huawei Ascend 910C ~ équivalent H100 selon certaines estimations, mais moins fiable. Facteur conservateur.*

---

## Fichiers associés

| Fichier | Description |
|---|---|
| `./TFLOPS_REFERENCE.md` | Méthodologie complète conversion MW → TFLOPS |
| `US_datacenters_existant.csv` | 83 US DC avec colonne GFLOPS_BF16 |
| `EU_datacenters_existant.csv` | 47 EU DC avec colonne GFLOPS_BF16 |
| `China_datacenters_existant.csv` | 50 CN DC avec colonne GFLOPS_BF16 |
| `projets_dc_france.csv` | 70 projets France (pas encore GFLOPS) |

---

## Limites & Avertissements

1. **Estimations, pas mesures** : Les valeurs sont calculées à partir de la puissance électrique et de facteurs GPU typiques
2. **Pas de données GPU réelles** : Les CSV ne contiennent pas le type/model de GPU réellement installé
3. **Mix hétérogène** : Un même data center peut avoir des serveurs CPU, GPU NVIDIA, GPU AMD, et Ascend
4. **Utilisation réelle** : Les valeurs théoriques × 60-80% = valeurs effectives
5. **Inférence vs entraînement** : L'inférence est typiquement 3-5× plus efficace que l'entraînement
6. **Évolution rapide** : Les facteurs changent avec les nouvelles générations (B200,下一代 GB300/VR200)
7. **Pas de réseau** : Ne prend pas en compte la puissance réseau (NVLink, InfiniBand)
