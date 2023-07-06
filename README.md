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

# N-gram
