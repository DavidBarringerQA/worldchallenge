
# Table of Contents



1.  \#+BEGIN-SRC SQL
    SELECT first<sub>name</sub>, last<sub>name</sub> from actor;
    \#+END-SRC
2.  \#+BEGIN-SRC SQL
    SELECT last<sub>name</sub> FROM actor WHERE first<sub>name</sub>="John";
    \#+END-SRC
3.  \#+BEGIN-SRC SQL
    SELECT first<sub>name</sub>, last<sub>name</sub> FROM actor WHERE last<sub>name</sub>="Neeson";
    \#+END-SRC
4.  \#+BEGIN-SRC SQL
    SELECT first<sub>name</sub>, last<sub>name</sub> FROM actor WHERE actor<sub>id</sub>%10=0;
    \#+END-SRC
5.  \#+BEGIN-SRC SQL
    SELECT description FROM film<sub>list</sub> WHERE FID=100;
    \#+END-SRC
6.  \#+BEGIN-SRC SQL
    SELECT title FROM film<sub>list</sub> WHERE rating='R';
    \#+END-SRC
7.  \#+BEGIN-SRC SQL
    SELECT title FROM film<sub>list</sub> WHERE rating!='R';
    \#+END-SRC
8.  \#+BEGIN-SRC SQL
    SELECT title FROM film ORDER BY length ASC LIMIT 10;
    \#+END-SRC
9.  \#+BEGIN-SRC SQL
    SELECT title FROM film WHERE length IN (SELECT MAX(length) FROM film);
    \#+END-SRC
10. \#+BEGIN-SRC SQL
    SELECT title, special<sub>features</sub> FROM film WHERE special<sub>features</sub> LIKE '%Deleted Scenes%';
    \#+END-SRC
11. \#+BEGIN-SRC SQL
    SELECT last<sub>name</sub> FROM actor GROUP BY last<sub>name</sub> HAVING COUNT(last<sub>name</sub>)=1;
    \#+END-SRC
12. \#+BEGIN-SRC SQL
    SELECT last<sub>name</sub> FROM actor GROUP BY last<sub>name</sub> HAVING COUNT(last<sub>name</sub>)>1 ORDER BY COUNT(last<sub>name</sub>) DESC;
    \#+END-SRC
13. \#+BEGIN-SRC SQL
    SELECT a.first<sub>name</sub>, a.last<sub>name</sub> FROM film<sub>actor</sub> f INNER JOIN actor a ON f.actor<sub>id</sub> = a.actor<sub>id</sub> GROUP BY f.actor<sub>id</sub> ORDER BY COUNT(f.actor<sub>id</sub>) DESC LIMIT 1;
    \#+END-SRC
14. \#+BEGIN-SRC SQL
    SELECT DATE<sub>ADD</sub>(rental<sub>date</sub>, INTERVAL f.rental<sub>duration</sub> DAY) AS due<sub>date</sub> FROM rental r INNER JOIN inventory i ON r.inventory<sub>id</sub>=i.inventory<sub>id</sub> INNER JOIN film f ON i.film<sub>id</sub>=f.film<sub>id</sub> WHERE f.title='Academy Dinosaur' AND return<sub>date</sub> IS NULL;
    \#+END-SRC
15. \#+BEGIN-SRC SQL
    SELECT AVG(length) FROM film;
    \#+END-SRC
16. \#+BEGIN-SRC SQL
    SELECT c.name, AVG(f.length) FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> GROUP BY fc.category<sub>id</sub>;
    \#+END-SRC
17. \#+BEGIN-SRC SQL
    SELECT title FROM film WHERE description LIKE "%robot%";
    \#+END-SRC
18. \#+BEGIN-SRC SQL
    SELECT title FROM film WHERE release<sub>year</sub>='2010';
    \#+END-SRC
19. \#+BEGIN-SRC SQL
    SELECT f.title FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> WHERE c.name = "Horror";
    \#+END-SRC
20. \#+BEGIN-SRC SQL
    SELECT CONCAT(first<sub>name</sub>, " ", last<sub>name</sub>) AS full<sub>name</sub> FROM staff WHERE staff<sub>id</sub> = 2;
    \#+END-SRC
21. \#+BEGIN-SRC SQL
    SELECT f.title FROM film f INNER JOIN film<sub>actor</sub> fa ON f.film<sub>id</sub>=fa.film<sub>id</sub> INNER JOIN actor a ON fa.actor<sub>id</sub>=a.actor<sub>id</sub> WHERE a.first<sub>name</sub>="Fred" AND a.last<sub>name</sub>="Costner";
    \#+END-SRC
22. \#+BEGIN-SRC SQL
    SELECT COUNT(DISTINCT country) FROM country;
    \#+END-SRC
23. \#+BEGIN-SRC SQL
    SELECT name FROM language ORDER BY name DESC;
    \#+END-SRC
24. \#+BEGIN-SRC SQL
    SELECT CONCAT(first<sub>name</sub>, " ", last<sub>name</sub>) AS full<sub>name</sub> FROM actor WHERE last<sub>name</sub> LIKE "%son" ORDER BY first<sub>name</sub> ASC;
    \#+END-SRC
25. \#+BEGIN-SRC SQL
    SELECT c.name FROM film f INNER JOIN film<sub>category</sub> fc ON f.film<sub>id</sub>=fc.film<sub>id</sub> INNER JOIN category c ON fc.category<sub>id</sub>=c.category<sub>id</sub> GROUP BY c.category<sub>id</sub> ORDER BY COUNT(c.category<sub>id</sub>) DESC LIMIT 1;
    \#+END-SRC

