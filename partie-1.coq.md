## Docker

Si vous avez déjà vu Docker, créez via docker un conteneur MySQL et importez le fichier `beer.sql` dans votre conteneur.

Si vous n'avez pas encore vu Docker, importez le fichier `beer.sql` dans votre base de données MySQL ou demandez à votre
formateur de vous aider ou de vous donner le docker-compose.

### Prérequis

- Vous devez avoir un dockerfile et un docker-compose.yml
- Vous ne devez pas utiliser de `bind mount` !
- Vous avez le droit d'utiliser un `volume`

## Etude du modèle

### Effectuez un reverse engineering du modèle

- Quelles sont les tables ?

### Il y a des mauvaises pratiques dans ce modèle, lesquelles ?


## Exercices

Réalisez les requêtes suivantes :

### Quels sont les tickets qui comportent l’article d’ID 500, afficher le numéro de ticket uniquement ?

```mysql
SELECT * from ticket WHERE NUMERO_TICKET=500
```

### Afficher les tickets du 15/01/2014.

```mysql
SELECT * from ticket WHERE DATE_VENTE='2014-01-15'
```

### Afficher les tickets émis du 15/01/2014 et le 17/01/2014.

```mysql
SELECT * FROM ticket WHERE DATE_VENTE BETWEEN '2014-01-15' AND '2014-01-17'
```

### Editer la liste des articles apparaissant à 50 et plus exemplaires sur un ticket.

```mysql
SELECT * FROM ventes INNER JOIN article WHERE QUANTITE >=50
```

### Quelles sont les tickets émis au mois de mars 2014.

```mysql
SELECT * FROM ticket WHERE year(DATE_VENTE)='2014' AND month(DATE_VENTE)='03'
```

### Quelles sont les tickets émis entre les mois de mars et avril 2014 ?

```mysql
SELECT NUMERO_TICKET FROM tilcket WHERE month(DATE_VENTE) IN (3, 4) AND year(DATE_VENTE)='2014'
```

### Quelles sont les tickets émis au mois de mars et juin 2014 ?

```mysql
SELECT NUMERO_TICKET FROM ticket WHERE month(DATE_VENTE) IN (4, 6) AND year(DATE_VENTE)='2014'
```

### Afficher la liste des bières classée par couleur. (Afficher l’id et le nom)

```mysql
SELECT ID_ARTICLE, NOM_ARTICLE FROM article INNER JOIN couleur ORDER BY NOM_COULEUR
```

### Afficher la liste des bières n’ayant pas de couleur. (Afficher l’id et le nom)

```mysql
SELECT ID_ARTICLE, NOM_ARTICLE FROM article WHERE ID_Couleur IS NULL
```