# Annotated Model Card Template


## Template

[https://github.com/huggingface/huggingface_hub/blob/main/src/huggingface_hub/templates/modelcard_template.md](https://github.com/huggingface/huggingface_hub/blob/main/src/huggingface_hub/templates/modelcard_template.md)


## Directions

Fully filling out a model card requires input from a few different roles. (One person may have more than one role.)  We’ll refer to these roles as the **developer**, who writes the code and runs training; the **sociotechnic**, who is skilled at analyzing the interaction of technology and society long-term (this includes lawyers, ethicists, sociologists, or rights advocates); and the **project organizer**, who understands the overall scope and reach of the model, can roughly fill out each part of the card, and who serves as a contact person for model card updates.

* The **developer** is necessary for filling out [Training Procedure](#training-procedure) and [Technical Specifications](#technical-specifications). They are also particularly useful for the “Limitations” section of [Bias, Risks, and Limitations](#bias-risks-andlimitations). They are responsible for providing [Results](#results) for the Evaluation, and ideally work with the other roles to define the rest of the Evaluation: [Testing Data, Factors & Metrics](#testing-data-factors-and-metrics).

* The **sociotechnic** is necessary for filling out “Bias” and “Risks” within [Bias, Risks, and Limitations](#bias-risks-and-limitations), and particularly useful for “Out of Scope Use” within [Uses](#uses).

* The **project organizer** is necessary for filling out [Model Details](#model-details) and [Uses](#uses). They might also fill out
[Training Data](#training-data). Project organizers could also be in charge of [Citation](#citation), [Glossary](#glossary), 
[Model Card Contact](#model-card-contact), [Model Card Authors](#model-card-authors), and [More Information](#more-information).

_Instructions are provided below, in italics._

# Model Name

_Provide a 1-2 sentence summary of what the model is. Important disclaimers may go here as well._

# Model Details

**Section Overview:** This section provides basic information about what the model is, its current status, and where it came from. It should be useful for anyone who wants to reference the model.


## Model Description


{{ model_description | default("", true) }}

_Provide basic details about the model. This includes the architecture, version, if it was introduced in a paper, if an original implementation is available, and the creators. Any copyright should be attributed here. General information about training procedures, parameters, and important disclaimers can also be mentioned in this section._


* **Developed by:** {{ developers | default("[More Information Needed]", true)}}

_List (and ideally link to) the people who built the model._



* **Shared by [optional]:** {{ shared_by | default("[More Information Needed]", true)}}

_List (and ideally link to) the people/organization making the model available online._



* **Model type:** {{ model_type | default("[More Information Needed]", true)}}

_You can name the “type” as:_

_1. Supervision/Learning Method_

_2. Machine Learning Type_

_3. Modality_

* **Language(s)** [NLP]: {{ language | default("[More Information Needed]", true)}}

_Use this field when the system is a natural language processing system._



* **License:** {{ license | default("[More Information Needed]", true)}}

_Name, and link to, the license being used._



* **Finetuned From Model [optional]:** {{ finetuned_from | default("[More Information Needed]", true)}}

_If this model has another model as its base, link to that model here._


## Model Sources [optional]

_Provide sources for the user to directly see the model and its details. Additional kinds of resources – training logs, lessons learned, etc. – belong in the [More Information](#more-information) section. If you include one thing for this section, link to the repository._

* **Repository:** {{ repo | default("[More Information Needed]", true)}}
* **Paper [optional]:** {{ paper | default("[More Information Needed]", true)}}
* **Demo [optional]:** {{ demo | default("[More Information Needed]", true)}}


# Uses
**Section Overview:** This section addresses questions around how the model is intended to be used, discusses the foreseeable users of the model (including those affected by the model), and describes uses that are considered out of scope or misuse of the model.  Note this section is not intended to include the license usage details. For that, link directly to the license.


## Direct Use


{{ direct_use | default("[More Information Needed]", true)}}

_List how the model can be used without fine-tuning, post-processing, or plugging into a pipeline._


## Downstream Use [optional]

{{ downstream_use | default("[More Information Needed]", true)}}

_List how this model can be used when fine-tuned for a task, or when plugged into a larger ecosystem or app._


## Out-of-Scope Use

_List how the model may foreseeably be misused and address what users ought not do with the model._


{{ out_of_scope_use | default("[More Information Needed]", true)}}



# Bias, Risks, and Limitations

**Section Overview:** This section identifies foreseeable harms and misunderstandings, and both technical and sociotechnical limitations.

{{ bias_risks_limitations | default("[More Information Needed]", true)}}


_What are the known or foreseeable issues stemming from this model?_


## Recommendations

**Section Overview:** This section provides information on warnings and potential mitigations.


{{ bias_recommendations | default("Users (both direct and downstream) should be made aware of the risks, biases and limitations of the model. More information needed for further recommendations.", true)}}

_What are recommendations with respect to the foreseeable issues? This can include everything from “downsample your image” to filtering explicit content._


# Training Details

**Section Overview:** This section provides information to describe and replicate training, including the training data, the speed and size of training elements, and the environmental impact of training. This relates heavily to the [Technical Specifications](#technical-specifications) as well, and content here should link to that section when it is relevant to the training procedure.  It is useful for people who want to learn more about the model inputs and training footprint.
It is relevant for anyone who wants to know the basics of what the model is learning.

## Training Data


{{ training_data | default("[More Information Needed]", true)}}

_Write 1-2 sentences on what the training data is. Ideally this links to a Dataset Card for further information. Links to documentation related to data pre-processing or additional filtering may go here as well as in [More Information](#more-information)._
 

## Training Procedure [optional]


### Preprocessing


{{ preprocessing | default("[More Information Needed]", true)}}


### Speeds, Sizes, Times


{{ speeds_sizes_times | default("[More Information Needed]", true)}}

_Detail throughput, start/end time, checkpoint sizes, etc._


# Evaluation

**Section Overview:** This section describes the evaluation protocols, what is being measured in the evaluation, and provides the results.  Evaluation is ideally constructed with factors, such as domain and demographic subgroup, and metrics, such as accuracy, which are prioritized in light of foreseeable error contexts and groups. Target fairness metrics should be decided based on which errors are more likely to be problematic in light of the model use. 


## Testing Data, Factors & Metrics

### Testing Data

{{ testing_data | default("[More Information Needed]", true)}}

_Ideally this links to a Dataset Card for the testing data._

### Factors

{{ testing_factors | default("[More Information Needed]", true)}}

_What are the foreseeable characteristics that will influence how the model behaves? This includes domain and context, as well as population subgroups. Evaluation should ideally be **disaggregated** across factors._

### Metrics

{{ testing_metrics | default("[More Information Needed]", true)}}

_What metrics will be used for evaluation in light of tradeoffs between different errors?_

## Results

{{ results | default("[More Information Needed]", true)}}


_Results should be based on the Factors and Metrics defined above._

### Summary

_What do the results say? This can function as a kind of tl;dr for general audiences._

# Model Examination [optional]

**Section Overview:** This is an experimental section some developers are beginning to add, where work on explainability/interpretability may go.

{{ model_examination | default("[More Information Needed]", true)}}


# Environmental Impact

* **Hardware Type:** {{ hardware | default("[More Information Needed]", true)}}
* **Hours used:** {{ hours_used | default("[More Information Needed]", true)}}
* **Cloud Provider:** {{ cloud_provider | default("[More Information Needed]", true)}}
* **Compute Region:** {{ cloud_region | default("[More Information Needed]", true)}}
* **Carbon Emitted:** {{ co2_emitted | default("[More Information Needed]", true)}}

_Carbon emissions can be estimated using the [Machine Learning Impact calculator](https://mlco2.github.io/impact#compute) presented in [Lacoste et al. (2019)](https://arxiv.org/abs/1910.09700)._


# Technical Specifications [optional]


**Section Overview:** This section includes details about the model objective and architecture, and the compute infrastructure. It is useful for people interested in model development. Writing this section usually requires the model developer to be directly involved.


## Model Architecture and Objective

{{ model_specs | default("[More Information Needed]", true)}}

## Compute Infrastructure

{{ compute_infrastructure | default("[More Information Needed]", true)}}

### Hardware

{{ hardware | default("[More Information Needed]", true)}}

### Software

{{ software | default("[More Information Needed]", true)}}


# Citation [optional]


**Section Overview:** The developers’ preferred citation for this model. This is often a paper.


### BibTeX 

{{ citation_bibtex | default("[More Information Needed]", true)}}


### APA 

{{ citation_apa | default("[More Information Needed]", true)}}


# Glossary [optional]


**Section Overview:** This section defines common terms and how metrics are calculated.


{{ glossary | default("[More Information Needed]", true)}}

_Clearly define terms in order to be accessible across audiences._

# More Information [optional]


**Section Overview:** This section provides links to writing on dataset creation, technical specifications, lessons learned, and initial results.


{{ more_information | default("[More Information Needed]", true)}}


# Model Card Authors [optional]


**Section Overview:** This section lists the people who create the model card, providing recognition and accountability for the detailed work that goes into its construction.

{{ model_card_authors | default("[More Information Needed]", true)}}



# Model Card Contact


**Section Overview:** Provides a way for people who have updates to the Model Card, suggestions, or questions, to contact the Model Card authors

{{ model_card_contact | default("[More Information Needed]", true)}}


# How to Get Started with the Model


**Section Overview:** Provides a code snippet to show how to use the model.