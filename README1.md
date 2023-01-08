## Background & Objectives

The goal of this project is to query the database **from our Python code**.

## Data
We will work with the `movies.sqlite` database


## Tool

For that we will use a library that comes with Python, called **sqlite3**.


**IMPORTANT**: Each function takes a `db` argument, which is a cursor connected to the database. 

The function will look like this:

```python
def your_function(db):
    query = ""
    db.execute(query)
    results = db.fetchall()
    # results in a list (rows) of tuples (columns)
    print(results)  # Inspect what you get back! Don't guess!
    # Then you'll need to return something.
    return ?
```

### Number of directors

How many directors are in this database?

### List of directors

What is the list of all the names of all the directors sorted in alphabetical order? Return a list of names (as `str`ings).

### List of movies about "love"

What are the movies which contain the exact word "love" in their title, sorted in alphabetical order? Return a list of movie titles.

### Number of directors named like...

How many directors contain a word XXX (parameter) in their name?

### List of movies longer than...

What are the movies which are longer than a duration, given by a user, sorted in the alphabetical order? Return a list of movie titles.

## Tips

👉 When you take input from a user to build a SQL query, make sure you protect your SQL query from **SQL injection** with [parameter substitution](https://docs.python.org/3.7/library/sqlite3.html).

👉 SQL queries tend to get pretty long pretty quickly. In Python, you can use the [triple-quote](https://docs.python.org/3.2/tutorial/introduction.html#strings) syntax to write **multi-line** strings:

```python
query = """
    SELECT
      title,
      minutes
    FROM movies
    WHERE title LIKE "%Z%"
    ORDER BY title
    LIMIT 3
"""
rows = db.execute(query)
# [...]
```
