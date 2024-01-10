# basic_Information_Retrieval_System


## Introduction
This report outlines the development and implementation of an Information Retrieval System using Python. The system comprises several interconnected classes: `TextPreprocessor()`, `PositionalInvertedIndex()`, `Query()`, `BooleanSearch()`, `PhraseSearch()`, `TFIDF()`.

### 1. Tokenization and Stemming
The `TextPreprocessor()` class focuses on text preprocessing (removing stop words, tokenization, and stemming).

- Tokenization breaks text into tokens, typically words or sentences. We utilized the Natural Language Toolkit (nltk) library for tokenization, employing methods like `word_tokenize()`.
- Stemming, the process of reducing words to their base or root form, was accomplished using the Porter Stemmer algorithm available in nltk. This step standardizes words to their base form, allowing for better matching during search operations.

### 2. Inverted Index Implementation
The `PositionalInvertedIndex()` class serves as the backbone of the system, constructing an inverted index for the corpus. The index is a mapping of terms to the documents in which they appear, along with additional information such as term frequency and positional information.

#### Example:
```json
{
  "Term_n°01": {
    "document_frequency": 2,
    "postings": {
      "doc4_.txt": [0],
      "doc5_.txt": [4]
    }
  },
  "Term_n°02": {
    "document_frequency": 3,
    "postings": {
      "doc4_.txt": [1],
      "doc1_.txt": [0, 2],
      "doc3_.txt": [1]
    }
  }
}
```
 
We implemented the inverted index as a Python dictionary where the keys represent unique terms. The values contain metadata about the term's occurrences in documents. Additionally, positional information is stored to enable advanced search functionalities such as phrase search.

### 2. Search Function Implementations

#### Boolean Search
The `BooleanSearch()` class enables users to perform Boolean operations (AND, OR, NOT) on the inverted index. It processes user queries and retrieves relevant documents based on the applied Boolean logic. This functionality is fundamental for basic information retrieval operations.

#### Phrase Search
The `PhraseSearch()` class handles complex queries by considering the positions of terms in documents. It enables users to search for sequences of words or phrases within documents, utilizing the positional information stored in the inverted index.

#### TF-IDF Calculation
The `TFIDF()` class calculates the TF-IDF (Term Frequency-Inverse Document Frequency) scores for terms in the corpus. This scoring system evaluates a term's importance in a document relative to its frequency in the entire corpus. TF-IDF scores aid in ranking and retrieving documents based on relevance to user queries.


#### Improvement and Scaling Ideas
To enhance performance and scalability we can use :
- **Parallel Processing:** Utilize parallel processing for faster retrieval, especially with large datasets.
- **Cloud Computing Resources:** Utilize scalable storage solutions offered by cloud platforms (e.g., AWS, Google Cloud, Azure) for efficient data retrieval.

### Conclusion
The development and implementation of the Information Retrieval System provided multifaceted insights into information retrieval, natural language processing, and system architecture.

#### Insights Gained
- **Text Processing Techniques:** Understanding tokenization and stemming for efficient information retrieval.
- **Inverted Index Construction:** Importance of data structures and their role in efficient search operations.
- **Complex Search Algorithms:** Implementing functionalities like Boolean search, phrase search, and TF-IDF calculation unveiled complexities in handling user queries efficiently.
- **Challenges and Solutions:** Addressing challenges in performance optimization, memory management, and query complexity showcased strategies for scalability and performance improvement.


