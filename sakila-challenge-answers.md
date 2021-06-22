
# Table of Contents



1.  SELECT first\_name, last\_name from actor;
2.  SELECT last\_name FROM actor WHERE first\_name="John";
3.  SELECT first\_name, last\_name FROM actor WHERE last\_name="Neeson";
4.  SELECT first\_name, last\_name FROM actor WHERE actor\_id%10=0;
5.  SELECT description FROM film\_list WHERE FID=100;
6.  SELECT title FROM film\_list WHERE rating='R';
7.  SELECT title FROM film\_list WHERE rating!='R';
8.  SELECT title FROM film ORDER BY length ASC LIMIT 10;
9.  SELECT title FROM film WHERE length IN (SELECT MAX(length) FROM film);
10. SELECT title, special\_features FROM film WHERE special\_features LIKE '%Deleted Scenes%';
11. SELECT last\_name FROM actor GROUP BY last\_name HAVING COUNT(last\_name)=1;
12. SELECT last\_name FROM actor GROUP BY last\_name HAVING COUNT(last\_name)>1 ORDER BY COUNT(last\_name) DESC;
13. SELECT a.first\_name, a.last\_name FROM film\_actor f INNER JOIN actor a ON f.actor\_id = a.actor\_id GROUP BY f.actor\_id ORDER BY COUNT(f.actor\_id) DESC LIMIT 1;
14. SELECT DATE\_ADD(rental\_date, INTERVAL f.rental\_duration DAY) AS due\_date FROM rental r INNER JOIN inventory i ON r.inventory\_id=i.inventory\_id INNER JOIN film f ON i.film\_id=f.film\_id WHERE f.title='Academy Dinosaur' AND return\_date IS NULL;
15. SELECT AVG(length) FROM film;
16. SELECT c.name, AVG(f.length) FROM film f INNER JOIN film\_category fc ON f.film\_id=fc.film\_id INNER JOIN category c ON fc.category\_id=c.category\_id GROUP BY fc.category\_id;
17. SELECT title FROM film WHERE description LIKE "%robot%";
18. SELECT title FROM film WHERE release\_year='2010';
19. SELECT f.title FROM film f INNER JOIN film\_category fc ON f.film\_id=fc.film\_id INNER JOIN category c ON fc.category\_id=c.category\_id WHERE c.name = "Horror";
20. SELECT CONCAT(first\_name, " ", last\_name) AS full\_name FROM staff WHERE staff\_id = 2;
21. SELECT f.title FROM film f INNER JOIN film\_actor fa ON f.film\_id=fa.film\_id INNER JOIN actor a ON fa.actor\_id=a.actor\_id WHERE a.first\_name="Fred" AND a.last\_name="Costner";
22. SELECT COUNT(DISTINCT country) FROM country;
23. SELECT name FROM language ORDER BY name DESC;
24. SELECT CONCAT(first\_name, " ", last\_name) AS full\_name FROM actor WHERE last\_name LIKE "%son" ORDER BY first\_name ASC;
25. SELECT c.name FROM film f INNER JOIN film\_category fc ON f.film\_id=fc.film\_id INNER JOIN category c ON fc.category\_id=c.category\_id GROUP BY c.category\_id ORDER BY COUNT(c.category\_id) DESC LIMIT 1;

