# 15. Batch size and learning Rates in CNNs (2019)

## Video Notes

[15. Batch size and learning Rates in CNNs (2019)](https://youtu.be/ZBVwnoVIvZk)

• This video is the sequel to one on CNNs that can be found [here](https://youtu.be/wzy8jI-duEQ)

• The focus of this video is Learning Rate and Batch size

• It’s easy for beginners to get stuck in a batch size/learning rate optimization loop, but it should not be the first thing to tackle. It doesn’t matter that much except to train faster or squeeze out the last bit of performance

• Learning Rate is the size of the step the model takes to find optimal weights
— Really low -> takes long to find best set of parameters
— Really high -> jumps over the best set of parameters or get into areas of numerical instability

• Batch size is the number of examples the model looks at before deciding the direction to send weights
— Really small -> could add a lot of noise
— Really large -> not enough noise to learn, but can train faster (especially if you have a gpu)
— Too big of a batch size may cause gpu to over-load memory
— Too small may take long to train model

• The demo in the video uses the CIFAR-10 dataset

• First step as usual is to normalize the data and one hot encode the labels

• Default: Adam learning rate is set to 0. 001

• Test Model: In the experiment, the test Iearning rate is set to 0.0001

* Test 1: Both models are ran in parallel and we can see in the wandb graph that training for a smaller learning rate takes longer

• Test 2: The test model learning rate is set to 0.1 and we can see that the accuracy stays around 10%, and log(loss) is massive at ~ 14.5. There are 10 classes, so the model is guessing

• Default Model: The batch size is set to 32

• Test 3: Batch size is set to 128 on the test model, which takes longer to load to memory, but learns a lot faster.

• When changing batch size, there is trade off between the memory load time and learning speed

• Rule of thumb: Batch size and learning rate should be scaled the same. If batch size goes from 32 -> 128, learning rate should go from .001 -> .004

• Test 4: The CNN trains faster with about the same accuracy as baseline!

• Useful Trick: reduce Ir once the performance plateaus. Can use a Keras callback, [ReduceLROnPlateau](https://keras.io/callbacks/#reducelronplateau)

• At 35 epoch the model stopped improving and the learning rate trick kicked in which resulted in improved performance

* Take away: The defaults are pretty good, but can use these hyper parameters to squeeze out more performance.

* Additionally, it is good practice to use ReduceLROnPlateau for long time training model.
