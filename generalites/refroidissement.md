#Principales alternatives du marché

## 1. Vertiv – Le géant américain du Direct-to-Chip
Vertiv est le concurrent le plus frontal de Schneider Electric. L'entreprise maîtrise l'intégralité de la chaîne, de la fabrication des plaques froides jusqu'aux immenses groupes de production d'eau glacée pour l'extérieur.

* Technologie & Fluide : Direct-to-Chip (monophasique). Le fluide intérieur est une combinaison d'eau déionisée et de glycol, garantissant 0 % de PFAS.
* Solution phare : La gamme d'unités de distribution de fluide Liebert XDU. Ces CDU gèrent l'échange thermique entre la boucle du bâtiment et le circuit fermé des serveurs, avec des capacités allant jusqu'à 1,3 MW par unité.
* Points forts :
* Échelle industrielle : Capable d'équiper de très grands datacenters (hyperscalers comme Meta).
   * Partenariats solides : Certifié par NVIDIA pour refroidir les architectures denses comme les puces Blackwell.

## 2. CoolIT Systems – Le spécialiste de la puce informatique
Contrairement aux géants de l'énergie, CoolIT Systems est une entreprise purement dédiée au refroidissement liquide. Elle conçoit les éléments au plus près du processeur.

* Technologie & Fluide : Direct-to-Chip (monophasique). Utilise le fluide breveté CoolIT ECH2O (à base d'eau et d'inhibiteurs de corrosion), sans aucun PFAS.
* Solution phare : Les plaques froides Split-Flow Cold Plates. Ces modules en cuivre ultra-précis sont conçus sur mesure pour s'adapter exactement à la géométrie des puces NVIDIA, AMD ou Intel.
* Points forts :
* Intégration OEM : Leurs technologies sont directement intégrées en usine par des fabricants de serveurs mondiaux (Dell, HPE, Lenovo, Gigabyte).
   * Densité extrême : Leurs collecteurs de distribution (Manifolds) en acier inoxydable gèrent les profils de flux les plus complexes directement à l'intérieur du rack.

## 3. Submer – Le leader de l'immersion propre (Zéro PFAS)
Cette entreprise européenne s'impose comme la référence de l'immersion monophasique, une alternative radicale où les serveurs n'ont plus de ventilateurs et baignent entièrement dans un liquide.

* Technologie & Fluide : Immersion monophasique. Le liquide reste stable et ne s'évapore pas. Submer utilise le fluide SmartCoolant, un hydrocarbure synthétique ou ester biosourcé (issu du végétal), biodégradable et 100 % exempt de PFAS.
* Solution phare : La cuve SmartPod. Il s'agit d'un réservoir horizontal dans lequel on glisse verticalement les serveurs comme des fiches dans un classeur.
* Points forts :
* Sécurité et Éco-responsabilité : Fluide non toxique pour l'humain en cas de contact cutané ou d'inhalation.
   * Simplicité mécanique : Suppression totale des ventilateurs des serveurs, ce qui réduit drastiquement la consommation électrique globale du rack.

## 4. LiquidStack – L'expert de l'immersion haute performance
LiquidStack défend une approche à très haut rendement : l'immersion diphasique. Le fluide bout au contact des puces, s'évapore, se condense sur un toit froid et retombe en pluie.

* Technologie & Fluide : Immersion diphasique. Suite au retrait du marché du fluide 3M Novec (banni car classé PFAS), LiquidStack s'est allié à des chimistes comme Chemours pour utiliser des fluides HFO (Hydrofluorooléfines) de nouvelle génération.
* Solution phare : Les cuves DataTank. Conçues pour des charges thermiques colossales, elles peuvent dissiper plus de 250 kW dans un espace très restreint.
* Points forts & Vigilance :
* Performance thermique inégalée : Le changement d'état (liquide à gaz) capture la chaleur bien plus vite que n'importe quelle autre méthode.
   * Le point de vigilance environnemental : Bien que ces nouveaux fluides HFO aient un impact quasi nul sur la couche d'ozone et le réchauffement global (faible GWP), ils restent des composés fluorés. Les régulateurs surveillent de près leurs sous-produits de dégradation (comme l'acide trifluoroacétique ou TFA), ce qui pousse certains exploitants à leur préférer l'eau ou les huiles de Submer.


