# Natural Language Processing:

## Roadmap of NLP:

Step 1) Text Preprocessing part 1 - Tokenization, Lemmatization, Stemming, etc (Cleaning the input text)

Step 2) Text Proprocessing part 2 - Bow(Bag of words), TF-IDF, Unigram, Bigrams, etc (Convert Input text into Vectors)

Step 3) Text Preprocessing part 3 - Word2Vec, AvgWord2Vec, etc (Convert Input text into Vectors in advanced way)

Step 4) RNN, LSTM-RNN, GRU-RNN (Neural Network)

Step 5) Text Preprocessing part 4 - Word Embedding (DL part)

Step 6) Transformer (DL part)

Step 7) BERT (DL part)

Libraries: nltk, spaCy, Tensorflow/Pytorch

### Note: From going step 1 to step 7 the accuracy of model will imporve but size of model will also increase

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

Stopwords are the words which are filtered out before or after processing of text. These are the most common words in a language. For example, in English, the words "is", "and", "the", "a" are considered stopwords. These words do not carry significant meaning and are often removed from text data to improve the performance of NLP tasks.

# Named Entity Recognition:

In a sentence/paragraph there are many entities like Person, Place, Date, Time, Money, Organization, Percent, etc then we need to identitfy those entities that helps in text preprocessing

# Sentiment Analysis:

Sentiment Analysis means finding the emotion or opinion expressed in a text.

In simple words, it tells us whether a sentence is:

Positive -> "I love this movie."

Neutral -> "The movie starts at 7 PM."

Negative -> "I hate this movie."

For Sentiment Analysis we need to convert text into vector/numbers and there are many ways of conversion

# Types of ways to convert text into vectorrs:

1) One Hot Encoded

2) Bag of Words (Bow)

3) TF-IDF

4) Word2Vec

5) AvgWord2Vec

## 1) OHE:

One Hot Encoding is a technique used in NLP to represent words or categories as numerical vectors containing 0s and 1s, so that machine learning models can process them.

![Image](WhatsApp%20Image%202026-09-05%20at%208.22.06%20PM-1.jpeg)

## Advantges:

1) Easy to implement with python [sklearn, OHE, pd.get_dummies()]


## Disadvantages:
1) Sparse matrix reason overfitting (good accuracy for training data but gives bad accuracy for new data)
2) ML Algorithm need fixed size of input words
3) No semantic meaning is getting captured ex-> The food is good (we dont know which word is more important/relation/etc)
4) Out of Vocabulary (when new word is coming then it not in vocaluary)

## 2) Bag of Words (Bow):

Bag of Words is a technique used in NLP to represent text as numerical vectors based on the frequency of words in the text.

![Image](C:\Projects\NLP_Concepts_and_Notes\image.png)

## Advantges:

1) Easy to implement with python
2) Fixed Sized Input words -> ML Algorithms


## Disadvantages:
1) Sparse matrix reason overfitting (good accuracy for training data but gives bad accuracy for new data)
2) Ordering of the word is getting changed
3) No semantic meaning is getting captured ex-> The food is good and The food is not good (we dont know which word is more important/relation/etc)
The food is good -> [1 1 1 0 1] v1
The food is not good -> [1 1 1 1 1] v2
when we plot graph then both vector v1 and v2 similar because angle is small between them but in actual both are opposite word 
4) Out of Vocabulary (when new word is coming then it not in vocaluary)

## 3) TF-IDF:

TF-IDF is an NLP technique that assigns a numerical importance score to words based on their frequency in a document and rarity across all documents.

TF-IDF = Term Frequency × Inverse Document Frequency

TF (Term Frequency) → Word document mein kitni baar aaya.
IDF (Inverse Document Frequency) → Word kitne documents mein common hai.

![Image](C:\Projects\NLP_Concepts_and_Notes\TF_IDF.png)

## Advantges:

1) Intuitive -> Easy to understand and implement because text is simply converted into numerical values based on word frequency/importance.
2) Fixed Sized Input words -> ML Algorithms
3) Word Importance is getting captured


## Disadvantages:

1) Sparse matrix reason overfitting (good accuracy for training data but gives bad accuracy for new data)
2 Out of Vocabulary (when new word is coming then it not in vocaluary)

# Word Embedding:

A numerical vector representation of a word that captures its meaning and relationships with other words.

![Image](C:\Projects\NLP_Concepts_and_Notes\WordEmbeddings.png)



# Word2Vec:

A technique that converts words into numerical vectors while learning their semantic and contextual relationships.

## Cosine Similarity:

A measure used to calculate the similarity between two vectors based on the angle between them.
dsitance = 1 - cos(theata)

For example-> if distance near to 0 then both vectors are similar and if near to 1 then opposite to each other  (0 <= Distance <=1)

Similarity high → distance low
Similarity low → distance high

                Large Text Corpus
                       ↓
                  Word2Vec
                       ↓
             Learn word embeddings
                       ↓
         Each word → Numerical Vector
                       ↓
            Semantic relationships
                       ↓
          Cosine Similarity
                       ↓
       Find similar/related words

![Image](C:\Projects\NLP_Concepts_and_Notes\Word2Vec.png)

## There are two type of Word2Vec:

-CBOW (Continuous Bag of Words)
-Skipgram

## 1) CBOW:

CBOW predicts a target word from its surrounding context words and learns word embeddings during this process.

For example ->

Sentence = "The cat is sitting on the mat"

If target word is:
sitting

CBOW might take:
cat, is, on, the

and predict:
sitting

![Image](C:\Projects\NLP_Concepts_and_Notes\CBOW.png)

### 1. Context Window:

Context window defines how many surrounding words are considered to predict the target word.

Example:

I love eating mangoes

Context → love, eating, mangoes

Target  → I

### 2. One-Hot Encoding:

Context words are converted into one-hot vectors before being given to the neural network.

Example:

I → [1,0,0,0]

love → [0,1,0,0]

### 3. Input Layer:

The input layer receives the one-hot encoded vectors of the context words.

Context Words → One-Hot Vectors → Input Layer

### 4. Hidden Layer / Weight Matrix:

The hidden layer contains learnable weights, which are used to learn the word embeddings.

One-Hot Vector × Weight Matrix → Word Embedding

Important: The learned weights represent the word embeddings.

### 5. Combining Context Words:

CBOW combines the embeddings of all context words, usually by taking their average, to create a context representation.

Embedding₁ + Embedding₂ + ... → Average → Context Representation

### 6. Output Layer:

The output layer predicts the target word from the combined context representation.

Example:

Context → CBOW → Data

It produces a score/probability for every word in the vocabulary.

### 7. Softmax:

Softmax converts the output scores into probabilities for each word in the vocabulary.

Example:

Data     → 0.85

Company  → 0.05

Science  → 0.03

The word with the highest probability is selected as the prediction.

### 8. Backpropagation:

Backpropagation calculates the error between the predicted and actual word and updates the weights to improve the model.

Prediction → Error → Backpropagation → Weight Update