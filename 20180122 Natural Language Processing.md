# References
Colah github blog
ruder.io
cs224n (Stanford lecture series)

# Natural Language Processing

- Extract features and insights from unstructured data. 
- Used in:
	information retrieval
	Extraction
	Machine translation
	Text simplification (resimplyfy)
	Predictive text
	Sentiment analysis
	Speech reognition and generation (text to speech)
	Question answering (IBM Watson)
	(new) Visual question answering: ask qns specific to image
	Image captioning (computer vision + NLP)

# Methods
## Count Vectorization
- converts words into get dummies variables/one- hot encoding
- available in sklearn

## Word2Vec, Doc2vec, GloVec
[WORD2VEC Use case]
- looks at co-occurence of words
- Word2vec, set a window of 3 then slides it across:

iteration 1:
roses are red, violets are blue
=============

iteration 2:
roses are red, violets are blue
      ================
.....
.....

- 2 vectors
- can use transfer learning to use vector from pre-trained dataset (wikipedia dataset, common crawl)

*** Remember to change encoding to UTF-8 (default is utf8 just make sure)

## sklearn count vectorizer
- arguments
ngram_range (min_n, max_n)
stop_words
lowercase
max_df : remove common occurring words across the corpus

## Hash vectorizer
faster to process
represent words as number
cant tell what word the number represents


## Stemming (NLTK)
find common elements of words belonging to same group

## Part of speech tagging

## Term freq - inverse document freq (tf-idf)
A tf-idf score tells us which words are most discriminating between documents. Words that occur a lot in one document but don't occur in many documents contain a great deal of discriminating power.

