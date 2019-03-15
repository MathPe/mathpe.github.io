---
layout: post
title: Different types of Machine Learning ?
---

As Machine Learning is developed from statistical-based algorithms, we can imagine there are many and many different ways it is implemented. But in fact, all these algorithms can be grouped in three big categories. These three categories are *Supervised Learning*, *Unsupervised Learning* and *reinforcement*.

I will shortly present these three categories :

- *Supervised Learning* is a way to find patterns between input values and output values using a training dataset (in which the input AND output values are given to the algorithm). An example of this can be the prediction of house price. The dataset can be, for example, composed for the input values of the location of the house, its surface, and the presence of a swimming pool, and for the output, the price of the house. Once you have "fed" the algorithm with this training dataset, giving new input values will predict the output value according to what it have learned. Supervised Learning problems can be grouped into two sub-categories : Regression problems and Classification problems. The example presented previously is a Regression problem. To illustrate the category of Classification Problem we can use a medical example. Let's say we have a dataset giving has input values the size of a cell, its roughness, its composition and its pH, and as output value the fact that it is cancerous or not. The algorithm will find patterns according to input values to determine the output value. In that case, the values are finite values, that is why it is called Classification Problem. Typical algorithms found in supervised learning are : *regression analysis*, *decision trees*, *neural networks*, and *support vector machines*. I will present these concept with more details in future posts.
