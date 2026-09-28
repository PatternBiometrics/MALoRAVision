# MALoRAVision

**MALoRAVision** is the official repository for **MA-LoRA**, a research framework for multimodal apparent-gender and age-category prediction from visual inputs under partial observability.

The project investigates how information from multiple visual modalities, including **face, hand, and body images**, can be combined when one or more modalities may be unavailable at inference time.

> **Publication status:** The associated research paper is currently in the submission/review phase.  
> To preserve the integrity of the peer-review process, some implementation details, trained weights, processed data, experimental configurations, numerical results, and reproducibility materials are temporarily withheld. After acceptance/publication, the processed dataset and trained MA-LoRA weights will be released through Google Drive links, together with the corresponding documentation and reproducibility materials, subject to applicable licensing and redistribution conditions.

---

## Overview

Multimodal visual systems often assume that every expected input modality is available. In practical settings, however, one or more inputs may be missing because of acquisition conditions, occlusion, sensor limitations, data availability, or deployment constraints.

MA-LoRA studies this problem in the context of soft-biometric prediction.

The framework is designed to process combinations of:

- Face images
- Hand images
- Body images

for the prediction of:

- Apparent gender
- Apparent age category

while supporting incomplete modality combinations.

The main research question is whether a shared multimodal model can exploit complementary information from several visual sources while remaining usable when only a subset of those sources is available.

---

## Key Features

MALoRAVision focuses on the following research directions:

- **Multimodal visual learning**
- **Partial observability**
- **Missing-modality handling**
- **Parameter-efficient adaptation**
- **LoRA-based adaptation**
- **Modality-aware representation learning**
- **Attribute-aware representation learning**
- **Adaptive multimodal fusion**
- **Apparent-gender prediction**
- **Apparent-age-category prediction**
- **Soft biometrics**
- **Cross-modal evaluation**
- **External generalization analysis**

The complete methodological formulation will be made available after publication of the associated paper.

---

## Supported Modalities

MA-LoRA considers three visual modalities:

| Symbol | Modality |
|---|---|
| `F` | Face |
| `H` | Hand |
| `B` | Body |

The framework is designed to operate under different modality-availability configurations, including:

| Available inputs | Configuration |
|---|---|
| Face only | `F` |
| Hand only | `H` |
| Body only | `B` |
| Face + Hand | `F+H` |
| Face + Body | `F+B` |
| Hand + Body | `H+B` |
| Face + Hand + Body | `F+H+B` |

This allows the model to be studied under both complete and incomplete visual observations.

---

## Prediction Tasks

### Apparent Gender

The first task concerns apparent-gender prediction from the available visual modalities.

Further information about:

- target definition,
- annotation procedure,
- loss formulation,
- evaluation protocol,
- class conventions,

will be provided after publication.

---

### Apparent Age

The second task concerns apparent-age prediction using discrete age categories.

The current research formulation uses seven age groups:

1. `0–17`
2. `18–24`
3. `25–34`
4. `35–44`
5. `45–54`
6. `55–64`
7. `65+`

Additional details concerning the age formulation, training objectives, and evaluation procedure will be documented in the public release accompanying the accepted paper.

---

## Partial Observability

A central objective of MA-LoRA is to study multimodal prediction when not all modalities are available.

Rather than assuming that face, hand, and body information are simultaneously present, the framework is evaluated across multiple availability conditions.

Conceptually:

```text
Available visual observations
          │
          ├── Face
          ├── Hand
          └── Body
          │
          ▼
   Modality-aware processing
          │
          ▼
 Attribute-aware adaptation
          │
          ▼
 Multimodal representation
          │
          ▼
 Task-specific prediction
```

The exact mechanisms used for missing-modality representation, routing, adaptation, and fusion are part of the submitted work and will be documented after acceptance.

---

## Method Overview

MA-LoRA combines parameter-efficient adaptation with multimodal representation learning.

At a high level, the framework contains components for:

```text
Visual Inputs
    │
    ├── Face
    ├── Hand
    └── Body
    │
    ▼
Shared Visual Representation
    │
    ▼
Modality-Aware Adaptation
    │
    ▼
Attribute-Aware Adaptation
    │
    ▼
Availability-Aware Multimodal Processing
    │
    ▼
Task-Specific Fusion
    │
    ├── Apparent Gender
    └── Apparent Age
```

The detailed architecture, adaptation configuration, parameterization, training strategy, and ablation design are intentionally omitted from the repository while the paper remains under review.

They will be released with the final reproducibility package.

---

## Repository Status

The repository is being released in stages.

### Currently available

The public repository may contain:

- project documentation,
- high-level method description,
- licensing information,
- citation information,
- public metadata,
- non-sensitive project assets.

### Planned after paper acceptance

Subject to licensing and redistribution constraints, the following materials are planned for release:

