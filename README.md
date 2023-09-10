# Chinook Music Store Analysis - SQLite

| Summary | 
| ----------- | 
|The dataset downloaded from Kaggle.com contains the Chinook Database and the schema for the databased. This project is the examination of the dataset to help the store understand the media in their store, their customers and employees, and their invoice information by answering the following questions|

## Schema
<img width="457" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/f9c46b56-b35f-4678-b079-e9cb118e3b90">


## SQLite
**Query 1: Top 10 Genres**
  

**Query 1.1: The best city to host a rock concert**

*Location: Prague*

**Query 1.2: Top 4 artists with highest tracks to perform**

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


- **Top sales agent**

## Analysis Powerpoint Slides
 
