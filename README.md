# Information-Retrieval-Project
A information retrieval engine that searches for wikipedia pages based on query. 

In our Implementation, we used the following techniques: Inverted Indices, stemming, stopwords removal, BM25, tf-idf(?) and more.
Key techniques employed in our project include the use of an inverted index to facilitate rapid searches, stemming to reduce words to their root forms, and the removal of stopwords to improve search relevance. 
Furthermore, we incorporated the BM25 algorithm to enhance the ranking of search results, ensuring that users receive the most pertinent information in response to their queries. 
Through these methodologies, we aimed to deliver a search engine that not only performs quite well but also delivers relevant content to its users.

# Inverted Index- 
We started with creating an inverted index for the retrieval task. We uploaded it in a pickle file. it contains the following attributes:
posting_locs - the posting list dictionary.
doc_lengths - the doc length dictionary.
N - the number of docs in the corpus.
avgdl - the average doc length.



