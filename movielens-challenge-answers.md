
# Table of Contents



1.  SELECT title, release\_date FROM movies WHERE release\_date BETWEEN '1983-01-01' AND '1993-12-31' ORDER BY release\_date ASC;
2.  CREATE VIEW avg\_ratings as select movie\_id, AVG(rating) as avgr FROM ratings group by movie\_id;
    CREATE VIEW min\_rating as select MIN(avgr) as minr from avg\_ratings;
    SELECT m.title FROM movies m inner join avg\_ratings r on r.movie\_id = m.id inner join min\_rating s on r.avgr=s.minr;
3.  SELECT DISTINCT m.title FROM movies m INNER JOIN ratings r ON m.id=r.movie\_id INNER JOIN users u ON r.user\_id=u.id INNER JOIN genres\_movies gm ON m.id=gm.movie\_id INNER JOIN genres g ON g.id=gm.genre\_id WHERE g.name="Sci-fi" and r.rating = 5 AND u.gender="M" AND u.age=24;
4.  CREATE view pop\_rel\_date AS SELECT release\_date FROM movies GROUP BY release\_date ORDER BY COUNT(title) DESC LIMIT 1;
    SELECT title FROM movies WHERE release\_date IN (SELECT release\_date FROM pop\_rel\_date);
5.  SELECT g.name, COUNT(mv.id) FROM movies mv INNER JOIN genres\_movies gm ON mv.id=gm.movie\_id INNER JOIN genres g ON gm.genre\_id=g.id GROUP BY g.id ORDER BY COUNT(mv.id) ASC;

