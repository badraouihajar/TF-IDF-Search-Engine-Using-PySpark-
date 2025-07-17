# 🔍 TF-IDF Search Engine with PySpark

This project is a mini search engine built with **Apache Spark**, using the **TF-IDF** (Term Frequency - Inverse Document Frequency) model to rank and retrieve relevant documents based on user queries.

---

##  Project Summary

 **Title**: Implementation of a TF-IDF Based Search Engine using PySpark
 **Author**: Hajar BADRAOUI
 **Institution**: Université de Caen Normandie
 **Master**: M2 Statistiques Appliquées et Analyse Décisionnelle (SAAD)
 **Academic Year**: 2023–2024

This project was carried out as part of a practical assignment, focusing on:

* Text preprocessing with Spark RDDs
* Calculating TF (Term Frequency)
* Calculating DF (Document Frequency)
* Computing TF-IDF scores
* Building a simple query interface with cosine similarity

---

##  Technologies

* Python 3.x
* Apache Spark (PySpark – RDD API)
* Text files (plain corpus)

---

##  Methodology

1. **Corpus Loading**: Documents are loaded from a text file into a Spark RDD.

2. **Tokenization**: Each line/document is split into a list of words.

3. **TF Calculation**: For each document, count the number of occurrences of each word.

4. **DF Calculation**: For the whole corpus, count in how many documents each word appears.

5. **TF-IDF**: For each word in each document:

   ```
   TF-IDF(w, d) = TF(w, d) × log(N / DF(w))
   ```

   where N is the number of documents.

6. **Query Processing**:

   * Tokenize the query
   * Build a query vector (TF-IDF weights)
   * Compare with document vectors using **cosine similarity**
   * Rank documents by similarity

---

##  Example

Given a small corpus:

```
Document 0: il fait beau et chaud  
Document 1: il fait chaud et beau  
Document 2: chaud chaud chaud macao  
Document 3: chaud chaud chaud chocolat
```

And a query:

```
['il', 'chaud']
```

The engine will return documents ranked by similarity:

```
→ Document 0: 0.480  
→ Document 1: 0.480  
```

---

##  Scaling

Tested successfully on a large corpus of **990 documents**, showing Spark’s capability for scalable document analysis.

---

##  License

This project is shared for educational purposes.
© 2024 Hajar BADRAOUI – Université de Caen Normandie