## 5. Schneider Electric – Le leader de la gestion énergétique globale
Schneider Electric (via l'intégration complète des technologies de sa filiale Motivair) se positionne sur une approche « From Grid to Chip » (du réseau électrique à la puce). Le groupe combine son expertise historique en distribution électrique et en logiciels de gestion (DCIM) avec une offre thermique de pointe.

* Technologie & Fluide : Direct-to-Chip (monophasique). Le liquide qui circule dans les serveurs et les plaques froides est un mélange d'eau déionisée et de propylène glycol, garantissant 0 % de PFAS et une absence totale de toxicité.
* Solution phare : La gamme d'unités de distribution de fluide CDU In-Rack et Floor-Mount (issues du catalogue Motivair). Elles permettent de réguler le débit et la température du liquide avec des capacités modulables allant de 200 kW (au sein du rack) jusqu'à 2,5 MW (unités au sol pour les très grands datacenters).
* Points forts :
* Écosystème unifié : Schneider est le seul acteur capable de fournir à la fois le refroidissement liquide, les armoires électriques, les onduleurs (UPS) et le logiciel de pilotage automatisé du datacenter.
   * Architectures de référence NVIDIA : Schneider a co-développé et validé des designs d'infrastructures officiels pour les plateformes de calcul intensif de nouvelle génération (comme les puces Blackwell et l'architecture NVL72), simplifiant le déploiement de l'IA à grande échelle.


-------------------
# Contraintes

Pour arbitrer entre ces différentes technologies (portées par Schneider, Vertiv, CoolIT, Submer ou LiquidStack), il faut analyser d'un côté la réalité opérationnelle au quotidien (la maintenance) et de l'autre la performance énergétique globale (le PUE).
------------------------------
## 1. Contraintes de Maintenance : La réalité du terrain
Les opérations de maintenance varient radicalement selon que le fluide est confiné dans des tuyaux ou que les serveurs y sont totalement immergés.
## Technologie 1 : Le Direct-to-Chip (Monophasique)
Modèles : Schneider Electric (Motivair), Vertiv, CoolIT
Cette approche conserve le format classique des racks informatiques. La maintenance s'intègre facilement dans les habitudes des techniciens.

* 
* Changement des filtres : Les filtres à sédiments (situés dans les CDU au sol ou en rack) doivent être nettoyés ou remplacés tous les 6 à 12 mois pour éviter que des microparticules n'obstruent les microcanaux en cuivre des plaques froides.
* Vidange & Fluide : Pas de vidange fréquente nécessaire. Le mélange eau déionisée + glycol circule en circuit fermé étanche. Une analyse annuelle du pH et de la conductivité de l'eau est recommandée pour s'assurer que les inhibiteurs de corrosion restent actifs.
* Manipulation : Très simple grâce aux connecteurs rapides anti-goutte (Quick Disconnects). Pour changer un serveur ou une puce, on déclipse les tuyaux souples sans couper le reste du rack.
* Point noir : Le risque de fuite localisée. Bien que minime avec les technologies actuelles, une rupture de tuyau envoie de l'eau glycolée conductrice directement sur des composants sous tension.
* 

## Technologie 2 : L'Immersion Monophasique (Bains d'huile)
Modèles : Submer, GRC, Asperitas
Le format change : les serveurs sont horizontaux ou verticaux dans des cuves pleines de fluide diélectrique (huiles PAO ou esters).

* 
* Changement des filtres : Les cuves intègrent des pompes de recirculation continue avec des filtres à huile à remplacer tous les 12 à 24 mois, principalement pour capturer les résidus de poussière résiduelle ou les exsudats de plastique des câbles des serveurs.
* Vidange & Fluide : Les huiles synthétiques de haute qualité ont une durée de vie de plus de 10 ans sans vidange. Le niveau est simplement ajusté en cas de pertes mineures lors des manipulations.
* Manipulation : C'est ici que la logistique se corse. Pour remplacer une barrette de RAM ou un disque, il faut extraire le serveur de la cuve à la verticale (parfois à l'aide d'un palan pour les serveurs lourds). Le serveur doit ensuite être placé sur une station d'égouttement pour éliminer l'huile résiduelle avant d'intervenir. Les techniciens travaillent "les mains dans l'huile", ce qui nécessite des équipements de protection (gants) et des bacs de rétention.
* 

