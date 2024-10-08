# Create-Your-Own-Image-Classifier-project
In this project, we first develop an image classifier using PyTorch pre-trained model from trochvision, then convert it into a command line application.
The project is broken down into multiple steps:
Load and preprocess the image dataset
Train the image classifier on your dataset
Use the trained classifier to predict image content
# Data Description
The dataset is split into three parts, training, validation, and testing. For the training, you'll want to apply transformations such as random scaling, cropping, and flipping. This will help the network generalize leading to better performance. You'll also need to make sure the input data is resized to 224x224 pixels as required by the pre-trained networks.

The validation and testing sets are used to measure the model's performance on data it hasn't seen yet. For this you don't want any scaling or rotation transformations, but you'll need to resize then crop the images to the appropriate size.

The pre-trained networks you'll use were trained on the ImageNet dataset where each color channel was normalized separately. For all three sets you'll need to normalize the means and standard deviations of the images to what the network expects. For the means, it's [0.485, 0.456, 0.406] and for the standard deviations [0.229, 0.224, 0.225], calculated from the ImageNet images. These values will shift each color channel to be centered at 0 and range from -1 to 1.
# Building & Training A classifier 
The script is designed to train a deep neural network to classify flower species. It utilizes the VGG16 architecture, a model pre-trained on the ImageNet dataset, and adapts it to classify 102 different flower categories.
# # Model Description
The script modifies the VGG16 model by replacing its classifier with a new one tailored to our specific task:

An input layer that matches the output features of VGG16.
Two hidden layers with ReLU activations and dropout for regularization.
An output layer with 102 units corresponding to the flower classes, using log softmax for classification.
# Building the command line application
Now after building and training a deep neural network on the flower data set, it's time to convert it into an application that others can use. the application should be a pair of Python scripts that run from the command line. For testing, we used the checkpoint saved in the first part.
it includes three files:
1- train.py 
2-run_utlis 
3-test.py
