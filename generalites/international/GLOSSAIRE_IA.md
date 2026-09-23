# Glossaire IA — Data Centers et Calcul Haute Performance

**Date** : 17 septembre 2026  
**Périmètre** : Termes techniques liés à l'IA, au calcul GPU et aux data centers

---

## Architectures GPU et Accélération

| Terme | Définition |
|---|---|
| **GPU** (Graphics Processing Unit) | Processeur parallèle initialement conçu pour le graphisme, utilisé pour l'entraînement et l'inférence IA |
| **TPU** (Tensor Processing Unit) | Circuit intégré spécialisé de Google pour les opérations tensorielles (IA) |
| **NPU** (Neural Processing Unit) | Accélérateur IA intégré dans les SoC (Apple Neural Engine, Qualcomm AI Engine) |
| **DPU** (Data Processing Unit) | Processeur spécialisé pour le traitement des données réseau/storage en data center |
| **IPU** (Intelligence Processing Unit) | Processeur graphique de Graphcore optimisé pour l'IA |
| **ASIC** (Application-Specific Integrated Circuit) | Circuit intégré dédié à une tâche spécifique (ex: Google TPU, Huawei Ascend) |
| **FPGA** (Field-Programmable Gate Array) | Circuit reprogrammable utilisé pour l'accélération IA flexible |

### Générations NVIDIA

| Architecture | Année | GPU représentatifs | Caractéristique |
|---|---|---|---|
| **Volta** | 2017 | V100 | Tensor Cores introduits |
| **Ampere** | 2020 | A100, RTX 3090 | 3e gen Tensor Cores, sparsity |
| **Hopper** | 2022 | H100, H200 | Transformer Engine, FP8, HBM3 |
| **Blackwell** | 2024-2025 | B200, GB200 | 2× GPU die, NVLink 5, FP4 |
| **Rubin** | 2026 (annoncé) | R100 | Successeur de Blackwell |

### Termes GPU spécifiques

| Terme | Définition |
|---|---|
| **CUDA** | Plateforme de calcul parallèle de NVIDIA (langage + runtime) |
| **Tensor Core** | Unité matérielle dans les GPU NVIDIA pour opérations matricielles rapides |
| **Transformer Engine** | Module matériel accélérant les modèles Transformer (H100+) |
| **FP8** | Format float 8-bit — nouveau standard pour l'entraînement IA (Hopper+) |
| **TF32** | TensorFloat-32 — format mixte precision (19 bits) introduit avec Ampere |
| **BF16** | BrainFloat-16 — format 16-bit pour IA, plage dynamique équivalente à FP32 |
| **FP16** | Float16 — 16-bit, utilisé pour inférence et entraînement mixte precision |
| **FP64** (Double Precision) | Float64 — haute précision, utilisé en HPC scientifique |
| **Sparse Tensor Core** | Tensor Core accélérant les calculs avec matrices creuses (2× throughput) |
| **NVLink** | Interconnexion GPU-to-GPU de NVIDIA (bande passante : 900 Go/s sur NVLink 5) |
| **NVSwitch** | Commutateur interne permettant la communication full-mesh entre GPU |
| **Infinity Fabric** | Interconnexion AMD équivalente à NVLink |
| **HBM** (High Bandwidth Memory) | Mémoire VRAM à très haute bande passante (H100 : HBM3 3,35 To/s) |
| **HBM3** | 3e génération de HBM (1,35 To/s par puce, 80 Go/sur H100) |
| **HBM3E** | 4e génération (B200 : 8 TB/s) |
| **CoWoS** | Technologie d'empaquettage avancée de TSMC (bottleneck production GPU) |

---

## Modèles et Entraînement IA

