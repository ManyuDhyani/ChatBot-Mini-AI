# ChatBot-Mini-AI
Developed a chatbot for a freelance project. Some Key aspects of the project explained below.

# Word Stemming
You may have heard me talk about word stemming in the previous tutorial. Stemming a word is attempting to find the root of the word. For example, the word "thats" stem might be "that" and the word "happening" would have the stem of "happen". We will use this process of stemming words to reduce the vocabulary of our model and attempt to find the more general meaning behind sentences.

# Bag of Words
Now that we have loaded in our data and created a stemmed vocabulary it's time to talk about a bag of words. As we know neural networks and machine learning algorithms require numerical input. So out list of strings wont cut it. We need some way to represent our sentences with numbers and this is where a bag of words comes in. What we are going to do is represent each sentence with a list the length of the amount of words in our models vocabulary. Each position in the list will represent a word from our vocabulary. If the position in the list is a 1 then that will mean that the word exists in our sentence, if it is a 0 then the word is nor present. We call this a bag of words because the order in which the words appear in the sentence is lost, we only know the presence of words in our models vocabulary.

As well as formatting our input we need to format our output to make sense to the neural network. Similarly to a bag of words we will create output lists which are the length of the amount of labels/tags we have in our dataset. Each position in the list will represent one distinct label/tag, a 1 in any of those positions will show which label/tag is represented.

Finally we will convert our training data and output to numpy arrays.

# Training & Saving the Model
Now that we have setup our model its time to train it on our data! To do these we will fit our data to the model. The number of epochs we set is the amount of times that the model will see the same information while training.

# Making Predictions
Now its time to actually use the model! Ideally we want to generate a response to any sentence the user types in. To do this we need to remember that our model does not take string input, it takes a bag of words. We also need to realize that our model does not spit out sentences, it generates a list of probabilities for all of our classes. This makes the process to generate a response look like the following:<br />
– Get some input from the user<br />
– Convert it to a bag of words<br />
– Get a prediction from the model<br />
– Find the most probable class<br />
– Pick a response from that class<br />

The bag_of_words function will transform our string input to a bag of words using our created words list. The chat function will handle getting a prediction from the model and grabbing an appropriate response from our JSON file of responses.
