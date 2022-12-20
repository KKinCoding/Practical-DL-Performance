# Practical-DL-Performance
This is the final project of COMS 6998 Practical DL Performance

In the COMS6998_Final_Project.ipynb is found the code for the LSTM variational autoencoder with 2 loss models: reconstruction loss, and reconstruction+information bottleneck loss (i.e. mutual information between the input data and the latent representation, z).

After downloading financial data for various S&P500 stocks to construct a portfolio, the aforementioned models are trained using 3 different processing units\n Tesla T4, A100, and a TPU. The wall time for the total training, and epochal training times are reported.
PU/Training Time | MSE Model Wall Clock Time | IB Model Wall Clock Time | MSE Model Epochal Wall Clock Average | IB Model Epochal Wall Clock Average
| ------------- |:-------------:| -----:|-----:|-----:|
Tesla T4 (GPU) | 0:06:14.00 | 0:03:06.06 | 37s | 19s
A100-SXM4-40GB (GPU) | 0:05:42.30 | 0:02:31.59 | 34s | 15s
(TPU) | 0:02:18.00 | 0:01:04.60 | 14s | 6s


Additionally included is code performing hyperparameter search for the beta hyperparameter that gives a weight to the information bottleneck loss w.r.t. the reconstruction loss. The data from this search is then plotted for the two loss models (the reconstruction loss model will always have a beta value of 0 of course).

Finally, in the Experiment.ipynb notebook, a comparison of the two models for a given hyperparameter set is done to show how the two models differ in their portfolio optimization performance. The portfolio quality metric used is the Sharpe ratio, the maximization of which gives the optimal portfolio. A Sharpe ratio above 2 is considered a good quality portfolio.
