## Predict Customer Churn with Spark

### Project Overview
Sparkify is a frictional music application like Spotify that offers both free and paid services. Customers churn happens when a user downgrade from paid premium service to free tier or cancel the service altogether. 

This project focuses on identifying factors that help predict user churn risk by analyzing Sparkify’s user event data and builds and tunes machine learning models using Spark ML libraries to predict churn users. 

In real cases, user event datasets are large data files that record every detailed interactions users have with the application. Currently we’re analyzing a small subset data file (128 MB) in local workspace. In the future we'll analyze the full data (12 GB) in the cloud with AWS.

 1. **Medium Post**

Project details and results are discussed in the [post](https://medium.com/@candywendao/churn-prediction-with-spark-aecad96a5d4c) on Medium.


2. **File Structure**
	- 'Sparkify_Churn_Prediction.ipynb' is the ipython notebook that includes code for data cleaning, data wrangling, model preprocessing, and model training. 
	- 'ML_metrics.xlsx' stores the evaluation metrics of three models.
	- Folder 'image' saves screenshots of charts and tables used in the repo.
	 - Data input file is too large to be uploaded here. 

3. **Implementation**

This project is implemented using Apache Spark Python AP and uses the following python libraries:

	- pyspark
	- numpy
	- pandas
	- matplotlib
	- seaborn
	- datetime
	- time

### Exploratory Data Analysis

 1. **Data Exploration**

	- Data file ''mini_sparkify_event_data.json" contains 286500 lines and 18 columns of user event data from 2018–10–01 to 2018–12–03; Data schema is shown as below:
	![Data Schema](https://github.com/candywendao/Sparkify_Predict_Churn/blob/master/image/Data_Schema.png)
	
	- Null values: Dropped 8346 lines of null values created by 'Logged-out' and 'guest' users; Columns 'Song', 'Artist' and 'Length'  logged null values when users were visiting pages other than 'NextSong' page thus these null values are kept in the dataset.
	
	- 225 distinct users included: 104 female and 121 male.

 2. **Data Visualization**

Charts can be found from the [notebook](https://github.com/candywendao/Sparkify_Predict_Churn/blob/master/Sparkify_Churn_Prediction.ipynb) in this repo or the Medium [post](https://medium.com/@candywendao/churn-prediction-with-spark-aecad96a5d4c).

### Modeling and Evaluation

 1. **Feature Engineering**
	-   gender (Male: 1; Female: 0)
	-   level (paid or free)
	-   most frequent device
	-   number of songs listened per user
	-   number of artists listened to per user
	-   number of sessions per user
	-   average number of pages visited per session per user
	-   number of ads views per user
	-   number of page views of ‘Error’ per user
	-   number of page views of ‘Help’ per user
	-   number of page views of ‘Downgrade’ per user
	-   number of page views of ‘Upgrade’ per user
	-   number of page views of ‘Logout’ per user
	-   percentage of thumb-ups of total ‘NextSong’ page views per user
	-   percentage of thumb-downs of total ‘NextSong’ page views per user

A screenshot of the preprocessed dataset:
![Screenshot of Dataset](https://github.com/candywendao/Sparkify_Predict_Churn/blob/master/image/data_preprocessed.png)


 2. **Modeling and Evaluation**
 - Methods: first train the base model, Logistic Regression and then apply Random Forest and Gradient-boosted tree.
 
 - Metrics: As the sample size is comparatively small, we use **f1** score as the accuracy metric, which considers both the precision the recall to compute the score.
 
 - Results:

According to the results, the model using Random Forest looks very promising as it achieved 0.90 and 0.78 scores for train and test datasets.

![Metrics](https://github.com/candywendao/Sparkify_Predict_Churn/blob/master/image/F1_results.png)


 - Future Improvement:

In the future, we’ll apply the models on the full dataset. To improve the mode performance, we may consider add more features such as location, time spent on the application, and device used when churn.

### Acknowledgement
I wish to thank [Udacity](https://www.udacity.com/) for the instructions and advice.
