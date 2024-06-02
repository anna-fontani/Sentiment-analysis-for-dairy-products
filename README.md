# Sentiment analysis of dairy production

Sentiment analysis in this project is based on social network opinions extracted for specific keywords. 

Following tasks were set for this Data Analytics project:
-	Study what consumers think of dairy produced in Ireland.
- Develop a model to evaluate sentiment polarity.
- Research most discussed products, most positive and most negative opinions. 

In this code I will use a .csv file with preliminary extracted posts and comments. 

Dataframe is created based on preliminary extracted posts on specific keywords: dairy, cream, buttermilk, milk, ice cream, butter, yoghurt, and cheese. 

Extracted 30k comments were used to build a dataframe containing post text, keyword, and posting time. 

Data will be cleaned, processed, and prepared for ML application. Further, visualizations and calculations will be made to answer research questions. 

## Data Pre-processing
Meaningless words, punctuation marks, duplicate posts, and stopwords were cleaned. 

Original data did not contain sentiment labels to feed to our ML model. Hence, it was necessary to either add some labels manually, or use a tool to build labels. 
In this porject, TextBlob was implemented to define sentiment polarity [-1,1] where -1 is a highly negative sentiment and 1 is a highly positive sentiment (Arora, 2024). 

## Data Balance
Positive comments:  38.09%
Negative comments:  61.91 %

The dataframe appeared not perfectly balanced, and this type of imbalance can be called marginally unbalanced (Weiss, 2013). It would be practical to fit models on imbalanced data and consider differences in model performance for labels.

## Bag of Words
Müller and Guido (2014) call the bag of words text representation is one of the most common and efficient approaches to represent text for machine learning models.
The bag of words counts occurrence of words in the text (Arora, 2024). In Python, bag of words can be added using CountVectorzer (sklearn library).

## ML

## Confusion Matrix
precision    recall  f1-score   support

           0       0.86      0.91      0.89      5679
           1       0.84      0.76      0.80      3496

    accuracy                           0.86      9175
   macro avg       0.85      0.84      0.84      9175
weighted avg       0.85      0.86      0.85      9175

## Conclusions
To analyze dairy products discussions in Irish social media, over 30k posts and comments were extracted for dairy-specific keywords. Data was explored, cleaned, analyzed, and prepared for ML. Punctuation marks and stopwords were removed from text.
Sentiments polarity feature was added using Text Blob from scikit library. 

Data is not perfectly balanced (38% positive and 62% negative comments), and this issue can be addressed in further research. 

Naive Bayes classifier for multinomial models with 70% / 30% train-test split showed best results with accuracy 0.86, f1-scores 0.89 and 0.80.

It is essential to consider precision, recall and f1-score along with accuracy for imbalanced data (Cohen, 2020). We received rather high values using Naive Bayes classifier for multinomial models with some lower values obtained for “Positive” label which is less represented in the dataframe. 

In terms of practical application, extracted and processed data offers following insights:

-	Butter, cheese, cream, and milk are the top discussed dairy products in social media (Irish segment). 
-	Negative and neutral comments outweigh positive ones.
-	Ice cream, buttermilk and butter have most positive discussions.
-	Longest posts and comments are dedicated to dairy products in general and milk. Shortest comments are shared on cream and cheese.  
-	We can notice that sentiment labels didn’t manage to identify sarcasm and irony, for example, “If you put sugar in your tea, ur disgusting”. These labels could be identified using subjectivity label. 
-	Many comments switched from discussion of dairy products into politics and other topics. Such comments could be cleaned for further research. 



## Further Research

-	Correcting class imbalance using balancing tools such as imbalanced-learn library from scikit-learn.
-	Defining main discussion trends.
-	Extracting specific company names and feedback on their products.
-	Analyzing top polarity comments and posts to extract recommendations for the industry.


# References / Additional Reading
* Raj, 2024. https://www.analyticsvidhya.com/blog/2022/07/sentiment-analysis-using-python/
* Chawla, Nitesh & Japkowicz, Nathalie & Kołcz, Aleksander. (2004). Editorial: Special Issue on Learning from Imbalanced Data Sets. SIGKDD Explorations. 6. 1-6. 10.1145/1007730.1007733. https://www3.nd.edu/~dial/publications/chawla2004editorial.pdf
* Cohen, J. (2020). Machine Learning: Target Feature Label Imbalance Problem and Solutions. [online] Towards Data Science. Available at: https://towardsdatascience.com/machine-learning-target-feature-label-imbalance-problem-and-solutions-98c5ae89ad0.
* Weiss, G.M. (2013). Foundations of Imbalanced Learning. In: Imbalanced Learning. Wiley, pp.13–41. doi:https://doi.org/10.1002/9781118646106.ch2.
* https://github.com/scikit-learn-contrib/imbalanced-learn
* https://towardsdatascience.com/yet-another-twitter-sentiment-analysis-part-1-tackling-class-imbalance-4d7a7f717d44
* https://medium.com/swlh/tweet-sentiment-analysis-using-python-for-complete-beginners-4aeb4456040
* https://www.kaggle.com/code/amarsharma768/sentiment-analysis-of-reddit-data
