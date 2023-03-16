<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 3: Web APIs & NLP

### Overview

Project 3 involves two main objectives. 
- Firstly, the project requires the collection of posts from two chosen subreddits. To accomplish this, the Pushshift API can be used or any other low-code platform. It is also possible to web-scrape or use other low-code platforms such as ParseHub to collect data from different social media platforms such as Twitter, Facebook, Instagram, or Wikipedia.

- Secondly, the project involves training a classifier using Natural Language Processing (NLP) techniques. The classifier is trained to predict which subreddit (or other sub-sections of the site that the data is collected from) a post belongs to. This is a binary classification problem, and the model will be trained to classify posts as belonging to one of the two chosen subreddits.


In this project, we will explore the following two sub reddits:
1) [Retirement](https://www.reddit.com/r/retirement/)
2) [Financial Planning](https://www.reddit.com/r/FinancialPlanning/)

---
### Problem Statement

The goal of this project is to develop a classifier that can accurately distinguish between posts from two subreddits, Retirement and Financial Planning. This is important because although both subreddits deal with personal finance, they have distinct differences in their focus and audience.

Being able to differentiate between the two subreddits can help financial professionals and individuals better tailor their content and advice to the specific needs and interests of their audience.

To achieve this, natural language processing techniques will be used to analyze the content of posts from both subreddits and build a classifier that can accurately identify which subreddit a given post belongs to.

The success of the project will be measured by the accuracy of the classifier in correctly identifying the source subreddit of new posts. The accuracy score is selected as the decision metric as it tells us how often the model correctly predicts the class of a post.  The cost of misclassification is equal across the classes of retirement and financial planning since there are significant overlaps in features, and retirement adequacy is a major component in personal financial planning. A post related to retirement would help provide related information that an individual could consider when embarking on personal financial planning; while posts on financial planning will help those who are interested in retirement source for relevant information to provide better financial independence and peace of mind.

---

### Datasets

Data was obtained from selected posts from the two subreddits (i.e. r/retirement and r/FinancialPlanning).These are:

- Retirement: https://www.reddit.com/r/retirement/
- Financial Planning: https://www.reddit.com/r/FinancialPlanning/

---
### Data Dictionary
|Feature|Type|Description|
|---|---|---|
|subreddit|object| Retirement, Financial Planning|
|selftext|object|Reddit poster's body text|
|title|object|Reddit poster's title text|
|content|object|Reddit poster's selftext+title|

---

### Technical Report

The technical report comprises two main components. This includes:
- Part 1 - Background, Problem Statement and Scrapping of Reddit Data: A total of 2,000 posts per subreddit were scrapped. These were the most recent posts created before 4 Feb 2023 and 8 Mar 2023 for the financial planning and retirement subreddits respectively.
- Part 2 - Cleaning, EDA, Modelling, Key Findings & Recommendations: The cleaning of data, analysis on various features, construction, evaluation and selection of models.

---

### Conclusion and Recommendations

In summary, we note that: 
1) Individuals who are looking for advice on financial planning and retirement could consider using model B (TfidVectorizer with MultinomialNB) to direct their query to the relevant subreddit to glean insights relevant to their interest. This is based on Model B's comparatively higher accuracy score. 

2) On balance, model B is recommended compared to the other models as based on the scores outlined below, the accuracy score for model B is higher than the baseline (model A) and it has the highest test accuracy and compartively lesser overfitting.

|Model|Type|Train Score|Test Score|Overfitting
|---|---|---|---|---|
|Model A| Multinomial Naive Bayes with Count Vectorizer| 0.84| 0.77| 0.07
|Model B| Multinomial Naive Bayes with Tfidf Vectorizer| 0.88| 0.80| 0.08
|Model C| Logistic Regression with Count Vectorizer| 0.93| 0.77| 0.16
|Model D| Logistic Regression with Tfidf Vectorizer| 0.88| 0.79| 0.09
|Model E| Gradient Boost| 0.69| 0.69| 0

3) Model B has limitations and only mediocre performance. It has 230 posts classified incorrectly. 
4) From examining the features from the two subreddits we note that there are significant overlaps. 
5) From examining the tokens of the posts with the lowest predicted probabilities, we note that due to the overlaps in featues this could have caused results to be unclear.
6) For future iterations of the study, we could consider (i) obtaining more data; (ii) consider financial sentiments.

--- 
