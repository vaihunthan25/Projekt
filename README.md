# Projektarbeit
Name: Vaihunthan Vyramuthu

Matrikelnummer: 87761

## About

Extraction of an entity-relationship model from a text using natural language processing

## General info

Because of easier iterative testing & better visualization mainly jupyter notebooks are used through this project 

## Rule based approach

1. Preprocessing
    - Text cleaning
    - Fault correction (levenshtein distance) --> optional
2. Structuring
    - Generate Subject-Predicate-Object tuples
    - Text Summarization (with term frequency-normalized) --> optional
    - Extract keywords (with tf-idf) --> optional
3. Analysis
    - Extraction of primary keys
    - Extraction of attributes
    - Extraction of ISA-Relation --> optional (limitations)
    - Extraction of entities
    - Extraction of relations
    - Extraction of cardinalities
4. Transformation
    - Generate .json output (to feed it into ER-Modeling Tool from Simon Ruttmann)

## Model based approach

- contains two different models:
- train own transformer model with spacy
- train own LSTM model with keras
- both are trained with self annotated text data

## Main workflow/idea

1. unstructured text data into .txt file (directory: examples)
2. get results from rule based approach (input.txt --> de_rule_based.ipynb --> output.json)
3. load the output.json into ER-Modeling-Tool
4. compare it with the results from the model based approach (de_model_based_keras.ipynb or de_model_based_spacy.ipynb)


It is better to use the results from the model as a comparison:
- model has to be trained with a lot of data the be better than the rule based approach
- at the latest when we want to enter the model extracted data in the output.json, similar rules must be applied. Therefore it would be redundant to put the results into the output.json
- nevertheless the self-trained model with spacy shows good performance (view confusion matrix)

## Files

- directory "examples"

In this folder the unstructured raw text data are saved as .txt files.

- directory "model_based":

This dir contains all relevant files for the two model based approaches with keras and spacy. It contains also the annotated data in json format. The following annotation tool was used to create training data: https://tecoholic.github.io/ner-annotator/  

- directory "pictures":

This directory saves pictures which are used in the jupyter notebooks

- directory "rule_based":

In this folder the main de_rule_based.ipynb is saved. The corresponding output files from this notebook are also saved in this directory

- file "preprocessedData.json":

This .json contains each step of preprocessing 

- file "collection.json":

This .json contains all unstructured raw text data. It is used as a document collection to calculate the tf-idf (term frequency- inverted document frequency)

- file "output.json":

This file can be uploaded into ER-Modeling-Tool to get the extracted ER-Model from unstructured text with nlp techniques




