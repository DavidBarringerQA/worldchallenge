
# Table of Contents



1.  SELECT first<sub>name</sub>, last<sub>name</sub> from actor;
2.  SELECT last<sub>name</sub> FROM actor WHERE first<sub>name</sub>="John";
3.  SELECT first<sub>name</sub>, last<sub>name</sub> FROM actor WHERE last<sub>name</sub>="Neeson";
4.  SELECT first<sub>name</sub>, last<sub>name</sub> FROM actor WHERE actor<sub>id</sub>%10=0;
5.  SELECT description FROM film<sub>list</sub> WHERE FID=100;
6.  SELECT title FROM film<sub>list</sub> WHERE rating='R';
7.  SELECT title FROM film<sub>list</sub> WHERE rating!='R';
8.  SELECT title FROM film ORDER BY length ASC LIMIT 10;
9.  SELECT title FROM film WHERE length IN (SELECT MAX(length) FROM film);
10. SELECT title, special<sub>features</sub> FROM film WHERE special<sub>features</sub> LIKE '%Deleted Scenes%';
11. SELECT last<sub>name</sub> FROM actor GROUP BY last<sub>name</sub> HAVING COUNT(last<sub>name</sub>)=1;
12. SELECT last<sub>name</sub> FROM actor GROUP BY last<sub>name</sub> HAVING COUNT(last<sub>name</sub>)>1 ORDER BY COUNT(last<sub>name</sub>) DESC;
13. SELECT a.first<sub>name</sub>, a.last<sub>name</sub> FROM film<sub>actor</sub> f INNER JOIN actor a ON f.actor<sub>id</sub> = a.actor<sub>id</sub> GROUP BY f.actor<sub>id</sub> ORDER BY COUNT(f.actor<sub>id</sub>) DESC LIMIT 1;
14. SELECT DATE<sub>ADD</sub>(rental<sub>date</sub>, INTERVAL f.rental<sub>duration</sub> DAY) AS due<sub>date</sub> FROM rental r INNER JOIN inventory i ON r.inventory<sub>id</sub>=i.inventory<sub>id</sub> INNER JOIN film f ON i.film<sub>id</sub>=f.film<sub>id</sub> WHERE f.title='Academy Dinosaur' AND return<sub>date</sub> IS NULL;
15. SELECT AVG(length) FROM film;
16. SELECT c.name, AVG(f.length) FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> GROUP BY fc.category<sub>id</sub>;
17. SELECT title FROM film WHERE description LIKE "%robot%";
18. SELECT title FROM film WHERE release<sub>year</sub>='2010';
19. SELECT f.title FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> WHERE c.name = "Horror";
20. SELECT CONCAT(first<sub>name</sub>, " ", last<sub>name</sub>) AS full<sub>name</sub> FROM staff WHERE staff<sub>id</sub> = 2;
21. SELECT f.title FROM film f INNER JOIN film<sub>actor</sub> fa ON f.film<sub>id</sub>=fa.film<sub>id</sub> INNER JOIN actor a ON fa.actor<sub>id</sub>=a.actor<sub>id</sub> WHERE a.first<sub>name</sub>="Fred" AND a.last<sub>name</sub>="Costner";
22. SELECT COUNT(DISTINCT country) FROM country;
23. SELECT name FROM language ORDER BY name DESC;
24. SELECT CONCAT(first<sub>name</sub>, " ", last<sub>name</sub>) AS full<sub>name</sub> FROM actor WHERE last<sub>name</sub> LIKE "%son" ORDER BY first<sub>name</sub> ASC;
25. SELECT c.name FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> GROUP BY c.category<sub>id</sub> ORDER BY COUNT(c.category<sub>id</sub>) DESC LIMIT 1;

