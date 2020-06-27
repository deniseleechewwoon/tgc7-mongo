After we   `use` a database, ther's a special variable available.
The variable is called `db`

Shoe all documents in a collection
```
db.listingsAndReviews.find().limit(10)
```

Prettify the output with `.pretty()` function
```
db.listingsAndReviews.find().pretty().limit(10)
```

```
db.listingsAndReviews.find({
    'beds':3
}).pretty().limit(10)
```

With Projections
```
db.listingsAndReviews.find({
    'beds':3
},{
    'name':1,
    'beds':1
}).pretty().limit(10)
```
# more than 1 criteria
```
db.listingsAndReviews.find({
    'beds':3,
    'bedrooms':3
},{
    'name':1,
    'beds':1,
    'bedrooms':1
}).pretty().limit(10)
```
# count
```
db.listingsAndReviews.find({
    'beds':3,
    'bedrooms':3
},{
    'name':1,
    'beds':1,
    'bedrooms':1
}).count()
```
## Comparison
```
db.listingsAndReviews.find({
    'beds': {
        '$gt':4
    }
},{
    'name':1,
    'beds':1,
})
```

## greater than equal
```
db.listingsAndReviews.find({
    'beds': {
        '$gte':4
    }
},{
    'name':1,
    'beds':1,
})

```

## range
```
db.listingsAndReviews.find({
    'beds': {
        '$gte':4,
        '$lte':8
    }
},{
    'name':1,
    'beds':1,
})
```