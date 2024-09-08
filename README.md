# Introduction
This repository contains the data and code associated with the manuscript [Metastatic vs. Localized Disease As Inclusion Criteria That Can Be Automatically Extracted From Randomized Controlled Trials Using Natural Language Processing](https://www.medrxiv.org/content/10.1101/2024.06.17.24309020v1) which is currently available as a preprint while undergoing peer review.
The config file can be used to train a model using the spacy/prodigy packages. 

# Data


Each trial is a row in the csv file. For each trial there are the follwing columns:
- __doi__: Digital Object Identifier of the trial
- __date__: Publication data according to PubMed
- __title__: Title of the trial according to PubMed
- __abstract__: The abstract of the trial
- __abstract_introduction__: The introduction section of the abstract. Parsed from the PubMed abstract using regular expressions.
- __abstract_methods__: The methods section of the abstract. Parsed from the PubMed abstract using regular expressions. Note that sometimes this section might have a different name in the journal itself (e.g. "design, setting, and participants").
- __abstract_results__: The results section of the abstract. Parsed from the PubMed abstract using regular expressions.
- __abstract_conclusions__: The conclusion section of the abstract. Parsed from the PubMed abstract using regular expressions.
- __text__: The text that was displayed to the annotator.
- __accept__: Contains "accept" if an annotator annotated the trial.
- __answer__: The labels that the annotator assigned. Trials that allowed for the inclusion of patients with localized disease received the label “LOCAL”. Trials that allowed for the inclusion of patients with metastatic disease received the label “METASTATIC”. Trials that allowed for the inclusion of patients with either localized or metastatic disease received bot labels. Screening trials that enrolled patients without known cancer or trials of interventions to prevent cancer were assigned no label.
- __options__: List of labels that the annotator could select
- **_input_hash**, **_task_hash**, **_view_id**, **config**, **_timestamp**, **_annotator_id**, **_session_id**: Additional columns automatically created by the annotation tool during the annotation process. For detailed documentation see the [prodigy docs](https://prodi.gy/docs/api-components).

The dataset has also been uploaded to [Dryad](https://doi.org/10.5061/dryad.g4f4qrfzn).
