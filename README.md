<div align="center">

# Awesome Reliable Concept Bottleneck Models

**A curated reading map for Concept Bottleneck Models, concept-based explanations, and reliability-centered evaluation.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Focus](https://img.shields.io/badge/focus-reliable%20CBMs-2f6f9f)
![Scope](https://img.shields.io/badge/scope-survey%20companion-555555)
![Status](https://img.shields.io/badge/status-active%20curation-5b8c5a)

</div>

This repository collects papers for reading Concept Bottleneck Models (CBMs) through a reliability lens. Instead of organizing the area only by model family or publication date, it asks what each paper tells us about concept quality, bottleneck validity, intervention realism, uncertainty, scaling, and deployment stress tests.

The list is designed as a companion resource for a survey on reliable CBMs. It is not linked from the manuscript yet. The current version is intentionally conservative: papers are included because they change the reliability argument, not merely because they contain the phrase "concept bottleneck".

## Reliability Lens Map

| Lens | What it asks | Typical failure if ignored |
| --- | --- | --- |
| Concept quality | Are concepts semantically grounded, complete, and stable? | Concept accuracy is mistaken for meaningful concepts. |
| Bottleneck validity | Does prediction really pass through the stated concepts? | A visible interface is mistaken for faithful mediation. |
| Intervention realism | Who intervenes, under what budget and knowledge constraints? | Oracle correction curves are overread as usable human control. |
| Uncertainty and shift | Does the interface stay meaningful under ambiguity, perturbation, or deployment shift? | Clean explanations hide uncertainty and fragile behavior. |
| Scaling regime | What semantic control is lost when supervision becomes weak, post-hoc, or language-guided? | Scalable concepts are treated as if they had expert-label guarantees. |
| Stress tests | Which frontier assumption breaks first: continual, multimodal, generative, or adversarial? | Benign benchmark success is overread as reliability or safety. |

## Repository Files

- `README.md`: curated reading list and reliability map.
- `CONTRIBUTING.md`: inclusion criteria for future additions.
- `references.bib`: BibTeX metadata for the current bibliography.

## Contents

- [Start Here](#start-here)
- [Surveys and Background](#surveys-and-background)
- [Foundations](#foundations)
- [Concept Quality](#concept-quality)
- [Bottleneck Validity](#bottleneck-validity)
- [Intervention Realism](#intervention-realism)
- [Uncertainty, Stability, and Shift](#uncertainty-stability-and-shift)
- [Scaling and Supervision Transition](#scaling-and-supervision-transition)
- [Frontier Stress Tests](#frontier-stress-tests)
- [Benchmarks and Audit Tools](#benchmarks-and-audit-tools)
- [How to Read This List](#how-to-read-this-list)

## Start Here

- **Concept Bottleneck Models** - Koh et al., ICML 2020. The original CBM formulation with concept prediction, label prediction through concepts, and test-time concept intervention.
- **Post-hoc Concept Bottleneck Models** - Yuksekgonul et al., ICLR 2023. A practical bridge from pretrained representations to concept interfaces.
- **Label-Free Concept Bottleneck Models** - Oikarinen et al., ICLR 2023. A key scaling point for CBMs without dense manual concept labels.
- **Addressing Leakage in Concept Bottleneck Models** - Havasi et al., NeurIPS 2022. A central warning that soft bottlenecks can preserve hidden label information.
- **A Closer Look at the Intervention Procedure of Concept Bottleneck Models** - Shin et al., ICML 2023. Shows that intervention results depend heavily on selection policy and protocol details.

## Surveys and Background

### Explainable and Interpretable Machine Learning

- **Towards A Rigorous Science of Interpretable Machine Learning** - Doshi-Velez and Kim, 2017.
- **The Mythos of Model Interpretability** - Lipton, CACM 2018.
- **A Survey of Methods for Explaining Black Box Models** - Guidotti et al., ACM Computing Surveys 2018.
- **Peeking Inside the Black-Box: A Survey on Explainable Artificial Intelligence** - Adadi and Berrada, IEEE Access 2018.
- **Explainable Artificial Intelligence: Concepts, taxonomies, opportunities and challenges toward responsible AI** - Arrieta et al., Information Fusion 2020.
- **Explaining Deep Neural Networks and Beyond: A Review of Methods and Applications** - Samek et al., Proceedings of the IEEE 2021.
- **A Multidisciplinary Survey and Framework for Design and Evaluation of Explainable AI Systems** - Mohseni et al., ACM TiiS 2021.
- **Human-Centered Explainable AI: From Algorithms to User Experiences** - Liao and Varshney, 2021.
- **Stop explaining black box machine learning models for high stakes decisions and use interpretable models instead** - Rudin, Nature Machine Intelligence 2019.
- **Explanation in Artificial Intelligence: Insights from the Social Sciences** - Miller, Artificial Intelligence 2019.
- **Trends and Trajectories for Explainable, Accountable and Intelligible Systems** - Abdul et al., CHI 2018.
- **Interpreting Interpretability** - Kaur et al., CHI 2020.
- **Evaluating Explainable AI** - Hase and Bansal, ACL 2020.
- **Towards Faithfully Interpretable NLP Systems** - Jacovi and Goldberg, ACL 2020.

### Concept-Based Explanation Ecosystem

- **Interpretability Beyond Feature Attribution: Quantitative Testing with Concept Activation Vectors** - Kim et al., ICML 2018.
- **Towards Automatic Concept-based Explanations** - Ghorbani et al., NeurIPS 2019.
- **Network Dissection: Quantifying Interpretability of Deep Visual Representations** - Bau et al., CVPR 2017.
- **On Completeness-aware Concept-Based Explanations in Deep Neural Networks** - Yeh et al., NeurIPS 2020.
- **Right for the Right Reasons** - Ross et al., IJCAI 2017.
- **Concept-based Explainable Artificial Intelligence: A Survey** - Poeta et al., ACM Computing Surveys 2025.
- **What's in the Bottle? A Survey and Roadmap of Concept Bottleneck Models** - Knab et al., 2026 preprint.

### Trustworthy AI Context

- **AI4People: An Ethical Framework for a Good AI Society** - Floridi et al., Minds and Machines 2018.
- **The global landscape of AI ethics guidelines** - Jobin et al., Nature Machine Intelligence 2019.
- **Trustworthy artificial intelligence** - Thiebes et al., Electronic Markets 2021.
- **Guidelines for Human-AI Interaction** - Amershi et al., CHI 2019.
- **Fooling LIME and SHAP** - Slack et al., AIES 2020.
- **Sanity Checks for Saliency Maps** - Adebayo et al., NeurIPS 2018.
- **A Benchmark for Interpretability Methods in Deep Neural Networks** - Hooker et al., NeurIPS 2019.

## Foundations

- **Concept Bottleneck Models** - Koh et al., ICML 2020.
- **Do Concept Bottleneck Models Learn as Intended?** - Margeloiu et al., 2021.
- **Concept Embedding Models** - Zarlenga et al., NeurIPS 2022.
- **Post-hoc Concept Bottleneck Models** - Yuksekgonul et al., ICLR 2023.
- **Label-Free Concept Bottleneck Models** - Oikarinen et al., ICLR 2023.

## Concept Quality

Concept accuracy is only the first rung. Reliable CBMs also need semantic alignment, local grounding, completeness, stability, and robustness to weak or noisy concept supervision.

- **Do Concept Bottleneck Models Learn as Intended?** - Margeloiu et al., 2021.
- **An Analysis of Concept Bottleneck Models: Measuring, Understanding, and Mitigating the Impact of Noisy Annotations** - Park et al., ICML 2025.
- **Addressing Concept Mislabeling in Concept Bottleneck Models Through Preference Optimization** - Penaloza et al., 2025.
- **Incremental Residual Concept Bottleneck Models** - Shang et al., CVPR 2024.
- **Faithful Vision-Language Interpretation via Concept Bottleneck Models** - Lai et al., ICLR 2024.
- **Improving Concept Alignment in Vision-Language Concept Bottleneck Models** - Selvaraj et al., 2024.
- **If Concept Bottlenecks are the Question, are Foundation Models the Answer?** - Debole et al., 2025.
- **On the Concept Trustworthiness in Concept Bottleneck Models** - Huang et al., 2024.
- **Discovering Fine-Grained Visual-Concept Relations by Disentangled Optimal Transport Concept Bottleneck Models** - Xie et al., CVPR 2025.
- **Coarse-to-Fine Concept Bottleneck Models** - Panousis et al., 2024.
- **Object-Centric Concept-Bottlenecks** - Steinmann et al., 2025.

## Bottleneck Validity

The presence of a concept layer is not the same as faithful mediation. This section collects work on leakage, residual routes, post-hoc interfaces, structured concepts, and causal or information-theoretic bottleneck claims.

- **Addressing Leakage in Concept Bottleneck Models** - Havasi et al., NeurIPS 2022.
- **Incremental Residual Concept Bottleneck Models** - Shang et al., CVPR 2024.
- **Beyond Concept Bottleneck Models: How to Make Black Boxes Intervenable?** - Laguna et al., 2024.
- **Do Concept Bottleneck Models Respect Localities?** - Raman et al., 2025.
- **There Was Never a Bottleneck in Concept Bottleneck Models** - Almudevar et al., ICLR 2026.
- **Concepts' Information Bottleneck Models** - Galliamov et al., ICLR 2026.
- **Energy-Based Concept Bottleneck Models** - Xu et al., 2024.
- **Relational Concept Bottleneck Models** - Barbiero et al., 2024.
- **Causally Reliable Concept Bottleneck Models** - De Felice et al., 2025.

## Intervention Realism

Intervention results are not comparable unless the user model, budget, selection policy, and local/global control regime are specified.

- **A Closer Look at the Intervention Procedure of Concept Bottleneck Models** - Shin et al., ICML 2023.
- **Interactive Concept Bottleneck Models** - Chauhan et al., AAAI 2023.
- **Learning to Receive Help: Intervention-Aware Concept Embedding Models** - Zarlenga et al., NeurIPS 2023.
- **Adaptive Test-Time Intervention for Concept Bottleneck Models** - Shen et al., 2025.
- **Avoiding Leakage Poisoning: Concept Interventions Under Distribution Shifts** - Espinosa Zarlenga et al., 2025.
- **Editable Concept Bottleneck Models** - Hu et al., 2025.
- **Debugging Concept Bottleneck Models through Removal and Retraining** - Enouen et al., 2025.
- **Deferring Concept Bottleneck Models** - Pugnana et al., 2025.
- **Chat-CBM** - He et al., 2025.
- **Intervening in Black Box: Concept Bottleneck Model for Enhancing Human Neural Network Mutual Understanding** - Xiong et al., ICCV 2025.

## Uncertainty, Stability, and Shift

Reliable concept interfaces should express ambiguity, separate uncertainty types where possible, and remain meaningful under perturbation or deployment shift.

- **Probabilistic Concept Bottleneck Models** - Kim et al., ICML 2023.
- **Stochastic Concept Bottleneck Models** - van den Hirtz et al., NeurIPS 2024.
- **Credal Concept Bottleneck Models** - Mukherjee et al., 2026.
- **Evidential Concept Embedding Models** - Gao et al., 2024.
- **Adaptive Concept Bottleneck for Foundation Models Under Distribution Shifts** - Choi et al., 2025.
- **Avoiding Leakage Poisoning: Concept Interventions Under Distribution Shifts** - Espinosa Zarlenga et al., 2025.
- **BEARS Make Neuro-Symbolic Models Aware of their Reasoning Shortcuts** - Marconato et al., 2024.

## Scaling and Supervision Transition

As CBMs move from dense expert labels to post-hoc, label-free, VLM-guided, LLM-guided, or open-vocabulary regimes, annotation cost falls but semantic debt rises.

- **Post-hoc Concept Bottleneck Models** - Yuksekgonul et al., ICLR 2023.
- **Label-Free Concept Bottleneck Models** - Oikarinen et al., ICLR 2023.
- **Faithful Vision-Language Interpretation via Concept Bottleneck Models** - Lai et al., ICLR 2024.
- **Semi-supervised Concept Bottleneck Models** - Hu et al., 2025.
- **V2C-CBM: Building Concept Bottlenecks with Vision-to-Concept Tokenizer** - He et al., AAAI 2025.
- **Selective Concept Bottleneck Models Without Predefined Concepts** - Schrodi et al., TMLR 2025.
- **Show and Tell: Visually Explainable Deep Neural Nets via Spatially-Aware Concept Bottleneck Models** - Benou and Riklin Raviv, CVPR 2025.
- **Language in a Bottle: Language Model Guided Concept Bottlenecks for Interpretable Image Classification** - Yang et al., CVPR 2023.
- **Explain via Any Concept** - Tan et al., ECCV 2024.
- **Interpreting Pretrained Language Models via Concept Bottlenecks** - Tan et al., 2024.
- **Concept Bottleneck Language Models for Protein Design** - Ismail et al., ICLR 2025.
- **Bayesian Concept Bottleneck Models with LLM Priors** - Feng et al., 2024.

## Frontier Stress Tests

These papers are useful because they test where the classical CBM assumptions break first: fixed concept vocabularies, single-modality evidence, static prediction, and benign evaluation.

### Continual Learning

- **Learning New Concepts, Remembering the Old** - Lai et al., 2025.
- **CI-CBM: A Concept-Based Approach for Continual Learning in Vision Tasks** - Javadi et al., 2026.
- **Language Guided Concept Bottleneck Models for Interpretable Continual Learning** - Yu et al., CVPR 2025.

### Multimodal Reasoning

- **Cross-Modal Conceptualization in Bottleneck Models** - Alukaev et al., 2023.
- **Multimodal Concept Bottleneck Models** - Shi et al., 2025.
- **Graph-Integrated Multimodal Concept Bottleneck Model** - Lin et al., 2025.

### Generative Control

- **Concept Bottleneck Generative Models** - Ismail et al., UAI 2024.
- **Interpretable Generative Models through Post-hoc Concept Bottlenecks** - Kulkarni et al., CVPR 2025.
- **Interpretable Concept Bottlenecks to Align Reinforcement Learning Agents** - Delfosse et al., 2024.

### Security-Sensitive Settings

- **Multimodal Deception in Explainable AI: Concept-Level Back-door Attacks on Concept Bottleneck Models** - Lai et al., TMLR 2026.

## Benchmarks and Audit Tools

- **A Neuro-Symbolic Benchmark Suite for Concept Quality and Reasoning Shortcuts** - Bortolotti et al., 2024.
- **BEARS Make Neuro-Symbolic Models Aware of their Reasoning Shortcuts** - Marconato et al., 2024.
- **Claim-to-evidence ladder for CBM papers** - Suggested audit pattern from the companion survey: identify the interpretability claim first, then require the matching evidence bundle.

## How to Read This List

Not every paper here earns the same strength of reliability claim. A useful way to read the literature is:

1. Check whether concepts are semantically grounded and complete enough for the task.
2. Check whether prediction is genuinely mediated by the concept interface.
3. Check whether interventions correspond to realistic human control.
4. Check whether uncertainty, shift, or perturbation changes the meaning of the interface.
5. Check which supervision assumptions were relaxed when the model scaled.
6. Check whether frontier claims have stress tests matched to the deployment setting.

Contributions are welcome once this repository is made public. For now, keep the list conservative: add papers because they change the reliability argument, not merely because they use the phrase "concept bottleneck".
