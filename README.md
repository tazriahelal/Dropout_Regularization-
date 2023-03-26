# Dropout_Regularization-
Dropout in Deep Learning

**What is dropout?**
Dropout refers to data, or noise, that's intentionally dropped from a neural network to improve processing and time to results.
The human brain contains billions of neurons that fire electrical and chemical signals to each other to coordinate thoughts and life functions. A neural network uses a software equivalent of these neurons, called units. Each unit receives signals from other units and then computes an output that it passes onto other neuron/units, or nodes, in the network.

<h2>At first, understand the problem </h2>
If we want to buy a dress for us, we will purchase a convenient size for our body. If we purchase a tight fitting or smaller size than our body size then it will make us uncomfortable,
even if we purchase a loose or bigger  size than our body then its look like a cloth hanging on skeleton. So we have to buy a right fit for our body. The problem of these overfitting and underfitting happens in machine learning  world as well. 
To tackle this problem we have **Regularization** technique.

When we have a train data and training a data or if we train the data too much then it might be overfit and when we get the actual test data for doing prediction it probably it will not performing well.

**Dropout Regularization** technique is the way to tackle this overfitting problem in a model in deep learning that's we are going to look into.
Here is picture of these problem - 

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F9942bc6159ded6c8c236e0d00925138a%2Foverfit.PNG?generation=1679846398806157&alt=media)

So now, suppose we have neural network like this- 

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F109d7a7a7aed52d3398f587d89889ad9%2Fneural.PNG?generation=1679846551398661&alt=media)

here we have  hidden layer but in real life there will be more hidden layer.  Let's say if our dataset is too big and if we run too many epochs then this neural network will try to overfit our dataset & it won't perform well on test dataset because now it cannot generalize well. 
One of the thing we can do is just randomly drop some neurons like this -

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F6446a2c498f967f3ff54b44ab6cc7ad5%2Fdropneurons.PNG?generation=1679846835807561&alt=media)

Here from the first layer drop these two which are marked in red and from the second hidden layer we also drop two neurons and we dropping them at random doesn't matter which neuron we drop also it is noticeable here I am dropping 50 percent because we can see we drop 2 out of 4. There is a factor which we can specify when we are creating dropout layer and we can say 0.5 means 50 percent or 0.2 means 20 percent or in other way, if we have 10 neurons then we will drop 2 neurons. Now we feed our first training sample in feed forward pass we calculate the error and when it comes to second sample we again choose randomly 2 different neurons and drop them. The drop out range rate is  50 50 in both the layers and when we will do that we are addressing the problem of overfitting

**Why will Dropout help with overfitting?**
1. It can't rely on one input as it is might be dropped out at random
2. Neurons will not learn redundant details of input

For example- We have this particular neuron 

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F390cc0b9c0390ae43b23e49efdce16bb%2Fneural.PNG?generation=1679848089153996&alt=media)

which is relying on 4 neurons in hidden layer but if we drop these 2 neurons at random

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F78723291b3ddb26fc22d1f78ae8f9c66%2Fdropneurons.PNG?generation=1679848175736382&alt=media)

now this neuron is not seeing the output from these 2 neurons so that way it doesn't create any bias hence this technique works.

After implement this technique it might look like this-

![](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F9494541%2F7f548ad0ce7dfe0139ecd8d3a4710821%2Fdropout.PNG?generation=1679848541662629&alt=media)

**Ref:** https://towardsdatascience.com/dropout-in-neural-networks-47a162d621d9
               https://www.techtarget.com/searchenterpriseai/definition/dropout
