# 14. Data Augmentation
[14. Data Augmentation | Keras (2019) - YouTube](https://youtu.be/yYqAvlkRwUQ)

## Video Notes
* Data used in this project is CIFAR which contains slightly bigger, more diverse data than MNIST

* Big Idea: You can get more training data by augmenting existing data

* Augmenting isn’t always useful. For example, it doesn’t make sense to rotate upright-camera images since we care about the vertical axis 

* Baseline Implementations: Normalize images to values between 0 and 1 and use non-augmented data = ~63 % with 50k training examples

* Function to augment: ImageDataGenerator. It pulls in batches of training data and lets us modify the data as it comes in (strech, squeeze, rotate, mirror images) 
 
* Another benefit of this function is it helps with saving memory since you don’t load all the data right away

* Validation accuracy increases by apply thing this techniques! The model generalizes better

* In language problems, take a word translate to another language and retranslate it back

## Useful Links
[Image Preprocessing - Keras Documentation](https://keras.io/preprocessing/image/)