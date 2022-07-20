# crypto-predictor - ML Project for Predicting (!) the Crypto Prices 

I made this project for Machine Learning class at masters.  
Looked on lots of other similar projects, code isn't all mine.  
This was my first time around using Python.   
There might be lots of room for optimization / code cleaning.  
In the end, this one was failed to predict the prices of cryptocurrencies. (What a surprise! lol)  
But I have learned tons of stuff about Python and it's libraries.  
This readme got a lot personal sorry, lets move to project details.  

## SOFTWARE REQUIREMENTS

Python 3.7+  
Jupyter Notebook (not required but recommended)

## LIBRARIES USED

1- Numpy  
2- Matplotlib  
3- Pandas  
4- Sklearn aka scikit-learn  
5- Keras   

## HOW IT WORKS

Using "datareader" package of Pandas library, daily prices of cryptocurrencies imported from Yahoo Finance API.  
Which cryptocurrency to import and what fiat currency to compare is up to you. You can choose on first 2 lines after import section.  
Due to the fact that we are unable to use indicators such as MACD, RSI via Yahoo Finance API(at the time this code was written) I've used 'Close' (closing price) column's data to train.  

After importing the data, I've used Keras' MinMaxScaler library for converting the data to numbers between 0 and 1.   
Used the range of 60 days, decided after trying lots of different ranges.  
Then there is the prep data section. (Pretty self explanatory)  

While preparing the neural network, used sequential model of Keras due to the data being sequential.  
Used Keras' LSTM pack to keep the data in memory and used Dropout few times to layer the data to prevent overfitting.  
All those layered data must be packed into one data, so I've used Dense method.  
To compile the model, used "Adam" optimiser and calculated loss via "mean squeared error". This was choosen mainly because of it's lower system requirements.

To test the model, imported lastest prices from Yahoo Finance again and compared it to trained data.  
Visualised the results via Numpy and Matplotlib.

Mainly only variable I've changed was epoch and tested different ones for days.   
After 2000 epochs, there were diminishing returns compared to time spent. (Compared it via "mean squared error" vs time spent)  
Optimal test point I choose was 2000 epoch.  

All in all, this was a fun project to work on even though it was a futile attempt to do.
