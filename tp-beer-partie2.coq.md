## 10 Listez pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, sum(QUANTITE) as TOTAL from ventes GROUP BY NUMERO_TICKET ORDER BY TOTAL DESC
```

## 11 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, sum(QUANTITE) as TOTAL from ventes GROUP BY NUMERO_TICKET HAVING TOTAL>500 ORDER BY TOTAL DESC
```

## 12 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité supérieure à 50 (classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, sum(QUANTITE) as TOTAL from ventes WHERE QUANTITE<=50 GROUP BY NUMERO_TICKET HAVING TOTAL>500 ORDER BY TOTAL DESC
```

## 13 Listez les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

```mysql
SELECT ID_ARTICLE, NOM_ARTICLE, VOLUME, TITRAGE, NOM_TYPE FROM article INNER JOIN `type` ON article.ID_TYPE = type.ID_TYPE WHERE NOM_TYPE= 'Trappiste'
```

## 14 Listez les marques de bières du continent ‘Afrique’

```mysql
SELECT pays.ID_PAYS, NOM_MARQUE, NOM_CONTINENT from marque INNER JOIN pays ON marque.ID_PAYS = pays.ID_PAYS INNER JOIN continent ON pays.ID_CONTINENT = continent.ID_CONTINENT WHERE NOM_CONTINENT= 'Afrique'
```

## 15 Lister les bières du continent ‘Afrique’

```mysql
SELECT NOM_ARTICLE, ID_ARTICLE, NOM_CONTINENT, VOLUME
from article
INNER JOIN marque ON article.ID_MARQUE = marque.ID_MARQUE
INNER JOIN pays ON marque.ID_PAYS = pays.ID_PAYS
INNER JOIN continent ON pays.ID_CONTINENT = continent.ID_CONTINENT
WHERE NOM_CONTINENT= 'Afrique'
```

## 16. Lister les tickets (année, numéro de ticket, montant total payé). En sachant que le prix de vente est égal au prix d’achat augmenté de 15%.

```mysql
SELECT ticket.ANNEE, ticket.NUMERO_TICKET, ticket.DATE_VENTE,
SUM(ventes.QUANTITE * article.PRIX_ACHAT * 1.15) as TOTAL
from ticket
INNER JOIN ventes ON ticket.NUMERO_TICKET = ventes.NUMERO_TICKET
INNER JOIN article ON ventes.ID_ARTICLE = article.ID_ARTICLE
GROUP BY ticket.ANNEE, ticket.NUMERO_TICKET
ORDER BY TOTAL DESC
```

## 17  Donner le C.A. par année.

```mysql
SELECT ventes.ANNEE,
SUM(ventes.QUANTITE * article.PRIX_ACHAT * 1.15) as TOTAL
from ventes
INNER JOIN article ON ventes.ID_ARTICLE = article.ID_ARTICLE
GROUP BY ventes.ANNEE
```

## 18. Lister les quantités vendues de chaque article pour l’année 2016.

```mysql
SELECT ventes.ANNEE,
SUM(ventes.QUANTITE * article.PRIX_ACHAT * 1.15) as TOTAL
from ventes
INNER JOIN article ON ventes.ID_ARTICLE = article.ID_ARTICLE
WHERE ventes.ANNEE="2016"
GROUP BY ventes.ANNEE
```

## 19. Lister les quantités vendues de chaque article pour les années 2014, 2015, 2016.

```mysql

```

