# Requêtes SQL oBlog

## Auteurs

### Lister les auteurs

```sql
-- Si on récupère que le nom des auteurs
SELECT `name` FROM `author`
-- Si on récupère toutes les infos des auteurs
SELECT * FROM `author`
```

### Afficher l'auteur ayant l'id 2

```sql
SELECT `name` FROM `author` WHERE `id` = 2
-- Si on veut toutes les infos de l'auteur 2
SELECT * FROM `author` WHERE `id` = 2
```

## Auteurs (bonus)

### Lister les auteurs par ordre alphabétique (sur le nom)

```sql
-- Par défaut, ORDER BY fait un tri "ascendant" (ordre croissant)
-- SELECT * FROM `author` ORDER BY `name` ASC
-- on n'est donc pas obligé de préciser le terme ASC
SELECT * FROM `author` ORDER BY `name`
```

### Lister les auteurs dont l'e-mail contient @gmail.com

```sql
SELECT * FROM `author` WHERE `email` LIKE '%@gmail.com%'
```

### Lister les auteurs qui n'ont pas d'image de profil

```sql
SELECT * FROM `author` WHERE `image` IS NULL

SELECT * FROM `author` WHERE ISNULL(`image`)
```

## Articles

### Lister tous les articles

```sql
SELECT * from `post`
```

### Afficher l'article ayant l'id 1

```sql
SELECT * FROM `post` WHERE `id` = 1
```

## Articles (bonus)

### Lister le titre et la date de publication de tous les articles

```sql
SELECT `title`, `published_date` FROM `post`
```

### Afficher le titre de l'article ayant l'id 2

```sql
SELECT `title` FROM `post` WHERE `id` = 2
```

### Lister les 3 derniers articles publiés

```sql
SELECT `title` FROM `post` ORDER BY `published_date` DESC LIMIT 3
```

### Lister les articles d'une catégorie (ici Teamfront ayant l'ID 2 )

```sql
SELECT *
 FROM post
INNER JOIN  category ON post.category_id = category.id
WHERE category.id = 2

