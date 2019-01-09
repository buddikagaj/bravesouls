## BraveSouls

Use Natural Language Processing (NLP) to predict Positive and Negative sentiments on customer reviews on amazon product reviews.

* Simple Negative/Positive sentiment prediction (Supervised Classification)
* Generate Word Embeddings (Unsupervised)

### Data Analysis
___
* Download the provided file from s3 (https://s3.amazonaws.com/fast-ai-nlp/amazon_review_polarity_csv.tgz)
* Unzip and Reveiw the data  
* There are 3 files (train.csv , test.csv), each havnig 3 columns (label,title and comment). 
  Label indicates
  
  1. Negative Comments (Rating 1,2)
  
  2. Positive Comments (Ratings 4,5)
* Perform shape and historgram on the train and test data sets. 

### Model Creation
___

####  Simple Negative/Positive sentiment prediction (Supervised Classification)

Three models to be created

1. Comment (Feature selection)
2. Title (Feature selection)
3. Title + Comment (Feature creation)

Reveiw performance of each model to understand the effectiveness of each. 
* Accuracy
* Confusion Matrix

Perform some manual tests with arbitary comments.

####  Generate Word Embeddings (Unsupervised) 



### References

Wor2Vec:
https://github.com/awslabs/amazon-sagemaker-examples/blob/master/introduction_to_amazon_algorithms/blazingtext_word2vec_text8/blazingtext_word2vec_text8.ipynb
