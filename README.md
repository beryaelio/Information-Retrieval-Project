# Information-Retrieval-Project
A information retrieval engine that searches for wikipedia pages based on query. 

In our Implementation, we used the following techniques: Inverted Indices, stemming, stopwords removal, BM25, tf-idf(?) and more.
Key techniques employed in our project include the use of an inverted index to facilitate rapid searches, stemming to reduce words to their root forms, and the removal of stopwords to improve search relevance. 
Furthermore, we incorporated the BM25 algorithm to enhance the ranking of search results, ensuring that users receive the most pertinent information in response to their queries. 
Through these methodologies, we aimed to deliver a search engine that not only performs quite well but also delivers relevant content to its users.

# Wikipedia preprocessed pages-
We were given access to files containing already preprocessed wikipedia pages.

Each wikipedia page has the following details: 

title, 

# Inverted Index- 
We started with creating an inverted index for the retrieval task. We uploaded it in a pickle file. it contains the following attributes:

posting_locs - the posting list dictionary.

doc_lengths - the doc length dictionary.

N - the number of docs in the corpus.

avgdl - the average doc length.

We save the documents' lengths for the BM25 algorithm.

# Tokenization- 
We use stemming and stopwords removal for saving an efficient set of tokens after tokenizatoin. We were already given preprocessed wiki pages, all we did was load the files, tokenize them, remove stopwords and stem the rest of the tokens. We also removed tokens that had less then 50 instances in the corpus. That's because our corpus is enourmous thus if a token only has a few instances it's probably a typo.

We used the porter stemmer from the nltk python package.

The code for the stopwords removal:
```python
nltk.download('stopwords')
english_stopwords = frozenset(stopwords.words('english'))
corpus_stopwords = ["category", "references", "also", "external", "links",
                    "may", "first", "see", "history", "people", "one", "two",
                    "part", "thumb", "including", "second", "following",
                    "many", "however", "would", "became"]

all_stopwords = english_stopwords.union(corpus_stopwords)
porter = PorterStemmer()
tokens = nltk.word_tokenize(query)
stemmed_tokens = [porter.stem(token) for token in tokens if token.isalpha() and token not in all_stopwords]
```

