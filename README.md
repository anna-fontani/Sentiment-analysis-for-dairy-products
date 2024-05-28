# Sentiment analysis for dairy products

Sentiment analysis based on social network opinions extracted for specific keywords. 

To explore consumers’ perception of Irish dairy products, we will try to answer following questions: 

-	What do consumers in Ireland think of dairy products?
-	Can we define text sentiment with high accuracy?
-	Which dairy products are most discussed in social media? 

In this code I will use a .csv file with preliminary extracted posts and comments. 

Dataframe was built based on extracted texts for following keywords: dairy, milk, butter, yoghurt, cream, cheese, buttermilk, and ice cream. 

Extracted 30.582 unique comments were stored in a dataframe with text, keyword, and creation time features. 

To prepare text for machine learning sentiment analysis, data was processed: meaningless words, punctuation marks, duplicate entries, and stopwords were removed. 

Since extracted data did not contain any labels to feed to machine learning algorithms, TextBlob was applied to determine sentiment polarity in range [-1,1] where -1 denotes a highly negative sentiment and 1 denotes a highly positive sentiment (Arora, 2024). Polarity values were then encoded into 0 (negative) and 1 (positive) labels to proceed with machine learning. 

Labels ration in data: 
- Positive: 38.08%
- Negative: 61.91%
 
The dataframe appeared not perfectly balanced, and this type of imbalance can be called marginally unbalanced (Weiss, 2013). It would be practical to fit models on imbalanced data and consider differences in model performance for labels.

## Bag of Words
Since computers do not perceive text as it is, we need approach to feed it to machine learning algorithms. According to Müller and Guido (2014), bag of words text representation is one of the easiest but still effective approaches to represent text for machine learning.

The grammar and the order of words in a sentence are not given any importance, instead, multiplicity is the main point of concern. The bag of words describes the total occurrence of words within a document (Arora, 2024). In Python, bag of words can be implemented using CountVectorzer tool from sklearn library.


# References / Additional Reading
- Arora, S. (2024). Sentiment Analysis Using Python. [online] Analytics Vidhya. Available at: https://www.analyticsvidhya.com/blog/2022/07/sentiment-analysis-using-python/.
- Müller, A.C. and Guido, S. (2014). Introduction To Machine Learning With Python. Third ed. London, England: The MIT Press Cambridge.
- Weiss, G.M. (2013). Foundations of Imbalanced Learning. In: Imbalanced Learning. Wiley, pp.13–41. doi:https://doi.org/10.1002/9781118646106.ch2.
