# Chinook Music Store Analysis - SQLite

| Summary | 
| ----------- | 
|The dataset downloaded from Kaggle.com contains the Chinook Database and the schema for the databased. This project is the examination of the dataset to help the store understand the media in their store, their customers and employees, and their invoice information by answering the following questions|

## Schema
<img width="457" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/f9c46b56-b35f-4678-b079-e9cb118e3b90">


## SQLite
**Query 1: Top country/market**

SELECT billing_country as 'Country', COUNT(invoice_id) as 'Orders', SUM(total)as 'Sales amount'
FROM invoice
Group By 1
Order By 2 Desc;

<img width="209" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/40a8ad52-95a5-48b3-8669-1451b2a75c79">


**Query 2: Email, first name, last name, and Genre of all Rock Music listenerss**

SELECT DISTINCT c.first_name,
C.last_name,
C.email,
G.name

FROM CUSTOMER AS C

JOIN INVOICE AS I ON C.customer_id = I.customer_id
JOIN INVOICE_LINE AS IL ON I.invoice_id = IL.invoice_line_id
JOIN TRACK AS T ON IL.track_id = T.track_id
JOIN GENRE AS G ON T.genre_id = G.genre_id

WHERE G.name = "Rock"

order by 1;

<img width="326" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/93750001-2c3a-4cce-a827-59d996fec75f">

**Query 3: Which customer spent the most and how much**

SELECT C.first_name,C.last_name,sum(I.TOTAL)AS 'Spend Amount'
FROM CUSTOMER AS C
JOIN INVOICE AS I ON C.customer_id = I.customer_id
group by 1
ORDER BY 2 DESC

<img width="236" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/2f54d623-925a-49eb-9ffb-3561e97167fd">

**Query 4: If we are hosting a Rock concert, which Top 4 artists will perform**

SELECT AR.name, COUNT(T.name)
FROM artist as AR
JOIN album as AL ON AL.artist_id = AR.artist_id
JOIN track AS T ON T.album_id = AL.album_id
JOIN genre as G ON G.genre_id = T.genre_id
WHERE G.name = 'Rock'
GROUP BY 1
ORDER BY 2 DESC;

 *Led Zeppelin; U2; Deep Purple; Iron Maiden;*
 
<img width="365" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/b6264bb2-b809-4cf5-98e8-6f6e76feab02">

##
 
