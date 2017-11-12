# ann-from-scratch
### Please use the link provided in github to view the file with the external viewer *nbviewer*

Build an Artificial Neural Network from scratch to learn XOR.

XOR's truth table is the following :

| A | B | Result |
|---|---|--:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

The purpose is to send **(A,B)** data as input into the model to train it with *feed forward* et *back propagation* algorithms.

#### Feed forward

Each input is spread through all the layers, one by one. The next layer output is the the following computed value :
<img src="http://latex.codecogs.com/gif.latex?g(W\cdot&space;X&plus;bias)" title="g(W\cdot X+bias)" />

where :
- g is the activation function (such as sigmoid or tanh)
- W is the weights vector of the layer
- X is input vector or the output of the previous layer
- bias is the bias of the layer

#### Back propagation

Once each input has been spread, the model must propagate the error to the previous layer to update each weight.

To update a weight, the error is propagated as following :
<img src="http://latex.codecogs.com/gif.latex?\frac{\partial&space;L}{\partial&space;w_{ij}}=\frac{\partial&space;L}{\partial&space;g'}\cdot\frac{\partial&space;g'}{\partial&space;output}\cdot\frac{\partial&space;output}{\partial&space;w_{ij}}" title="\frac{\partial L}{\partial w_{ij}}=\frac{\partial L}{\partial g'}\cdot\frac{\partial g'}{\partial output}\cdot\frac{\partial output}{\partial w_{ij}}" />

This weight is thus updated :
<img src="http://latex.codecogs.com/gif.latex?w_{ij}=-lr\cdot\frac{\partial&space;L}{\partial&space;w_{ij}}" title="w_{ij}=-lr\cdot\frac{\partial L}{\partial w_{ij}}" />

where LR is the learning rate.

#### Training

To better train the model, all the inputs are spread many times. Each time is called an epoch. For each epoch, I compute the error the *Mean Square Error* loss function.

Here is the **error evolution through learning** :

![Result](https://raw.githubusercontent.com/cheillanju/ann-from-scratch/master/error.png)