- MA-LoRA implementation
- model definitions
- training scripts
- evaluation scripts
- inference scripts
- configuration files
- preprocessing utilities
- missing-modality evaluation utilities
- processed dataset used for the reported experiments, released through a Google Drive link where redistribution is permitted
- trained model weights, released through a Google Drive link
- checkpoint metadata
- dependency specifications
- reproducibility instructions
- examples
- selected figures
- evaluation protocols
- ablation configurations
- external-validation instructions

The release will correspond to a versioned snapshot of the implementation associated with the published paper.

---

## Planned Repository Structure

The final repository is expected to follow a structure similar to:

```text
MALoRAVision/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── .gitignore
│
├── configs/
│   ├── training/
│   ├── evaluation/
│   └── ablations/
│
├── src/
│   ├── models/
│   ├── datasets/
│   ├── training/
│   ├── evaluation/
│   └── utils/
│
├── scripts/
│   ├── train.py
│   ├── evaluate.py
│   └── inference.py
│
├── examples/
│
├── assets/
│
└── docs/
    ├── DATASETS.md
    ├── TRAINING.md
    ├── EVALUATION.md
    ├── MODEL_CARD.md
    └── REPRODUCIBILITY.md
```

The exact structure may change before the final public release.

---

## Processed Dataset

The processed dataset used in the MA-LoRA experiments is **not currently distributed** while the associated manuscript is under review.

After acceptance/publication, the project will publish the processed dataset through a **Google Drive link** announced in this repository. The release is intended to include, where licensing and redistribution conditions permit:

- the processed face, hand, and body data used by the reported experiments,
- the final sample organization and modality-availability structure,
- label and class information required to reproduce the reported tasks,
- train/validation/test split information where it can be shared,
- preprocessing metadata and preparation documentation,
- integrity information or checksums where appropriate.

Third-party source datasets remain governed by their original licenses and terms of use. If any underlying resource cannot legally be redistributed, the public processed-data package will exclude the restricted material and provide the corresponding preparation metadata, source references, and reconstruction instructions instead.

The Google Drive URL will be added to this README when the public release is made.

---


## Pretrained Weights

Pretrained MA-LoRA weights are **not currently distributed** while the associated manuscript is under review.

After acceptance/publication, subject to the applicable licensing and redistribution conditions, the project will publish the trained MA-LoRA weights through a **Google Drive link** announced in this repository. The release is intended to include:

- the checkpoint corresponding to the reported model,
- model configuration,
- checkpoint metadata,
- class definitions,
- preprocessing information,
- integrity checksums,
- loading instructions.

The Google Drive URL will be added to this README when the public release is made.

A permanent archived version may also be provided later for long-term reproducibility and citation.

---

## Inference

Public inference code will be included after publication.

The final interface is intended to support both complete and incomplete modality inputs, for example:

```text
Face + Hand + Body
Face + Hand
Face + Body
Hand + Body
Face only
Hand only
Body only
```

Example scripts and sample command-line usage will be added with the public implementation.

---

## Training

Training code and exact experimental settings are temporarily withheld during peer review.

After acceptance, the release is intended to document:

- model initialization,
- preprocessing,
- optimization,
- training configuration,
- parameter-efficient adaptation settings,
- multimodal sampling,
- missing-modality training,
- checkpoint selection,
- random seeds,
- hardware information,
- evaluation schedule.

Where possible, configuration files will be provided so that experimental settings do not need to be reconstructed manually from the paper.

---

## Evaluation

The final release will include scripts for evaluating MA-LoRA under different modality-availability conditions.

The evaluation package is intended to cover relevant metrics for the two prediction tasks, including classification, imbalance-aware, ordinal, and calibration-oriented measures where applicable.

Exact metrics, evaluation procedures, and numerical results are withheld until completion of the publication process.

The public release will map the evaluation commands to the corresponding experiments reported in the accepted manuscript.

---

## Reproducibility

Reproducibility is a planned part of the final release.

Following publication, the repository is intended to provide a dedicated guide:

```text
docs/REPRODUCIBILITY.md
```

It will document, where redistribution permissions allow:

- environment creation,
- dataset preparation,
- preprocessing,
- configuration files,
- model initialization,
- training commands,
- evaluation commands,
- modality-mask evaluation,
- checkpoint loading,
- random seeds,
- result generation,
- correspondence between repository experiments and paper tables/figures.

A versioned release will identify the exact source-code state associated with the published manuscript.

---

## Experimental Results

Detailed numerical results are intentionally not included in this public README while the manuscript is in the submission/review phase.

This includes unpublished:

- performance values,
- ablation results,
- external-validation results,
- statistical comparisons,
- efficiency measurements,
- sensitivity analyses,
- checkpoint-selection results.

These results will be added or linked after publication of the paper.

---

