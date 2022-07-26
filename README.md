# Amazon_Vine_Analysis
Module 16 Challenge

## Overview

The purpose of this project is to determine whether or not Amazon reviews written by paid members of the Amazon Vine program are biased. To make this determination, reviews from Vine program members will be compared to reviews written by unpaid reviewers. The dataset chosen for this comparison is composed of reviews of musical instruments.
 
 
## Deliverable 1
### Amazon Product Review ETL

The ![Amazon_Reviews_ETL.ipynb](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb) file does the following:

• Initiates a Spark session.

• Extracts the review dataset.

• Transforms the dataset into four DataFrames with correct columns.

• Loads the DataFrames into an Amazon Web Services Relational Database via pgAdmin.
<pre>

</pre>
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img00.png)
This image shows the creation of the first three DataFrames, matching the tables given in the ![database schema](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/challenge_schema.sql) as provided in the module.
<pre>

</pre>
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img01.png)
This image shows the creation of the final DataFrame, connection configuration to Amazon AWS (edited for security), and the code to populate each table with the correct DataFrame.
<pre>

</pre>
Each table is verified in pgAdmin:
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img02.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img03.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img04.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img05.png)

## Deliverable 2

The dataset extracted and transformed in Deliverable 1 is recreated and analyzed to check for bias in paid reviews versus unpaid reviews. For this analysis, the code in the ![Vine_Review_Analysis.ipynb](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb) file does the following:

• Filters the review data to products with 20 or more votes.

• Further filters the DataFrame for products with 50% or greater helpful votes.

• Splits the data into two DataFrames for paid and unpaid reviews.

The following images show these steps:
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img06.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img07.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img08.png)
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img09.png)
<pre>

</pre>
The percentage of 5-Star reviews from Vine program members is calculated:
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img10.png)
<pre>

</pre>
The percentage of 5-Star reviews from unpaid reviews is calculated:
![image](https://github.com/Bryan-Corn/Amazon_Vine_Analysis/blob/main/Resources/Images/Img11.png)

## Deliverable 3
The following is an analysis of the data from deliverables 1 and 2.

### Results
The filtered data for musical instrument products shows the following:

Vine Program Member Reviews (paid)

• 60 total paid reviews analyzed

• 34 gave 5-Star reviews

• 5-Star percentage is 56.67%
<pre>


</pre>
Unpaid Reviews

• 14477 unpaid reviews analyzed

• 8212 gave 5-Star reviews

• 5-Star review percentage is 56.72%

### Analysis

The data shows the following:

• The 5-Star rating percentage for both the paid and unpaid review is virtually identical.

• The total number of reviews after filtering the data is heavily weighted towards unpaid reviews (14477 unpaid vs 60 paid).

From this, we can conclude that there is no evidence of bias in reviews from Vine program members. Further, if there were a bias in the paid reviews, it would be insignificant given the tiny percentage of reviews from paid reviewers.

Further analysis to detect bias could include reviews with 4, 3, 2, and 1-Star ratings. Additionally, there could be bias with 1-Star reviews that doesn't show up in 5-Star reviews. A larger dataset could be examined that includes reviews with fewer than 20 votes or all 'helpful' percentages.
