# Definition 
*While the particular design or “architecture” of CNNs may vary, they are built using a common set of basic elements and share a similar overall structure. The first layer is a convolutional layer, comprising several convolutional filters applied to the image in parallel. These filters act as a set of feature extractors−their outputs are known as feature maps.* [^1] 

*Most CNN architectures are built by stacking several convolutional layers and pooling layers on top of one another. 
This enables the CNN to learn a set of low-level features in early layers, then hierarchically group them into high-level features in later layers. 
After this, the final set of feature maps are passed to a set of fully connected layers that perform the classification. 
As in a traditional neural network, every neuron in a fully connected layer is connected to each of the outputs of the previous layer. 
Multiple fully connected layers can be stacked on top of one another to form deep architectures. 
The final (visible) fully connected layer of neurons is trained to produce class scores for each class. 
If sigmoids are used as activation functions for each neuron in this layer, the class scores can be interpreted as class probabilities.* [^1]*
### Convolution
More specifically, the analytical expression of the convolution within the CNN architecture is given in Eq. (1);
$$ h^{(n)}_j = \sum^K_{k=1} h^{(n−1)}_k * w^{(n)}_{kj} + b_j^{(n)} , \tag{1}$$
where 
- $h^{(n)}_j$ is the $j$th feature map output in the hidden layer $h^{(n)}$ , 
- $h^{(n−1)}_k$ is the $k$th channel in the hidden layer $h^{(n−1)}$ , 
- $w^{(n)}_{kj}$ is the $k$th channel in the $j$th filter in $h^{(n)}$ 
- and $b^{(n)}_j$ is its corresponding bias term
### Pooling
*A convolutional layer is typically followed by a pooling layer whose purpose is to reduce the dimensionality of the feature maps.
This reduces the computational cost associated with training the network and decreases the chances of over-fitting. 
Pooling layers operate by dividing feature maps into small, possibly overlapping windows, then retaining only single value per window.
Two of the most popular forms of pooling are max-pooling and mean-pooling which retain the maximum and mean value of each window respectively.* [^1]

# Background 

*Convolutional neural networks first appeared in the late 1980’s with the handwritten zip code recognition [13] as an extended version of artificial neural networks (ANN). They have been also applied to handwritten digit recognition[11], images, speech and time series data [12]. Instead of relying on hand-designed features, CNNs are able to adaptively learn classification features* [^1]
###### references
[^1]:[[DL new conv]]

