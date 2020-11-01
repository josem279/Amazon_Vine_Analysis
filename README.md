# Amazon_Vine_Analysis

## Project Overview

The purpose of this challenge was to analyze Amazon reviews written by members of the paid Amazon Vine program to see whether or not there is an existing bias from Vine members. The challenge asked us to make use of our familiarity with Amazon Web Services (AWS), PySpark, SQL, and Google Colab. The challenge required us work through the Extract, Transform, and Load (ETL) process by first creating an AWS RDS database with tables in pgAdmin based on one of the previously mentioned Amazon review datasets - I chose the https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz dataset. This Video_Games_V1 dataset was then transformed into dataframes and loaded into pgAdmin as tables that we could enabled further analysis. In my case, I chose to perform the final part of the analysis through Pandas.

## Results

The analysis of the pgAdmin tables through Pandas allowed us to answer the following questions:

1. How many Vine reviews and non-Vine reviews were there?

    ![image of count](https://github.com/josem279/Amazon_Vine_Analysis/blob/main/images/paid_unpaid_count.PNG)

    As shown above, there are a total of 94 Vine (paid) reviwers and 40,471 unpaid reviews in the Video_Games_V1 dataset. This is after dataset was filtered to only include rows where the total votes count was equal to or greater than 20 and then the number of helpful votes divided by total votes was equal to or greater than 50%.

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

    ![image of 5-star reviews output](https://github.com/josem279/Amazon_Vine_Analysis/blob/main/images/5_star_count.PNG)

    As shown in our Pandas output, there are a total of 48 five star reviews by Vine (paid) reviewers and 15,663 five star reviews by unpaid reviwers.

3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

    ![image of percentages](https://github.com/josem279/Amazon_Vine_Analysis/blob/main/images/5_star_percentages.PNG)

    Based on our previous answers and as is demonstrated in our Pandas output, this means that in the Video_Games_V1 dataset approximately 51% of Vine reviews are 5-stars whereas only 38% of non paid reviews are 5-stars.

## Summary

Based on the results of the Analysis conducted, I would say that there does appear to be some existing bias in Vine reviews when it comes to rating products as 5-stars. There is a  difference of about 13% when it comes to the percentage of 5-star reviews that are given out by paid reviewers than by non-paid reviewers. However, it is important to note that this analysis only looked at one dataset and that this particular dataset had many more rows of data for nonpaid reviews than paid reviews. In order to better determine whether or not this bias is real among Vine reviewers I would suggest reviewing more than one dataset at a time. This could be done by loading in more amazon sample data, creating tables in pgAdmin, performing joins in pgAdmin, and then once again cleaning and running a similar analysis on SQl/Pandas/PySpark. By conducting this similar analysis we are able to add more data, increasing the chance of a normal distribution, and remove the potential risk that one group of reviewers has a bias that negatively impacts the image of all Vine reviewers.