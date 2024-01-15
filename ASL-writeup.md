Yirui Song
yfsong@usc.edu

This project uses computer vision to classify images of the 26 letters and 3 non-character signs that make up the ASL alphabet. 

Dataset:
The dataset I used to train this model is the Kaggle ASL Alphabet dataset that includes 29 classes, one for each of the letters in the ASL alphabet along with classes for delete, space, and nothing. The dataset contains 87,000 labeled images that are 200 x 200 pixels. For data preprocessing, I rescaled the images so that pixel values will only have a value between 0 and 1 inclusive to reduce model sensitivity to large input pixel values and to ensure smooth incorporation of the pre-trained VGG16 model. 

Model Development and Training:
I decided to split the data with 0.65 for training and 0.35 testing so that there is a larger test dataset to see the model’s performance in classifying images with different hand positioning in the image, image brightness, and many other attributes. The model uses the pre-trained VGG16 as a base model and employs transfer learning to train it on this specific dataset. VGG16 is a CNN with 13 convolutional layers, 5 max pooling layers, and 3 dense layers. Softmax is used as the activation function and dropout layers are included to prevent overfitting. Adam is used as the optimizer with a learning rate of 0.001. Categorical cross entropy is used as the loss function for this classification project. The model trained for 10 epochs with a batch size of 64.

Model Evaluation and Results:
The model is evaluated on the test accuracy along with a loss plot and an accuracy plot. The model showed a test accuracy of approximately 0.91 and the test loss was approximately 0.07. The results show that the model is performing well, but still has room for improvement. 

Discussion:
My model is decently successful in classifying the different ASL signs from the images. This project has great potential to better connect the people that communicate using ASL with those that do not understand ASL. The model can be implemented in translators to mediate conversations between people and in forms of media as well such as live interpretation of news broadcasts and more. However, as this model was trained on this Kaggle dataset which only included images of the same person signing in the same room with slight variances in other image properties, the model currently is not trained to account for slight differences in the way different people sign the ASL alphabet, different backgrounds that could be distracting to the model, and different skin tones of the signer that could confuse the model. All of these are attributes I would make sure are incorporated into my dataset if I were to move forward with this project to ensure its ability to generalize its predictions in real world situations with little to no bias. With more time, I would also want to continue experimenting with different hyperparameters, batch sizes, and training-testing split ratios to improve the accuracy of the model. 
