# Sentiment analysis of dairy production

Sentiment analysis in this project is based on social network opinions extracted for specific keywords. 

Following tasks were set for this Data Analytics project:
-	Study what do consumers think of dairy produced in Ireland.
- Develop a model to evaluate sentiment polarity.
- Research most discussed products and most common opinions. 

In this code I will use a .csv file with preliminary extracted posts and comments. 

Dataframe is created based on preliminary extracted posts on specific keywords: dairy, cream, buttermilk, milk, ice cream, butter, yoghurt, and cheese. 

Extracted 30k comments were used to build a dataframe containing post text, keyword, and posting time. 

## Data Pre-processing

Meaningless words, punctuation marks, duplicate posts, and stopwords were cleaned. 

Original data did not contain sentiment labels to feed to our ML model. Hence, it was necessary to either add some labels manually, or use a tool to build labels. 
In this porject, TextBlob was implemented to define sentiment polarity [-1,1] where -1 is a highly negative sentiment and 1 is a highly positive sentiment (Arora, 2024). 

## Bag of Words
Müller and Guido (2014) call the bag of words text representation is one of the most common and efficient approaches to represent text for machine learning models.
The bag of words counts occurrence of words in the text (Arora, 2024). In Python, bag of words can be added using CountVectorzer (sklearn library).


# References / Additional Reading
- Arora, S. (2024). Sentiment Analysis Using Python. [online] Analytics Vidhya. Available at: https://www.analyticsvidhya.com/blog/2022/07/sentiment-analysis-using-python/.
- Müller, A.C. and Guido, S. (2014). Introduction To Machine Learning With Python. Third ed. London, England: The MIT Press Cambridge.
- Weiss, G.M. (2013). Foundations of Imbalanced Learning. In: Imbalanced Learning. Wiley, pp.13–41. doi:https://doi.org/10.1002/9781118646106.ch2.
