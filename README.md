# CLPSYCH
CLPSYCH Shared Task for Automatic Triage of Posts from a Mental Health Forum

This repository contains three separate programs for classification of posts from a mental health forum to four possible categories: green, amber, red and crisis. Each model type required slightly different package requirements and could therefore not be compiled into one single program. The portion of the notebook that imports and processes the data is the same in all three files. Data preprocessing involves deriving non-text features from the metadata and cleaning the xml posts. In the end, the result is three separate training texts. One is the raw text as received from ReachOut.com, the second is fixed text which has HTML tags removed, and the third is fixed text + features, where non-text features have been added to the fixed text. Below is a description of the models applied in each notebook, after the data importing and processing code.

**-clpsych.ipynb: **This notebook contains the code for the four base models (random, majority, and XGBoost and logistic regression, the later two both using non-text features only). This notebook contains the fine-tuned BERT model on the raw, fixed and fixed + features text using training and validation datasets. This code also applies the final fine-tuned BERT model to the testing dataset and creates a confusion matrix of results.

**-clpsych_nn.ipynb:** This notebook fine-tunes all the hyperparameters for the neural network models on the training and validation datasets.

**-cplsych4.ipynb:** This notebook applies RoBERTa and four separate binary BERT models to the fixed text and evaluates performance using the training and validation datasets.

