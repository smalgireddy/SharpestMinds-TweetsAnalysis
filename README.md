# SharpestMminds-TweetsAnalysis
Contextual Tweets classification - SharpestMind evaluation
<br><b>Note :</b> I consider only tweets data with food context.

<br><b>Data Loading & preprocessing:</b>
As part of this analysis, the data is collected in the form of json format, that collected data is loaded into dataframes. Apart from the existed columns, I added a new column to the existed dataframe with the tweet content of that corresponding row. Removed the special charactes and mentioned urls (since the url is in random format) with help of regular expression patterns, and transformed the tweet text into alpha numeric sentences. After text formatting, filetered the dataframes into 3 different dataframes (food, borne and exercises) based on their context column attribute of the data.
<br><b>Irregularities in data:</b> I found few irregularities in the label_data colum values across 3 data frames. i.e. eventhogh the dataset is of food tweets, it has values of relevant, irrelevant in their label_data column which isn't the expected behaviour. SO i filtered out thos irregularities. After filtering the data,
            tweets_food : healthy, unhealthy, junk (labels)
<br> <b>The architecture of this project is as follows:</b>
![Pipeline_Food](ftc.JPG?raw=true "Tweets classification pipline")
            
<br><b>NLP Algorithms:</b>
  * Convolution neural networks with pre-trained Glove word embeddings (200 dimensional embeddings)
  * Convolution neural networks without pretrained word embedding weights using word2vec model
  * Convolution neural networks with word2vec-Skip gram word embeddings
  * Gradient Boosting CLassifier with doc2vec word embedding features.
<br><b>Reported Accuracy:</b>
  * pretrained Glove + CNN : 74%
  * word2vec-without pretrained word embeddings + CNN : 81%
  * word2vec-skipgram + CNN : 96%
  * doc2vec+GradientBoostingClassifier : 54%
 
 <br><b>Performance Analysis:</b>
  1. CNN with pretrained Glove didn't performa as expected as there are so many irregularities within the text. So most of the words don't have their corresponding embedding wieghts.
  2. CNN with word2vec-skipgram model gave the best accuracy as the word2vec model was trained with theour own dataset and used resulted word embeddings as features for the CNN classifier.
  3. Doc2vec couldn't do well on the limited dataset as Doc2vec model is suggestible in only huge data avalaiility cases.
 
 <b>##reference:</b> for pretrained glove word embedding model, please download the glove word embeddings from Stanford NLP library link.
 Download link: https://nlp.stanford.edu/projects/glove/
