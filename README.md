# SOEN 471

## PROJECT SUMMARY

### Project definition and introduction

The main aim of this project is to create a Spark-based pipeline for anonymizing patient data, and ensuring that privacy and data protection laws are followed due to the sensitive nature of the information.

Furthermore, our objective extends to building a ML model that will look through our dataset and check if any names or otherwise identifying information were inadvertently inserted into the report from the radiologist (eg., in the wrong entry). This process is intended to further robustness regarding anonymity.

## Model Design

### Dataset

Our dataset consists of two different types of data, the generated reports and the MRI Dicom image. The former has the following seven features: age, location, ethnicity, study date, PSA (Prostate-specific antigen) - a protein used for screening prostate cancer, PI-RAD score - a score indicating how likely an area is cancerous, and MR Model & Brand. Finally, it contains an outcome (is it a tumour) (low, moderate and high). 

The latter contains the MRI of the prostate, and patient metadata: name, sex, age, weight (kg), study date and time, study modality, study description, series date and time and series description and other metadata (around 100) that covers other information such as: manufacturer, software version and so on.

### Research Question

In our project, we will be aiming to answer the question: given a file generated by a radiologist, can we verify that no identifying information has slipped into the report? In other words, create a natural language processing (NLP) model that predicts whether input text is anonymized or not.

### Class of models

Here, we will be using classification models. More precisely, Named Entity Recognition (NER), a component of Natural Language Processing, will be used to tokenize words and classify them into two relevant groups (identifying: “name, location etc. '' or non-identifying). Two open source and free libraries will be used and compared : spaCy and Natural Language Toolkit (NLTK).

Evaluation Method

To measure our models accuracy at labelling words, we can use precision, recall and f1 score regarding the labelling of the text output. This will be useful since the dataset will likely contain a huge class imbalance (more non-identifying than identifying), highlighting the importance of f1. The score of both these models will be compared

### Algorithms

Both spaCy and Natural Language Toolkit (NLTK) are libraries that implement NER. First this algorithm pre-processes the textual data. This works by tokenizing the words (breaking down sentences into smaller chunks like words) and labelling these words (parts-of-speech tagging). 

Next, features are extracted from these tags (such as the words itself, its grammatical label etc.): 

Then, a model is trained on these features and learns to predict these labels.

[1] Radiological Society of North America (RSNA) and American College of Radiology (ACR), “How to read your prostate MRI report,” Radiologyinfo.org, https://www.radiologyinfo.org/en/info/article-prostate-mri-report#:~:text=Radiologists%20use%20the%20Prostate%20Imaging,to%205%20. (accessed Mar. 13, 2024).

# 

# Appendix

Image 1 - Data Pipeline

![img](https://lh7-us.googleusercontent.com/kzRFjtqYs8MaoMNBb0tlCKc-qUuYeySLdrC16GsItXD-7woPez3o7xMHESsCtHIFLe8j8gZ_Yu-82VPoUzL8jiZyp6GyLH3AYZzhWCUUf8YNEWxt-j8bP5cvuRJAfkEicV2RcEwD6WIH0r4RXOfzVAs)

### Image 2 - Radiologist suggestion

![img](https://lh7-us.googleusercontent.com/ZT62uJj-jk07CfI76BA2toqRsMMx95BAWUYJgHd_NvpI5IUGw9Cp00hnN_i-GIzTfQo5J2noi8Nkzbn4epaLCKn25UW3_MktcTk72GUW59JmdLN90lyUro27NuuXgB7qfnETfhT8cWnMbuQ-Kqdy7Qo)
