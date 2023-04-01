# Genre-Identifier


The code is a Python implementation of a machine learning model that classifies music genre based on audio features extracted from music files. It uses the GTZAN Genre Collection dataset, which consists of 1000 audio files, each 30 seconds long, and divided into 10 genres (blues, classical, country, disco, hiphop, jazz, metal, pop, reggae, and rock). The code is divided into the following main sections:

Importing libraries:
The code imports the necessary libraries such as librosa, numpy, matplotlib, and keras.

Mounting Google Drive:
This line of code mounts the Google Drive so that the code can access the dataset stored on Google Drive.

Displaying MFCC:
This function takes a music file as an input, loads the audio file using the librosa library, and then extracts Mel-frequency cepstral coefficients (MFCC) from the audio signal. The MFCCs are then displayed using the matplotlib library.

Extracting Features from Songs:
This function extracts features from the audio signal of a song. The function loads the audio file using librosa, extracts the MFCCs, normalizes the values between -1 and 1 by dividing them by the maximum value, and then flattens the MFCCs into a one-dimensional array of length 25000.

Generating Features and Labels:
This function processes all the audio files in the dataset and extracts features and labels. The features are extracted using the extract_features_song function, and the labels are extracted from the name of the file. The labels are then converted to one-hot encoding using the to_categorical function in keras.

Splitting Data into Training and Testing Sets:
The code splits the data into a training set and a testing set. The split is done randomly, and the training split is set to 80% of the data. The training and testing sets are created by stacking the features and labels into a single array and then splitting the array.

Creating the Model:
The code creates a Sequential model using keras. The model has two dense layers, the first with 100 nodes and the second with 10 nodes (one for each genre). The activation function for the first layer is relu, and the activation function for the second layer is softmax. The model is compiled using the adam optimizer and categorical_crossentropy loss function.

Training the Model:
The model is trained using the fit method in keras. The training input and labels are passed as arguments, along with the number of epochs (150) and the batch size (32). A validation split of 20% is also specified.

Evaluating the Model:
The model is evaluated using the evaluate method in keras. The testing input and labels are passed as arguments, along with the batch size (32). The loss and accuracy of the model are printed to the console.

Making Predictions:
The code uses the trained model to make a prediction on a single audio file. The audio file is loaded using librosa, and the features are extracted using the extract_features_song function. The features are then reshaped to a 2D array with a single row and passed to the predict method in keras. The predicted genre is printed to the console.

In summary, the code performs the following tasks:

Loads the GTZAN Genre Collection dataset from Google Drive.

Extracts audio features (MFCCs) from each song in the dataset.

Splits the dataset into a training set and a testing set.

Creates and trains a machine learning model to classify the genre of a song based on its audio features.

Evaluates the accuracy of the model on the testing set.

Makes a prediction on a single audio file.


