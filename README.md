# Divorce
Predicting if you are going to divorce!


In this project i try to predict if a person is gonna divorce or not depending on the answers given to certain questions.\
The questions are in attributes.txt. \
The answers are numbers from 0 to 4, the last agreeing the most with the question. \
I did some reduction dimnesionality to graph the classes, as well as trying some models and analysing them. \
Finally i deploy the model in flask, and created a function where you answer the questions and the model predicts if you are gonna divorce or not. 



![image](https://user-images.githubusercontent.com/70241561/118702956-ee692d80-b7eb-11eb-9e73-bf86fe3d286c.png)


I used PCA to reduce the dimensionality of the dataset to plot both classes.\
From this i assume the binary classification can be done with a plane, so im gonna use models that classify based on this. \
We can also see the classes are quite separated from each other.
--------------------------

I trained three models. A logistic regression and an LDA, models that separate classes linearly, and a KNN. Since in the PCA graph the classes appeared clearly separated i
could assume the features in a hyperplane look somewhat similar. The KNN would perform quite ok. 

![image](https://user-images.githubusercontent.com/70241561/118703782-dba32880-b7ec-11eb-8ac5-00f639677f59.png)

Logistic Regression with 0.5 as threshold

![image](https://user-images.githubusercontent.com/70241561/118703910-f7a6ca00-b7ec-11eb-81b7-bea777c957c4.png)

Knn scores and best parameters of the GridSearch

-------------------------

I compared the models and end up using the LDA.
I used Lime library to analyse how much features weight in a prediction.

I ended up with questions 











