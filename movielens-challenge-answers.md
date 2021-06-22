
# Table of Contents



1.  SELECT title, release<sub>date</sub> FROM movies WHERE release<sub>date</sub> BETWEEN '1983-01-01' AND '1993-12-31' ORDER BY release<sub>date</sub> ASC;
2.  CREATE VIEW avg<sub>ratings</sub> as select movie<sub>id</sub>, AVG(rating) as avgr FROM ratings group by movie<sub>id</sub>;

CREATE VIEW min<sub>rating</sub> as select MIN(avgr) as minr from avg<sub>ratings</sub>;
SELECT m.title FROM movies m inner join avg<sub>ratings</sub> r on r.movie<sub>id</sub> = m.id inner join min<sub>rating</sub> s on r.avgr=s.minr;

1.  SELECT DISTINCT m.title FROM movies m INNER JOIN ratings r ON m.id=r.movie<sub>id</sub> INNER JOIN users u ON r.user<sub>id</sub>=u.id INNER JOIN genres<sub>movies</sub> gm ON m.id=gm.movie<sub>id</sub> INNER JOIN genres g ON g.id=gm.genre<sub>id</sub> WHERE g.name="Sci-fi" and r.rating = 5 AND u.gender="M" AND u.age=24;
2.  CREATE view pop<sub>rel</sub><sub>date</sub> AS SELECT release<sub>date</sub> FROM movies GROUP BY release<sub>date</sub> ORDER BY COUNT(title) DESC LIMIT 1;
    SELECT title FROM movies WHERE release<sub>date</sub> IN (SELECT release<sub>date</sub> FROM pop<sub>rel</sub><sub>date</sub>);
3.  SELECT g.name, COUNT(mv.id) FROM movies mv INNER JOIN genres<sub>movies</sub> gm ON mv.id=gm.movie<sub>id</sub> INNER JOIN genres g ON gm.genre<sub>id</sub>=g.id GROUP BY g.id ORDER BY COUNT(mv.id) ASC;

