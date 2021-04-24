# sql-query-practice


### Round 1

Connect to the LikeyPix database in Beekeeper, and answer the following questions:

1. Write a query that returns all Users

```
Paste your query below:

select * from users;

```

2. Write a query that returns all Posts

```
Paste your query below:

select * from posts;

```

3. Write a query that returns the count of all Posts

```
Paste your query below:

select count(*) from posts;

```

4. Which Post had the most Comments?

Answer: walking-the-cat.jpg

5. Write a query that returns the Post which had the least Comments

```
Paste your query below:

select count(*) as num, post_id from comments
	  group by post_id
    order by num asc
    limit 1
;

```

6. Which User has the most Comments?

Answer: Alice

7. Write a single query to get all of the Posts and their Comments (You'll see the same Post repeated in the results)

```
Paste your query below:

select count(*) as num, post_id from comments
	group by post_id
    order by num asc
    limit 1
;

```

### Round 2

- Disconnect from the `likeypix` database connection
- Connect to the `classroom` database connection

1. Write a query to get the first name, last name, and github URL for every Student in the `students` table

```
Paste your query below:

select first_name, last_name, github_url from students;

```

2. Write a query to get a list of Students who do not have a LinkedIn URL

```
Paste your query below:

select first_name, last_name, github_url from students;

```

3. Write a query to get a list of Teachers with the "Teaching Assistant" Role

```
Paste your query below:

select first_name, last_name, github_url from students;

```

4. Write a query to get a list of Students, and their Class' `slug`

```
Paste your query below:

select s.*, c.slug
	from students s inner join classes c
    sql	on s.class_id = c.id
;

```

5. Write a query to get the length of every students First Name

```
Paste your query below:

select first_name, length(first_name) as length_of_name from students;

```

6. What is the ID of the Student with the longest Last Name?

Answer: 8

7. Write a query to get a list of Students in reverse alphabetical order of First Name

```
Paste your query below:

select first_name from students
	order by first_name desc
;

```

### Round 3

- Disconnect from the `classroom` database connection
- Connect to the `food` database connection

This Round is going to require you to get curious about your surroundings. At some point in your path as a developer, you will work on a project that already has an existing database. That database may be quite old, or have been built on a different set of standards.

These questions will be focused on exploring an unknown database that does not follow the standards we have established in class. See if you can work out answers to the following questions:


1. What table contains information about individual food items? 

Answer: food_des

2. Using the table from the previous answer as your starting point - what table do you think contains Food Group information about individual foods?

Answer: fd_group

3. Write a query to get the name of a food, and its corresponding food group name 

```
Paste your query below:

select fd.shrt_desc, fg.fddrp_desc
	from food_des fd inner join fd_group fg
    	on fd.fdgrp_cd = fg.fdgrp_cd
;

```

4. Identify the table that has information about data sources

Answer: data_src

5. Using the table from your previous answer, write a query that will get the oldest data source

```
Paste your query below:

select fd.shrt_desc, fg.fddrp_desc
	from food_des fd inner join fd_group fg
    	on fd.fdgrp_cd = fg.fdgrp_cd
;

```

6. How many foods contain "Egg" in their description?

Answer: 101

7. Write a query that will return a count of foods in each food group

```
Paste your query below:

select count(*) as num, fg.fddrp_desc
	from food_des fd inner join fd_group fg
    	on fd.fdgrp_cd = fg.fdgrp_cd
    group by fg.fddrp_desc
;

```
