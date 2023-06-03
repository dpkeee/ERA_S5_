

# <h1 align = "center">Session 5 Assignment</h1>

# FIRST NEURAL NETWORK

In this assignment, we are trying to make the code  modular. There are 3 files 
1. Models.py 
2. Utils.py
3. S5.ipynb




## Models.py 
### Intialization

- CONV1 -  Convolution layer has  1 input channel and 32 output channels. A kernel of size 3*3 is convolved on the input image.
- CONV2 -  Second Convolution layer has 32 input channels(from previous layer)  and 64 output channels. A kernel of size 3*3 is convolved on the out of the previous conv layer .
- CONV3 -  Third  Convolution layer has 64  input channels(from previous layer)  and 128 output channels. A kernel of size 3*3 is convolved on the out of the previous conv layer .
- CONV4-   Fourth  Convolution layer has  128  input channels(from previous layer)  and 256  output channels. A kernel of size 3*3 is convolved on the out of the previous conv layer .
- Fc1 - First Fully Connected layer -  CONV4 layer's output  is  flattened so that it can be sent as input to Fully connected layer.
- Fc2- Second Fully Connected layer -  Gets input as input to Fully connected layer with  10 outputs .

## Error Calculation
- The errors are due to the differences in the expected outputs from the neuron and the received outputs
- Criterion Loss Fucntion is used for calculating the Error 


  
### Data Augmentation
- The input images were randomly rotated by 10 degress to introduce slightly more variance and have the model generalize better.
- Transforms.RandomApply([transforms.CenterCrop(22), ], p=0.1): This transformation randomly applies a center crop of size 22x22 to the input with a probability of 0.1. This operation helps to introduce some randomness and diversity in the data.

-Transforms.Resize((28, 28)): This transformation resizes the input to a fixed size of 28x28 pixels. This is a common step in image preprocessing, ensuring that all images have the same dimensions.

-Transforms.RandomRotation((-15., 15.), fill=0): This transformation randomly rotates the input image by a degree between -15 and 15 degrees. The fill=0 argument specifies that any areas created by the rotation that are not filled by the original image should be filled with zeros.

-Transforms.ToTensor(): This transformation converts the input image from a PIL.Image or numpy.ndarray format to a PyTorch tensor. It also scales the pixel values from the range [0, 255] to [0, 1].

-Transforms.Normalize((0.1307,), (0.3081,)): This transformation normalizes the input tensor by subtracting the mean (0.1307) and dividing by the standard deviation (0.3081). The normalization helps in achieving faster and more stable training.

      transforms.RandomRotation(10)

- Input data was also normalized with the mean and standard deviation of the input dataset.

      transforms.Normalize((0.1307,), (0.3081,))
      





