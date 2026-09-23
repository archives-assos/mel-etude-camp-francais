# Référence : Conversion MW → TFLOPS/GFLOPS

**Date** : 17 septembre 2026  
**Sources** : NVIDIA (H100/H200/B200/A100 datasheets, sept. 2026), Uptime Institute

---

## Specs GPU NVIDIA (TFLOPS Tensor Core, densité)

| GPU | Architecture | BF16 TFLOPS/GPU | BF16 Sparse | FP8 TFLOPS | TDP (W) | Année |
|---|---|---|---|---|---|---|
| **B200** | Blackwell | **2 250** | 4 500 | **9 000** | 1 000 | 2025 |
| **H200** | Hopper | **989** | 1 979 | **3 958** | 700 | 2024 |
| **H100** | Hopper | **989** | 1 979 | **3 958** | 700 | 2022 |
| **A100** | Ampere | **312** | 624 | **1 248** | 400 | 2020 |
| **L40** | Ada | **479** | 479 | — | 350 | 2023 |

---

## Conversion MW → TFLOPS (méthode)

### Formule
```
TFLOPS = (Puissance_IT_MW × 10⁶) / (TDP_GPU × Overhead_serveur) × BF16_par_GPU
```

### Paramètres typiques
| Paramètre | Valeur | Note |
|---|---|---|
| **PUE** | 1,3-1,4 | Colocation/hyperscale typique |
| **IT power / total power** | 70-75% | = 1/PUE |
| **Overhead serveur** | 1,2× | PSU + mémoire + réseau |
| **GPU par serveur** | 4-8 | HGX standard |
| **GPU par MW IT** | ~1 000-1 400 | Selon génération |
| **GPU par MW total** | ~750-1 000 | Inclut refroidissement |

---

## TFLOPS Estimés par MW (BF16 dense, mix GPU typique)

| Époque GPU | GFLOPS BF16/MW total | GFLOPS FP8/MW total | Efficacité |
|---|---|---|---|
| **H100/H200** (2022-2025) | **~2 000-2 500** | **~4 000-5 000** | Référence |
| **B200** (2025+) | **~1 800-2 000** | **~7 000-9 000** | Plus efficace |
| **A100** (2020-2022) | **~3 500-4 500** | **~7 000-9 000** | Moins performant/GT |
| **Mélangé** (mix actuel) | **~2 000-2 500** | **~4 000-6 000** | Moyenne pondérée |

> *Note : Ces valeurs sont des estimations théoriques. L'utilisation réelle est typiquement 60-80% du pic.*

---

## Exemple de Calcul

**Pour un DC de 100 MW (PUE 1,3) en H100 :**
- Puissance IT : 100 MW / 1,3 = 77 MW
- GPUs ≈ 77 000 kW / (0,7 kW × 1,2) ≈ 91 600 GPUs (≈ 1 150 par rack × 80 racks)
- GFLOPS BF16 ≈ 91 600 × 989 / 1 000 = **~90 GFLOPS**
- GFLOPS FP8 ≈ 91 600 × 3 958 / 1 000 = **~362 GFLOPS**

**Pour un DC de 100 MW en B200 :**
- Puissance IT : 77 MW
- GPUs ≈ 77 000 / (1,0 kW × 1,2) ≈ 64 200 GPUs
- GFLOPS BF16 ≈ 64 200 × 2 250 / 1 000 = **~144 GFLOPS**
- GFLOPS FP8 ≈ 64 200 × 9 000 / 1 000 = **~578 GFLOPS**

---

## Limites

- Ces valeurs ne prennent **pas en compte** les serveurs CPU, stockage, réseau (~20% de la puissance IT)
- L'**inférence** vs **entraînement** a des efficacités différentes
- Les **nœuds Grace CPU** (GB200) ajoutent de la puissance CPU mais consomment aussi du power
- Le **réseau NVLink** consomme ~5-10% de la puissance totale
- Réaliste : diviser par **1,5-2×** pour obtenir du GFLOPS "utile"
