# Information-Retrieval-Project
A information retrieval engine that searches for wikipedia pages based on query. 

In our Implementation, we used the following techniques: Inverted Indices, stemming, stopwords removal, BM25 and more.
Key techniques employed in our project include the use of an inverted index to facilitate rapid searches, stemming to reduce words to their root forms, and the removal of stopwords to improve search relevance. 
Furthermore, we incorporated the BM25 algorithm to enhance the ranking of search results, ensuring that users receive the most pertinent information in response to their queries. 
We stored and ran the files on a google cloud project. 
Through these methodologies, we aimed to deliver a search engine that not only performs quite well but also delivers relevant content to its users.

# Wikipedia preprocessed pages-
We were given access to parquet files containing already preprocessed wikipedia pages. 

Each wikipedia page has the following details: 

<img width="404" alt="image" src="https://github.com/beryaelio/Information-Retrieval-Project/assets/47675083/d2d3a0d2-0aea-44ec-a614-7a0986052cce">


# Inverted Index- 
We started with creating an inverted index for the title, for the retrieval task. We uploaded it in a pickle file. 

We also added BM25 attribute inside the index to store the BM25 calculations that don't require the query.

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

# Ranking Methods Used
The methods for document retrieval we used are BM25 and pagerank for ranking. 

the BM25 algorithm we implemented is based on this version:

Moreover, the pagerank function is based on a function in 'GraphFrames' - a Spark package that provides DataFrame-based graphs with various graph algorithms implemented, including PageRank.

Using both of these methods results in a ranking process, we managed to return relevant documents for given queries.

# Packages
NLTK ; PySpark ; pickle ; google.cloud

# Built By
Mickael Zeitoun | Yael Berkovich
