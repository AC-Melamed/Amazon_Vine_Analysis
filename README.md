# Amazon_Vine_Analysis

## Overview
This project involved the use of ETL methods in combination with PySpark in Python 3 and Google Collab, Hadoop, PostgreSQL and the pgAdmin programming environment for the purpose of analyzing one of 50 separate datasets, each containing a collection of reviews for a distinct product category.  These reviews include ones submitted as part of Amazon Vine, an intivation-only program intended to promote selected accounts as "Vine Voices" who are provided with free products in exchange for high-quality reviews.     

### Purpose
The purpose of this project is to analyze the corpora of review datasets for latent biases.  Since the reviewers in question are being compensated by Amazon for their reviews, there is a strong basis for suspecting that they might exhibit some form of favoritism in exchange.   

## Results 
From the list of available datasets, the set containing data for reviews of "Digital_Video_Games" was selected for analysis.  An RDS instance was created to store this data using the Amazon Web Services hosting service, which was then linked to an SQL database.  Using a series of queries, four tables were generated inside of pdAdmin 4 -- "review_id_table", "customers_table", "products_table", and "vine_table" which contained information specifically regarding reviews submitted as part of the Vine program.  These tables were inspected preliminarily before being recreated using Python 3 inside of Google Collab.  From there, the recreated tables were serially filtered until the most significant data remained; namely, the "vine_table" table filtered down to a minimum 50% distribution of reviews voted as "helpful" by at least 20 users.  This filtering was performed to improve the quality opf the data for more detailed analysis.  

![f1](/Images/f1.png)

![f2](/Images/f2.png)


### Analysis
  - How many Vine reviews and non-Vine reviews were there?
    - Total Vine Reviews = 0

      ![f3](/Images/f3.png)  

    - Total Non-Vine Reviews = 1563

      ![f4](/Images/f4.png)


  - How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
    - Total Five Star Vine Reviews = 0
    - Total Five Star Non-Vine Reviews = 582

  - What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
    - Percentage Five Star Vine Reviews = [DIVIDE BY ZERO ERROR]
    - Percentage Five Star Non-Vine Reviews = ~37%

## Summary
Due to the total lack of documented Vine program reviews in the particular dataset selected for this project, it is not possible to draw any conclusions regarding the presence of potential bias on that basis.  Even before being filtered for quality, there are no datapoints present that are marked as Vine reviews, leading to the conclusion that the category of "Digital Video Games" must not represent an economically viable or otherwise advisable venue for the program.  It might be hypothesized that this is due to community preferences or other factors unique to the form of digital video games as a commodity, such as virtual piracy or artificial limits on product keys, which could render them undesirable for Vine program participants.   

### Proposal for Additional Analysis
The obvious next step for this project would be to continue exploring the remaning 49 entries in the full data corpus using the same techniques developed herein.  With a larger sample size across a wider range of product categories, such analysis should eventually render apparent any latent trends regarding both the predominance and potential bias of Vine program reviews.   
