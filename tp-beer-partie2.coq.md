## 10 Listez pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

```mysql
SELECT ID_ARTICLE, sum(QUANTITE) as TOTAL from ventes GROUP BY ID_ARTICLE ORDER BY TOTAL DESC
```

## 11 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. (Classer par quantité décroissante)

```mysql
SELECT ID_ARTICLE, sum(QUANTITE) as TOTAL from ventes GROUP BY ID_ARTICLE HAVING TOTAL>500 ORDER BY TOTAL DESC
```

## 12 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité supérieure à 50 (classer par quantité décroissante)

```mysql
SELECT ID_ARTICLE, sum(QUANTITE) as TOTAL from ventes WHERE QUANTITE<=50 GROUP BY ID_ARTICLE HAVING TOTAL>500 ORDER BY TOTAL DESC
```

## 13 Listez les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

```mysql
SELECT ID_ARTICLE, NOM_ARTICLE, VOLUME, TITRAGE FROM article INNER JOIN `type` WHERE NOM_TYPE="Trappiste"
```

## 14 Listez les marques de bières du continent ‘Afrique’

```mysql

```

## 15 Lister les bières du continent ‘Afrique’

```mysql
```

## 16. Lister les tickets (année, numéro de ticket, montant total payé). En sachant que le prix de vente est égal au prix d’achat augmenté de 15%.

```mysql

```

## 17  Donner le C.A. par année.

```mysql
```

## 18. Lister les quantités vendues de chaque article pour l’année 2016.

```mysql

```

## 19. Lister les quantités vendues de chaque article pour les années 2014, 2015, 2016.

```mysql

```
