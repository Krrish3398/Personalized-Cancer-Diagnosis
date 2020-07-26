# Personalized-Cancer-Diagnosis

# Business Problem

Description
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/

Data: Memorial Sloan Kettering Cancer Center (MSKCC)

Download training_variants.zip and training_text.zip from Kaggle.

Context:
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/discussion/35336#198462

# Problem statement :
Classify the given genetic variations/mutations based on evidence from text-based clinical literature.

Source/Useful Links
Some articles and reference blogs about the problem statement

https://www.forbes.com/sites/matthewherper/2017/06/03/a-new-cancer-drug-helped-almost-everyone-who-took-it-almost-heres-what-it-teaches-us/#2a44ee2f6b25

https://www.youtube.com/watch?v=UwbuW7oK8rk

https://www.youtube.com/watch?v=qxXRKVompI8

# Real-world/Business objectives and constraints.

*No low-latency requirement.
*Interpretability is important.
*Errors can be very costly.
*Probability of a data-point belonging to each class is needed.

# Machine Learning Problem Formulation

Data Overview

Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data
We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.
Both these data files are have a common column called ID
Data file's information:

training_variants (ID , Gene, Variations, Class)
training_text (ID, Text)
2.1.2. Example Data Point
training_variants
ID,Gene,Variation,Class
0,FAM58A,Truncating Mutations,1
1,CBL,W802*,2
2,CBL,Q249E,2
...
training_text
ID,Text
0||Cyclin-dependent kinases (CDKs) regulate a variety of fundamental cellular processes. CDK10 stands out as one of the last orphan CDKs for which no activating cyclin has been identified and no kinase activity revealed. Previous work has shown that CDK10 silencing increases ETS2 (v-ets erythroblastosis virus E26 oncogene homolog 2)-driven activation of the MAPK pathway, which confers tamoxifen resistance to breast cancer cells. The precise mechanisms by which CDK10 modulates ETS2 activity, and more generally the functions of CDK10, remain elusive. Here we demonstrate that CDK10 is a cyclin-dependent kinase by identifying cyclin M as an activating cyclin....

# Mapping the real-world problem to an ML problem

Type of Machine Learning Problem
There are nine different classes a genetic mutation can be classified into => Multi class classification problem


# Performance Metric
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment#evaluation

# Metric(s):

Multi class log-loss
Confusion matrix

Machine Learing Objectives and Constraints
Objective: Predict the probability of each data-point belonging to each of the nine classes.

# Constraints:

1.Interpretability.

2.Class probabilities are needed.

3.Penalize the errors in class probabilites => Metric is Log-loss.

4.No Latency constraints.

# Results
![alt text](https://github.com/Krrish3398/Personalized-Cancer-Diagnosis/blob/master/Result.png)



 From the above table Logistic Regresion(using tfidf vectorizer) gives better results (Log-Loss = 0.97 for test) and the percentage of missclassified points = 34%.
 LR with countvectorizer also gave test log loss=0.98
