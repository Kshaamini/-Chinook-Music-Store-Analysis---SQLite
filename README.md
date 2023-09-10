# Chinook Music Store Analysis - SQLite

| Summary | 
| ----------- | 
|The dataset downloaded from Kaggle.com contains the Chinook Database and the schema for the databased. This project is the examination of the dataset to help the store understand the media in their store, their customers and employees, and their invoice information by answering the following questions|

## Schema
<img width="457" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/f9c46b56-b35f-4678-b079-e9cb118e3b90">


## SQLite
- **The highest number of invoices belongs to which country?**
  
  *USA*
  
  <img width="263" alt="image" src="https://github.com/Kshaamini/DataAnalysis-SQL/assets/139740694/d26a2c0e-95d9-4074-b357-923f9c587c70">

- **Sale per unit per genre and percentage of sale. Limited to top 10**

- **The best city to host a rock concert and which artists to perfom**

Location: *Prague*

<img width="230" alt="image" src="https://github.com/Kshaamini/DataAnalysis-SQL/assets/139740694/1178fa95-fc01-486a-9a47-7949adb0bd76">

Top 5 artists with highest tracks to perform: *Led Zeppelin; U2; Deep Purple; Iron Maiden; Pearl Jam*

SELECT AR.name, COUNT(T.name)

FROM artist as AR
JOIN album as AL ON AL.artist_id = AR.artist_id
JOIN track AS T ON T.album_id = AL.album_id
JOIN genre as G ON G.genre_id = T.genre_id

WHERE G.name = 'Rock'

GROUP BY 1
ORDER BY 2 DESC;
<img width="365" alt="image" src="https://github.com/Kshaamini/Chinook-Music-Store-Analysis-SQLite/assets/139740694/b6264bb2-b809-4cf5-98e8-6f6e76feab02">


- **Top sales agent**

## Analysis Powerpoint Slides
