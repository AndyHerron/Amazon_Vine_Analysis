# Amazon Vine Reviews analysis

## Overview of analysis
Using Google Colab and pyspark, we were asked to select reviews of product categories on Amazon and determine whether paid Vine reviews influence the overall reviews of products.

### Resources
* Data Sources: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Tools_v1_00.tsv.gz
* Software: Google Colab, pyspark, pgAdmin, AWS RDS and S3

## data tables in pgAdmin
Customers table
![customers_table](https://github.com/AndyHerron/Amazon_Vine_Analysis/blob/main/resources/pgAdmin_customers_table.png)

Products table
![products_table](https://github.com/AndyHerron/Amazon_Vine_Analysis/blob/main/resources/pgAdmin_products_table.png)

Review ID table
![review_id_table](https://github.com/AndyHerron/Amazon_Vine_Analysis/blob/main/resources/pgAdmin_review_id_table.png)

Vine table
![vine_table](https://github.com/AndyHerron/Amazon_Vine_Analysis/blob/main/resources/pgAdmin_vine_table.png)

## Results
---
- Total number of reviews and 5 star reviews in the raw data
	There were a total of 1,740,974 reviews of tools in the data category that I selected.
	There were a total of 1,113,482 reviews with 5 stars in the raw data.
	This indicates that 63.98% of the total number of reviews are 5 stars.

### To further evaluate the data, we chose to only look at products that had at least 20 reviews, and furthermore that of those more than 50% of the reviews were considered "helpful".
- How many Vine reviews and non-Vine reviews were there?
	There were 285 Vine reviews.
	There were 31,542 non-Vine reviews.

- How many Vine reviews were 5 stars?  How many non-Vine reviews were 5 stars
	There were 163 Vine reviews that were 5 stars.
	There were 14,614 non-Vine reviews that were 5 stars.

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
	Of the paid Vine reviews, 57.2% were 5 stars.
	Of the non-Vine reviews, 46.33% were 5 stars.

- The percentage of 5 star reviews from the rows with 20 or more votes was 42.85% (regardless of Vine status.)
- The percentage of 5 star reviews from the rows with 20 or more votes and more than 50% helpful reviews was 46.43% (regardless of Vine status.)


## Summary 
There is a positive effect of Vine reviews within the dataset. When looking at the subset of data with 20 or more votes and more than 50% helpful reviews,
the products with Vine reviews had a higher percentage of 5 star reviews.  The percentage of 5 star reviews for non-Vine reviewed products is essentially the same as the percentage
of the helpful reviews at just a bit over 46%.  (46.33% and 46.43% respectively) The products with Vine reviews get 5 star reviews 57.2% of the time.

As an additional analysis, I also calculated the number of 5 star reviews for the raw data.  63.98% of the reviews were 5 stars.  There could be many factors as to why this percentage is
higher than the percentages in our subset of data.  It's possible that many of those reviews were not considered helpful by other reviewers.  It's also likely that people who are happy
with the product are more likely to take the time to provide a review.  5 star reviews that did not receive at least 20 votes may indicate that other users didn't have quite the same experience (even if they also
left a 5 star review.) 

=======

