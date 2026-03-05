# Lab 8: Feed Forward Neural Networks

**Write the answers all questions in markdown cells (or code cells if appropriate) in the `work.ipynb` notebook file.  Include all relevant code.**

**Lab questions are repeated in the `work.ipynb` notebook file.  If there are any discrepancies between this file (Readme) and the notebook file, use the version of the question in the notebook file.** 

**Instructions:**
- Complete all code and analysis in this notebook
- Put all written responses directly in this notebook (use markdown cells when appropriate)
- Keep plots labeled and readable
- Submit both `work.ipynb` and a PDF copy of it
- Push your final files to GitHub

## Part 1: Understanding Neural Networks

The [TensorFlow playground](https://playground.tensorflow.org/) is a handy neural network simulator built by the TensorFlow team. In this exercise, you will train several binary classifiers in just a few clicks, and tweak the model’s architecture and its hyperparameters to gain some intuition on how neural networks work and what their hyperparameters do. 



*The "default" neural network is the one that is available when you first visit the site:*
- Data: Circles (top left dataset)
- Ratio of training to test data: 50%
- Noise: 0
- Batch size 10
- Features: X1 and X2
- Layers: 2 hidden layers
  - 4 neurons in first hidden layer
  - 2 neurons in second hidden layer
- Learning rate: 0.03
- Activation: Tanh
- Regularization: None
- Regularization rate: 0
- Problem type: Classification
---
1. **The patterns learned by a neural net.** Try training the default neural network by clicking the Run button (top left). 

- How do the patterns learned by neurons in the first hidden layer differ from those learned by neurons in the second layer?
- Add third hidden layer with two neurons.  What do you notice about the patterns learned in each of the hidden layers?  
- Based on your observations, explain how adding hidden layers might impact the model's ability to classify more complex datasets. 
---
2. **Exploring the Learning Rate.** Go back to the default network with 2 hidden layers.  Train the model again and notice how quickly it finds a good solution. 

- Approximate how long (either in seconds or in number of epochs) it took the model to find a stable solution.
* Reset the model by clicking the Reset button next to Play button.  Change the learning rate to 0.003.  What do you notice about the time it took to find a solution as compared to the 0.03 learning rate?
- Reset the model again and change the learning rate to 3.  Run the model for at least 2000 epochs.  Was the model able to find a solution?   Do you think the model will converge eventually if you just let it run for a long time?  Why or why not?
- What are the consequences of a learning rate that is set too high or too low?

---
3. **Activation functions.** Reset the model and change the learning rate back to 0.03.  Train the default network again.  

* Reset the model and change the activation function to ReLU.  How does the time to find a solution and the decision boundary compare to the Tanh activation?
* Reset the model again and now change the activation function to Sigmoid.  How does the Sigmoid activation function compare to ReLU and Tanh? 
* Why do you think ReLU is generally the preferred activation function in modern neural networks? 
---
4. **Impact of Regularization.** Set the learning rate to 0.03 and use the ReLU activation function.  Also change the dataset to the "blobs" data (lower left) and increase the Noise to 40.  Create a large neural network with 6 hidden layers with 6, 7, 8, 7, 6, 5 neurons in each of the layers, respectively. 

* Let the model run for at least 1000 epochs.  What do you notice about the decision boundary? 
* Now add L2 Regularization with a Regularization Rate of 0.01.  Again let the model run for at least 1000 epochs. How does the regularized model compare with the unregularized model? 
* What happens if you increase the regularization rate too much (for example, to 0.3)? 
---

5. **What happens when neural nets are too small.** Return to the [default network](https://playground.tensorflow.org/). 

- Now set the model so that it only has one hidden layer with two neurons.  Is your model able to find a good solution? 
- Try adding more layers, but limit the number of neurons to two.  How many layers do you need to find a good solution or does your model struggle even with the maximum number of hidden layers (max is 6 hidden layers)? 
- Return to a model with only one hidden layer but this time use three neurons. Is your model about to find a good solution now? 
 - Try a more complicated dataset.  Use the spiral data (lower right).  Is a network with 1 hidden layer and 3 neurons large enough to find a solution?
 - What happens if you add more neurons.  Train your model with 1 hidden layer and 8 neurons.  Comment on how you feel the model performed.  
 - Experiment with the number of hidden layers and number of neurons per layer.  Can you find a combination that is able to find a stable and suitable solution?  If so what was it? (*I was able to find a network that work reasonably well.*)
 * Comment on your findings about how the number of hidden layers and the number of neurons contribute to the model's performance.
 ---
 6.  **Explore on your own.** Spend some more time playing with the different options in playground.  Write a few sentences about something you learned or gained a better understanding of with this problem.  

 ---
 ---
## Part 2:  Musical Emotion

For this problem use the [music_emotion.csv](https://github.com/rhodes-byu/stat-486/raw/refs/heads/main/data/music_emotion.csv) to build a classifier that predicts whether the music in the sound clip is happy or sad.  This data is a subset of [this kaggle data](https://www.kaggle.com/datasets/akhilnshukla/datasetfeaturesmfccs).  The features in the dataset are various audio features and [MFCC features](https://en.wikipedia.org/wiki/Mel-frequency_cepstrum) for various musical clips.  The audio and MFCC features were extracted using the [librosa library](https://librosa.org/doc/latest/index.html) on the original wav files containing the musical clips. 

---
(a.) **Process the data.**
- Split into a training and a test set with 20% of the data in the test set.
- Transforms the features to the same scale 
    * Remember to fit the scaling transformer to the training data only, then apply the scaling transformer to the training and the testing data

---
(b.) Using  `MLPClassifer` from `sklearn`, build an ANN with 2 hidden layers (100 and 50 nodes, respectively) with the ReLU activation function and the "adam" solver.  
*- Report your your training accuracy, testing accuracy, testing F1 score, and the number of epochs (`n_iter_`) it took for the model to run.
*- State whether there is any evidence of overfitting.

---
(c.) Repeat part (b.), but this time add in early stopping.
* Report your your training accuracy, testing accuracy, testing F1 score, and the number of epochs (`n_iter_`) it took for the model to run this time.
* State whether there is any evidence that the model isn't overfitting as much.

---
(d.) Using `Keras`, build the same model from part (b.) with the ReLU activation function and adam solver (optimizer). Run the model for 100 epochs.
* Report your your training accuracy, testing accuracy, and testing F1 score.
* State whether there is any evidence of overfitting.

* *You'll need to use `binary_crossentropy` for the loss function, adjust the input and output layer sizes to match the data, and adjust the output activation function.*

---
(e.) Repeat part (d.), but this time add in early stopping (as a callback).
* Report your your training accuracy, testing accuracy, testing F1 score, and the number of epochs it took for the model to run this time.
* State whether there is any evidence that the model isn't overfitting as much?
