## Creating a Database and Inserting Documents

### Before we Start

In this lesson, we are going to be working directly with MongoDB to create and modify data using the _Mongo Shell_ application in a Terminal window. 

You will find the Mongo Shell handy for examining and modifying data while developing your application.

### The Mongo Shell

Make sure that the MongoDB engine (`mongod`) is running then...

Start the app in terminal by typing `mongo`

The app will load and change the prompt will change to `>`

List the shell's commands available: `> help`

Show the list of databases: `> show dbs`

Show the name of the currently active database: `> db`

Switch to a different database: `> use [name of database to switch to]`

Let's switch to the `local` database: `> use local`

Show the collections of the current database `> show collections`

### Creating a new Database

To create a new database in the Mongo Shell, we simply have to _use_ the database.  Lets create a database named _myDB_:

```
> use myDB
```

### Inserting Data into a Collection

This is how we can create and insert a document into a collection named _people_:

```
> db.people.insert({
... name: "Fred",   // Don't type the dots, they are from the 
... age: 21         // shell, indicating multi-line input mode
})
```
Using a collection for the first time creates it!

__YOU DO: Let's add another person to the _people_ collection. But this time, add an additional field called _birthDate_ and assign it a date value with something like this: *birthDate: new Date('3/21/1981')*__

Remember, documents in Mongo are schema-less. Each document within a collection can contain **completely** different data.  This is in direct contrast to SQL databases which have schemas where contains the same type of data.

To list all documents in a collection, we can use the _find_ method on the collection without any arguments:

```
> db.people.find()
```

We can also provide an optional _query object_ to specify criteria.  If we provide an empty query object, `find` will once again return all documents:

```
> db.people.find({})
```

#### Plant the Seed and Watch your Data Grow

To practice querying our database, here are few more documents to put in your _people_ collection.

In addition to a single document, we can also provide an __array__ to the _insert_ method and it will create a document for each object in the array.

```js
db.people.insert(
    [
        {
            "name": "Emma",
            "age": 20
        },
        {
            "name": "Ray",
            "age": 45
        },
        {
            "name": "Celeste",
            "age": 33
        },
        {
            "name": "Stacy",
            "age": 53
        },
        {
            "name": "Katie",
            "age": 12
        },
        {
            "name": "Adrian",
            "age": 47
        }
    ]
)
```
Be sure to include the closing paren of the _insert_ method.

#### Review Questions

- **How do we "create" a new collection?**

- **What method adds documents to a collection?**

### Embedded Documents

In MongoDB, by design, it is common to __embed__ related data in the parent document.

However, MongoDB works best when related data is embedded. Embedded data allows MongoDB to read and return large amounts of data far more quickly than a SQL database that requires join operations.

To demonstrate __embedding__, we will add another person to our _people_ collection, but this time we want to include contact info. A person may have several ways to contact them, so we will be modeling a typical one-to-many relationship: A Person has many Contacts / A Contact belongs to a Person

```
> db.people.insert({
... name: "Manny",
... age: 33,
... contacts: [
... {
... type: "email",
... contact: "manny@domain.com"
... },
... {
... type: "mobile",
... contact: "(555) 555-5555"
... }
... ]
... })
```

The embedded data objects, like we see above, are called _subdocuments_.

The above approach of embedding "contact" data provides a great deal of flexibility in what types and how many contacts a person may have.

Another example of a data model where embedding works well is the typical a _post_ has many _comments_ scenario. Embedding comments within a _post_ document works great because those comments don't make sense without the post that they belong to.

## Querying Data

We've seen how to retrieve all of the documents in a collection using the `find()` method.

We can also use the `find()` method to query the collection by passing in an argument containing our query criteria as an JS object:

```
> db.people.find( {name: "Miguel"} )
```

Here's how we can use MongoDB's `$gt` query operator to return all _people_ documents with an age greater than 20:

```
> db.people.find( {age: { $gt: 20 } } )
```

MongoDB comes with a slew of built-in [query operators](http://docs.mongodb.org/manual/reference/operator/query/#query-selectors) we can use to write complex queries.

In addition to selecting which data is returned, we can modify how that data is returned by limiting the number of documents returned, sorting the documents, and by projecting which fields are returned.

This sorts our age query and sorts by _name_:

```
> db.people.find( {age: { $gt: 20 } } ).sort( {name: 1} )
```
The "1" indicates ascending order. 

[This documentation](http://docs.mongodb.org/manual/core/read-operations-introduction/) provides more detail about reading data.

>Notice that the `query object`, is just that, a JS object with key:value pairs.

## Updating Data

In MongoDB, we use the `update()` method on a collection.

We will need to specify the _update criteria_ (like we did with `find()`), and use the `$set` action to set the new value.

```
> db.people.update( { name: "Miguel" }, { $set: { age: 99 } })
```

By default `update()` will only modify a single document. However, with the `multi` option, we can update all of the documents that match the query.

```
> db.people.update( { name: { $lt: "M" } }, { $inc: { age: 10 } }, { multi: true } )
```
We used the `$inc` update operator to increase the existing value.

Here is the [list of Update Operators](http://docs.mongodb.org/manual/reference/operator/update/) available.

## Removing Data

We use the `remove()` method to data from collections.

If you want to completely remove a collection, including all of its indexes, use `[name of the collection].drop()`.

Call `remove({})` on the collection to remove **all** docs from a collection.

Otherwise, specify a criteria to remove all documents that match it:

```
>db.people.remove( { age: { $lt: 16 } } )
```



