# Intro to SQL

1. Install the SQLite Browser if you haven't already [here](http://sqlitebrowser.org/)
2. Open the SQLite Browser and click 'File -> Open DataBase'
3. Choose the `chinook.db` file from this repo. This database is open source and maintained by Microsoft (SQL is no fun if you don't have any data)


## WHAT are the 4 things I can do to data?

Create
Read
Update
Destroy



## Challenges

1. How would you return all of the rows in the artists table?
  ```SQL
  SELECT * FROM artists;
  ```
2. How would you select the artist with the name "Black Sabbath"
  ```SQL
  SELECT * FROM artists WHERE name = "Black Sabbath";
  ```
3. How would you create a table named 'fans' with an autoincrementing ID that's a primary key and a name field of type text

  ```sql
   CREATE_TABLE fans (id INTEGER PRIMARY KEY, name TEXT);
  ```

4. How would you alter the fans table to have a artist_id column type integer?

  ```sql
   ALTER TABLE fans ADD COLUMN artist_id INTEGER
  ```
5. How would you add yourself as a fan of the Black Eyed Peas? ArtistId **169**
  ```sql
    INSERT INTO fans (name, artist_id) VALUES ('alex', 169)
  ```

6. Check out the [Faker gem](https://github.com/stympy/faker). `gem install faker`, open up irb, run `require 'faker'` and then generate a fake name for yourself using `Faker::Name.name`. How would you update your name in the fans table to be your new name?
   ```sql

   ```

7. How would you return fans that are not fans of the black eyed peas.
  ```sql
  SELECT * from fans where artist_id != 169
  ```
8. Display an artists name next to their album title
```sql
SELECT artists.name, albums.title from artists
INNER JOIN albums
ON albums.ArtistId = artists.ArtistId
```

9. Display artist name, album name and number of tracks on that album
```sql
SELECT artists.name as artist_name, albums.title as album_title, COUNT(tracks.name) as track_name FROM artists
JOIN albums
ON albums.ArtistId = artists.ArtistId
JOIN tracks
ON tracks.AlbumId = albums.AlbumId
GROUP BY (albums.AlbumId);


```

10.  How would you return the name of all of the artists in the 'Pop' Genre
  ```sql
SELECT DISTINCT artists.name  FROM artists
JOIN albums
ON albums.ArtistId = artists.ArtistId
JOIN tracks
ON tracks.AlbumId = albums.AlbumId
JOIN genres
ON genres.GenreId = tracks.GenreId
WHERE genres.name = 'Pop'

  ```


11. I want to return the names of the artists and their number of rock tracks
 who play Rock music
and have move than 30 tracks
in order of the number of rock tracks that they have
from greatest to least

```sql

```
