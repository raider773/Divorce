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

I ended up with questions 18, 48, 15 and 54 affecting most of the predictions:

15. Our dreams with my spouse are similar and harmonious.
18. My spouse and I have similar ideas about how marriage should be
48. I feel right in our discussions.
54. I'm not afraid to tell my spouse about her/his incompetence.

![image](https://user-images.githubusercontent.com/70241561/118704712-cda1d780-b7ed-11eb-958b-00a0c3f1cd0f.png)
LDA Confusion Matrix. This is the model i choose


![image](https://user-images.githubusercontent.com/70241561/118704791-df837a80-b7ed-11eb-93b0-14cd00bbf719.png)
ROC and AUC of the three models 

![image](https://user-images.githubusercontent.com/70241561/118704861-f033f080-b7ed-11eb-9005-243dc03f7045.png)
Importance of features in a specific prediction. 18, 48, 15 and 54 appearing in a lot of random selected samples from prediction

-----------------------------

Finally i used Flask for deployment and created a simple function to evaluate teh statements and recieve the model prediction.


![image](https://user-images.githubusercontent.com/70241561/118705103-32f5c880-b7ee-11eb-934d-34cfe1b12f5e.png)


![image](https://user-images.githubusercontent.com/70241561/118705122-3a1cd680-b7ee-11eb-818d-813208c29ef6.png)








