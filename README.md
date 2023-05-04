Download Link: https://assignmentchef.com/product/solved-cs725-assignment-1-different-regression-loss-functions
<br>
In this assignment, you will perform ​<strong>Linear Regression</strong>​ by implementing <strong>Different Regression Loss</strong>​  <strong> Functions</strong>​ (like MSE, MAE, etc) using the method of gradient descent. For the concept, refer to the class notes/slides.

<h1>Dataset (Bike-rental prediction)</h1>

These days the whole process of renting a bike is automated, anyone can rent a bike at a location and return it to some other location. The companies which are in bike-rental business are interested in knowing the number of bikes that will be rented given the date, time of day, weather conditions, temperature, humidity etc. Your task is to find the best linear regression model that can predict with good accuracy the number of bike rental count given the conditions.

<strong>Bike-rental Dataset</strong>

(http://bigpicture.net/article/highway-85-creative-prints-everything-motorcycle)

There are 13 columns in the dataset. The last column (“count”) is the value which you have to predict.

The columns are-

<ol>

 <li>instance (id) – id of the row of dataset</li>

 <li>date – in format DD/MM/YYYY</li>

 <li>season – discrete (1 – spring, 2 – summer, 3 – fall, 4 – winter)</li>

 <li>hour – discrete (0-23)</li>

 <li>holiday – discrete (1 – holiday, 0 – not a holiday)</li>

 <li>weekday – day of the week in string</li>

 <li>working day – discrete (1 – neither a holiday or weekend, 0 – otherwise)</li>

 <li>weather situation – discrete (1-clear,2-mist/clouds,3-light snow/rain,4-thunderstorm/heavy rain)</li>

 <li>temperature – normalised temp in ​° calculated as ​ ​(t – t_min)/(t_max – t_min) (t_min = -8, t_max = 39)</li>

</ol>

10.atemperature – normalised feeling temp in ​°C. ​ ​(t – t_min)/(t_max – t_min) (t_min = -16, t_max = 50)

11.humidity – float

12.wind speed – float

13.count –  integer (This is target variable)

The train file consist ​<strong>13865</strong>​ rows of ​<strong>13</strong>​ columns. The test set consists of <strong>3514</strong>​       ​ rows with ​<strong>12</strong>​ columns (the features). The last column is held out for checking.

The assignment has 2 parts

<ul>

 <li>​<strong>[20 Marks]</strong>​ Implement the class LinearRegressor. There are 3 functions to implement ​<strong>__init__</strong>​, <strong>train</strong> and ​ <strong>predict</strong>​ ​. The primary loss function used for linear regression is mean squared error. So you are required to implement ​<strong>mean_squared_loss</strong>​ and ​<strong>mean_squared_gradient</strong>​. We have provided the basic function to read data from csv. You need to implement ​<strong>preprocess_dataset</strong>​ which will process the dataset so that it can be used for training. (ie converting strings to floats or int, converting categorical variables to suitable value, or fancy things such as feature scaling etc)</li>

 <li>​<strong>[20 + 5 Marks]</strong>​ Experimenting with different loss functions. In this part we ask you to implement​ the following 3 loss functions along with their gradient functions</li>

</ul>

mean_absolute_loss mean_absolute_gradient mean_log_cosh_loss mean_log_cosh_gradient root_mean_squared_loss root_mean_squared_gradient




To know what these loss functions are please refer to these <a href="https://en.wikipedia.org/wiki/Mean_squared_error">https://en.wikipedia.org/wiki/Mean_squared_error</a> <a href="https://en.wikipedia.org/wiki/Mean_absolute_error">https://en.wikipedia.org/wiki/Mean_absolute_error</a>

<a href="https://memoex.github.io/note/tech/ml/loss/">https://memoex.github.io/note/tech/ml/loss/</a>​ (RMSE and logcosh loss given)




After implementing the above losses you are required a plot a graph showing different losses as a function of epoch. Do the following –

Train your model using the 4 different gradient functions to update model weights. After each epoch find the mean_squared_loss of the model on the complete training dataset. Plot this mean_squared_loss as a function of epoch for each gradient function in the same graph (use legends in matplotlib). For the above task you have keep the learning rate same across all 4 gradient update functions. Choose a suitable learning rate so that none of the loss function diverges. Choose number of epochs such that we can see the losses converging. Note that even though you use different gradient function, we calculate the same loss (mean_squared_error) per epoch. This is done because

these losses would differ in their absolute magnitude and hence not suitable for comparison). Save

this graph with name ​<strong>comparison.jpg</strong>




(c) ​<strong>[5 Marks]</strong>​ For the final part you are required to tune the parameters (lr, epochs etc) to build the best classifier and perform well on the kaggle leaderboard. You can play around with <strong>preprocess_dataset</strong>​ to scale/modify/normalize features according to your wish. For example if you have a categorical variable which takes three values {“Red”,”Green”,”Blue”} you can either convert it into ordinal variables giving values {Red = 0, Green = 1, Blue = 2} or you could add more columns and one-hot encode the categorical variables e.g Red = (1,0,0), Green = (0,1,0) and Blue = (0,0,1). You are allowed to drop or add your own features as well. Kaggle will calculate ​<strong>mean squared error loss</strong>​ between your predicted y and true y on test dataset. Submit main.py with the appropriate hyperparameters so that on running  python3 main.py –train_data train.csv –test_data test.csv




Your model prints out the predicted output on test data. Also make sure this runs within 10 minutes. We will cross check that your model is able to reproduce your kaggle result. The final score for this part will be dependent on your standing in the leaderboard.


