---
layout:     post
title:      Maths operations in Tensorflow
date:       2018-02-09 12:31:19
summary:    See what the different elements looks like.
categories: jekyll
thumbnail: cogs
tags:
 - demo
 - action
 - carte
 - noire
---

Machine Learning is making a boom in the tech world, specifically for the developers and for the talented data scientists. We will never learn new things if we don’t start it from the bottom. In this article, we are striking at the root of Tensorflow. After reading this article you will be able to perform some basic mathematical operations in Tensorflow.

**Where it starts?**

Tensorflow was published in November 2015 by the Google Brain Team and currently Tensorflow 1.5 version is the latest release with Tensorflow lite, announced for mobile and embedded devices.

> Tensor is a multidimensional array. Nodes in the graph (aka ops or operations) perform mathematical computations and produce the tensors.

Have you installed Tensorflow on your PC yet? Not yet? Click the link and follow the instructions.

For running the following code you will need:

- Python 3.5
- Tensorflow
- Anaconda IDE

If you are getting errors while installing it, post it on StackOverflow.

To check the current version of Tensorflow run the following code in the command line:

```python
import tensorflow as tf;
print(tf.__version__)
```

Above code will print the version of Tensorflow.

**Let’s begin it.**
I assume that you have correctly installed above listed tools and now `activate tensorflow`.

***Hello World***

```python
from __future__ import print_function
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
# Start tf session
sess = tf.Session()
# Run the op
print(sess.run(hello))
```

Now let’s understand the code, we have imported `print_function` and `tensorflow` libraries. Created the constructor of the constant class form tensorflow and added the values to it `Hello TensorFlow!` In tensorflow session, we have run the node of constant op. That’s it??

As I am running this code in Anaconda command prompt, it is not necessary to activate the Tensorflow for basic operations.

Output:

![Thumper](https://cdn-images-1.medium.com/max/1250/1*8am5q181sXjku4hSOdEiQA.png)

**Arithmetic operations**

We have learned to make the constant node and printing the values in it. Next is to performing arithmetic operations.

```python
from __future__ import print_function
import tensorflow as tf

# Basic constant operations
a = tf.constant(2)
b = tf.constant(4)

# Launch the default graph.
with tf.Session() as sess:
    print("a=2, b=4")
    print("Addition with constants: %i" % sess.run(a+b))
    print("Multiplication with constants: %i" % sess.run(a*b))
    print("Substraction with constants: %i" % sess.run(b-a))
    print("Division with constants: %i" % sess.run(b/a))
```

We have created the 2 constant constructors, assigned the values in a and b. In the Tensorflow session, we are running calculating the operations in it. the values returned by the constants represents the output of the constant ops. Need Explanations in above code….???

Output:

![Thumper](https://cdn-images-1.medium.com/max/1250/1*pc_3OTOzLyV6Y0QBtMMl0w.png)

In the above code snippet we have added the values at the initialization time, now we are writing the code to perform those operations at the run-time.

***Adding values in running session***

```python
from __future__ import print_function

import tensorflow as tf

a = tf.placeholder(tf.int32)
b = tf.placeholder(tf.int32)

# Define some operations
add = tf.add(a, b)
sub = tf.subtract(a, b)
mul = tf.multiply(a, b)
div = tf.div(a, b)

# Launch the default graph.
with tf.Session() as sess:
    # Run every operation with variable input
    print("Addition with variables: %i" % sess.run(add, feed_dict={a: 4, b: 2}))
    print("Subtraction with variables: %i" % sess.run(sub, feed_dict={a: 4, b: 2}))
    print("Multiplication with variables: %i" % sess.run(mul, feed_dict={a: 4, b: 2}))
    print("Division with variables: %i" % sess.run(div, feed_dict={a: 2, b: 2}))
```
We have defined types of variables in `tf.placeholder` to feed the data when the session is running, by `feed_dict` we have added data in the Tensorflow session.

***Matrix manipulation***

![Thumper](https://giphy.com/gifs/movie-matrix-cyberpunk-sJ5lbgCiGJAZO)

We have implemented basic arithmetic operations and now time is to the same with the matrix.

```python
from __future__ import print_function

import tensorflow as tf

# Create a Constant op that produces a 1x2 matrix.  The op is
# added as a node to the default graph.

matrix1 = tf.constant([[3., 3.]])

# Create another Constant that produces a 2x1 matrix.
matrix2 = tf.constant([[2.],[2.]])

product = tf.matmul(matrix1, matrix2)

with tf.Session() as sess:
    result = sess.run(product)
    print(result)
```

We have created two matrices, in `matrix1` we have created one 1x2 matrix, in `matrix2` we have created a 2x1 matrix. In above code, `matmul` will return the multiplication of the two matrices.

>Output

![Thumper](https://cdn-images-1.medium.com/max/1250/1*QeJ5BFRiwvgv51uIISulFA.png)

From above we can declare the variables and perform the basic maths operations in it. Run the above code and be confident in it.

> The programmer who writes code to learn, learns quickly.

Next step will be to understand maths operations. How mean, median and mode works for the data and in graph.

***References:***
- [Installation guidelines][0]
- [Placeholder][1]
- [Maths operators][2]

[0]: (https://www.tensorflow.org/install/)
[1]: (https://www.tensorflow.org/api_docs/python/io_ops/placeholders)
[2]: (https://www.tensorflow.org/api_guides/python/math_ops)	