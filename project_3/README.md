# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP


### Background
The effects of COVID-19 continue to flow through the world’s health, educational, financial, and commercial institutions, and the global sporting goods industry is no different. In 2020, the sporting goods industry contracted for the first time since the financial crisis of 2007–08, with most brands, retailers, and manufacturers finishing the year significantly in the red, despite a bounce back in activity after the first and before the
 second wave of COVID-19-related lockdowns. 
[(source)](https://www.mckinsey.com/industries/retail/our-insights/sporting-goods-2021-the-next-normal-for-an-industry-in-flux)

Despite slowing economic activity during the pandemic, the pandemic has led to a surge in e-commerce retail and accelerated digital transformation. A report [(source)](https://iprice.sg/trends/insights/report-how-pandemic-affects-southeast-asias-online-shopping-in-2020/?nocache=0) done by iPrice Group, an e-commerce aggregator, reveals that the overall website traffic of online shopping platforms increased positively across all countries year-over-year. Data also showed that online department stores’ web traffic experienced a 52% average increase from Q1 of 2020. 


---

### Problem Statement
With more intense competition from many sporting companies which are moving to e-commerce retail amidst the pandemic, an e-commerce water sporting goods company, which also operates a discussion forum on their website, is looking to improve their sales revenue by staying ahead of the e-commerce competition. To do this, they have engaged our data science team to use Machine Learning to help predict what kinds of sports apparel and equipments these forum users would be interested in (e.g. wetsuit, mask, surf boards) based on their posts in the forum, so that they can offer highly personalized product recommendations to them.


---

### Data Source
The data used for this project was collected through the scraping of subreddit posts via the PushShift API.

A total of 4,000 posts were collected from r/scubadiving and r/surfing, but only data from the 3 columns were kept for analysis. They are 'title', 'selftext' and 'subreddit' category.  


---

### Executive Summary
In the first notebook, 2000 posts will be scraped from each subreddit, r/scubadiving and r/surfing. As we will be focusing on classifying which category a discussion post belong to, we will drop all except for the 'title' of the discussions, 'selftext' which contains the discussions, and the 'subreddit' category that the posts were scraped from. 

In the second notebook, These datasets will then be checked for missing values, removed and deleted 'selftext', and duplicated posts. Missing values in 'selftext', and 'seltext' with '[removed]' and '[deleted]' will be replaced with empty strings, while duplicated posts will be dropped. A new column called 'text' will be created by combining the 'title' and the 'selftext' of a post. Another new column 'diving' with binary values will also be created according to the 'subreddit' column; '1' for r/scubadiving and '0' for surfing.

Preprocessing of the dataset was then done to prepare them for modeling. Preprocessing steps are as follows:
1. Removal of special characters, html tags, hyperlinks and punctuation marks
2. Convert text to lowercase 
3. Lemmatization of words in 'text' with POS tag (Comparisons between Stemming and Lemmatization were made)
4. Removal of stop words
5. Plot barcharts of the most top 20 frequently used unigrams, bigrams and trigrams to identify words that should be added to the stop word list
6. Go back to step 4 

In the 3rd notebook, the dataset that is preprocessed in 2nd notebook will be fitted into classification models such as Logistic Regression, Random Forest Classifier, and KNeighbors Classifier, to train the models on the classification of the subreddit categories. These models are then used to predict which subreddits categories the 'text' from the test dataset belong to. The best model will then be selected to be used on the waster sporting goods company's discussion forum to identify the water sports that people are interested in.

---

### Model Evaluation
| Models                   | Vectorizer      |   Accuracy |   F1-Score |   AUC Score |
|:-------------------------|:----------------|-----------:|-----------:|------------:|
| Logistic Regression      | CountVectorizer |       0.85 |       0.84 |        0.93 |
| Logistic Regression      | TfidfVectorizer |       0.87 |       0.86 |        0.94 |
| Random Forest Classifier | CountVectorizer |       0.8  |       0.81 |        0.89 |
| Random Forest Classifier | TfidfVectorizer |       0.84 |       0.82 |        0.91 |
| KNeighbors Classifier    | CountVectorizer |       0.7  |       0.65 |        0.77 |
| KNeighbors Classifier    | TfidfVectorizer |       0.82 |       0.81 |        0.91 |

Refering to the score table, the model built using the Logistic Regression algorithm and Tfid Vectorizer is the best performing model, since it has the highest accuracy score of 0.87 and AUC score at 0.94. This indicates that the model has a decently good ability to distinguish between whether an observation is from r/scubadiving or r/surfing, and in general, can classify the observations to the right category 87% of the time.

Meantime, KNeighbors Classifier performed the worst. In general, the KNN algorithm does not seem to perform well compared to the other algorithms for balanced data binary classification problems, which is the exact problem we are dealing with in this project. Problem arises when there is an even (>1) number of, say n nearest neighbors and half of n neighbors belong to label 0 and the other half belong to label 1. Then, (n+1)th nearest neighbors have to be found (according to the algorithm) and if the same case arises again, (n+2)th nearest neighbors are found and so on. If this case continues to arise, and in this case, with our balanced data between scubadiving and surfing, at a particular instant, there will be no more samples remaining in the data set and at each nth nearest neighbors consideration, same number of instances of the both the labels are found. Hence, no decision can be taken about the prediction of a test sample, even though after reaching the maximum value of k as per the data set. (source)

We can also see that models built using Tfidf Vectorizer perform better than those using Count Vectorizer. This is understable as count vectorizer gives more importance to the words which occurs more frequently but tfidf vectorizer works in such a way that it will give importance to both sets of words which occur more and less in the dataset.

---

### Conclusion
In order for the water sporting goods company to be able to offer highly personalized product recommendations to forum users, a predictor model that is able to distinguish between the two water sports categories is essential. Hence, we will select the best model based on the highest AUC score, which is the Logistic Regression algorithm and Tfid Vectorizer model, since this score is a measure of a model's separability between two different categories. The higher the AUC score of a model, the better its perfomance in distinguishing different categories. Meanwhile, it is also important to note that this model not only performs better than the rest in terms of its AUC score, but it also has the highest accuracy score.


