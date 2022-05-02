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
![CE_DataScientistRP_1](https://user-images.githubusercontent.com/102244119/166242977-9220557d-4803-44d2-8873-b8b85b758428.png)

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
![CE_DataScientistRP_2](https://user-images.githubusercontent.com/102244119/166243100-c52090e6-1a36-4367-9098-3f115ac12680.png)

3. Are there any columns with null values in the Users table? Indicate "yes," or "no."
* Answer: No

SQL code user to arrive at answer:
![CE_DataScientistRP_3](https://user-images.githubusercontent.com/102244119/166243170-0977e9de-65fe-47e4-be90-b0f1bf2f24d9.png)

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
![CE_DataScientistRP_4](https://user-images.githubusercontent.com/102244119/166243216-db06eef4-472f-4d63-ba25-97315700cd10.png)

5. List the cities with the most reviews in descending order:
* SQL code used to arrive at answer:
![CE_DataScientistRP_5_1](https://user-images.githubusercontent.com/102244119/166243254-ffd07ffe-1735-46d9-9b65-f22a93688f04.png)

* Copy and Paste the Result Below:
![CE_DataScientistRP_5_2](https://user-images.githubusercontent.com/102244119/166243288-430674a6-a201-498d-9792-d46febdffa66.png)

6. Find the distribution of star ratings to the business in the following cities:
* i. Avon
* SQL code used to arrive at answer:
![CE_DataScientistRP_6_1](https://user-images.githubusercontent.com/102244119/166243318-a07d3ce1-9d28-41e8-bbb8-482bf626ac90.png)

* Copy and Past the Resulting Table Below (2 columns as star rating and count):
![CE_DataScientistRP_6_2](https://user-images.githubusercontent.com/102244119/166243361-a503cd90-48fd-416b-b960-2f937e5cd711.png)

* ii. Beachwood
* SQL code used to arrive at answer:
![CE_DataScientistRP_6_3](https://user-images.githubusercontent.com/102244119/166243402-874b75fd-5214-472d-92ad-4da3aae29cc5.png)

* Copy and Past the Resulting Table Below (2 columns as star rating and count):
![CE_DataScientistRP_6_4](https://user-images.githubusercontent.com/102244119/166243419-bfa14108-9bc5-41e9-b38c-948c76162ac6.png)

7. Find the top 3 users based on their total number of reviews:
* SQL code used to arrive at answer:
![CE_DataScientistRP_7_1](https://user-images.githubusercontent.com/102244119/166243460-f9bf5e30-9a0a-4f63-94eb-101956aa62b3.png)

* Copy and Paste the Result Below:
![CE_DataScientistRP_7_2](https://user-images.githubusercontent.com/102244119/166243483-0f8db347-5087-4aa0-9380-613445d70ce4.png)

8. Does posing more reviews correlate with more fans? Answer: No
* Please explain your findings and interpretation of the results: As you can see by the below result, more reviews does not result in more fans.
![CE_DataScientistRP_8_1](https://user-images.githubusercontent.com/102244119/166243523-6354e364-806e-4ae8-8fd7-9e16b80910fa.png)

* SQL code used to arrive at answer:
![CE_DataScientistRP_8_2](https://user-images.githubusercontent.com/102244119/166243579-e7c416ad-ad51-4017-a102-617669a10fca.png)

9. Are there more reviews with the word "love" or with the word "hate" in them? Answer: Love
* SQL code used to arrive at answer:
![CE_DataScientistRP_9](https://user-images.githubusercontent.com/102244119/166243608-c7106b83-5cf4-4af5-b08e-2a8e8dd30008.png)

10. Find the top 10 users with the most fans:
* SQL code used to arrive at answer:
![CE_DataScientistRP_10_1](https://user-images.githubusercontent.com/102244119/166243649-7d8682ea-4e24-46e1-b23e-ec23670eb267.png)

* Copy and Paste the Result Below:
![CE_DataScientistRP_10_2](https://user-images.githubusercontent.com/102244119/166243679-171130fd-5328-4d4e-8b15-df39559f4ac2.png)
