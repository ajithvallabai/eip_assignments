**Result of DNN:**

Accuracy = 99.03%

**Question and Answer**

1.**Convolution**
Convolution is the process by which two function combine to give output.Example input and kernel(feature extractor) combine to provide the required output.

2.**Filters/Kernels:**
Kernels are feature extractor which can extract required feature from a given image.

3.**Epochs:**
Epoch is the process of forward and backward propagation performed as a operation.Training dataset is loaded and forward and backward propagation is carried over for one epoch.A epoch can contain one or more batches ( input dataset is processed as batch).

4.**1x1 Convolution :**
1x1 convolution maps all input channel pixel to output pixel . it is often used to reduce the depth channels

5.**3x3 Convolution:**
When an input image is combined/multiplied/operated with a 3x3 filter it is called 3x3 convolution.it is used to extract features in a image . 
eg: used for edge detection ,sharpening ,blur etc..

6.**Feature Maps:**
Feature map or activation map is the output activations for a given filter.When an input image is operated with a filter it produces feature map.

7.**Activation Function:**
Activation function is function which is used to decide whether specific neurons should be activated or not by calculating weights and biases.


8.**Receptive Field:**
Receptive field is the region of interest where cnn is looking at.if a image is 224x224 then receptive field of neural network also should be 224x224 to make the network to percieve entire image.
