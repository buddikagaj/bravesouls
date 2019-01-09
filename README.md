## BraveSouls

Use Natural Language Processing (NLP) to predict Positive and Negative sentiments on customer reviews on amazon product reviews.

* Simple Negative/Positive sentiment prediction (Supervised Classification)
* Generate Word Embeddings (Unsupervised)
* Linear Learner for 1:1 model interpretation, using word embeddings as features
* Clustering negative reviews to extract topics and key words

### Data Analysis
___
* Download the provided file from s3 (https://s3.amazonaws.com/fast-ai-nlp/amazon_review_polarity_csv.tgz)
* Unzip and Reveiw the data  
* There are 2 data files (train.csv , test.csv), each havnig 3 columns (label,title and comment). 
  The label indicates
  
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

Model creation for each is very similat except for the transformation, in which we select different columns to use for inputs

##### Steps

1. Import necessary libraries
2. Environment Setup
3. Data Pulling and pre-prep
4. Implement __Transformation__ and __Preprocess__ functions
5. Obtain a training __SageMaker__ container for __blazingtext__
6. Set __Hyper Parameters__
7. __fit__ : Train to create model (If accuracy meet desired perform next steps)
8. Deploy model to an __End Point__
9. Test it out

Reveiw performance of each model to understand the effectiveness of each. 
* Accuracy
* Confusion Matrix

Perform some manual tests with arbitary comments.

####  Generate Word Embeddings (Unsupervised) 

Word embeddings are used in NLP to represent words in a numerical context and establish distance relationships. While there are pre-created word embeddings, we can create our own word embedings, with respect to the context. In this excercise we create new Word Embeddings for the Product reviews (title+comments) and generate a vectors for the words.

_NOTE: This is unsuperviced learning._

Process is very similar to 1st model, yet we do not generate labels or test/validation data set as it's unsupervised.
##### Steps

1. Import necessary libraries
2. Environment Setup
3. Data Pulling and pre-prep
4. Implement __Transformation__ and __Preprocess__ functions. _Note: We drop label column and use only title and comments. Also no test data set_
5. Obtain a training __SageMaker__ container for __blazingtext__
6. Set __Hyper Parameters__ _Note: use __mode="batch_skipgram"__ in hyper parameters. We also use 100 as the vector demension.
7. __fit__ : Train to create model (If accuracy meet desired perform next steps)
8. Deploy model to an __End Point__
9. Test it out. Analysis includes plotting the word vector.

#### Linear Learner for 1:1 model interpretation, using word embeddings as features

Extending the Word2Vec excercise, we are using the word vectors as the features to create a supervised model using __Linear Learner__.

### References

__Text Classification:__

https://github.com/awslabs/amazon-sagemaker-examples/blob/master/introduction_to_amazon_algorithms/blazingtext_text_classification_dbpedia/blazingtext_text_classification_dbpedia.ipynb


__Wor2Vec:__

https://github.com/awslabs/amazon-sagemaker-examples/blob/master/introduction_to_amazon_algorithms/blazingtext_word2vec_text8/blazingtext_word2vec_text8.ipynb

__LInear Learner:__

https://docs.aws.amazon.com/sagemaker/latest/dg/linear-learner.html
