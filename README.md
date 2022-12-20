# Practical-DL-Performance
This is the final project of COMS 6998 Practical DL Performance

In the COMS6998_Final_Project.ipynb is found the code for the LSTM variational autoencoder with 2 loss models: reconstruction loss, and reconstruction+information bottleneck loss (i.e. mutual information between the input data and the latent representation, z).

After downloading financial data for various S&P500 stocks to construct a portfolio, the aforementioned models are trained using 3 different processing units: Tesla T4, A100, and a TPU. The wall time for the total training, and epochal training times are reported.

Additionally included is code performing hyperparameter search for the beta hyperparameter that gives a weight to the information bottleneck loss w.r.t. the reconstruction loss. The data from this search is then plotted for the two loss models (the reconstruction loss model will always have a beta value of 0 of course).

Finally, in the Experiment.ipynb notebook, a comparison of the two models for a given hyperparameter set is done to show how the two models differ in their portfolio optimization performance. The portfolio quality metric used is the Sharpe ratio, the maximization of which gives the optimal portfolio. A Sharpe ratio above 2 is considered a good quality portfolio.
