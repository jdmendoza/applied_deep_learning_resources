# 13. Keras Speech Recognition
[13. Keras Speech Recognition (2019) - YouTube](https://youtu.be/Qf4YJcHXtcY)

## Video Notes
* Arguably the field that got people interested in deep learning

* Objective of the project is to classify sound files as words

* Approach: Take wavfiles -> apply transformation -> feed into neural networks

* MFCC for feature extractions. Roughly, it buckets of frequencies and time and converts wav files into images

* Each sample is an image (audio spectrogram) with a label

* Initial approach: flatten image and feed into dense network

* Second: convolutional neural network, A 2d conv is reasonable since adjacent pixels have meaning and are related. This approaches gets over 90% accuracy 

* Third: Add additional 2d conv net. This gives slightly better performance ~94% accuracy.

* Fourth: Dropout for overfitting, helps increase validation accuracy

* Fifth: LSTM and GRUs may be better for variable length files, non-image based speech recognition. But can still try. After trying, it is significantly worse, but may be due to how the problem was set up (images)

## Useful Links

[MFCC - Mel Frequency Cepstral Coefficent](http://practicalcryptography.com/miscellaneous/machine-learning/guide-mel-frequency-cepstral-coefficients-mfccs/)
Tutorial for algorithm that is used to turn sound data to features


## Video Feedback 
* Would like to see a video on wandb workflow, best practices, how to use the tool most efficiency in prototyping