## Technologie 3 : L'Immersion Diphasique (Fluides chimiques HFO)
Modèles : LiquidStack, ZutaCore

* 
* Changement des filtres : Très réduit car l'ébullition et la condensation se font en milieu hermétique pur.
* Vidange & Fluide : Pas de vidange, mais un contrôle strict de l'étanchéité de la cuve. Comme le liquide s'évapore à basse température (~50°C), la moindre fuite dans les joints du couvercle entraîne une évaporation du fluide dans l'air ambiant, ce qui coûte extrêmement cher (les fluides HFO ou fluorés sont très onéreux).
* Manipulation : Pour ouvrir la cuve, il faut activer un système de condensation rapide afin de faire retomber les gaz sous forme liquide pour éviter qu'ils ne s'échappent dans la salle informatique à l'ouverture du couvercle.
* 

------------------------------
## 2. Analyse de l'impact sur le PUE (Power Usage Effectiveness)
Le PUE mesure l'efficacité énergétique d'un datacenter. Plus il est proche de 1,00, plus l'infrastructure est vertueuse (toute l'énergie va à l'informatique, aucune n'est gaspillée dans la climatisation).
Pour rappel, un datacenter classique refroidi par air affiche un PUE moyen mondial situé entre 1,40 et 1,80.
Directement corrélé à l'efficacité des fluides, le match du PUE se joue ainsi :

[Moins performant] ---------------------------------------------> [Plus performant]
Air classique     Direct-to-Chip     Immersion Monophasique     Immersion Diphasique
PUE: 1.40-1.80    PUE: 1.10-1.15     PUE: 1.03-1.08             PUE: 1.02-1.04

## Le Direct-to-Chip (Schneider, Vertiv, CoolIT) ➔ PUE cible : 1,10 à 1,15

* 
* Pourquoi ce score ? Les plaques froides capturent environ 70 à 80 % de la chaleur directement à la source (sur les GPU/CPU). L'eau chaude sortant des serveurs (~45°C à 50°C) peut être refroidie à l'extérieur par de simples aéroréfrigérants (dry-coolers) en mode Free Cooling toute l'année, sans allumer de compresseurs de climatisation énergivores.
* La limite : Les 20 à 30 % de chaleur restants (mémoires, alimentations, cartes réseau) sont dissipés dans l'air du serveur. Le datacenter doit donc conserver des ventilateurs dans les serveurs et une infrastructure de climatisation par air minimale (comme des portes arrière thermiques Schneider/Motivair ou des armoires de clim). Ces ventilateurs consomment de l'énergie et brident le PUE à ~1,10.
* 

## L'Immersion Monophasique (Submer, GRC) ➔ PUE cible : 1,03 à 1,08

* Pourquoi ce score ? L'huile diélectrique enveloppe 100 % des composants. Tous les ventilateurs internes des serveurs sont définitivement retirés, car c'est le liquide qui circule partout. On économise immédiatement environ 10 à 15 % de la consommation électrique propre du serveur.
* De plus, il n'y a plus aucune armoire de climatisation par air dans la pièce. L'énergie de refroidissement externe se résume aux pompes de circulation et aux ventilateurs extérieurs des dry-coolers, ce qui propulse le PUE à des niveaux extrêmement bas (~1,05).
* 

## L'Immersion Diphasique (LiquidStack) ➔ PUE cible : 1,02 à 1,04


* Pourquoi ce score ? C'est le summum de l'efficacité physique. Le changement d'état (le liquide devient gaz) absorbe une quantité d'énergie thermique gigantesque sans effort mécanique. Les pompes de circulation ont besoin de travailler beaucoup moins que dans un système monophasique. Le gain énergétique est maximal, mais le coût initial (CapEx) et les incertitudes réglementaires sur les fluides synthétiques limitent cette solution aux applications hyper-spécifiques.


