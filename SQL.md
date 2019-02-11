select statement:

select Name from Artist;        (display number of records/rows in artist table)

select FirstName, LastName from Customer;       (shows first and last names)

select * from Track;    (return all columns for all rows in table)


challenge:
select Name from MediaType;         (select all names from 'mediatype table')


WHERE CLAUSE:

select * from Track
    where Composer = 'U2';          (retrieves all columns from the Track table..but only the U2 ones will be                                            returned)

select * from Album
    where AlbumId = 232;
    
CHALLENGE:

select FirstName, LastName, Title from Employee         (select FirstName,lastname and title for every employee 
    where Title = 'IT Staff';                               that has a title of IT Staff)
    
    
    
JOIN:

select * from Track                 (look in album table to find artist for track..)
    INNER JOIN Album on Track.AlbumId = Album.AlbumId;
    
    (the join pulls in the rows from track table. for each row it adds the data from the album table
     we can now see the ArtistId for each trACK)
    
    
select Name, Title, ArtistId from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId;
    (return name from track table, title from album table and artistId from album table)
    
    
select Name as Track, Title as Album, ArtistId from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId;
    
    
select Name as Track, Title as Album, ArtistId, Name as Artist from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId;
    (error..field list is ambiguos..column name specifically)
    (track and artist both have columns called name..so we need to define them..as we see below)
    
select Track.Name as Track, Title as Album, Album.ArtistId, Artist.Name as Artist from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId;
    
select Track.Name as Track, Title as Album,  Artist.Name as Artist from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId;      (removed artistId)
    
    
select Track.Name as Track, Title as Album, Artist.Name as Artist From Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId
    where Artist.Name = 'U2';
    
    
    
SELECT Track.Name as Track, Title as Album, Artist.Name as Artist from Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId
    WHERE Artist.Name = 'U2' and Track.Name = 'Pride (In The Name Of Love)';
(look for artist and track)


SELECT Track.Name as Track, Title as Album, Artist.Name as Artist FROM Track
    INNER JOIN Album on Track.AlbumId = Album.AlbumId
    INNER JOIN Artist on Album.ArtistId = Artist.ArtistId
    WHERE Track.Name = "Believe";
    (search for track name..regardless of artist or album)
    (looks for track called Believe...and it shows 3 seperate artists have recorded it)





    
    
    
    
    
    
    
    

