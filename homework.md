# SQL Homework

The GFT is having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

--marvel=# SELECT * FROM movies;
_time
----+-------------------------------------+------+-----
------
  1 | Iron Man                            | 2008 | 23:5
0
  2 | The Incredible Hulk                 | 2008 | 19:5
0
  3 | Iron Man 2                          | 2010 | 13:1
0
  4 | Thor                                | 2011 | 19:2
5
  5 | Captain America: The First Avenger  | 2011 | 15:5
0
  6 | Avengers Assemble                   | 2012 | 20:2
0
  7 | Iron Man 3                          | 2013 | 22:25
  8 | Thor: The Dark World                | 2013 | 21:25
  9 | Batman Begins                       | 2005 | 13:00
 10 | Captain America: The Winter Soldier | 2014 | 21:45
 11 | Guardians of the Galaxy             | 2014 | 15:50
 12 | Avengers: Age of Ultron             | 2015 | 14:55
 13 | Ant-Man                             | 2015 | 16:5:



2. Return ONLY the name column from the 'people' table

SELECT name FROM people;
       name        
-------------------
 Henrique Batista
 David Bell
 Valentina Bonetti
 Andrew Brown
 Gillian Campbell
 Jordan Davidson
 Neil Davidson
 Craig Dunlop
 Gil Franca
 Hadsan Geeele
 Stephen Hart
 Anna Henderson
 Alistair Kane
 Asma Malik
 Leah Meromy
 Drew Neillie
 Neal Rethvun
 David Telfer
 Raymond Yau
(19 rows)



3. Oh bother! Someone at CodeClan spelled Neil R's name wrong! Change it to reflect the proper spelling (change 'Neal Rethvun' to 'Neil Ruthven').

marvel=# UPDATE people SET name = 'Neil Ruthven' WHERE name = 'Neal Rethvun';
UPDATE 1


4. Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Gil Franca';
    name    
------------
 Gil Franca
(1 row)

5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman';
DELETE 0

SELECT title FROM movies WHERE title = 'Batman';
 title
-------
(0 rows)



6. Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Steve');
INSERT 0 1



7. Oh no! Nefarious G7 instructor Alistair Kane has decided to hijack our movie evening! Remove him from the table of people.

DELETE FROM people WHERE name = 'Alistair Kane';
DELETE 1

8. The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers Infinity War', 2018, '12:00');
INSERT 0 1




9. The cinema would also like to make the Guardian movies a back-to-back feature. Update the 'Guardians of the Galaxy 2' show time from 14:45 to 18:00

UPDATE movies SET show_time = '18:00' WHERE title = 'Guardians of the Galaxy 2';
UPDATE 1



## Extension

1. Research how to delete multiple entries from your table in a single command.
