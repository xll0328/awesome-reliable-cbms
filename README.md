<div align="center">

# Awesome Reliable Concept Bottleneck Models

**A curated, clickable reading map for reliable Concept Bottleneck Models (CBMs).**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Focus](https://img.shields.io/badge/focus-reliable%20CBMs-2f6f9f)
![Format](https://img.shields.io/badge/format-reading%20map%20%2B%20paper%20index-555555)
![Status](https://img.shields.io/badge/status-active%20curation-5b8c5a)

</div>

Concept Bottleneck Models promise an interpretable interface: predict human-meaningful concepts first, then predict the task label from those concepts. Reliability is the hard part. A CBM can look interpretable while its concepts are noisy, incomplete, leaky, hard to intervene on, or brittle under shift.

This repository is organized as a **reading map**, not a paper dump. Each entry is linked and annotated by what it helps you check: concept quality, bottleneck validity, intervention realism, uncertainty, scaling, or stress testing.

## Quick Links

- [Core Reading Paths](#core-reading-paths)
- [Reliability Lens Map](#reliability-lens-map)
- [Foundational Papers](#foundational-papers)
- [Curated Paper Map](#curated-paper-map)
- [Code and Reproducibility](#code-and-reproducibility)
- [Structured Index](papers.csv)
- [BibTeX](references.bib)
- [Contributing](CONTRIBUTING.md)

## Core Reading Paths

| Goal | Read in this order | What you get |
| --- | --- | --- |
| Understand CBMs quickly | [CBM](https://proceedings.mlr.press/v119/koh20a/koh20a.pdf) -> [CEM](https://papers.nips.cc/paper_files/paper/2022/hash/867c06823281e506e8059f5c13a57f75-Abstract-Conference.html) -> [PCBM](https://openreview.net/forum?id=nA5AZ8CEyow) -> [LF-CBM](https://openreview.net/forum?id=FlCg47MNvBA) | The classical architecture, embedding variant, post-hoc variant, and scalable label-free variant. |
| Audit reliability claims | [Leakage](https://proceedings.neurips.cc/paper_files/paper/2022/file/944ecf65a46feb578a43abfd5cddd960-Paper-Conference.pdf) -> [Intervention Procedure](https://proceedings.mlr.press/v202/shin23a.html) -> [Localities](https://openreview.net/forum?id=4mCkRbUXOf) -> [Never a Bottleneck](https://openreview.net/forum?id=Fy7V5dalvX) | Why a visible bottleneck is not automatically faithful, causal, or usable. |
| Build a practical model | [PCBM](https://openreview.net/forum?id=nA5AZ8CEyow) -> [LF-CBM](https://openreview.net/forum?id=FlCg47MNvBA) -> [VLG-CBM](https://proceedings.neurips.cc/paper_files/paper/2024/hash/90043ebd68500f9efe84fedf860a64f3-Abstract-Conference.html) -> [SCBM](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5c7894ac8788555f1cecf536f1e0fd35-Abstract-Conference.html) | A route from retrofitting to weak supervision, visual grounding, and correlated-concept uncertainty. |
| Write survey background | [Rigorous Interpretable ML](https://arxiv.org/abs/1702.08608) -> [Mythos](https://doi.org/10.1145/3233231) -> [XAI Survey](https://doi.org/10.1016/j.inffus.2019.12.012) -> [Concept-based XAI Survey](https://doi.org/10.1145/3774643) | The broader XAI and concept-based explanation context around CBMs. |
| Find frontier stress tests | [Continual CBM](https://doi.org/10.1145/3746027.3758157) -> [Multimodal CBM](https://openreview.net/forum?id=6r2ercqOo8) -> [Concept Bottleneck Generative Models](https://openreview.net/forum?id=6KG8YqEafn) -> [Concept Backdoor Attacks](https://openreview.net/forum?id=64ec7189fe460c57949df59db5ad5d2ca4154069) | Where fixed vocabulary, single-modality, static-task, and benign-evaluation assumptions start to break. |

## Reliability Lens Map

| Lens | Reliability question | Representative papers |
| --- | --- | --- |
| Concept quality | Are concepts semantically aligned, complete, stable, and robust to noisy labels? | [Margeloiu 2021](https://arxiv.org/abs/2105.04289), [Park 2025](https://openreview.net/forum?id=s3TvewYDKk), [Penaloza 2025](https://proceedings.mlr.press/v267/penaloza25a.html) |
| Bottleneck validity | Does prediction really pass through the stated concept interface? | [Havasi 2022](https://proceedings.neurips.cc/paper_files/paper/2022/file/944ecf65a46feb578a43abfd5cddd960-Paper-Conference.pdf), [Raman 2025](https://openreview.net/forum?id=4mCkRbUXOf), [Almudevar 2026](https://openreview.net/forum?id=Fy7V5dalvX) |
| Intervention realism | Are interventions modeled with realistic users, budgets, and selection policies? | [Shin 2023](https://proceedings.mlr.press/v202/shin23a.html), [Chauhan 2023](https://doi.org/10.1609/AAAI.V37I5.25736), [Zarlenga 2023](https://papers.nips.cc/paper_files/paper/2023/hash/770cabd044c4eacb6dc5924d9a686dce-Abstract-Conference.html) |
| Uncertainty and shift | Does the interface expose ambiguity and remain meaningful under shift? | [ProbCBM](https://proceedings.mlr.press/v202/kim23g.html), [SCBM](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5c7894ac8788555f1cecf536f1e0fd35-Abstract-Conference.html), [CONDA](https://openreview.net/forum?id=8sfc8MwG5v) |
| Scaling regime | What is lost when supervision becomes post-hoc, label-free, VLM-guided, or open-vocabulary? | [PCBM](https://openreview.net/forum?id=nA5AZ8CEyow), [LF-CBM](https://openreview.net/forum?id=FlCg47MNvBA), [LaBo](https://openaccess.thecvf.com/content/CVPR2023/html/Yang_Language_in_a_Bottle_Language_Model_Guided_Concept_Bottlenecks_for_CVPR_2023_paper.html) |
| Stress tests | Which CBM assumptions fail in continual, multimodal, generative, or adversarial settings? | [CLG-CBM](https://openaccess.thecvf.com/content/CVPR2025/html/Yu_Language_Guided_Concept_Bottleneck_Models_for_Interpretable_Continual_Learning_CVPR_2025_paper.html), [CBGM](https://openreview.net/forum?id=6KG8YqEafn), [Backdoor CBM](https://openreview.net/forum?id=64ec7189fe460c57949df59db5ad5d2ca4154069) |

## Foundational Papers

| Paper | Why it matters | Links |
| --- | --- | --- |
| [Concept Bottleneck Models](https://proceedings.mlr.press/v119/koh20a/koh20a.pdf) | Defines the standard CBM pipeline and the idea of test-time concept intervention. | [code](https://github.com/yewsiang/ConceptBottleneck) |
| [Do Concept Bottleneck Models Learn as Intended?](https://arxiv.org/abs/2105.04289) | Early warning that high concept accuracy does not guarantee the intended internal semantics. | [paper](https://arxiv.org/abs/2105.04289) |
| [Concept Embedding Models](https://papers.nips.cc/paper_files/paper/2022/hash/867c06823281e506e8059f5c13a57f75-Abstract-Conference.html) | Replaces binary concept nodes with concept embeddings to improve the accuracy/intervention tradeoff. | [code](https://github.com/mateoespinosa/cem) |
| [Post-hoc Concept Bottleneck Models](https://openreview.net/forum?id=nA5AZ8CEyow) | Turns pretrained representations into concept interfaces and enables concept-level model editing. | [code](https://github.com/mertyg/post-hoc-cbm) |
| [Label-Free Concept Bottleneck Models](https://openreview.net/forum?id=FlCg47MNvBA) | Shows how to build CBM-like interfaces without dense manual concept labels. | [code](https://github.com/Trustworthy-ML-Lab/Label-free-CBM) |

## Curated Paper Map

### Surveys and Background

- [Concept-based Explainable Artificial Intelligence: A Survey](https://doi.org/10.1145/3774643) - The best entry point for concept-based XAI beyond CBMs.
- [What's in the Bottle? A Survey and Roadmap of Concept Bottleneck Models](https://openreview.net/forum?id=IF5vnqxBEW) - CBM-specific survey framing and roadmap.
- [Towards A Rigorous Science of Interpretable Machine Learning](https://arxiv.org/abs/1702.08608) - Useful for defining what interpretability evidence should prove.
- [The Mythos of Model Interpretability](https://doi.org/10.1145/3233231) - Separates different meanings of interpretability that CBM papers often conflate.
- [Explainable Artificial Intelligence: Concepts, taxonomies, opportunities and challenges](https://doi.org/10.1016/j.inffus.2019.12.012) - Broad XAI taxonomy for introduction/background sections.
- [Stop explaining black box machine learning models for high stakes decisions and use interpretable models instead](https://doi.org/10.1038/s42256-019-0048-x) - Important motivation for inherently interpretable systems.
- [Human-Centered Explainable AI](https://arxiv.org/abs/2110.10790) - Useful when discussing user-facing intervention and evaluation.
- [Guidelines for Human-AI Interaction](https://doi.org/10.1145/3290605.3300233) - Background for CBMs as human-control interfaces.

### Concept-Based Explanation Ecosystem

- [TCAV](https://proceedings.mlr.press/v80/kim18d.html) - Canonical concept activation baseline for concept-based explanation.
- [ACE](https://proceedings.neurips.cc/paper/2019/hash/77d2afcb31f6493e350fca61764efb9a-Abstract.html) - Automatic concept discovery before CBM-style prediction interfaces.
- [Network Dissection](https://doi.org/10.1109/CVPR.2017.354) - Quantifies semantic units in deep vision models.
- [Completeness-aware Concept-Based Explanations](https://proceedings.neurips.cc/paper/2020/hash/ecb287ff763c169694f682af52c1f309-Abstract.html) - Connects concept explanations to sufficiency/completeness.
- [Self-Explaining Neural Networks](https://proceedings.neurips.cc/paper/2018/hash/3e9f0fc9b2f89e043bc6233994dfcf76-Abstract.html) - Related architecture for interpretable intermediate reasoning.
- [ProtoPNet](https://proceedings.neurips.cc/paper/2019/hash/adf7ee2dcf142b0e11888e72b43fcb75-Abstract.html) - Prototype-based interpretability comparison point.
- [Right for the Right Reasons](https://doi.org/10.24963/ijcai.2017/371) - Background for aligning predictions with human-relevant evidence.

### Concept Quality

- [An Analysis of Concept Bottleneck Models: Measuring, Understanding, and Mitigating the Impact of Noisy Annotations](https://openreview.net/forum?id=s3TvewYDKk) - Directly studies noisy concept supervision.
- [Addressing Concept Mislabeling in Concept Bottleneck Models Through Preference Optimization](https://proceedings.mlr.press/v267/penaloza25a.html) - Targets mislabeling as a concept-quality failure mode.
- [Faithful Vision-Language Interpretation via Concept Bottleneck Models](https://openreview.net/forum?id=rp0EdI8X4e) - Defines a stricter faithful vision-language concept interface.
- [Improving Concept Alignment in Vision-Language Concept Bottleneck Models](https://arxiv.org/abs/2405.01825) - Studies alignment drift in VLM-generated concepts.
- [If Concept Bottlenecks are the Question, are Foundation Models the Answer?](https://arxiv.org/abs/2504.19774) - Tests whether foundation-model concepts solve or merely shift concept-quality problems.
- [On the Concept Trustworthiness in Concept Bottleneck Models](https://doi.org/10.1609/AAAI.V38I19.30109) - Focuses on whether concept predictions themselves deserve trust.
- [Coarse-to-Fine Concept Bottleneck Models](https://proceedings.neurips.cc/paper_files/paper/2024/hash/bdeab378efe6eb289714e2a5abc6ed42-Abstract-Conference.html) - Adds hierarchy to reduce overly coarse concept supervision.
- [Object-Centric Concept-Bottlenecks](https://openreview.net/forum?id=9lhijvd0fs) - Moves concept grounding toward object-level structure.

### Bottleneck Validity and Leakage

- [Addressing Leakage in Concept Bottleneck Models](https://proceedings.neurips.cc/paper_files/paper/2022/file/944ecf65a46feb578a43abfd5cddd960-Paper-Conference.pdf) - Central paper for hidden label information in soft concepts.
- [Incremental Residual Concept Bottleneck Models](https://openaccess.thecvf.com/content/CVPR2024/html/Shang_Incremental_Residual_Concept_Bottleneck_Models_CVPR_2024_paper.html) - Makes residual non-concept information explicit instead of pretending the bottleneck is complete.
- [Beyond Concept Bottleneck Models: How to Make Black Boxes Intervenable?](https://proceedings.neurips.cc/paper_files/paper/2024/hash/9a439efaa34fe37177eba00737624824-Abstract-Conference.html) - Generalizes intervention interfaces beyond classical CBMs.
- [Do Concept Bottleneck Models Respect Localities?](https://openreview.net/forum?id=4mCkRbUXOf) - Tests whether concept edits behave locally.
- [There Was Never a Bottleneck in Concept Bottleneck Models](https://openreview.net/forum?id=Fy7V5dalvX) - Strong critique of bottleneck faithfulness.
- [Concepts' Information Bottleneck Models](https://openreview.net/forum?id=JGIYfwaNpT) - Uses information bottleneck pressure to reduce leakage and spurious detail.
- [Energy-Based Concept Bottleneck Models](https://openreview.net/forum?id=I1quoTXZzc) - Models concept dependencies and interventions probabilistically. [code](https://github.com/xmed-lab/ECBM)
- [Causally Reliable Concept Bottleneck Models](https://openreview.net/forum?id=UX143QGvb8) - Adds causal structure to improve intervention reliability. [code](https://github.com/gdefe/causally-reliable-cbm)

### Intervention Realism

- [A Closer Look at the Intervention Procedure of Concept Bottleneck Models](https://proceedings.mlr.press/v202/shin23a.html) - Shows intervention gains depend heavily on concept selection and protocol.
- [Interactive Concept Bottleneck Models](https://doi.org/10.1609/AAAI.V37I5.25736) - Treats CBMs as interactive systems rather than static explanation artifacts.
- [Learning to Receive Help](https://papers.nips.cc/paper_files/paper/2023/hash/770cabd044c4eacb6dc5924d9a686dce-Abstract-Conference.html) - Trains concept embeddings to benefit from interventions. [code](https://github.com/mateoespinosa/cem)
- [Adaptive Test-Time Intervention for Concept Bottleneck Models](https://openreview.net/forum?id=wBygggbUV8) - Studies adaptive intervention policies.
- [Avoiding Leakage Poisoning](https://openreview.net/forum?id=7mxDGiF01U&noteId=t5cWRSRpJT) - Explains how interventions can fail under distribution shift.
- [Editable Concept Bottleneck Models](https://proceedings.mlr.press/v267/hu25u.html) - Uses concept-level edits as a model update mechanism.
- [Deferring Concept Bottleneck Models](https://openreview.net/forum?id=QdfdwsboOE) - Connects concept interventions with imperfect expert deferral.
- [Chat-CBM](https://arxiv.org/abs/2509.17522) - Explores interactive CBMs with frozen LLMs.

### Uncertainty, Stability, and Shift

- [Probabilistic Concept Bottleneck Models](https://proceedings.mlr.press/v202/kim23g.html) - Introduces probabilistic concept representations.
- [Stochastic Concept Bottleneck Models](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5c7894ac8788555f1cecf536f1e0fd35-Abstract-Conference.html) - Models correlated concept uncertainty and intervention propagation. [code](https://github.com/mvandenhi/SCBM)
- [Credal Concept Bottleneck Models](https://arxiv.org/abs/2602.11219) - Separates epistemic and aleatoric uncertainty in concept bottlenecks.
- [Evidential Concept Embedding Models](https://doi.org/10.1007/978-3-031-72117-5_29) - Applies evidential uncertainty to medical concept explanations.
- [CONDA](https://openreview.net/forum?id=8sfc8MwG5v) - Adapts foundation-model concept bottlenecks under distribution shift.
- [BEARS](https://proceedings.mlr.press/v244/marconato24a.html) - Benchmarking shortcut-aware reasoning in neuro-symbolic models.

### Scaling and Supervision Transition

- [Language in a Bottle](https://openaccess.thecvf.com/content/CVPR2023/html/Yang_Language_in_a_Bottle_Language_Model_Guided_Concept_Bottlenecks_for_CVPR_2023_paper.html) - Uses language models to generate concept bottlenecks for images.
- [VLG-CBM](https://proceedings.neurips.cc/paper_files/paper/2024/hash/90043ebd68500f9efe84fedf860a64f3-Abstract-Conference.html) - Adds vision-language grounding and evaluation for scalable CBM training. [code](https://github.com/Trustworthy-ML-Lab/VLG-CBM)
- [Discover-then-Name](https://doi.org/10.1007/978-3-031-72980-5_26) - Discovers task-agnostic bottleneck concepts before naming them.
- [Concept Bottleneck Large Language Models](https://openreview.net/forum?id=RC5FPYVQaH) - Extends bottleneck ideas into LLM reasoning.
- [Explain via Any Concept](https://doi.org/10.1007/978-3-031-73016-0_8) - Open-vocabulary concept bottlenecks.
- [Selective Concept Bottleneck Models Without Predefined Concepts](https://openreview.net/forum?id=PMO30TLI4l) - Removes the predefined concept vocabulary assumption.
- [Semi-supervised Concept Bottleneck Models](https://openaccess.thecvf.com/content/ICCV2025/html/Hu_Semi-supervised_Concept_Bottleneck_Models_ICCV_2025_paper.html) - Reduces concept annotation needs with semi-supervised learning.
- [V2C-CBM](https://doi.org/10.1609/aaai.v39i3.32352) - Builds concept bottlenecks through a vision-to-concept tokenizer.

### Frontier Stress Tests

- [Learning New Concepts, Remembering the Old](https://doi.org/10.1145/3746027.3758157) - Multimodal continual CBMs under evolving concept sets.
- [CI-CBM](https://openreview.net/forum?id=Wf6OpLgj2i) - Class-incremental CBMs for continual learning.
- [Language Guided Concept Bottleneck Models for Interpretable Continual Learning](https://openaccess.thecvf.com/content/CVPR2025/html/Yu_Language_Guided_Concept_Bottleneck_Models_for_Interpretable_Continual_Learning_CVPR_2025_paper.html) - Language-guided concepts for continual vision tasks. [code](https://github.com/FisherCats/CLG-CBM)
- [Cross-Modal Conceptualization in Bottleneck Models](https://aclanthology.org/2023.emnlp-main.318/) - Concept bottlenecks across modalities.
- [Multimodal Concept Bottleneck Models](https://openreview.net/forum?id=6r2ercqOo8) - Tests CBM assumptions in multimodal settings.
- [Concept Bottleneck Generative Models](https://openreview.net/forum?id=6KG8YqEafn) - Extends bottlenecks from classification to generation.
- [Interpretable Generative Models through Post-hoc Concept Bottlenecks](https://openaccess.thecvf.com/content/CVPR2025/html/Kulkarni_Interpretable_Generative_Models_through_Post-hoc_Concept_Bottlenecks_CVPR_2025_paper.html) - Post-hoc concept interfaces for generative models.
- [Interpretable Concept Bottlenecks to Align Reinforcement Learning Agents](https://proceedings.neurips.cc/paper_files/paper/2024/hash/7b76eea0c3683e440c3d362620f578cd-Abstract-Conference.html) - Concept bottlenecks for RL alignment.
- [Multimodal Deception in Explainable AI](https://openreview.net/forum?id=64ec7189fe460c57949df59db5ad5d2ca4154069) - Concept-level backdoor attacks against CBMs.

## Code and Reproducibility

| Resource | What it is useful for |
| --- | --- |
| [yewsiang/ConceptBottleneck](https://github.com/yewsiang/ConceptBottleneck) | Original CBM implementation and CUB/OAI preprocessing. |
| [mertyg/post-hoc-cbm](https://github.com/mertyg/post-hoc-cbm) | Post-hoc CBMs and concept-level editing. |
| [Trustworthy-ML-Lab/Label-free-CBM](https://github.com/Trustworthy-ML-Lab/Label-free-CBM) | Label-free CBM construction from pretrained models. |
| [mateoespinosa/cem](https://github.com/mateoespinosa/cem) | Concept Embedding Models, intervention-aware CEMs, and leakage-poisoning experiments. |
| [Trustworthy-ML-Lab/VLG-CBM](https://github.com/Trustworthy-ML-Lab/VLG-CBM) | Vision-language-guided CBM training and evaluation. |
| [mvandenhi/SCBM](https://github.com/mvandenhi/SCBM) | Stochastic CBMs with correlated concept uncertainty. |
| [xmed-lab/ECBM](https://github.com/xmed-lab/ECBM) | Energy-based CBMs. |
| [gdefe/causally-reliable-cbm](https://github.com/gdefe/causally-reliable-cbm) | Causally reliable CBMs. |
| [FisherCats/CLG-CBM](https://github.com/FisherCats/CLG-CBM) | Language-guided CBMs for continual learning. |
| [PyC book](https://pyc-team.github.io/pyc-book/intro.html) | Tutorial-style concept-based interpretability examples in Python. |

## Structured Index

This repository includes two machine-readable files:

- [`papers.csv`](papers.csv) - selected papers with title, year, venue, lens, maturity, paper link, code link, and a short reliability note.
- [`references.bib`](references.bib) - BibTeX metadata for the current bibliography.

The CSV is intentionally smaller than the BibTeX file. The README and CSV are for navigation; the BibTeX file preserves broader citation metadata.

## Contribution Standard

Please do not add papers only because they mention "concept bottleneck." A useful entry should clarify at least one reliability question:

1. What concept-quality assumption does it test?
2. What bottleneck-validity or leakage issue does it expose?
3. What intervention protocol does it make more realistic?
4. What uncertainty, shift, or robustness setting does it cover?
5. What supervision assumption does it relax?
6. What frontier setting does it stress-test?

See [CONTRIBUTING.md](CONTRIBUTING.md) for the entry format.
