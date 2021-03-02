# ChatBot
Chatbots are nothing but an intelligent piece of software that can interact and communicate with people just like humans.
All chatbots come under the NLP (Natural Language Processing) concepts.

Step 1. Import Libraries and Load the Data
Create a new python file and name it as train_chatbot and then we are going to import all the required modules. After that, we will read the JSON data file in our Python program.

Step 2. Preprocessing the Data
The model cannot take the raw data. It has to go through a lot of pre-processing for the machine to easily understand. For textual data, there are many preprocessing techniques available. The first technique is tokenizing, in which we break the sentences into words.

By observing the intents file, we can see that each tag contains a list of patterns and responses. We tokenize each pattern and add the words in a list. Also, we create a list of classes and documents to add all the intents associated with patterns.

In the end, the words contain the vocabulary of our project and classes contain the total entities to classify. To save the python object in a file, we used the pickle.dump() method. These files will be helpful after the training is done and we predict the chats.

Step 3. Create Training and Testing Data
To train the model, we will convert each input pattern into numbers. First, we will lemmatize each word of the pattern and create a list of zeroes of the same length as the total number of words. We will set value 1 to only those indexes that contain the word in the patterns. In the same way, we will create the output by setting 1 to the class input the pattern belongs to.

Step 4. Training the Model
The architecture of our model will be a neural network consisting of 3 dense layers. The first layer has 128 neurons, the second one has 64 and the last layer will have the same neurons as the number of classes. The dropout layers are introduced to reduce overfitting of the model. We have used the SGD optimizer and fit the data to start the training of the model. After the training of 200 epochs is completed, we then save the trained model using the Keras model.save(“chatbot_model.h5”) function.


Step 5. Interacting With the Chatbot
Our model is ready to chat, so now let’s create a nice graphical user interface for our chatbot in a new file. You can name the file as gui_chatbot.py

In our GUI file, we will be using the Tkinter module to build the structure of the desktop application and then we will capture the user message and again perform some preprocessing before we input the message into our trained model.

The model will then predict the tag of the user’s message, and we will randomly select the response from the list of responses in our intents file
