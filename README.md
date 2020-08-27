# lab-14
This lab involves seeding a database, then executing a series of commands to normalize data into two tables: books and authors. Using SQL I  normalized data and remove duplications.

# Number and name of feature: Database Setup

Estimate of time needed to complete: 30min

Start time: 11:20am 8/27/2019

Finish time: 11:45am

Actual time needed to complete: 25min

------------
# Number and name of feature: Database Migration
* CREATE TABLE AUTHORS (id SERIAL PRIMARY KEY, name VARCHAR(255));
* INSERT INTO authors(name) SELECT DISTINCT author FROM books;
* ALTER TABLE books ADD COLUMN author_id INT;
* UPDATE books SET author_id=author.id FROM (SELECT * FROM authors) AS author WHERE books.author = author.name;
* ALTER TABLE books DROP COLUMN author;
* ALTER TABLE books ADD CONSTRAINT fk_authors FOREIGN KEY (author_id) REFERENCES authors(id);

Estimate of time needed to complete: 1hr

Start time: 2:00pm 8/27/2019

Finish time: 3:15pm

Actual time needed to complete: 1hr15min



