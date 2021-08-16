# Inner Join

You could do an inner join on multiple tables at once. For eg, if you have tables that are related by some foreign keys, you would do an inner join like this

```sql
SELECT movies.* FROM cinemas INNER JOIN halls ON cinemas.id = halls.cinema_id INNER JOIN shows ON halls.id = shows.hall_id INNER JOIN movies ON movies.id = shows.movie_id WHERE cinemas.city = :city AND movies.name =:movieName
```
