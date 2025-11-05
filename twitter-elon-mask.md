# Twitter Elon Mask

## Outlines

*   [Introduction](broken-reference)

    ```
    - [Background](#background)
    - [Motivation](#motivation)
    - [Insights, implications or applications] (#NLTK)
    ```
*   [Collecting text](broken-reference)

    ```
    - [Which APIs?](#api)
    - [APIs policy, technique](#apis)
    - [Features of text](#texts)
    ```
* [Natural Language Process](broken-reference)
  * [Procedures](broken-reference)
  * [Tokenization, Part of Speech tagging, Lemmatization](broken-reference)
* [Sentiment / Textual analysis](broken-reference)
  * [Create wordcloud](broken-reference)
  * [Lexicon source](broken-reference)
  * [Distill sentiment](broken-reference)
* [Concluding remarks](broken-reference)
* [Additional Resources](broken-reference)
* [Reference](broken-reference)

***

## Markdown syntax

1.[glasgow](https://www.youtube.com/)

1. [Markdown basic](https://www.markdownguide.org/basic-syntax/)
2. [Markdown extended](https://www.markdownguide.org/extended-syntax/)

![James Quick](https://miro.medium.com/max/1110/0*M6-atLxy_WR3LN1R.jpg)

## Introduction

* with NLP, we can generate "machine-readable" text, that can be further analyzed by Artificial Intelligence or Machine Learning
* with NLP, we build an interaction between computers and humans using the natural language
* Most NLP techniques rely on machine learning to derive meaning from human languages
* NLP is considered a difficult problem in computer science. It’s the nature of the human language that makes NLP difficult.

### Background

* NLP identifies and extracts the natural language rules such that the unstructured text is converted into a form that computers can understand
* Given the text provided, the computer will utilize algorithms to extract meaning associated with every sentence and collect the essential data from them
* It may happen that the computer fails to understand the meaning of a sentence well, leading to obscure results.

### Motivation

* Text is unstructured data with implicit structure
  * Text, sentences, words, characters
  * Nouns, verbs, adjectives
  * Grammar
* Transform implicit text structure into explicit structure
* Reduce text variation for further analysis
* Python Natural Language Toolkit [NLTK](https://www.nltk.org/)

## Collecting text

you can give a breif here.....

### Which APIs?

> * Decompose a string into sentences
> * Decompose a sentence into words/tokens

```python
""" read text """
with open('shakespeare.txt', 'r', encoding='utf-8') as shakespeare_read:
    # read(n) method will put n characters into a string
    shakespeare_string = shakespeare_read.read()
```

```python
""" remove stop words """

STOPWORDS = ["an", "a", "the", "or", "and", "thou", "must", "that", "this", "self", "unless", "behind", "for", "which",
             "whose", "can", "else", "some", "will", "so", "from", "to", "by", "within", "of", "upon", "th", "with",
             "it"]

def _remove_stopwords(txt):
    """Delete from txt all words contained in STOPWORDS."""
    words = txt.split()
    # words = txt.split(" ")
    for i, word in enumerate(words):
        if word in STOPWORDS:
            words[i] = " "
    return (" ".join(words))
```

```python
""" create a list of sentences """
import re
from collections import Counter

doc_out = []
for k in shakespeare_split:
    cleantextprep = str(k)
        # Regex cleaning
    expression = "[^a-zA-Z ]"  # keep only letters, numbers and whitespace
    cleantextCAP = re.sub(expression, '', cleantextprep)  # apply regex
    cleantext = cleantextCAP.lower()  # lower case
    cleantext = _remove_stopwords(cleantext)
    bound = ''.join(cleantext)
    doc_out.append(bound)       # a list of sentences
```

### Stopwords

### Lemmatization

## Sentiment / Textual analysis

How to detect the tone or sentiment of text? Using the predefined lexicon that collects positive versus negative words with semantic polarity, we screen the tokens and count the words being classified via the employed lexicon. If the frequency of positive words is predominant than that of negative words, we infer an optimistic tone/sentiment in the text.

* We employ [opinion lexicon](https://www.cs.uic.edu/~lzhang3/programs/OpinionLexicon.html) to identify text polarity.

![James Quick](https://miro.medium.com/max/1606/0*IwaUifbmSaVjxqjQ)

### Create wordcloud

A demonstration of wordcloud generated from Shakespeare text

![James Quick](https://github.com/chencath/DataRetrieval/blob/master/wordcloud.png?raw=true)

## Additional Resources

* [NLTK](https://www.nltk.org/)
* [Online Python Interpreter](https://www.onlinegdb.com/online_python_interpreter)
* [Opinion Lexicon](https://www.cs.uic.edu/~lzhang3/programs/OpinionLexicon.html)
