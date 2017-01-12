## In your squads research these questions

Spend 1 hour researching and answering the following questions.

### What is a database?
```
- A structured set of data held in a computer/server, 
especially one that is accessible in various ways

- One of the most useful applications of the Web is
its capability to link a website to a database so that
web surfers can search for information

- The Web can serve and collect data

- Collection of data 

```

### How is accessing data from a database different from accessing data from a plain text file?
```
- Accessing data from plain text file: link file, depending on method, 
one example: jquery.get()

- Accessing data from a database: Query for all documents in a collection. 
Use the find() method to issue a query to retrieve data from a collection 
in MongoDB.

```

### What does the acronym CRUD stand for? 
```
- "Create, Read, Update, Delete"

Create, Read, Update, Delete Cycle

The CRUD cycle describes the basic elemental function of a database.  Users may have a different 
CRUD cycle, depending on the basic requirements of the system.  For instance, a customer may have 
the ability (or permission) to create a user account, read (or retrieve) the account when the 
return to the website, update it any time (new address, billing info, etc), and delete the account 
at any time.  In comparison, an operations manager may have different permissions, depending on 
how they need to use the database.  For instance, having the ability to create product records, 
read (or retrieve) them at any given time, update the product cost or specs, and delete the 
product entirely if it was discontinued. 

```

### In JavaScript what would the CRUD operations on an object or array be?
```
//create // var obj = {};
//read // obj.name
//update // obj.name = 'Tim'
//delete // delete obj.name
```

### In Databases what is an "atomic transaction"?
```
An atomic transaction is an indivisible and irreducible series of database operations 
such that either all occur, or nothing occurs. Either the transaction happens in its 
entirety, or nothing happens.

```

### Why would you use a database for web development?
```

Databases allow devs to store mass amounts of data, which can be retrieved, updated, or deleted 
at any given time.  Using a database allows the web developer to create dynamic web pages, that 
update according to how the user interacts with elements on the page.  If information stored in 
the database changes, so will the information visible on the webpage.  An example of the benefits 
to using a database, it online banking.  A user’s bank account balance is visible because the 
dynamic page is connected to the bank’s database via programming.  The bank account info updates 
on the page everytime you make a purchase, deposit, or withdraw money from your account.  

- Store information & persist data
- ie. User logins

```

### What is NoSQL?
```
- A non-relational and largely distributed database system 
that enables rapid, ad-hoc organization and analysis of
extremly high-volume, disparate data types

- Sometimes referred to as cloud databases, non-relational databases, Big Data databases

- Originally referred to as "non SQL", "non relational", 
"not only SQL"

- Encompasses a wide variety of different database 
technologies that were developed in response to the 
demands presented in building modern applications:
    - Developers working with apps that create massive
    volumes of new, rapidly changing datatypes
    - Now smaller teams work in agile sprints (shorter
    dev cycles)
    - Apps used to be served towards a finite audience - 
    now must be always-on, accessible from different devices,
    and scaled globally
    - Orgs now turning to scale-out architectures using open
    source software, commodity servers and cloud computing
    vs. large monolithic servers and storage infrastructure
- Relational databases were not designed to cope with the 
scale and agility challenges that face modern applications

- NoSQL is a database that provides a mechanism for storage and retrieval of data

- NoSQL databases are more scalable and provide superior
performance

- Data model addresses several issues relational model is
not designed to 

- Increasingly used in big data and real-time web apps

- NoSQL Database Types: 
    - Document Databases: Pair each key w/ a complex data 
    structure ('document'). Key-value pairs, key-arrays, nested documents
    - Graph Stores: Stores information about networks of data (ie. social connections)
    - Key-value Stores: Simplest NoSQL databases
    - Wide-column Stores: Optimized for queries over large
    datasets, and store columns of data together (instead 
    of rows)

```

### What is MongoDB?
```
- Open-sourced data storage solution 

```

### Why do we need MongoDB?
```
- Removes the complex object-relational mapping (ORM) layer
that translates object in code to relational tables 

- Schemaless - easier to work with

- A document-based data model. The basic unit of storage is analogous to JSON, 
Python dictionaries, Ruby hashes, etc. This is a rich data structure capable of 
holding arrays and other documents. This means you can often represent in a 
single entity a construct that would require several tables to properly represent 
in a relational db. This is especially useful if your data is immutable.
Deep query-ability. 

- MongoDB supports dynamic queries on documents using a document-based query 
language that's nearly as powerful as SQL.

- No schema migrations. Since MongoDB is schema-free, your code defines your schema.
Which provides a clear path to horizontal scalability.

```

### What is a schema and does mongoDB have them? Why or why not?
```
- Schema: The organization of data as a blueprint of how the 
database is contructed 
    - A way to logically group objects such as tables, views 
    stored procedures, etc. 
    - "Container of objects" - You can assign a user login 
    permissions to a single schema so that the user can only
    access the objects they are authorized to access 

- MongoDB is schemaless:
    - Data in MongoDB has flexible schema in the same
    collection
    - Do not need to have the same set of fields or 
    structure
    - Common fields in a collection's documents may hold
    different types of data

```

### What is BSON? How is similar/different from JSON?
```
Data is stored in a BSON object (short for  binary JSON object). 
The BSON spec guide can be found here - http://bsonspec.org/ 

```

### What is a collection?
```
Data collections are groups of related datasets or databases on 
specific subjects, held within a structured format. 

```

### What is a document?
```
- A document is a complex data structure

```

### What is a Namespace in MongoDB?
```
The canonical name for a collection or index in MongoDB. 
The namespace is a combination of the database name and the name of the 
collection or index, like so: [database-name].[collection-or-index-name]. 

```

### What is the shell command `mongod` do?
```
mongod is the primary daemon process for the MongoDB system. 
It handles data requests, manages data access, and performs 
background management operations.

The mongod process is the primary database process that runs 
on an individual server. mongos provides a coherent MongoDB 
interface equivalent to a mongod from the perspective of a 
client. The mongo binary provides the administrative shell.

```

### What does the shell command `mongo` do?
```
Enables the shell interface. If you invoke the mongo command and 
specify a JavaScript file as an argument, or use --eval to specify 
JavaScript on the command line, the --shell option provides the 
user with a shell prompt after the file finishes executing.

```

### What are the some features of MongoDB?
```
In summary, MongoDB has been built to be fast (no joins but embedded documents), 
flexible (schema less), scalable (horizontal no vertical), to minimize 
administrative tasks (replication, disaster recovery, automatic failover, 
sharding, load balancing, etc), easy to learn and with powerful tools for data analysis

```

### How is data stored?
```
Data is stored in a server, which communicates with a disk. 

```

### What is a _id field in Mongo?
```
- The primary key for every document/object 
- Also accessible via "id"
- Required - even if you don't explicitly assign, the document
will assign it 
(https://docs.mongodb.com/manual/reference/method/ObjectId/)

```

