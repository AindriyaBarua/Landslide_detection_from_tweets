# Natural_calamity_detection_from_tweets

This is done as part of my research internship at Amrita Center for Wireless Networks and Applications (https://www.amrita.edu/center/awna)

Twitter, a popular service for sending and receiving short, public text messages, can augment landslide response and the delivery of hazard information. Rapid detection and qualitative assessment of a natural calamities are possible because people begin sending public Twitter messages (tweets) within tens of seconds of experiencing a natural calamity. Here we present and evaluate natural calamities detection procedure that relies solely on Twitter data.The detections are fast; about 75% occur within two minutes of the origin time. This is considerably faster than sensor detections in poorly instrumented regions of the country. The tweets triggering the detections can also provide very short first-impression narratives from people who experience it.

The code and extensive datasets for diffferent natural calamities, namely, eathquake, landslides, floods, are given. The datasets consist of tweets, and labels identifying them as landslide, flood, earthquake or none respectively.

### WORK DONE TILL NOW:

1. Collected dataset: Basic cleaning and labeling of the dataset using regular expressions, removing symbols like @(usernames), #(hashtags), RT(retweet), normalizing capitalization
Cleaned dataset to form 33,955 lines of data: Processed using Numpy, ignoring bad lines
2. Label Encoded the labels: 
This is done to convert this kind of categorical text data into model-understandable numerical data.
3. Trained RNN model:
Humans don’t start their thinking from scratch every second. Traditional neural networks can’t do this, and it seems like a major shortcoming. 
Recurrent neural networks address this issue. They are networks with loops in them, allowing information to persist.
![image](https://user-images.githubusercontent.com/20969232/137827608-2ba22898-4679-4494-a712-a476696a506e.png)

In the above diagram, a chunk of neural network, A, looks at some input xt and outputs a value ht. A loop allows information to be passed from one step of the network to the next.  A recurrent neural network can be thought of as multiple copies of the same network, each passing a message to a successor.
Consider what happens if we unroll the loop:
![image](https://user-images.githubusercontent.com/20969232/137827558-5d145eff-8389-4d78-8cab-a49be995ed3d.png)

This chain-like nature reveals that recurrent neural networks are intimately related to sequences and lists. They’re the natural architecture of neural network to use for such data. And they certainly are used! In the last few years, there have been incredible success applying RNNs to a variety of problems: speech recognition, language modeling, translation, image captioning… The list goes on. Thus, RNN seems to be the right choice for our task.

In our RNN model, the output from the previous step are fed as input to the current step
Following hyperparameters have been tested: activation='sigmoid', 
loss function= 'categorical_crossentropy', optimizer='adam', metrics = 'accuracy'

5. Fitted model

## RESULT:
The current accuracy achieved is 62% We need to do further hyper-parameter tuning to increase the accuracy.

## FUTURE WORK:

Hyperparameter tuning of RNN model to increase accuracy
Write codes for CNN, LSTM, GRU, and other combinations of algorithms and run hyperparameter tuning on them to find the best accuracies

