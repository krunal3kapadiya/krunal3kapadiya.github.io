---
author: Krunal Kapadiya
title: "Machine Learning: Quick Introduction"
date: 2016-12-20
description: A Introduction to Machine Learning
math: true
---

Machine learning is trending topic for data-scientist, developers and researchers. Before, going into machine learning, first understand basic concepts about machine learning with it’s most used phrases.
Why we need machine learning?
People watch lots of science fiction movies, Iron-Man, Her, I-Robot etc. All those movies have character of machine that can interact like human. For achieving that part in real life we use a technique name as machine learning. We also succeed in some area, where user speak a command, machine will understand that command and give some output. e.g., Google Now, chat bot like Google Assistant in Allo application of Google.
What is machine learning?
There is too many definitions of machine learning. Definition given by Tom M. Mitchell is,
A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P if its performance at tasks in T, as measured by P, improves with experience E.
Definition says that, if a machine has improved based on it’s past experience that means, machine has learnt. And in machine learning, machine learn itself to give output based on past experience.
Where machine learning is used?
We use it in speech recognition, optical character recognition (OCR), mail, face detection, weather prediction, chat bot, game model object, and many more. Learn more about machine learning let see types of machine learning.
Types of Machine learning
There are major three types of machine learning. All that type are categorized based on algorithm of machine learning .
Supervised learning
In supervised learning, machine have set of label and the output will be one of them. While identifying alphabet, machine knows that output will be within 26 letters of alphabets. And in data-set it have all that entries, so machine can easily identify the letters. This type of learning algorithms known as supervised machine learning.
Image for post
Supervised learning is the machine learning task of inferring a function from labeled training data. The training data consist of a set of training examples. In supervised learning, each example is a pair consisting of an input object (typically a vector) and a desired output value (also called the supervisory signal).
- Wikipedia
So, we understand that in supervised learning is to predict data that have set of labels and output will be one of this label.
Unsupervised learning
Unsupervised learning not have data-set of label to predict output. It will make labels based on collection of same type of data, then it will identify the result. Now, visualize below image and predict what it is. Machine will find patterns, and predict output that image indicates some animals.
Image for post
Image of meerkat
Unsupervised learning is a type of machine learning algorithm used to draw inferences from data-sets consisting of input data without labeled responses. The most common unsupervised learning method is cluster analysis, which is used for exploratory data analysis to find hidden patterns or grouping in data.
- Wikipedia
In this technique, machine will find hidden patterns based on set of data, classify it and predict some label for output.
Reinforcement Learning
Like an unsupervised learning, reinforcement learning also not have any label to predict the output. In addition, reinforcement learning will find new algorithms, patterns based on past experience, and have constantly learning algorithm based on human interaction.
Autonomous car is one of the example of reinforcement learning. It will drive automatically and learn how to turn, when to turn, and when to drive fast/slow. Also it will find patterns how user drive car in specific lat-lang position.
Image for post
Audi RSQ car from I Robot
Reinforcement learning is an area of machine learning inspired by behaviorist psychology, concerned with how software agents ought to take actions in an environment so as to maximize some notion of cumulative reward.
-Wikipedia
This type of machine learning use artificial neural network, deep leaning concepts to make algorithms.
Also there is one more additional type name as, it falls between supervised learning and unsupervised learning.
Semi-supervised Learning
What if in data-set machine found some of data label and some not, in this scenario, learning algorithms known as semi-supervised learning.
Before deep diving into machine learning first we understand most used common words,
Classifications
In machine learning classification means to group data from whole data directory based on set of labels. We can say it as instance of supervised learning. Machine can recognize and categorize from data set, including from measurement and visual data.
Clustering
In terminology of machine learning clustering is, finding hidden pattern from data-set, task of grouping set of objects in a way that objects in same group is most similar to one another.
Features
All columns (exclude label column) in data-set (training data) used in machine learning is known as Features.
Regressions
In machine learning regression is to find a relationship between two objects. In common word regression means prediction of data.
Training Data
A data-set that we use in machine learning to predict the output is known as training data.
Image for post
Training data, with features, labels and set of examples
Okay ! We understand most common phrase use in machine learning now it is time to do lots of code. Let’s know required libraries about it.
Which software I use for machine learning?
Two popular libraries for machine learning.
TensorFlow
TensorFlow is open source software library provided by Google Brain team for Google’s research and production purpose, later it is released under Apache 2.0 open source license. You can install and setup TensorFlow using this link. TensorFlow playground tool will help to grasp the idea of neural network without calculating any hard mathematics.
Sci-kit learn
Sci-kit (SciPy Toolkit) learn is free machine learning library. It provides classification, regression, clustering algorithms.
First, download and install Anaconda. Make sure that you have python 2.7 installed. There is couple of libraries available but using anaconda, it makes easy to get all dependency set up and work well with cross platform.
Note: Before start coding make sure you have set environment variables for python.
Open editor and paste this code.

Importing tree from sklearn package

Adding features and labels

Full code using decision tree, to predict data
There is a AlphaGO computer program created by Google DeepMind developers.
Also you can start with Machine learning by this YouTube playlist series.
You can follow me on Twitter to get more updates from me. If you liked this, click the💚 below so other people will see this here on Medium.
