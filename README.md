## Predict Customer Churn with Spark

### Project Overview
Sparkify is a frictional music application like Spotify that offers both free and paid services. Customers churn happens when a user downgrade from paid premium service to free tier or cancel the service altogether. 

This project focuses on identifying factors that help predict user churn risk by analyzing Sparkify’s user event data and builds and tunes machine learning models using Spark ML libraries to predict churn users. In real cases, user event datasets are large data files that record every detailed interactions users have with the application. Currently we’re analyzing a small subset data file (128 MB) in local workspace and will analyze the full data (12 GB) in the cloud with AWS.

### Medium Post
Project details and results are discussed in the [post](https://medium.com/@candywendao/churn-prediction-with-spark-aecad96a5d4c) on Medium.


### Files
- 'Sparkify_Churn_Prediction.ipynb' is the ipython notebook that includes code for data cleaning, data wrangling, model preprocessing, and model training. 
- 'ML_metrics.xlsx' stores the evaluation metrics of three models.
 - Data input file is too large to be uploaded here. 

### Python Libraries 

- pyspark
- numpy
- pandas
- matplotlib
- seaborn
- datetime
- time

### Acknowledgement
Thank [Udacity](https://www.udacity.com/) for the instructions and advice.
