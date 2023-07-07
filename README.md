# Using LLMs

A Large Language Model, LLM, is a really big (humongous!) language model. Therefore, let us start with what is a language model.

## Language Model
A language model is a "probability distribution over sequences of words"... *What???*... well:

- You take some data: text, large amounts of text generally, but it can be any text, let's say a book. 
- From that text you extract sequences of words, let's say phrases or paragraphs, but it can be any sequence of words like single words, pairs, triplets, etc.
- Then you analyze how probable it is that each of those sequences appears on the text.

Example: if you have the text "you are what you are" and are interested in pairs of words (also called bigrams), then all the bigrams are: you are, are what, what you, you are. So, 4 bigrams. Now the probabilities of each of these bigrams appearing on this text are: you are 50% / are what 25% / what you 25%.

In itself this is not that interesting, but what if you can see only one word in this text, let's say the word "you"... what would you say is the word that follows?... well the must probable is "are". And here you have the basis for the autocomplete in google search, for instance. That is a lot more interesting I would say!

And it is more interesting because language models let us make predictions on what is the word or the sequence of words that follows. Something like: if I have this question, what is the more probable answer to that question (the answer being nothing more than the text that follows the question!).

So far we have mentioned bigrams, that are part of a more general family called the n-grams. N-grams are one of the historical basis for *next-word prediction*, and it is simple enough as to let us show the technical principle behind current LLMs.

## N-gram
An n-gram is a sequence on n consecutive items (or grammatical elements) in a text. Those items can be words, characters or tokens in general, where token is an arbitrary unit you define with an identified meaning. Normally we talk about words or characters.

The n in n-gram, therefore, can take any integer value. If n == 1, then we have a unigram, if n == 2, then we have a bigram, and so forth.

N-grams help us predict what is the next item in a series. For instance, if in our model we have the trigrams: "I am crazy", and "I am smart", with probabilities 0.02 and 0.01 respectively, and if we see the words "I am", then the must probable word that follows is "crazy", and therefore "I am crazy" is the best continuation (and kind of I am, so is very realistic also :D).

The theory behind next word prediction with n-grams is based on [Markov chains](https://en.wikipedia.org/wiki/Markov_chain). The main hypothesis is that the probability of some event happening, depends exclusively on the state from the previous event. In this case the previous event is seeing the first n-1 words off an n-gram, and the event we want to predict is seeing the n<sup>th</sup> word. In the example, the previous event is the words "I am", and the event to predict is whether we will have "crazy" or "smart". Markov chains is a simplification to such a complex problem, so it is not perfect at all, but it works nicely in practice.

If you are interested in learning how to build a simple Generative Language Model using n-grams, check [this Google Colab notebook](ngram-glm-sample.ipynb).

So far so good. It's been very simple and comprehensible I hope, but real world models are quite a complex stuff, so we need more. The next step in building language models is quite a big one: Word Embeddings, to extract the meaning of words, and neural networks to process and build the models. 

## Word Embeddings

A language model works with words, but words on themselves are not easily manageable. It would be a lot better if we could work with numbers. The next step then is to give words a numerical representation and meaning.

For doing this we use high dimensional vectors that we put into a matrix that will represent our dictionary. Each word will have a position in the matrix, and it's meaning will be given by the vector values. The closer the meaning of two words, the closer their vector values.

This meaning is given according to the context of the word throughout the text, so, the dataset used to build the word embedding has a big influence here.

...What???...

Ok. Let's go for a little example