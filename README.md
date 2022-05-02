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

SQL code used to arrive at answer:
* Attribute table:
SELECT 
COUNT (*) as attribute_rows
FROM attribute
* Business table:
SELECT 
COUNT (*) as business_rows
FROM business
* Category table:
SELECT 
COUNT (*) as category_rows
FROM category
* Checkin table:
SELECT 
COUNT (*) as checkin_rows
FROM checkin
* Elite years table:
SELECT 
COUNT (*) as eliteyears_rows
FROM elite_years
* Friend table:
SELECT 
COUNT (*) as friend_rows
FROM friend
* Hours table:
SELECT 
COUNT (*) as hours_rows
FROM hours
* Photo table:
SELECT 
COUNT (*) as photo_rows
FROM photo
* Review table:
SELECT 
COUNT (*) as review_rows
FROM review
* Tip table:
SELECT 
COUNT (*) as tip_rows
FROM tip
* User table:
SELECT 
COUNT (*) as user_rows
FROM user

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
* Business:
SELECT COUNT (DISTINCT id)
FROM business
* Hours:
SELECT COUNT (DISTINCT business_id)
FROM hours
* Category:
SELECT COUNT (DISTINCT business_id)
FROM category
* Attribute:
SELECT COUNT (DISTINCT business_id)
FROM attribute
* Review:
SELECT COUNT (DISTINCT id)
FROM review
SELECT COUNT (DISTINCT business_id)
FROM review
* Checkin:
SELECT COUNT (DISTINCT business_id)
FROM checkin
* Photo: 
SELECT COUNT (DISTINCT id)
FROM photo
SELECT COUNT (DISTINCT business_id)
FROM photo
* Tip:
SELECT COUNT (DISTINCT user_id)
FROM tip
SELECT COUNT (DISTINCT business_id)
FROM tip
* User:
SELECT COUNT (DISTINCT id)
FROM user
* Friend:
SELECT COUNT (DISTINCT user_id)
FROM friend
* Elite years:
SELECT COUNT (DISTINCT user_id)
FROM elite_years
-- Note: Primary Keys are denoted in the ER-Diagram with a yellow key icon.

3. Are there any columns with null values in the Users table? Indicate "yes," or "no."
* Answer: No

SQL code user to arrive at answer:

SELECT *
FROM user
WHERE id is NULL OR
name is NULL OR
review_count is NULL OR
yelping_since is NULL OR
useful is NULL OR
funny is NULL OR
cool is NULL OR
fans is NULL OR
average_stars is NULL OR
compliment_hot is NULL OR
compliment_more is NULL OR
compliment_profile is NULL OR
compliment_cute is NULL OR
compliment_list is NULL OR
compliment_note is NULL OR
compliment_plain is NULL OR
compliment_cool is NULL OR
compliment_funny is NULL OR
compliment_writer is NULL OR
compliment_photos is NULL

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

* Table: Review, Column: Stars 
SELECT MIN (stars), 
MAX (stars), 
AVG (stars)
FROM review
* Table: Business, Column: Stars
SELECT MIN (stars), 
MAX (stars), 
AVG (stars)
FROM business
* Table: Tip, Column: Likes 
SELECT MIN (likes), 
MAX (likes), 
AVG (likes)
FROM tip
* Table: Checkin, Column: Count
SELECT MIN (count), 
MAX (count), 
AVG (count)
FROM checkin
* Table: User, Column: Review_count
SELECT MIN (review_count), 
MAX (review_count), 
AVG (review_count)
FROM user

5. List the cities with the most reviews in descending order:
* SQL code used to arrive at answer:
SELECT city, SUM(review_count) as review_total
FROM business
GROUP BY city
ORDER BY review_total DESC
* Copy and Paste the Result Below:
+-----------------+--------------+
| city            | review_total |
+-----------------+--------------+
| Las Vegas       |        82854 |
| Phoenix         |        34503 |
| Toronto         |        24113 |
| Scottsdale      |        20614 |
| Charlotte       |        12523 |
| Henderson       |        10871 |
| Tempe           |        10504 |
| Pittsburgh      |         9798 |
| Montréal        |         9448 |
| Chandler        |         8112 |
| Mesa            |         6875 |
| Gilbert         |         6380 |
| Cleveland       |         5593 |
| Madison         |         5265 |
| Glendale        |         4406 |
| Mississauga     |         3814 |
| Edinburgh       |         2792 |
| Peoria          |         2624 |
| North Las Vegas |         2438 |
| Markham         |         2352 |
| Champaign       |         2029 |
| Stuttgart       |         1849 |
| Surprise        |         1520 |
| Lakewood        |         1465 |
| Goodyear        |         1155 |
+-----------------+--------------+
(Output limit exceeded, 25 of 362 total rows shown)

