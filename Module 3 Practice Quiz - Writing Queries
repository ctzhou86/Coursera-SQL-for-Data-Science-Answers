1. How many albums does the artist Led Zeppelin have?

select count(*) from (select *
from artists
left join albums
on artists.ArtistId=albums.ArtistId)
where Name="Led Zeppelin";

2. Create a list of album titles and the unit prices for the artist "Audioslave". How many records are returned?

select a.UnitPrice,b.Title,b.Name
from (select tracks.AlbumId,invoice_items.UnitPrice
from tracks
left join invoice_items
on tracks.TrackId=invoice_items.TrackId) as a
left join (select artists.Name,albums.Title,albums.AlbumId
from artists
left join albums
on artists.ArtistId=albums.ArtistId) as b
on a.AlbumId=b.AlbumId
where b.Name="Audioslave";

3. Find the first and last name of any customer who does not have an invoice. Are there any customers returned from the query?

select customers.FirstName,customers.LastName,
invoices.InvoiceId
from customers
left join invoices
on customers.CustomerId=invoices.CustomerId
where invoices.InvoiceId is null;

4. Find the total price for each album. What is the total price for the album “Big Ones”?

select sum(b.UnitPrice) as TotalPrice,b.Title as Title
from (select a.UnitPrice as UnitPrice,albums.Title as Title
from (select tracks.AlbumId,invoice_items.UnitPrice
from tracks
left join invoice_items
on tracks.TrackId=invoice_items.TrackId) as a 
left join albums
on a.AlbumId=albums.AlbumId
where albums.Title="Big Ones") as b

5. How many records are created when you apply a Cartesian join to the invoice and invoice items table?

select invoices.InvoiceId
from invoices
cross join invoice_items
