---
published: true
---
In this blog, I introduce an algorithm that is admirably suited for discovering the link between features and some particular outcome: **Logistic regression.**

##  What is Logistic Regression?
Both linear and logistic regression are used to predict certain results taking into consideration previous historical data. The main difference between them is the type of prediction each one does: 1. **Linear regression** ??? predicts any value. In order to do this, linear regression takes as input independent values CONTINUOUS VARIBLES, in other words, variables that can take any value, and hence, our prediction will also be a continuous variable and can take any value. 2. **Logistic regression** ??? it predicts the probability of bounded possible outcomes, in other words, logistic regression is a CLASSIFICATION algorithm.


As mentioned, logistic regression is one of main and most simple CLASSIFICATION algorithms. It extends the idea of linear regression to cases where the dependent variable, y, only has two possible outcomes, called classes (careful, this only applies with binary logistic regression; multiple logistic regression deals with situations where the outcome can have three or more possible types (e.g., “disease A” vs. “disease B” vs. “disease C”)).


##  Why Logistic, not Linear?

### Problem 1: Predicted value is continuous, not probabilistic

In a binary classification problem, what we are interested in is the probability of an outcome occurring. Probability is ranged between 0 and 1, where the probability of something certain to happen is 1, and 0 is something unlikely to happen. But in linear regression, we are predicting an absolute number, which can range outside 0 and 1.
Using our linear regression model, anyone age 30 and greater than has a prediction of negative “purchased” value, which don’t really make sense. But sure, we can limit any value greater than 1 to be 1, and value lower than 0 to be 0. Linear regression can still work, right?
Yes, it might work, but logistic regression is more suitable for classification task and that logistic regression yields better results than linear regression. 

### Problem 2: Sensitive to imbalance data

## 1. Intuition behind logistic regression
The following images show different classification examples.


![linear.png]https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629048511/samples/linear_fuo0jl.png
![linear.png]({{site.baseurl}}/_posts/linear.png)



![2.png]({{site.baseurl}}/_posts/2.png)


![3.png]({{site.baseurl}}/_posts/3.png)


For us humans, it would be really easy to differentiate groups in each of the datasets, and we would immediately be able to draw a boundary that separated them, but, how can a machine do this? Moving onwards in this blog, we will be focusing on the example shown in the 3 figure, which represents a binary classification


## 2 Introducing the logistic function
The logistic function is a model of the well-known sigmoid function, and the mathematical function which represent these is the following:

![4.png]({{site.baseurl}}/_posts/4.png)


For the sake of curiosity, just mention that the logistic function is used to describe many real-world situations, for example, population growth. This is easily understood by looking at the normalised graph: the initial stages suffer an exponential growth, but after some time, due to the competition for certain resources (bottle neck), the growth rate decreases until it gets to a stalemate and there is no growth.

## 3 Understanindg the sigmoid function
### 3.1 EXAMPLE 1: General sigmoid function

![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/19.PNG)

Let’s say we decide to establish a threshold of 0.5 (just to adapt to the sigmoid function cut in the Y-axis). So:


![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/20.PNG)


In order to achieve this:


![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/21.PNG)


### 3.2 EXAMPLE 2: Linear boundary

We have calculated the θ parameters of the linear expression and have the following data:

![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/22.PNG)


Using the same analysis as we did for the general sigmoid function:


![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/23.PNG)


### 3.3 EXAMPLE 3: Circular boundary


We have calculated the θ parameters of the linear expression and have the following data:


![]({{site.baseurl}}/https://joparga3.github.io/standford_logistic_regression/images/25.PNG)


Using the same analysis as we did for the general sigmoid function:


https://joparga3.github.io/standford_logistic_regression/images/27.PNG


**IMPORTANT NOTE! From these 3 examples we observe that the decision boundary is not directly defined by the training dataset, but by the θ parameters**



## Applications of Logistic Regression
### 1. Credit scoring
ID Finance is a financial company that makes predictive models for credit scoring. They need their models to be easily interpretable. They can be asked by a regulator about a certain decision at any moment. Logistic regression is widely used in credit scoring and it shows remarkable results.


### 2. Medicine
Medical information is gathered in such a way that when a research group studies a biological molecule and its properties, they publish a paper about it. Thus, there is a huge amount of medical data about various compounds, but they are not combined into a single database.
Logistic regression is well suited for this data type when we need to predict a binary answer. Thanks to this algorithm, the accuracy of a quick blood test have been increased.


### 3. Text editing
As we talked about texts, it is worth mentioning that logistic regression is a popular choice in many natural language processing tasks. First, the text preprocessing is performed, then features are extracted, and finally, logistic regression is used to make some claim about a text fragment. Toxic speech detection, topic classification for questions to support, and email sorting are examples where logistic regression shows good results. Other popular algorithms for making a decision in these fields are support vector machines and random forest.


### 4. Hotel Booking


Booking.com has a lot of machine learning methods literally everywhere on the site. They try to predict users’ intentions and recognize entities. Where will you go, where do you prefer to stop, what are you planning to do? Some predictions are made even if the user didn’t type anything in the search line yet. But how did they start to do this? No one can build a huge and complex system with various machine learning algorithms from scratch. They have accumulated some statistics and created some simple models as the first steps.


Logistic Regression tries to predict either user will change a journey date or not. Logistic regression could well separate two classes of users. Based on this data, the company then can decide if it will change an interface for one class of users.


### 5. Gaming
Speed is one of the advantages of logistic regression, and it is extremely useful in the gaming industry. Speed is very important in a game. Very popular today are the games where you can use in-game purchases to improve the gaming qualities of your character, or for fancy appearance and communication with other players. In-game purchases are a good place to introduce a recommendation system.
Advantages and Disadvantages of Logistic Regression


## Advantages and Disadvantages of Logistic Regression

![]({{site.baseurl}}/https://miro.medium.com/max/3600/1*Y_zp2gQu_Hj8pHyvq-xflQ.png)


So this is all from my side, I tried to provide all the important information on Logistic Regression. I hope you will find something useful here. Thank you for reading till the end.
