# Newborn mortality rate
In this project we will be studying the tweets of the twitter account @dog_rates.
 

## Installation
To execute this project you will need the following python librairies:
* pandas
* NumPy
* requests
* tweepy
* json
I recommend installing Anaconda, which comes with all the necessary packages, and the IPython notebook.

## Introduction

This readme describes the whole process of data analysis from data gathering to sharing my results. 
A project made for the Udacity data analyst Nanodegree program. The goal is to Leverage WeRateDogs Twitter data to create engaging and reliable analytics and visualizations.
Through this project i learned how to: 
* Collecte additonal data using the request library, the twitter API and by downloading the WeRateDogs Twitter archive data.
* Evaluate the data visually and programmatically, detected and document the issues, cleaned the data and analyzed, visualized the scrambled data.
* Write a report that briefly describes the data processing efforts.
* Write a report that communicates all observations and displays the visualization(s) produced from the data.


Through out this project i followed the following steps: 
Step 1. data collection
Step 2. data evaluation
Step 3. data cleaning
Step 4. data storage
Step 5. Analyze and visualize the data
Step 6: write 2 reports about my  data processing efforts and data analyzes and visualizations

 ## Data Gathering
**Data set 1** : WeRateDogs™ Twitter Archive (twitter-archive-enhanced.csv)
 I downloaded the data that is in twitter_archive_enhanced.csv using the basic pd.read_csv function that gives us the possibility to
read csv files.

**Data set 2** : Tweet image predictions (image_predictions.tsv)
 I downloaded the image prediction tsv file this time I used the second method learn from this course which is the use of the request library that helps us download data directly from an url.
 
**Data set 3** : Tweet json file (tweet_json.txt)
I tried to use the tweeter api as asked but not having a response from tweeter concerning my request to signup of a tweeter developer account, I had to directly use the tweet_json.txt file that gave us access to. To get the data from this file I read eachline and loeaded using json.loads and got the id of the tweet, favorite count
and retweet count
 
  ## Data Wrangling
Most of the efforts that I made during the project are here where I had to solve every single one of the issues that I have detected:

**Issue 1:** timestamp attribute is of type string
* Solution: convert the type using to_datetime function.
    
**Issue 2:** Some tweets are retweets
* Solution: Delete the tweets using the drop function
    
**Issue 3:** rating_denominator above and under 10
* Solution: Retrieve the id of the the tweets and delete.
    
**Issue 4:** Wrong values in the name column
* Solution: Replace the wrong name by none.
    
**Issue 5:** Missing values in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id
* Solution: Fill the NaN values with zero.
    
**Issue 6:** in_reply_to_status_id and in_reply_to_user_id type float instead of int.
* Solution: Convert using astype()
    
**Issue 7:** each type of dog is a column
* Solution: Concat 4 columns

**Issue 8:** duplicated images of dogs that have been rated
* Solution: Drop duplicates
    
**Issue 9:** 3 datasets
* Solution: Merge the three datasets
    
**Issue 10:** Rename columns
* Solution: Rename columns to have significate names
    
 ## My Findings
 For the analysis of this dataset, I asked myself the following questions:
 1. What is the most common name?
    To answer this question Charlie the most common name with 11 dogs named that way in our dataset.
    
 2. What is the breed of the highest rating?
    The breed of dogs with the highest rating is Clumber.
    
 3. What is the breed of the dog with the highest retweet?
     the breed of the dog with the highest retweet is a chihuahua that has a rating of 13/10.

 