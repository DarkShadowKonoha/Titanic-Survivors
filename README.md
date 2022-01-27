# Titanic-Survivors

This project is a great way to start with ML basics.

The task we have to perform is very simple, we will use machine learning to create a model that predicts which passengers survived the Titanic shipwreck.

I will be using Logistic Regression for this.

## Logistic Regression
Logistic Regression is a statistical method for analyzing a dataset in which there are one or more independent variables that determine an outcome. Logistic Regression is actually a classification algorithm. Logistic regression is used to describe data and to explain the relationship between one dependent binary variable and one or more nominal, ordinal, interval or ratio-level independent variables.

Before starting with Logistic regression we need to know about a function called Sigmoid function and its properties.

### Sigmoid Function
A sigmoid function is a mathematical function having an "S" shaped curve (sigmoid curve). Mathematically , the function is :

![image](https://user-images.githubusercontent.com/77683275/151319277-02705867-02d9-4986-bf2f-b16568f6ed4e.png)

(img-source : https://machinelearningmastery.com/a-gentle-introduction-to-sigmoid-function/)

With its output ranging between 0 and 1. As we can clearly see that the the curve quickly goes toward 1 when x>0 and toward 0 when x<0 and at x=0 it is equal to 0.5. 

Because of the property of sigmoid function to give output between 0 and 1 we can use its output like probability, but not exactly as probability. For example, the property of probability that P(true)+P(false)=1 may not be true is case of sigmoid function i.e. S(true)+S(false) may not be equal to 1.

## Implementation

Now, we will be implementing Logistic Regression ourselves instead of using sklearn LogisticRegression().

But before that we will be scaling our data using sklearn's preproccessing module.
I've already splitted whole titanic dataset into train.csv and test.csv and added it into repo, but if you wish to do it yourself and get more familiar with it, you are more than welcome. To that you can download the Titanic dataset from <a href="https://www.kaggle.com/c/titanic">Kaggle</a>, and then import sklearn's model_selection and use <i>train_test_split()</i> method to split the dataset into train and test.

I've used pandas _read_csv()_ to read train.csv file,you can use numpy's _genfromtext()_ or _loadtxt()_ as well.

Then I will be removing Name, Cabin and Ticket from my train file as these columns will not help me in my predictions. (Always take a look at the dataset provided beforehand to know what kind of datatypes, features, etc. you are dealing with and get a gist of dataset.

Then I will transform the 'Sex' column from male and female to 0s and 1s , as it is more easy to deal with it, and I will do this for 'Embarked' column as well, replace S,Q,C with 0,1,2.

Then I will take care of all the NA values in _Age_ columns, I decided to fill all NAs with the mean of whole age column and for null values in _Embarked_ I will replace it with 0 i.e, S.

I will repeat all this pre-procesing and cleaning of data for test.csv as well.
