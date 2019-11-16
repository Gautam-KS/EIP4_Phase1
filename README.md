/Convolution/ - A kernel or filter or a odd count martix on an input image bringups up a container of specfic information, that means varying channels. The mask slides over from top left to bottom right and during each sliding operation the middle value of of the input is replaced by sum of product of corresponding cells in matrix.


/Filters/Kernels/ - They are used to extract features of images. In convolutional neural network horizontal and vertical edges are extracted using Filters/Kernals.


/Epochs/ - 1 epoch is going into the entire data once and backpropagation is done.


/1x1 Convolution/ - when 1x1x3 filter convolves on 6x6x3 ---> 6 x 6 x 1 //depth is made one 


/3x3 Convolution/ - After 3x3 convoution the input looses 2 pixels. For example for a 4 x4 image when it is convolved on 3x3 filter the dimention of the output is 2x2.


/Feature Maps/ - Feature maps are the outcomes of convolution operation. The number of feature maps depends on the number of filters convolving the input.


/Activation Function/ - Activation function is to squash the real wold data that is linear data into non linear one. Activation function is a linear to non linear mapper.


/Receptive Field/ - In CNN we stack a series of convolutional layers to get meaninfful feature representation. The receptive field of the last layer must be equal to the size of the object.   

/score/ [0.04254276682498166, 0.9864]
