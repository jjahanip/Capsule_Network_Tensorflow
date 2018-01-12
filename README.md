# Capsule_Network_Tensorflow
Capsule Network implementation in Tensorflow based on Geoffrey Hinton's paper [Dynamic Routing Between Capsules](https://arxiv.org/abs/1710.09829).

> **Notes:**
I started learning about CapsNet by reading the paper and watch Hinton's talk (like [This](https://www.youtube.com/watch?v=rTawFwUvnLE&feature=youtu.be)). While they are fascinating, they give very limited information (most likely due to papers page limitation amd talk's time limitation). So to get the detailed picture, I watched many videos and read many blogs. My suggestions to fully master the Capsule Network's theory are the following sources (of course other than Hinton's paper):
> 1. Max Pechyonkin's [blog series](https://medium.com/ai%C2%B3-theory-practice-business/understanding-hintons-capsule-networks-part-i-intuition-b4b559d1159b)
> 2. Aurélien Géron's videos on [Capsule Networks – Tutorial](https://www.youtube.com/watch?v=pPN8d0E3900&t=297s) and [How to implement CapsNets using TensorFlow](https://www.youtube.com/watch?v=2Kawrd5szHE)


This code is inspired from Liao's implementation [CapsNet-Tensorflow](http://yann.lecun.com/exdb/mnist/) with changes applied to add some features as well as making the code more efficient.

The main changes include:
> 1. The Capslayer class is removed as I found it to be unnecessary at this level. This makes the whole code shorter and more understandable.
> 2. Hard-coded values (such as the number of capsules, hidden units, etc.) are all extracted and are accessible through ``config.py`` file. Therefore, making changes in the network is much more convenient.
> 3. Summary writers are modified. Liao's code writes the loss and accuracy only for the final batch after a certain desired steps. Here, it's modified to write the average loss and accuracy values which is what we should exactly look at.
> 4. __Masking__ procedure is modified. This code is much easier to understand how the masking changes between trai and test. 
> 5. __Visualize__ mode is added which helps to plot the reconstructed sample images and visualize the network prediction performance. 



## Requirements
- Python
- NumPy
- [Tensorflow](https://github.com/tensorflow/tensorflow)>=1.3
- tqdm (for displaying training progress info)
- scipy (for saving images)



