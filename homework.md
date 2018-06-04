# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

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

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

  SELECT * FROM movies;

  id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 23:55
  2 | The Incredible Hulk                 | 2008 | 12:10
  3 | Iron Man 2                          | 2010 | 15:45
  4 | Thor                                | 2011 | 16:25
  5 | Captain America: The First Avenger  | 2011 | 16:55
  6 | Avengers Assemble                   | 2012 | 13:25
  7 | Iron Man 3                          | 2013 | 23:15
  8 | Thor: The Dark World                | 2013 | 16:50
  9 | Batman Begins                       | 2005 | 20:05
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 17:45
 13 | Ant-Man                             | 2015 | 16:30
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 16:10
 16 | Guardians of the Galaxy 2           | 2017 | 17:25
 17 | Spider-Man: Homecoming              | 2017 | 13:50
 18 | Thor: Ragnarok                      | 2017 | 14:40
 19 | Black Panther                       | 2018 | 15:00

2.  Return ONLY the name column from the 'people' table

SELECT name FROM people;

name            
---------------------------
Shaun   Adams
James   Amos
Lee     Burgess
Stuart  Charters
Wil     Cornish
Gregor  Cox
Chris   Craig
Gabriel González Villalba
James   Henderson
Edward  Kinley
Magdalena       Kisala
Emily Milne
Iona    Macbeth
Gary    Muir
Helen   Oshea
David   Pears
Jezuz   Perez
Benjamin        Robinson
Stephen Rooney
Can     Toraman
Daniel  Warren

3.  Oops! Someone at CodeClan spelled Jesus's name wrong! Change it to reflect the proper spelling ('Jezuz Perez' should be 'Jesus Perez').

UPDATE people SET name = 'Jesus Perez' WHERE id = 17;

name            
---------------------------
Shaun   Adams
James   Amos
Lee     Burgess
Stuart  Charters
Wil     Cornish
Gregor  Cox
Chris   Craig
Gabriel González Villalba
James   Henderson
Edward  Kinley
Magdalena       Kisala
Emily Milne
Iona    Macbeth
Gary    Muir
Helen   Oshea
David   Pears
Benjamin        Robinson
Stephen Rooney
Can     Toraman
Daniel  Warren
Jesus Perez

4.  Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE id = 14;

name     
--------------
Gary    Muir

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 23:55
  2 | The Incredible Hulk                 | 2008 | 12:10
  3 | Iron Man 2                          | 2010 | 15:45
  4 | Thor                                | 2011 | 16:25
  5 | Captain America: The First Avenger  | 2011 | 16:55
  6 | Avengers Assemble                   | 2012 | 13:25
  7 | Iron Man 3                          | 2013 | 23:15
  8 | Thor: The Dark World                | 2013 | 16:50
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 17:45
 13 | Ant-Man                             | 2015 | 16:30
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 16:10
 16 | Guardians of the Galaxy 2           | 2017 | 17:25
 17 | Spider-Man: Homecoming              | 2017 | 13:50
 18 | Thor: Ragnarok                      | 2017 | 14:40
 19 | Black Panther                       | 2018 | 15:00

6.  Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('John Harper');

id |           name            
----+---------------------------
  1 | Shaun   Adams
  2 | James   Amos
  3 | Lee     Burgess
  4 | Stuart  Charters
  5 | Wil     Cornish
  6 | Gregor  Cox
  7 | Chris   Craig
  8 | Gabriel González Villalba
  9 | James   Henderson
 10 | Edward  Kinley
 11 | Magdalena       Kisala
 12 | Emily Milne
 13 | Iona    Macbeth
 14 | Gary    Muir
 15 | Helen   Oshea
 16 | David   Pears
 18 | Benjamin        Robinson
 19 | Stephen Rooney
 20 | Can     Toraman
 21 | Daniel  Warren
 22 | John Harper
 17 | Jesus Perez

7.  Emily Milne has decided to hijack our movie evening, Remove her from the table of people.

DELETE FROM people WHERE name = 'Emily Milne';

id |           name            
----+---------------------------
  1 | Shaun   Adams
  2 | James   Amos
  3 | Lee     Burgess
  4 | Stuart  Charters
  5 | Wil     Cornish
  6 | Gregor  Cox
  7 | Chris   Craig
  8 | Gabriel González Villalba
  9 | James   Henderson
 10 | Edward  Kinley
 11 | Magdalena       Kisala
 13 | Iona    Macbeth
 14 | Gary    Muir
 15 | Helen   Oshea
 16 | David   Pears
 18 | Benjamin        Robinson
 19 | Stephen Rooney
 20 | Can     Toraman
 21 | Daniel  Warren
 22 | John Harper
 17 | Jesus Perez

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 23:55
  2 | The Incredible Hulk                 | 2008 | 12:10
  3 | Iron Man 2                          | 2010 | 15:45
  4 | Thor                                | 2011 | 16:25
  5 | Captain America: The First Avenger  | 2011 | 16:55
  6 | Avengers Assemble                   | 2012 | 13:25
  7 | Iron Man 3                          | 2013 | 23:15
  8 | Thor: The Dark World                | 2013 | 16:50
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 17:45
 13 | Ant-Man                             | 2015 | 16:30
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 16:10
 16 | Guardians of the Galaxy 2           | 2017 | 17:25
 17 | Spider-Man: Homecoming              | 2017 | 13:50
 18 | Thor: Ragnarok                      | 2017 | 14:40
 19 | Black Panther                       | 2018 | 15:00
 20 | Avengers: Infinity War              | 2018 | 00:00

9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

UPDATE movies SET show_time = '21:05' WHERE title = 'Guardians of the Galaxy 2';

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 23:55
  2 | The Incredible Hulk                 | 2008 | 12:10
  3 | Iron Man 2                          | 2010 | 15:45
  4 | Thor                                | 2011 | 16:25
  5 | Captain America: The First Avenger  | 2011 | 16:55
  6 | Avengers Assemble                   | 2012 | 13:25
  7 | Iron Man 3                          | 2013 | 23:15
  8 | Thor: The Dark World                | 2013 | 16:50
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 17:45
 13 | Ant-Man                             | 2015 | 16:30
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 16:10
 17 | Spider-Man: Homecoming              | 2017 | 13:50
 18 | Thor: Ragnarok                      | 2017 | 14:40
 19 | Black Panther                       | 2018 | 15:00
 20 | Avengers: Infinity War              | 2018 | 00:00
 16 | Guardians of the Galaxy 2           | 2017 | 21:05

## Extension

1.  Research how to delete multiple entries from your table in a single command.

DELETE FROM movies WHERE id BETWEEN 1 AND 5;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  6 | Avengers Assemble                   | 2012 | 13:25
  7 | Iron Man 3                          | 2013 | 23:15
  8 | Thor: The Dark World                | 2013 | 16:50
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 17:45
 13 | Ant-Man                             | 2015 | 16:30
 14 | Captain America: Civil War          | 2016 | 16:00
 15 | Doctor Strange                      | 2016 | 16:10
 17 | Spider-Man: Homecoming              | 2017 | 13:50
 18 | Thor: Ragnarok                      | 2017 | 14:40
 19 | Black Panther                       | 2018 | 15:00
 20 | Avengers: Infinity War              | 2018 | 00:00
 16 | Guardians of the Galaxy 2           | 2017 | 21:05
