# Twitter-NLP-Sentiment

### Overview

My project submission seeks to provide sentiment analysis for Google and Apple producs using 9,000 Twitter Tweets. In order to successfully do so I will build and iterate on Random Forest and Gaussian Naive Bayes classifiers.

### Business And Data Understanding

My stakeholders for this project are Google and Apple. The dataset I will be using for this analysis contains Tweet data sourced from CrowdFlower via data.world. This dataset contains a total of 9,000 Tweets manually classified as containing Positive sentiment, Negative sentiment, or neither. 

I started my data exploration by looking at the dataset's features. There were two features: "Emotion in Tweet is Directed at" and the actual "Tweet Text", and the target: "Is There an Emotion Directed at a Brand or Product".

First I sought to understand how the features related to the target. I found that "Emotion in Tweet is Directed at" consisted of various Google versus Apple product categorizations, as well as many null values (over 6,000). Taking a closer look at these nulls, I found that there were cases of both Positive and Negative target values, however the sentiment was not directed at a particular brand or product. As such, I decided to exclude these values as they were not necessarily relevant to either brand. I wanted to start with a binary baseline model, and so I excluded any rows that were not classified as either "Positive emotion" or "Negative  emotion".

### Data Pre-Processing

I took the following data cleaning steps to prepare for modeling:
- Lower-cased all words
- Removed numbers and special characters
- Tokenized each Tweet

I also took a look at word frequency distributions to get a sense for which words were most common for each type of sentiment. Not surprisingly, there were many stopwords common for each (which I would later address) but I decided to fit my baseline model on the dataset with stopwords in order to see how laterr removing them would improve model performance.

### Modeling Approach

I split the dataset into Train and Test sets, then proceeded vectorize the training data. From there I used a Random Forest Classifier and cross-validated accuracy scores on the training dataset. It produced a mean accuracy of 83%, but this was misleading due to the heavy class imbalance.

From there I continued to iterate my modeling approach by:
- Removing stopwords
- Addressing class imbalance
- Incorporating Bigrams
- Incorporating neutral sentiment
- Incorporating product-specific sentiment

### Modeling Results

* Baseline binary RFC: 
* Binary RFC - stopwords removed: 
* Binary RFC - stopwords removed and stemmed:
* Binary Gaussian NB - random oversampling:
* Binary Gaussian NB - bigrams:
* Multi-class Gaussian NB: 
* Multi-class product-specific Gaussian NB:
* Multi-class product-specific Gaussian NB 4-gram:


### Conclusion



## Repository Structure
```
├── README.md                           <- The top-level README for reviewers of this project
├── Twitter-NLLP.ipynb                  <- Narrative documentation of analysis in Jupyter notebook
├── Presentation.pdf                    <- PDF version of project presentation
```