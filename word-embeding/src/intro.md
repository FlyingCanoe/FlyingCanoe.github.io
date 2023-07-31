# Introduction

This is the designs documentation for my `word-embedding` repo.

## Word Embedding

Word embedding is a natural language processing (NLP) technique in which each word in the vocabulary is assign
a multidimensional vector. Those vector have the propriety that word that are semantically and syntactically
similar have vector that are near one another.

This technique can be used in multiple NLP task including LLM where it is
the second step (the first step is tokenization).

This repo also contain code to perform k-mean clustering on the resulting word embedding.