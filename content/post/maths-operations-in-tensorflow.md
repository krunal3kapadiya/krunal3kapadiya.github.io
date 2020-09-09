---
author: Krunal Kapadiya
title: "Maths operations in Tensorflow"
date: 2018-02-09
description: Maths operations in Tensorflow
math: true
---


Machine Learning is making a boom in the tech world, specifically for the developers and for the talented data scientists. We will never learn new things if we don’t start it from the bottom. In this article, we are striking at the root of Tensorflow. After reading this article you will be able to perform some basic mathematical operations in Tensorflow.

# Where it starts?

Tensorflow was published in November 2015 by the Google Brain Team and currently Tensorflow 1.5 version is the latest release with Tensorflow lite, announced for mobile and embedded devices.

> Tensor is a multidimensional array. Nodes in the graph (aka ops or operations) perform mathematical computations and produce the tensors.

Have you installed Tensorflow on your PC yet? Not yet? Click the [link](https://www.tensorflow.org/install/)  and follow the instructions.

For running the following code you will need:

-   Python 3.5
-   Tensorflow
-   Anaconda IDE

If you are getting errors while installing it, post it on [StackOverflow](https://stackoverflow.com/).

To check the current version of Tensorflow run the following code in the command line:

Above code will print the version of Tensorflow.

# Let’s begin it.

I assume that you have correctly installed above listed tools and now  `activate tensorflow`.

## Hello World

Now let’s understand the code, we have imported  `print_function`  and  `tensorflow`  libraries. Created the constructor of the constant class form tensorflow and added the values to it  `Hello TensorFlow!`  In tensorflow session, we have run the node of constant op. That’s it??

As I am running this code in Anaconda command prompt, it is not necessary to activate the Tensorflow for basic operations.

Output:

![Image for post](https://miro.medium.com/max/60/1*8am5q181sXjku4hSOdEiQA.png?q=20)

![Image for post](https://miro.medium.com/max/1680/1*8am5q181sXjku4hSOdEiQA.png)

## Arithmetic operations

We have learned to make the constant node and printing the values in it. Next is to performing arithmetic operations.

We have created the 2 constant constructors, assigned the values in a and b. In the Tensorflow session, we are running calculating the operations in it. the values returned by the constants represents the output of the constant ops. Need Explanations in above code….???

Output:

![Image for post](https://miro.medium.com/max/60/1*pc_3OTOzLyV6Y0QBtMMl0w.png?q=20)

![Image for post](https://miro.medium.com/max/1685/1*pc_3OTOzLyV6Y0QBtMMl0w.png)

In the above code snippet we have added the values at the initialization time, now we are writing the code to perform those operations at the run-time.

**Adding values in running session**

We have defined types of variables in  `tf.placeholder`  to feed the data when the session is running, by  `feed_dict`  we have added data in the Tensorflow session.

## Matrix manipulation

Source giphy.

We have implemented basic arithmetic operations and now time is to the same with the matrix.

We have created two matrices, in  `matrix1`  we have created one 1x2 matrix, in  `matrix2`  we have created a 2x1 matrix. In above code,  `matmul`  will return the multiplication of the two matrices.

> Output

![Image for post](https://miro.medium.com/max/60/1*QeJ5BFRiwvgv51uIISulFA.png?q=20)

![Image for post](https://miro.medium.com/max/1686/1*QeJ5BFRiwvgv51uIISulFA.png)

From above we can declare the variables and perform the basic maths operations in it. Run the above code and be confident in it.

> The programmer who writes code to learn, learns quickly.

Next step will be to understand maths operations. How mean, median and mode works for the data and in graph.

----------

# References:

-   [Installation guidelines](https://www.tensorflow.org/install/)
-   [Placeholder](https://www.tensorflow.org/versions/r0.12/api_docs/python/io_ops/placeholders)
-   [Maths operators](https://www.tensorflow.org/api_guides/python/math_ops)

You can find me on:  [Twitter](https://twitter.com/krunal3kapadiya),  [Facebook](https://www.facebook.com/krunal3kapadiya),  [LinkedIn](https://www.linkedin.com/in/krunal3kapadiya).

![Image for post](https://miro.medium.com/freeze/max/60/1*RPqOZDIEFJjmPblXraCylw.gif?q=20)