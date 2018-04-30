# Requete Squaring the Circle.

--- EXERCICE 1 ---

1 -
Ecrire 'Show tables' dans la console Mysql

2-
Ecrire 'DESC film' dans la console Mysql

3-
SELECT titre  AS 'titre film'
FROM film

4-
SELECT titre
FROM film
WHERE id_genre is NULL


5-
SELECT titre
FROM film
WHERE date_debut_affiche BETWEEN '2000-01-01' AND '2000-12-31'
ORDER BY date_debut_affiche DESC
LIMIT 10



--- EXERCICE 2 ---

1-
SELECT titre
FROM film
WHERE titre LIKE 'a%' AND id_genre = 1 AND 2


2-
SELECT SUM(nbr_siege) AS 'nombre siege'
FROM salle


3-
SELECT etage_salle, SUM(nbr_siege)
FROM salle
GROUP BY etage_salle;

4-
SELECT nom_salle
FROM salle
WHERE nbr_siege < 200

5-
SELECT titre AS 'Titre Cool'
FROM film
WHERE titre LIKE '%day%' AND id_genre = 2



--- EXERCICE 3 ---

1-
SELECT floor(avg(prix))  AS 'avg abon', count(id_abo) AS 'Nbr abon'
FROM abonnement

2-
SELECT MAX(id_film) AS 'Max_id_film'
FROM film
WHERE id_genre = 8 AND YEAR(date_debut_affiche)BETWEEN '1980' AND '1999'

3-
SELECT membre.id_membre, membre.date_dernier_film AS 'last movie'
FROM membre
INNER JOIN historique_membre ON membre.id_membre = historique_membre.id_membre
WHERE id_film IN(2557,2741)
ORDER BY date DESC


--------- BOSS FINALE --------- 

SELECT genre.id_genre, (COUNT(genre.id_genre)) AS 'Nombre film', genre.nom AS 'Nom genre'
FROM genre
INNER JOIN film ON genre.id_genre = film.id_genre
WHERE film.id_genre BETWEEN 1 AND 3
GROUP BY genre.nom