6. Find the distribution of star ratings to the business in the following cities:
* i. Avon
* SQL code used to arrive at answer:
SELECT stars,
SUM (review_count) AS total_reviews
FROM business
WHERE city = 'Avon'
GROUP BY stars
* Copy and Past the Resulting Table Below (2 columns as star rating and count):
+-------+---------------+
| stars | total_reviews |
+-------+---------------+
|   1.5 |            10 |
|   2.5 |             6 |
|   3.5 |            88 |
|   4.0 |            21 |
|   4.5 |            31 |
|   5.0 |             3 |
+-------+---------------+
* ii. Beachwood
* SQL code used to arrive at answer:
SELECT stars,
SUM (review_count) AS total_reviews
FROM business
WHERE city = 'Beachwood'
GROUP BY stars
* Copy and Past the Resulting Table Below (2 columns as star rating and count):
+-------+---------------+
| stars | total_reviews |
+-------+---------------+
|   2.0 |             8 |
|   2.5 |             3 |
|   3.0 |            11 |
|   3.5 |             6 |
|   4.0 |            69 |
|   4.5 |            17 |
|   5.0 |            23 |
+-------+---------------+

7. Find the top 3 users based on their total number of reviews:
* SQL code used to arrive at answer:
SELECT name,
review_count
FROM user
ORDER BY review_count DESC
LIMIT 3
* Copy and Paste the Result Below:
+--------+--------------+
| name   | review_count |
+--------+--------------+
| Gerald |         2000 |
| Sara   |         1629 |
| Yuri   |         1339 |
+--------+--------------+

8. Does posing more reviews correlate with more fans? Answer: No
* Please explain your findings and interpretation of the results: As you can see by the below result, more reviews does not result in more fans.
+-----------+--------------+------+
| name      | review_count | fans |
+-----------+--------------+------+
| Amy       |          609 |  503 |
| Mimi      |          968 |  497 |
| Harald    |         1153 |  311 |
| Gerald    |         2000 |  253 |
| Christine |          930 |  173 |
| Lisa      |          813 |  159 |
| Cat       |          377 |  133 |
| William   |         1215 |  126 |
| Fran      |          862 |  124 |
| Lissa     |          834 |  120 |
| Mark      |          861 |  115 |
| Tiffany   |          408 |  111 |
| bernice   |          255 |  105 |
| Roanna    |         1039 |  104 |
| Angela    |          694 |  101 |
| .Hon      |         1246 |  101 |
| Ben       |          307 |   96 |
| Linda     |          584 |   89 |
| Christina |          842 |   85 |
| Jessica   |          220 |   84 |
| Greg      |          408 |   81 |
| Nieves    |          178 |   80 |
| Sui       |          754 |   78 |
| Yuri      |         1339 |   76 |
| Nicole    |          161 |   73 |
+-----------+--------------+------+
(Output limit exceeded, 25 of 10000 total rows shown)
* SQL code used to arrive at answer:
SELECT name, 
review_count, 
fans
FROM user 
ORDER BY fans DESC

9. Are there more reviews with the word "love" or with the word "hate" in them? Answer: Love
* SQL code used to arrive at answer:
SELECT COUNT(text) as love_review
FROM review
WHERE text LIKE '%love%'

SELECT COUNT(text) AS hate_review
FROM review
WHERE text LIKE '%hate%'
+-------------+
| love_review |
+-------------+
|        1780 |
+-------------+
+-------------+
| hate_review |
+-------------+
|         232 |
+-------------+

10. Find the top 10 users with the most fans:
* SQL code used to arrive at answer:
SELECT name, 
fans AS number_of_fans
FROM user 
ORDER BY fans DESC
Limit 10
* Copy and Paste the Result Below:
+-----------+----------------+
| name      | number_of_fans |
+-----------+----------------+
| Amy       |            503 |
| Mimi      |            497 |
| Harald    |            311 |
| Gerald    |            253 |
| Christine |            173 |
| Lisa      |            159 |
| Cat       |            133 |
| William   |            126 |
| Fran      |            124 |
| Lissa     |            120 |
+-----------+----------------+
