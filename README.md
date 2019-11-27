# DonorChoose

### Introduction
DonorsChoose.org receives hundreds of thousands of project proposals each year for classroom projects in need of funding. Right now, a large number of volunteers is needed to manually screen each submission before it's approved to be posted on the DonorsChoose.org website.

Next year, DonorsChoose.org expects to receive close to 500,000 project proposals. As a result, there are three main problems they need to solve:

How to scale current manual processes and resources to screen 500,000 projects so that they can be posted as quickly and as efficiently as possible
How to increase the consistency of project vetting across different volunteers to improve the experience for teachers
How to focus volunteer time on the applications that need the most assistance
The goal of the competition is to predict whether or not a DonorsChoose.org project proposal submitted by a teacher will be approved, using the text of project descriptions as well as additional metadata about the project, teacher, and school. DonorsChoose.org can then use this information to identify projects most likely to need further review before approval.




## Final Result:


| S.No |  Model   | Test Loss | Test AUC-ROC |
|----- | -------- | --------- | ------------ |
|  1   | Model- 1 |   0.3942  |    0.7549    |
|  2   | Model- 2 |  0.40941  |    0.7093    |
|  3   | Model- 3 |  0.37105  |    0.7496    |



## Summary

We have built 3 models for above case study.

**Model 1**: 
<br>
For Text features, we used pre-trained GloVe embedding layer.<br>
For Categorical features, we used tokenize categorical features uisng in-built keras Tokenizer.<br>
For numerical features, we standardized using Scikit Learning 'StandardScaler'.

Then flatten all output and concatenate using keras concatenate layer.

Then connect to few dense layer. We used ADAM as optimizer.
<br>
<br>

**Model 2**

Here in this model, for text features, we used 'TFIDF' vectorizer instead of GloVe pretrain model.<br>
Also, we removed those words which had higher IDF and lower IDF values, as most frequent word and most rare words are not important in NLP tasks. So we neglected all those words.

We used the same strategy for "Categoric" and "Numeric" features.

Then flatten all output and concatenate using keras concatenate layer.

Then connect to few dense layer. We used ADAM as optimizer.
<br>
<br>

**Model3**

Here in this model, for text features we used same featurization as we did in model1.
<br>
for categorical features, we used **OneHot encoding** and featurized all features<br>
for numeric features, we used same strategy as used in model1.

Then flatten all output and concatenate using keras concatenate layer.

Then connect to few dense layer. We used ADAMAX as optimizer.
