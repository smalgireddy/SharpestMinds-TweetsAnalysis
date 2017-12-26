# SharpestMminds-TweetsAnalysis
Contextual Tweets classification - SharpestMind evaluation
Note : I consider only tweets data with food context.

Data Loading & preprocessing:
As part of this analysis, the data is collected in the form of json format, that collected data is loaded into dataframes. Apart from the existed columns, I added a new column to the existed dataframe with the tweet content of that corresponding row. Removed the special charactes and mentioned urls (since the url is in random format) with help of regular expression patterns, and transformed the tweet text into alpha numeric sentences. After text formatting, filetered the dataframes into 3 different dataframes (food, borne and exercises) based on their cotext column attribute of the data.
Irregularities in data: I found few irregularities in the label_data colum values across 3 data frames. i.e. eventhogh the dataset is of food tweets, it has values of relevant, irrelevant in their label_data column which isn't the expected behaviour. SO i filtered out thos irregularities. After filtering the data,
            tweets_food : healthy, unhealthy, junk (labels)
 NLP Algorithms:
  1. Convolution neural networks with pre-trained Glove word embeddings (200 dimensional embeddings)
  2. Convolution neural networks without word embedding weights using word2vec CBOW model
  3. Convolution neural networks with word2vec-Skip gram word embeddings
  4. Gradient Boosting CLassifier with doc2vec word embedding features.
 Reported Accuracy:
  pretrained Glove + CNN : 74%
  word2vec-CBOW + CNN : 81%
  word2vec-skipgram + CNN : 96%
  doc2vec+GradientBoostingClassifier : 54%
 
 Performance Analysis:
  1. CNN with pretrained Glove didn't performa as expected as there are so many irregularities within the text. So most of the words don't have their corresponding embedding wieghts.
  2. CNN with word2vec-skipgram model gave the best accuracy as the word2vec model was trained with theour own dataset and used resulted word embeddings as features for the CNN classifier.
  3. Doc2vec couldn't do well on the limited dataset as Doc2vec model is suggestible in only huge data avalaiility cases.
 
 reference: for pretrained glove word embedding model, please download the glove word embeddings from Stanford NLP library link.
 Download link: https://nlp.stanford.edu/projects/glove/
