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


![linear.png](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629048511/samples/linear_fuo0jl.png)


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629048847/samples/2_gafyps.png)


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629048844/samples/3_aea8je.png)


For us humans, it would be really easy to differentiate groups in each of the datasets, and we would immediately be able to draw a boundary that separated them, but, how can a machine do this? Moving onwards in this blog, we will be focusing on the example shown in the 3 figure, which represents a binary classification


## 2. Introducing the logistic function
The logistic function is a model of the well-known sigmoid function, and the mathematical function which represent these is the following:

![4.png](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629048845/samples/4_ufw2tp.png)


For the sake of curiosity, just mention that the logistic function is used to describe many real-world situations, for example, population growth. This is easily understood by looking at the normalised graph: the initial stages suffer an exponential growth, but after some time, due to the competition for certain resources (bottle neck), the growth rate decreases until it gets to a stalemate and there is no growth.

## 3. Understanindg the sigmoid function
### 3.1 EXAMPLE 1: General sigmoid function

![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049430/samples/19_j5xbgr.png)

Let’s say we decide to establish a threshold of 0.5 (just to adapt to the sigmoid function cut in the Y-axis). So:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049803/samples/20_ews8zh.png)


In order to achieve this:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049803/samples/21_tomjc3.png)


### 3.2 EXAMPLE 2: Linear boundary

We have calculated the θ parameters of the linear expression and have the following data:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049803/samples/22_ixryu2.png)


Using the same analysis as we did for the general sigmoid function:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049429/samples/24_dplbhc.png)    ![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049803/samples/23_dposed.png)



### 3.3 EXAMPLE 3: Circular boundary


We have calculated the θ parameters of the linear expression and have the following data:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049803/samples/25_cenfmy.png)


Using the same analysis as we did for the general sigmoid function:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629050542/samples/26_dtmhlg.png)


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629049429/samples/27_uhxhig.png))


**IMPORTANT NOTE! From these 3 examples we observe that the decision boundary is not directly defined by the training dataset, but by the θ parameters**


## 4. Cost function


Now that we know what the expression of our logistic regression hypothesis is, we need to know how to define the cost function in order to evaluate the errors a logistic model is going to make. Recall the cost function for linear regression:



![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051063/samples/28_jidegv.png)


If we minimized this function applying our new hθ(x(i)) hypothesis we cannot assure that we will converge the global minimum of the cost function! As hθ(x)=1/(1+e(θTX)) is not linear we might end up in a local minimum. Therefore, our new cost function will be:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051063/samples/29_oco3ea.png)


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051062/samples/30_gokqrb.png)


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051062/samples/31_izixn1.png)


## 4.1 Simplified cost function


Thankfully, as we are dealing with a binary classification problem and y can only be 0 or 1, then the cost function can be simplified to the following expression:


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051062/samples/32_bvj4ej.png)

### 4.2 Choosing the parameters: using gradient descent



The gradient descent iterative process used in logistic regression is exactly the same than the one used for linear regression. The only difference between both, is the input hypothesis. Therefore, the gradient descent algorithm is again:

![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629051062/samples/33_dquk9w.png)



## 7.Multiclass logistic regression from scratch


Multiclass logistic regression is also called multinomial logistic regression and softmax regression. It is used when we want to predict more than 2 classes. 


### Problem statement


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629092363/samples/multi-1_nltnfn.png)


Let’s assume we have N people/observations, each person has M features, and they belong to C classes. We are given:
A matrix 𝑋 is ℝ𝑁×𝑀. 𝑋𝑖𝑗 represents person i with feature j.
A vector 𝑌 is ℝ𝑁. 𝑌𝑖represents person i belonging to class k.
We do not know:
The weight matrix 𝑊 is ℝ𝑀×𝐶.𝑊𝑗𝑘 represents the weights for feature j and class k.
We want to figure out 𝑊 and use 𝑊 to predict the class membership of any given observation X.


## Multiclass logistic regression workflow
If we know 𝑋 and 𝑊 (let’s say we give 𝑊 initial values of all 0s for example), Figure 1 shows the workflow of the multiclass logistic regression forward path.
First, we calculate the product of 𝑋 and 𝑊, here we let 𝑍=−𝑋𝑊.
Sometimes people don’t include a negative sign here. It doesn’t matter if there is a negative sign here or not.
Sometimes we would also add a bias term. For simplicity, let’s only look at the weights in this article.
Second, we take the softmax for each row 𝑍𝑖: 𝑃𝑖=softmax(𝑍𝑖)=𝑒𝑥𝑝(𝑍𝑖)/∑𝑒𝑥𝑝(𝑍𝑖𝑘). Each row of 𝑍𝑖 should be the product of each row of 𝑋(i.e., 𝑋𝑖) and the entire matrix of 𝑊. Now each row of 𝑃 should add up to 1.
Third, we take the argmax for each row and find the class with the highest probability.


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629092775/samples/multi-2_n34r14.png)


                                            Multiclass logistic regression forward path
                                     
                                     
                                     
 
Below figure shows another view of the multiclass logistic regression forward path when we only look at one observation at a time:
First, we calculate the product of 𝑋𝑖 and W, here we let 𝑍𝑖=−𝑋𝑖𝑊.
Second, we take the softmax for this row 𝑍𝑖: 𝑃𝑖=softmax(𝑍𝑖)=𝑒𝑥𝑝(𝑍𝑖)/∑𝑒𝑥𝑝(𝑍𝑖𝑘).
Third, we take the argmax for this row 𝑃𝑖 and find the index with the highest probability as 𝑌𝑖.


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093172/samples/multi-3_m4oaaa.png)


                                            Operation on one row.
                                            
                                            
 
## Likelihood


Recall that in the problem statement that we said we are given 𝑌. So for a given observation, we know the class of this observation, which is 𝑌𝑖. The likelihood function of 𝑌𝑖 given 𝑋𝑖 and 𝑊 is the probability of observation i and class 𝑘=𝑌𝑖, which is the softmax of 𝑍𝑖,𝑘=𝑌𝑖. And the likelihood function of 𝑌 given 𝑋 and 𝑊 is the product of all the observations. Figure 3 helps us understand this process from 𝑌𝑖 trace backward to 𝑊𝑘=𝑌𝑖.


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093316/samples/multi-5_yy2ltv.png)
 
 
                                             Calculate likelihood.
                                             
                                             
## Loss function


Next, we calculate the loss function. We use the negative log-likelihood function and normalized it by the sample size. One thing to note here is that



![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093516/samples/multi-6_ebti7d.png)



𝑇r means the sum of elements on the main diagonal. Below figure visualizes this calculation.


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093637/samples/multi-7_d20dck.png)



                                                Matrix calculations.
  
  
  
![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093738/samples/multi-8_pa0vli.png)
 
We often add an 𝑙2 regularization term to the loss function and try to minimize the combined function. In fact, the default of scikit-learn uses 𝑙2 penalities. 𝑙1 regularization is also very commonly used. Here we use the 𝑙2 regularization.


![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629093849/samples/multi-10_me7qww.png)
 

## 6. Applications of Logistic Regression
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


## 6. Advantages and Disadvantages of Logistic Regression



![](https://res.cloudinary.com/nusratmohiuddin/image/upload/v1629050732/samples/1_Y_zp2gQu_Hj8pHyvq-xflQ_khyw86.png)




So this is all from my side, I tried to provide all the important information on Logistic Regression. I hope you will find something useful here. Thank you for reading till the end.