| Terme | Définition |
|---|---|
| **LLM** (Large Language Model) | Modèle de langage volumineux (GPT-4, Llama 3, Claude 3.5) |
| **Transformer** | Architecture de réseau de neurones basée sur le mécanisme d'attention (depuis 2017) |
| **Attention** (Mécanisme d') | Permet au modèle de pondérer l'importance des tokens entre eux |
| **Multi-Head Attention** | Plusieurs têtes d'attention parallèles pour capturer différents types de relations |
| **Inference** (Inférence) | Exécution d'un modèle entraîné sur de nouvelles données |
| **Training** (Entraînement) | Processus d'optimisation des poids d'un modèle sur un jeu de données |
| **Fine-tuning** | Ajustement d'un modèle pré-entraîné sur un domaine spécifique |
| **RLHF** (Reinforcement Learning from Human Feedback) | Apprentissage par renforcement à partir de retours humains |
| **Pre-training** | Entraînement initial sur de vastes corpus de données non étiquetées |
| **Foundation Model** | Modèle de base entraîné sur de grandes données, adaptable à de nombreuses tâches |
| **Mixture of Experts** (MoE) | Architecture où seuls des sous-réseaux ("experts") sont activés par token |
| **Scaling Laws** | Lois empiriques décrivant comment la performance s'améliore avec la taille (données, params, compute) |
| **Chinchilla Scaling** | Modèle d'Optimum (DeepMind) : optimal pour un budget compute donné |
| **Tokenizer** | Algorithme de découpage du texte en tokens (BPE, SentencePiece, T5) |
| **Context Window** | Nombre maximal de tokens traités en une seule passe |
| **KV Cache** | Cache des clés/valeurs d'attention pour accélérer l'inférence |
| **LoRA** (Low-Rank Adaptation) | Méthode de fine-tuning efficace adaptant des matrices de faible rang |
| **Quantization** | Réduction de la précision des poids (FP32 → FP16 → INT8 → INT4) |
| **INT8 / INT4** | Quantification 8-bit ou 4-bit pour réduire la mémoire et accélérer l'inférence |
| **AWQ** (Activation-Aware Weight Quantization) | Quantization sensible aux activations |
| **GPTQ** | Algorithme de quantification post-entraînement |
| **Pruning** | Élagage des poids inutiles pour réduire la taille du modèle |
| **Knowledge Distillation** | Transfert de connaissances d'un gros modèle vers un plus petit |

---

## Infrastructure de Calcul IA

| Terme | Définition |
|---|---|
| **AI Factory** | Data center dédié à l'entraînement et l'inférence IA à grande échelle |
| **Hyperscale** | Data center de très grande taille (>20 MW) opéré par un seul grand client |
| **Neocloud** | Opérateur de cloud spécialisé en GPU pour l'IA (CoreWeave, Crusoe, Lambda) |
| **Colocation** | Service permettant de louer de l'espace et de l'énergie dans un data center |
| **GPU Cluster** | Ensemble de GPU connectés pour le calcul parallèle IA |
| **DGX** | Système NVIDIA DGX (serveur AI superordinateur : DGX H100, DGX B200) |
| **HGX** | Plateforme de référence NVIDIA pour les serveurs GPU (HGX H100) |
| **Superpod** | Cluster NVIDIA composé de DGX interconnectés pour les LLM |
| **GB200 NVL72** | Système NVIDIA Blackwell : 72 GPU B200 + 36 Grace CPU, connectés en NVLink |
| **Liquid Cooling** | Refroidissement par liquide (direct-to-chip ou immersion) pour les GPU à haute densité |
| **Direct-to-Chip** | Refroidissement liquide appliqué directement sur la puce GPU |
| **Immersion Cooling** | Immersion totale du serveur dans un fluide caloporteur non conducteur |
| **PUE** (Power Usage Effectiveness) | Ratio énergie totale / énergie IT (1,0 = parfait) |
| **WUE** (Water Usage Effectiveness) | Consommation d'eau par unité de calcul |
| **CUE** (Carbon Usage Effectiveness) | Émission de CO₂ par unité de calcul |
| **Rack Density** | Puissance par rack (kW/rack). Typique : 5-15 kW (classique), 40-100+ kW (AI) |
| **Overprovisioning** | Capacité installée supérieure aux besoins pour absorber les pannes GPU |
| **Flink** | Framework de traitement de données en temps réel (contexte data pipeline) |

---

## Réseau et Connectivité Data Center

| Terme | Définition |
|---|---|
| **InfiniBand** | Protocole d'interconnexion haute performance (RDMA) pour clusters IA (NVIDIA) |
| **RoCE** (RDMA over Converged Ethernet) | RDMA sur Ethernet, alternative à InfiniBand |
| **RDMA** (Remote Direct Memory Access) | Accès mémoire distant sans passage par le CPU (zero-copy) |
| **Ethernet** (Ultra/AI) | Ethernet haute performance pour AI clusters (400G, 800G) |
| **NVLink Switch** | Commutateur NVIDIA interconnectant les GPU en topologie full-mesh |
| **Bandwidth** | Débit de transfert de données (Go/s ou To/s entre GPU) |
| **Latency** | Temps de latence d'une communication inter-GPU (microsecondes) |
| **All-Reduce** | Opération collective distribuant une somme de gradients sur tous les nœuds |
| **Pipeline Parallelism** | Technique de parallélisme où les couches du modèle sont réparties sur des GPU |
| **Tensor Parallelism** | Parallélisme où les matrices tensorielles sont découpées sur plusieurs GPU |
| **Data Parallelism** | Chaque GPU traite un mini-batch différent avec une copie du modèle |
| **3D Parallelism** | Combinaison pipeline + tensor + data parallelism |

---

## Énergie et Efficacité

| Terme | Définition |
|---|---|
| **IT Load** | Puissance consommée par les équipements informatiques (serveurs, stockage, réseau) |
| **Facility Power** | Puissance totale consommée par le data center (IT + refroidissement + UPS) |
| **IT Load** | Charge informatique (kW ou MW) |
| **Power Budget** | Budget énergétique alloué à un site ou un cluster |
| **Energy Efficiency** | Rapport calcul produit / énergie consommée |
| **FLOPS** (Floating Point Operations Per Second) | Mesure de puissance de calcul |
| **GFLOPS** | GigaFLOPS = 10⁹ FLOPS |
| **TFLOPS** | TeraFLOPS = 10¹² FLOPS |
| **PFLOPS** | PetaFLOPS = 10¹⁵ FLOPS |
| **EFLOPS** | ExaFLOPS = 10¹⁸ FLOPS |
| **TOPS** (Tera Operations Per Second) | Mesure pour accélérateurs IA (entier) |
| **TOPS/W** | Efficacité énergétique : opérations par watt |
| **Token/s** | Nombre de tokens générés par seconde (mesure de débit d'inférence) |
| **Throughput** | Débit global (tokens/s ou requêtes/s) |
| **Utilization** | Pourcentage de capacité GPU effectivement utilisée |

---

## Stockage et Pipeline de Données

| Terme | Définition |
|---|---|
| **Dataset** | Ensemble de données d'entraînement (texte, images, code) |
| **Data Pipeline** | Processus ETL/ELT pour préparer les données d'entraînement |
| **Checkpoint** | Sauvegarde intermédiaire des poids du modèle pendant l'entraînement |
| **Shard** | Fragmentation d'un dataset ou modèle pour distribution parallèle |
| **Persistent Storage** | Stockage à long terme pour les données d'entraînement |
| **NVMe** (Non-Volatile Memory Express) | Interface de stockage rapide (SSD) |
| **Parallel File System** | Système de fichiers distribué haute performance (Lustre, BeeGFS, GPFS) |
| **Data Locality** | Proximité physique des données par rapport au calcul (minimise le transfert) |

---

## Sécurité et Confiance

| Terme | Définition |
|---|---|
| **Hallucination** | Génération de contenu faux ou trompeur par un LLM |
| **Alignment** | Alignement du modèle avec les valeurs et intentions humaines |
| **Jailbreak** | Technique pour contourner les filtres de sécurité d'un LLM |
| **Adversarial Attack** | Attaque visant à tromper un modèle IA avec des entrées malveillantes |
| **Guardrail** | Mécanisme de sécurité pour filtrer les sorties d'un LLM |
| **Red Teaming** | Tests de sécurité systématiques sur les modèles IA |
| **Watermarking** | Insertion de marqueurs invisibles dans les sorties IA pour détecter le contenu généré |
| **RLAIF** (RL from AI Feedback) | Alternative à RLHF utilisant un modèle IA pour fournir les retours |

---

## Termes Réglementaires et Marché

| Terme | Définition |
|---|---|
| **EU AI Act** | Règlement européen sur l'IA (approbation 2024, application progressive) |
| **NVIDIA Export Controls** | Restrictions américaines sur l'export de GPU vers la Chine (H20, B200 limités) |
| **Compute Cap** | Limitation de puissance de calcul imposée par les contrôles à l'export |
| **Sovereign AI** | Capacité d'un pays à développer son propre écosystème IA |
| **AI Sovereignty** | Concept de maîtrise nationale de l'infrastructure et des modèles IA |
| **Carbon Footprint** | Empreinte carbone d'un data center ou d'un entraînement de modèle |
| **Green AI** | Pratiques de développement IA éco-responsables |
| **Carbon Credits** | Crédits carbone compensant les émissions des data centers |
| **AI Compute** | Puissance de calcul dédiée à l'IA (souvent mesurée en GPU-months ou FLOPS) |
| **GPU Supply** | Disponibilité des GPU NVIDIA (contrainte majeure 2024-2026) |
| **CoWoS Bottleneck** | Goulot d'étranglement de production TSMC CoWoS limitant la sortie de GPU |
| **Silicon Photonics** | Photonique intégrée pour interconnecter les GPU à basse consommation |
| **CXL** (Compute Express Link) | Protocole d'interconnexion mémoire cache-cohérent entre CPU et GPU/accélérateurs |

---

## Abréviations Fréquentes

| Abréviation | Signification |
|---|---|
| AI | Artificial Intelligence |
| GPU | Graphics Processing Unit |
| CPU | Central Processing Unit |
| TPU | Tensor Processing Unit |
| LLM | Large Language Model |
| NLP | Natural Language Processing |
| CNN | Convolutional Neural Network |
| RNN | Recurrent Neural Network |
| GAN | Generative Adversarial Network |
| VAE | Variational Autoencoder |
| RL | Reinforcement Learning |
| DL | Deep Learning |
| ML | Machine Learning |
| SL | Supervised Learning |
| UL | Unsupervised Learning |
| API | Application Programming Interface |
| RAG | Retrieval-Augmented Generation |
| RAG | Retrieval-Augmented Generation |
| RAG | Retrieval-Augmented Generation |
| AGI | Artificial General Intelligence |
| ARC | AI Research Center |
| FLOPS | Floating Point Operations Per Second |
| TOPS | Tera Operations Per Second |
| HBM | High Bandwidth Memory |
| PUE | Power Usage Effectiveness |
| WUE | Water Usage Effectiveness |
| CXL | Compute Express Link |
| NVMe | Non-Volatile Memory Express |
| RDMA | Remote Direct Memory Access |
| IB | InfiniBand |
| RoCE | RDMA over Converged Ethernet |
| MoE | Mixture of Experts |
| LoRA | Low-Rank Adaptation |
| QLoRA | Quantized LoRA |
| KV Cache | Key-Value Cache |
| BERT | Bidirectional Encoder Representations from Transformers |
| GPT | Generative Pre-trained Transformer |
| LLaMA | Large Language Model Meta AI |
| Mistral | Modèle de langage open-source français |
| Claude | Modèle de langage Anthropic |
| Gemini | Modèle de langage Google |
| Phi | Modèle compact Microsoft |
| Gemma | Modèle open-source Google |
| Qwen | Modèle chinois Alibaba |
| Yi | Modèle chinois 01.AI |
| Jais | Modèle arabe G42 |
| Falcon | Modèle TII (Émirats) |
| MPT | MosaicML Pretrained Transformer |

---

## Sources & Références

- [NVIDIA Data Center Products](https://www.nvidia.com/en-us/data-center/)
- [Uptime Institute — Data Center Standards](https://uptimeinstitute.com/)
- [MLPerf — AI Benchmarking](https://mlperf.org/)
- [EU AI Act — European Commission](https://artificialintelligenceact.eu/)
- [arXiv — AI Research Papers](https://arxiv.org/)
- [LMSYS Chatbot Arena](https://chat.lmsys.org/) — benchmarks LLM
