# wikipedia-reversion

ACCeSs Lab Project of Q Angos and Kenneth Tan


## OVERVIEW

This mini-project explores whether machine learning can predict if a Wikipedia edit will be reverted. Wikipedia is an open collaborative platform where anyone can contribute edits, but many edits are later reverted due to vandalism, misinformation, or low-quality changes. By analyzing historical edit data from Wikipedia revision history datasets, this project will build a predictive model that estimates the probability that a new edit will be reverted. The system will use features derived from edit metadata, user characteristics, and textual changes between revisions.

## GOALS

- Predict whether an edit on Wikipedia would be reverted.

## PLAN

### Input

A subset of Wikipedia revision history obtained from the MediaWiki History dataset. The dataset will contain information about edits including page identifiers, timestamps, editor information, edit size, and whether the revision was later reverted..

## Phase 1 – Baseline Dataset and Model (Easy)

The first phase focuses on building a working baseline system.

#### Steps:

- Download a small subset of the Wikipedia revision dataset.

- Parse revision records and extract sequential edits for each page.

- Extract simple metadata features such as:

    - edit size (bytes added or removed)

    - whether the editor is anonymous

    - timestamp of the edit.

- Label each edit using the revision_is_reverted field.

- Train a baseline classification model (such as Logistic Regression).

- Evaluate model performance using accuracy and ROC-AUC.

#### Outcome:

 A working pipeline that loads the dataset, extracts features, trains a model, and predicts whether edits are reverted.

## Phase 2 – Improved Features and Model (Medium)

The second phase improves predictive performance through richer features.

#### Steps:

- Add behavioral and contextual features including:

    - editor experience (number of prior edits or account age)
    
    - historical revert rate of the page
    
    - time-of-day of edits.

- Compare multiple models such as Random Forest, XGBoost, or Gradient Boosting.

- Evaluate performance improvements using precision, recall, and ROC-AUC.

- Identify the most important predictive features.

#### Outcome:

 A more accurate model that incorporates user behavior and page-level patterns.

## Phase 3 – Text Similarity and Advanced Features (Hard)

The final phase incorporates textual analysis of edits.

#### Steps:

- Compute similarity between the previous revision text and the new revision text using TF-IDF or embedding similarity.

- Derive semantic change features such as edit similarity collapse.

- Integrate these features into the prediction model.

- Analyze whether text-based features significantly improve prediction accuracy.

#### Outcome:

An advanced revert prediction model that combines metadata, behavioral features, and textual change analysis.

#### Output

The final deliverables will include:

- scripts for dataset parsing and feature extraction

- trained machine learning models

- evaluation results and performance metrics

- visualizations of feature importance and model accuracy

- example predictions demonstrating the probability that new edits will be reverted.

#### Success Criteria

- The scene is recognizable and stable from multiple viewpoints

- Real-time rendering is smooth enough for interactive exploration

- Clear documentation of steps, tools used, and limitations

## MILESTONES

### Easy

- Download a subset of the Wikipedia revision dataset and parse edits.

- Extract basic features such as edit size, anonymous user status, and edit timestamp.

- Train a baseline classification model and report initial accuracy.

### Medium

Add more advanced features such as:

- editor experience

- page revert rate

- similarity between revisions

- Train and compare multiple models and evaluate performance.

### Hard

Implement text-based semantic features using TF-IDF or sentence embeddings.

## Feasibility to be Assessed

- Predict the likelihood of reverts within a specific time window (e.g., within 24 hours).

- Explore whether models can distinguish between vandalism and legitimate edit disputes.
