# Hangman AI

Hangman is a turn based games where a player guesses letters in a word of known length.  As they guess correct letters they are told where in the word those letters appear.  Wrong guesses result in strikes.  The player wins if they guess all the letters in the word before they run out of strikes.

Using the python notebook you can create a model in keras and train it using NLTK corpuses.  

# Results

I have tried several different model architectures:
- An LSTM
- A 1D CNN with the already guessed letters combined at the end (this is the type of model in the current notebook)
- A 2D CNN where the already guessed letters where the already guessed letters are added as a second dimension

The most successful was the 2D CNN and least was the LSTM

<img src="https://github.com/mkspillane/hangman_AI/blob/main/Images/Average_misses" width="300" height="200">
<img src="https://github.com/mkspillane/hangman_AI/blob/main/Images/Win_Rate" width="300" height="200">

# Letter Embeddings

Instead of one-hot encoding the letters it is also possible to train embedding vectors for them instead.  This does not have much effect on the model performance, but provided the following interesting plot.  Using PCA the letter embeddings were projected so that they can be viewed.

<img src="https://github.com/mkspillane/hangman_AI/blob/main/Images/letter_embeddings.png" width="300" height="200">

There are a couple of things to notice, to the lower right are the vowels (and "y"), on the left is "q" which is presumbably singled out because it is almost always followed by "u".  You may also notice the non-letter "{" which represents the embedding for a blank space for an unguessed letter. 
