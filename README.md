# Amazon_Vine_Analysis
Module 16 Challenge

## Overview

The purpose of this project is to determine whether or not Amazon reviews written by paid members of the Amazon Vine program are biased. To make this determination, reviews from Vine program members will be compared to reviews written by unpaid reviewers. The dataset chosen for this comparison is composed of reviews of music-related products.


## Deliverable 1
### Amazon Product Review ETL

The ![Amazon_Reviews_ETL.ipynb](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb) file does the following:

• Initates a Spark session.

• Extracts the review dataset.

• Transforms the dataset into four DataFrames with correct columns.

• Loads the DataFrames into an Amazon Web Services Relational Database via pgAdmin.

![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img01.png)
