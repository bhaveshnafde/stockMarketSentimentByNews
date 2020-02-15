# stockMarketSentimentByNews
a stock market sentiment analysis which predicts the change in opening price of the stock.<br>
there are two datasets which are being used namely:<br>
1.> Reddit news headlines dataset which contains news headlines from 2008 to 2016 for each date there are 25 headlines.<br>
2.> Dow Johns industrial average stock dataset it have the opening closing high low volume and adj. volume fields.<br>
the solution is approcahed in the following manner-<br>
CNN -> RNN -> LSMT<br>
keras 2.0.0 is used to build the model<br>
LSTM is used instead of GRU as it gives more accuracy on large amount of data, though it is slow and take more memory<br>
GloVE is used for word embedding and if some word is there which is not in the GloVe Voacb we assign a random vector to it.<br>
step-1> create dataframes, isin() is used to ensure same date in both the datasets<br>
step-2> assign difference in opening prices to target vaiues<br>
step-3> create a list of headlines and check corresponding price change<br>
step-4> clean the data and covert it to lower case as GloVe detects two same words with different cases as different words<br>
step-5> use regex to clear unwanted symbols<br>
step-6> as discussed about we used GloVe for word embeddings<br>
step-7> make each days headlines to approx 200 words, if you want to train more then maximize the no. of words.<br>
step-8> perform grid search on the model using wider and deeper variable<br>
        wider : it doubled the values of hyperparameters(param whose value is defined before training)<br>
        deeper : to add an extra convolution  layer<br>
Note : whilst training we notices the best results were obtained when i used a single layer.<br>
while training early stopping was used to prevent unnecessary training<br>
the median absolute error for this model is 75.14<br>
Scope:<br>
news from several sites can be used to make the accuracy of our model even better.<br>
But the honest truth is stock market is rather random and no model can predict it beyond `60%<br>
