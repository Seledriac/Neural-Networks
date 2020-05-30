
* This repository contains a network module, with a class which models a neural Network you can train in a supervised learning paradigm with the standard SGD (Stochastic Gradient Descent)/backpropagation algorithm method

* How to setup your testing environment :
    - see "practical_commands.md" 

* Requirements :
    - python 3
    - numpy
    - matplotlib
    - Pillow
    - ImageMagick

* How to use the network module :
    - Import it : "import network"
    - Create a network instance, specifying its identifier, its shape with a list of numbers, the activation function, and the output regulation function :
    	- The first and last number of the list will always respectively describe the input and output layers of the created network.
        - There are 3 possible activation functions : sigmoid, relu, and tanh
    - Train your network, specifying your hyper-parameters, using "net.SGD(training_data, epochs, mini_batch_size, learning_rate, test_data, dropout_value)"
    	- The training/test/validation data must be lists of tuples of a numpy vector x and a digit y : [(x1 , y1), ... ,(xn , yn)] (where n is the training/validation data-set's size)
    	- The numpy vector x is the input given to the network, and y is this expected output
    - Save your trained model as a serialized Network object in a file
    - Track the performances of your model during training, and after training, try to predict with the model on custom examples
    - Use your model to solve a problem :)

* Usage examples :
    - handwritten digits recognition : we use the mnist dataset : 50000 training images, 10000 test images, and 10000 validation images

* Side notes :
    - the data used for the hdr (handwritten digits recognition) models is loaded from the mnist database by the "mnist_loader" library
    - the custom paint test images are 256-RGB format .bmp files
    - WARNING : the performance on the mnist dataset =/= the performance on custom handwritten digits
    - WARNING : the only currently correctly working combination for regu/activation function is sigmoid with no regularization
    - There is a nasty matplotlib deprecation warning at each epoch if you display the weights. You can safely ignore it
    - The "test_hd.py" script trains a model, stores it in the "models/hd_recognition" folder, and the tracked training process in "trainings". It can also live display the weights training, and once the training is done, let the user use the model to predict on custom examples.
    - The models are saved in the "models" folder, and the trainings in the "trainings" folder

* Warning :
    - It is not recommended to close the model's prediction window during the execution of the program --> its best to press "n" to terminate the program

This library was inspired by the Michael Nielsen's e-book : Neural Networks and deep learning (http://neuralnetworksanddeeplearning.com)
    
	