## Responsible Use

MA-LoRA is a research project involving visual soft-biometric attributes.

Apparent attributes inferred from images should not automatically be interpreted as objective demographic or biological ground truth.

Predictions may be influenced by:

- dataset composition,
- visual conditions,
- annotation conventions,
- demographic imbalance,
- domain shift,
- image quality,
- occlusion,
- modality availability.

The system is intended primarily for research into multimodal learning, parameter-efficient adaptation, missing-modality inference, and soft biometrics.

It should not be used as the sole basis for decisions that have legal, medical, employment, financial, surveillance, or other high-impact consequences for individuals.

A more complete model card and limitations statement will accompany the model release.

---

## Limitations

The project studies a constrained research formulation and should not be interpreted as a universal model of human age or gender.

Important limitations include the dependence on:

- available training data,
- annotation definitions,
- visual domain,
- modality quality,
- dataset demographics,
- acquisition conditions,
- external-domain differences.

The accepted paper and final model card will provide a more detailed discussion of limitations and the interpretation of the predictions.

---


## Citation

A `CITATION.cff` file will be maintained in this repository.

Until the corresponding paper receives a public bibliographic record, citation metadata should be considered provisional.

After publication, users of the code or model will be encouraged to cite both:

1. the associated research paper, and
2. the archived software/model release when applicable.

---

## Release Plan

The project currently follows approximately this release sequence:

```text
Phase 1
Public repository and project documentation
        ↓
Phase 2
Paper acceptance/publication
        ↓
Phase 3
Sanitized source-code release
        ↓
Phase 4
Configuration and evaluation release
        ↓
Phase 5
Processed dataset release via Google Drive, subject to redistribution conditions
        ↓
Phase 6
Pretrained MA-LoRA weights release via Google Drive
        ↓
Phase 7
Versioned reproducibility release
        ↓
Phase 8
Permanent archival record / DOI when available
```

The exact release schedule may depend on publication, licensing, and dataset restrictions.

---

## License

Unless otherwise stated, the source code released through this repository is intended to be distributed under the:

**Apache License 2.0**

See:

```text
LICENSE
```

for the complete license text.

### Model weights

Model weights may be distributed under separate terms.

The applicable model-weight license will be stated explicitly when checkpoints are released.

### Datasets

Third-party datasets are not covered by the MALoRAVision software license.

Each dataset remains subject to the license and usage terms established by its original provider. The processed MA-LoRA dataset will be released through Google Drive after acceptance/publication to the extent permitted by those terms. Restricted third-party content will not be redistributed when its original license prohibits redistribution.

---

## Frequently Asked Questions

### Is the full MA-LoRA code available?

Not yet.

The associated paper is currently in the submission/review phase. The implementation will be released after the publication process reaches an appropriate stage.

### Are pretrained weights available?

Not yet.

The weights will be released after acceptance/publication through a Google Drive link announced in this repository, subject to applicable licensing and redistribution requirements.

### Why are some technical details omitted?

Some methodological and experimental details correspond to unpublished research currently undergoing peer review.

The repository intentionally avoids disclosing sensitive or incomplete information before publication.

### Will the repository reproduce the published results?

That is the objective of the final public release.

The repository is intended to include the configuration, evaluation procedure, and versioned implementation associated with the accepted manuscript.

### Will the datasets be uploaded to GitHub?

No.

The processed dataset used by MA-LoRA will be published after acceptance/publication through a **Google Drive link** announced in this repository. Third-party source data will only be included where redistribution is permitted by the original licenses. For restricted resources, the release will provide source references, processing metadata, and reconstruction instructions rather than redistributing prohibited content.

### Does MA-LoRA require all three modalities?

No.

A central objective of the work is to support prediction when only a subset of face, hand, and body modalities is available.

### Can I use MA-LoRA commercially?

The source-code license and model-weight license must be considered separately.

The Apache-2.0 license applies only to materials explicitly released under it. Future model weights and third-party resources may have different conditions.

---

## Updates

Major public-release milestones will be announced through repository releases and updates to this README.

Expected future additions include:

- [ ] Public paper information
- [ ] Complete source code
- [ ] Environment specification
- [ ] Training configuration
- [ ] Evaluation scripts
- [ ] Inference examples
- [ ] Processed dataset (Google Drive)
- [ ] Pretrained weights (Google Drive)
- [ ] Model card
- [ ] Dataset preparation guide
- [ ] Reproducibility guide
- [ ] Paper-to-code experiment mapping
- [ ] Final citation metadata
- [ ] Versioned paper release
- [ ] Archival DOI, if available

---

## Disclaimer

This repository represents an active academic research project.

Until the associated paper is formally published, documentation, APIs, file organization, model specifications, and release plans may change.

The final archived release associated with the publication should be considered the authoritative version for scientific reproduction.
