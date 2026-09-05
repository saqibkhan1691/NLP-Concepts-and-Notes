# Natural Language Processing:

## Roadmap of NLP:

Step 1) Text Preprocessing part 1 - Tokenization, Lemmatization, Stemming, etc (Cleaning the input text)

Step 2) Text Proprocessing part 2 - Bow(Bag of words), TF-IDF, Unigram, Bigrams, etc (Convert Input text into Vectors)

Step 3) Text Preprocessing part 3 - Word2Vec, AvgWord2Vec, etc (Convert Input text into Vectors in advanced way)

Step 4) RNN, LSTM-RNN, GRU-RNN (Neural Network)

Step 5) Text Preprocessing part 4 - Word Embedding (DL part)

Step 6) Transformer (DL part)

Step 7) BERT (DL part)

### Note: From going step 1 to step 7 the accuracy of model will imporve but size of model will also increase

### Libraries: NLTK, spaCy, Tensorflow/Pytorch

# Tokenization in NLP:

Basics topics:

-Corpus (Paragraph/Sentence)

-Documents (Sentences in a list)

-Vocabulary (Unique Words)

-Words (All the words that are baasically present in corpus that is word)

In tokenization sentence convert into tokens(words/subwords/sentences)

ex-"Hello, my name is Rahul"

Word-level tokenization:
["Hello", "my", "name", "is", "Rahul"]

Lekin modern LLMs mein subword tokenization common hai:

"playing" → ["play", "ing"]

Aur punctuation bhi token ho sakta hai:

"Hello!" → ["Hello", "!"]

# Stemming in NLP:

Stemming is the process of reducing a word to its root/base form by removing prefixes or suffixes.

Example:

[playing, played, plays] -> play

studies -> studi (not always a proper English word)

So, stemming is a simple rule-based technique and may produce an invalid word.

# Lemmitization in NLP:

It is similar to stemming but in lemmitization the output word after lemmitization is "Lemma" that is root word ex-> [eating, eaten, eats] -> eat where "eat" is root word

# Stopwards in NLP:

