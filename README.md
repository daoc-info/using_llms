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

# N-gram
An n-gram is a sequence on n consecutive items (or grammatical elements) in a text. Those items can be words, characters or tokens in general, where token is an arbitrary unit you define with an identified meaning. Normally we talk about words or characters.

The n in n-gram, therefore, can take any integer value. If n == 1, then we have a unigram, if n == 2, then we have a bigram, and so forth.

N-grams help us predict what is the next item in a series. For instance, if in our model we have the trigrams: "I am crazy", and "I am smart", with probabilities 0.02 and 0.01 respectively, and if we see the words "I am", then the must probable word that follows is "crazy", and therefore "I am crazy" is the best continuation (and kind of I am, so is very realistic also :D).

Prediction with n-grams is theoretically based on [Markov chains](https://en.wikipedia.org/wiki/Markov_chain). The main hypothesis is that the probability of some event happening, depends exclusively on the state form the previous event.

If you are interested in learning how to build a simple Generative Language Model using n-grams, check [this](ngram-glm-sample.md).