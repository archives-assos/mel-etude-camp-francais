# Sources — Data Centers France

Répertoire contenant les documents sources téléchargés pour l'analyse des data centers en France.

**Date** : 16 septembre 2026  
**Total** : 14 fichiers, ~86,5 Mo

---

## PDF réglementaires et officiels (12 fichiers)

| Fichier | Source | Taille |
|---|---|---|
| `RTE_Bilan_Electrique_2025_rapport_complet.pdf` | RTE — 25 fév. 2026 | 40,1 Mo |
| `RTE_Annual_Review_2025_full_report.pdf` | RTE Annual Review — 15 avr. 2026 | 9,4 Mo |
| `RTE_Bilan_Previsionnel_2025_consommation.pdf` | RTE — 23 déc. 2025 | 5,4 Mo |
| `RTE_SDDR2025_Fiche5_Raccordement.pdf` | RTE SDDR 2025 — fiche raccordement DC/industrie | 5,5 Mo |
| `ASNR_Cahiers_07_1300MWe_2026.pdf` | ASNR — Cahiers #07, 1300 MWe au-delà 40 ans — 14 janv. 2026 | 15,7 Mo |
| `CRE_SDDR2025_Consultation.pdf` | CRE — SDDR 2025 consultation publique | 874 Ko |
| `SDES_Chiffres_cles_energie_2025.pdf` | SDES — Chiffres clés énergie 2025 | 4,4 Mo |
| `IAEA_France_National_Report_2026.pdf` | IAEA — France National Report 10th Review | 2,5 Mo |
| `IAEA_PLIM_Symposium_2007_Bezdikian.pdf` | IAEA — French PLM Strategy (Bezdikian) | 872 Ko |
| `Tresor_Commerce_exterieur_2025.pdf` | Trésor-Économie — Résultats du commerce extérieur 2025 | 884 Ko |
| `Enedis_Prospective_2035_2050.pdf` | Enedis — Prospective 2035-2050 | 477 Ko |
| `RTE_Annual_Results_2025.pdf` | RTE — Résultats annuels 2025 | 128 Ko |

## HTML (2 fichiers)

| Fichier | Source | Taille |
|---|---|---|
| `Connaissance_Energies_Parc_nucleaire_2026.html` | Connaissance des Énergies — Parc nucléaire français | 100 Ko |
| `World_Nuclear_France_Profile.html` | World Nuclear Association — France country profile | 167 Ko |

---

## Sources web (non téléchargeables)

Ces URL ont été consultées mais ne sont pas des fichiers téléchargeables :
- `guidedatacenter.fr/carte` — carte des projets DC
- `travail-industrie.com` — recoupement régional FLAP-D
- `datacenterdynamics.com` — investissements DC
- `lafibre.info` — projets avancés
- `edf.fr` — programme EPR2, data centers
- `stratégie-plan.gouv.fr` — réindustrialisation 2035
- `dlaipper.com` — PPE3 roadmap
- `reuters.com` — investissements Choose France
- `politico.eu` — débat sortie nucléaire

---

## Méthode de téléchargement

```python
import urllib.request, ssl
ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE
req = urllib.request.Request(url, headers={'User-Agent': 'Mozilla/5.0'})
with urllib.request.urlopen(req, context=ctx, timeout=60) as resp:
    with open(fname, 'wb') as f:
        f.write(resp.read())
```

---

## Liens vers les MD d'analyse

- [`RECENSEMENT.md](../RECENSEMENT.md) — synthèse du recensement (65→70 projets)
- [`RECOUPEMENT.md](../RECOUPEMENT.md) — croisement sources
- [`INVESTISSEMENTS_2023_2026.md](../INVESTISSEMENTS_2023_2026.md) — chronologie
- [`ANALYSE_ENERGETIQUE.md](../ANALYSE_ENERGETIQUE.md) — énergie, mix, EPR2, balance commerciale
- [`GLOSSAIRE_VIEILLISSEMENT_CUVE.md](../GLOSSAIRE_VIEILLISSEMENT_CUVE.md) — dictionnaire technique
- [`projets_dc_france.csv`](../projets_dc_france.csv) — base de données (70 projets)
- [`projets_dc_france.json`](../projets_dc_france.json) — version JSON

---

## Sources États-Unis (2026)

| Fichier | Source | Taille |
|---|---|---|
| `US_datacenters_existant.csv` | Recensement 83 installations US | — |
| `LBNL_Data_Center_Energy_2025_Update.pdf` | LBNL — US DC Energy Report | — |
| `LBNL_DC_Energy_2025.html` | LBNL — Publication page | — |

**US Data Center Stats (2026)**:
- 1 214 opérationnels, 57 431 MW (ElectricChoice)
- 982 facilities suivies, 127 288 MW (USDataMap)
- 176 TWh consommés en 2023 (LBNL)
- 5 427 DC référencés (Cloudscene)
