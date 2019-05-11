# 12. One Shot Learning
[12. One-Shot Learning (2019) - YouTube](https://youtu.be/H4MPIWX6ftE)

## Video Notes
* Used to classify things the neural network has never seen in training

* Technique is known as one-shot, zero-shot or few shot if there are a couple examples

* Big Idea: Rather than train on single instances of an object, train on pairs of objects i.e. are they the same thing?

* This is done so that the classifier may be able to generalize on things outside of training data

* This approach can be used on video data, audio data, tons of different examples

* The crux for this technique is the function make_pairs:  it iterates through the training data and randomly appends images. Each training sample is an array of two images with a label. If they same category make label 1, if different make it label 0

* Naive Approach: Use one dense layer per pair of images and concatenate. This is then fed to a dense layer which outputs a 0 or 1

* Accuracy increases (better than random), but is not very good. Can use weight sharing!

* Change: Flatten the images and concat in to a dense layer

* To improve further, we can use a siamese network - link below

* Euclidean distance function measures sum of square error between the image vectors

* A Lambda layer is added to the model that applies euclidean distance function to the image vectors

* Potential application: apply this technique to handwriting data like omniglot, try to generalize to other characters that the network may not have seen before

## Useful Links
[Siamese Neural Networks for One-Shot Image Recognition](https://www.cs.cmu.edu/~rsalakhu/papers/oneshot1.pdf)
Paper that describes the one shot learning network

[Merge Layers - Keras Documentation](https://keras.io/layers/merge/)
Keras documentation page to read about concatenation 

[Core Layers - Keras Documentation](https://keras.io/layers/core/)
Keras documentation page to read about lambda layer

[GitHub - brendenlake/omniglot: Omniglot data set for one-shot learning](https://github.com/brendenlake/omniglot)


