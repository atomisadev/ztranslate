# ZTranslate

This is a personal project inspired by [@jD2R](https://github.com/jD2R) that did this at a hackathon. The goal of this project is to translate Gen Z slang into common English (moreover, this is a personal learning opportunity for me, as I am interested in the field of AI engineering). The difference between his project and mine is that his uses a predefined text file containing Gen Z phrases and definitions. My project uses TensorFlow and ChatGPT-generated training data to train the AI to perform sentiment analysis on 50 different Gen Z phrases (this dataset will surely grow in due time).

## Well, how does it work?

> **Note**: On the current release, the program doesn't quite yet fully translate phrases. It only determines if the repsonse is positive or negative. The AI is still actively being trained with new data to translate it.

What a great question! This isn't anything too complicated, and anyone with a basic understanding of TensorFlow and Keras should understand how this works. I'm going to get pretty professional and well-worded, so prepare yourself.

Well, this is an implementation of a sentiment analysis algorithm that utilizes the TensorFlow library. The primary purpose of this algorithm is to perform sentiment classification on a set of linguistic expressions, specifically slang phrases commonly used by the Gen Z demographic.

To achieve this:
- The program employs a mutli-layer neural network architecture, consisting of a combination of linear transformations and non-linear activation functions
- The architecture includes:
  - An `Embedding` layer to project the word representations into a continuous dense vector space
  - A `GlobalAveragePooling1D` layer to aggregate the contextual information across the sequence length
  - 2 `Dense` layers with rectified linear activation functions, and a final `Dense` layer with a sigmoid activation function for producing the binary classification of the result
- The input data for this algorithm is a manually created list of Gen Z slang phrases and their sentiment annotations
- This list is preprocessed to convert each phrase into a numerical representation using the `Tokenizer` module of the TensorFlow library
  - This preprocessing step is crucial as it enables the neural network to process and learn from text data
- The numerical representations (also known as sequences) are then padded to ensure that all the sequences have the same length and are ready for input into the model
- The model is then trained using the binary cross-entropy loss function and the Adam optimizer for 5 epochs
- The training process adjusts the weight of the model's parameters to minimize the difference between the predicted and actual sentiments
- The program finally includes a function for predicting the sentiment of an unseen slang phrase
  - The function takes as input a Gen Z phrase, tokenizes it, pads it, and inputs it into the trained model to produce a sentiment prediction, which is a continuous value in the range of 0 to 1
  - A threshold of 0.5 is used to convert this continuous value into a binary classification result, where values greater than 0.5 indicate a positive sentiment, and values below 0.5 indicate a negative statement
  
That was a mouthful.

## How can I run it?

The source code is written in a Jupyter Notebook. The best way to run the code would be to clone the repository locally and use your favorite IDE to run the notebook. Alternatively, you can manually copy and paste the code into a Python file and run it (although this isn't highly recommended).

If you don't want to run it locally, you can whip up something like Codespaces that has a built-in browser JupyterLab. Otherwise, you can use [Google Colaboratory](//colab.research.google.com/) and import from GitHub.
