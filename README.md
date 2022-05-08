# Data Scientist Role Play: Profiling and Understanding (Part 1)

1. Profile the data by finding the total number of records for each of the tables below:
* i. Attribute table = 10000
* ii. Business table = 10000
* iii. Category table = 10000
* iv. Checkin table = 10000
* v. elite_years table = 10000
* vi. friend table =  10000
* vii. hours table = 10000
* viii. photo table =  10000
* ix. review table =  10000
* x. tip table =  10000
* xi. user table = 10000
![Peer_review_records_table](https://user-images.githubusercontent.com/102244119/167318131-8f87f045-aa8c-4b63-be3a-b565daee885b.png)

2. Find the total distinct records by either the foreign key or primary key for each table. If two foreign keys are listed in the table, please specify which foreign key.
* i. Business = 10000 records for id
* ii. Hours = 1562 records for business_id
* iii. Category = 2643 records for business_id
* iv. Attribute = 1115 records for business_id
* v. Review = 10000 records for id and 8090 records for business_id
* vi. Checkin = 493 records for business_id
* vii. Photo = 10000 records for id and 6493 records for business_id
* viii. Tip = 537 records for user_id and 3979 records for business id
* ix. User = 10000 records for id
* x. Friend = 11 records for user id
* xi. Elite_years = 2780 records for user id

SQL code used to arrive at answer:
![Peer_review_key](https://user-images.githubusercontent.com/102244119/167318165-4cbd3a61-c2f0-4c7f-b414-18bb3ec5b04b.png)

3. Are there any columns with null values in the Users table? Indicate "yes," or "no."
* Answer: No

SQL code user to arrive at answer:
![Peer_review_nulls](https://user-images.githubusercontent.com/102244119/167318224-9871c225-48ca-44a1-b9a4-f54ec52f99d0.png)

4. For each table and column listed below, display the smallest (minimum), largest (maximum), and average (mean) value for the following fields:
	
   	i. Table: Review, Column: Stars
	min: 1		max: 5		avg: 3.6549
	
	ii. Table: Business, Column: Stars
	min: 1		max: 5		avg: 3.6549
		
	iii. Table: Tip, Column: Likes
	min: 0		max: 2		avg: 0.0144
	
	iv. Table: Checkin, Column: Count
	min: 1		max: 53		avg: 1.9414
		
	v. Table: User, Column: Review_count
	min: 0		max: 2000	avg: 24.2995
![Peer_review_stars](https://user-images.githubusercontent.com/102244119/167318251-ea44f9ce-1d10-47be-a9fc-48e3298d09f3.png)

5. List the cities with the most reviews in descending order:
* SQL code used to arrive at answer:
![Peer_review_most_city](https://user-images.githubusercontent.com/102244119/167318307-0f9efb80-8b8a-4a00-9076-f33d16882202.png)

* Copy and Paste the Result Below:
![Peer_review_most_rev_cities](https://user-images.githubusercontent.com/102244119/167318317-117504e5-18db-4584-8104-2e4ee0c99b0b.png)

6. Find the distribution of star ratings to the business in the following cities:
* i. Avon
* SQL code used to arrive at answer:
![Peer_review_P1_avon_1](https://user-images.githubusercontent.com/102244119/167317967-77914263-3455-4d79-8eb7-946a94c2864f.png)

* Copy and Paste the Resulting Table Below (2 columns as star rating and count):
![Peer_review_P1_avon_2](https://user-images.githubusercontent.com/102244119/167317993-3c7dfca1-e84c-488c-899d-831d1b3789bf.png)

* ii. Beachwood
* SQL code used to arrive at answer:
![Peer_review_P1_beachwood_1](https://user-images.githubusercontent.com/102244119/167318070-b535b742-63f8-4e86-8626-68b6d598a921.png)

* Copy and Paste the Resulting Table Below (2 columns as star rating and count):
![Peer_review_P1_beachwood_2](https://user-images.githubusercontent.com/102244119/167318080-8670f918-7178-4716-adbd-d955750ef12c.png)

7. Find the top 3 users based on their total number of reviews:
* SQL code used to arrive at answer:
![Peer_review_top3users1](https://user-images.githubusercontent.com/102244119/167318398-bdcafa94-43ac-4608-a741-d3e8c397e1ce.png)

* Copy and Paste the Result Below:
![Peer_review_top3users2](https://user-images.githubusercontent.com/102244119/167318419-7b9db304-9a06-4b4c-9bef-eeb12d8df123.png)

8. Does posing more reviews correlate with more fans? Answer: No
* Please explain your findings and interpretation of the results: As you can see by the below result, more reviews does not result in more fans.
![peer_review_fans](https://user-images.githubusercontent.com/102244119/167318441-eaad6fd9-ca07-448f-ab9e-1ac207925248.png)

* SQL code used to arrive at answer:
![peer_review_fans2](https://user-images.githubusercontent.com/102244119/167318469-1f105ea2-2ad3-438a-ad09-71f1d8a81aec.png)

9. Are there more reviews with the word "love" or with the word "hate" in them? Answer: Love
![peer_review_landh2](https://user-images.githubusercontent.com/102244119/167318536-eb3c3887-3798-4bf2-8f46-5d4d1589fb92.png)

* SQL code used to arrive at answer:
![peer_review_landh](https://user-images.githubusercontent.com/102244119/167318494-76fa5d9e-d6ef-4e69-899f-a499ce2e815e.png)

10. Find the top 10 users with the most fans:
* SQL code used to arrive at answer:
![peer_review_top10_1](https://user-images.githubusercontent.com/102244119/167318553-01e0eeb6-0b22-4b59-9364-9df050c78b4f.png)

* Copy and Paste the Result Below:
![peer_review_top10_2](https://user-images.githubusercontent.com/102244119/167318586-4c85a330-b4f7-49af-a103-a5c8231956c8.png)
