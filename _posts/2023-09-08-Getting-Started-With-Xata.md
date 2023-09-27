---
title: Getting started with Xata
date: 2023-09-08 00:00:00
categories: [Technology, Web Development]
tags: [database, serverless, xata]
---

![Butterfly in a server room](/assets/media/Xata-Server-AI-Generated.png)

[Xata](https://xata.io/) is a cloud database service that makes it easy to build modern applications with rich data types, full-text search, AI capabilities, and serverless scalability. In this article, I will show you how to get started with Xata and perform an ACID transaction example.

## Getting Started with Xata

To get started with Xata, you need to sign up for a free account on their [website](https://xata.io/). You will get access to a generous free tier that lets you create and manage up to 10 databases with 10 GB of storage each and 750k total records measured across all tables and 15 GB Data size on disk.

Once you have an account, you can create a new database in your workspace. Provide the name of your database and select a region for it. Then click "Create" and the database is created.

![Xata-Create-DB](/assets/media/Xata-Create-DB.png)

After creating your database, you will see the dashboard where you can view and edit your database schema, data, and settings. You can also use the Data API or the TypeScript SDK to interact with your database programmatically.

## How to use Xata's transactions endpoint to execute multiple operations in one go

One of the features that Xata offers is the transactions endpoint, which allows you to execute multiple operations together as a single unit. Let's see why transactions are important, how to use Xata's transactions endpoint, and perform an example of a transaction in action.

## Why transactions are important

Reliability is important when it comes to your data. You want to know that when you ask for something to be stored, that it'll be stored or that you'll receive an error explaining why not. No half-written records, no returning "OK" but not writing it, no writing it and then removing it again.

As you add new features to your application, you'll see some patterns emerge. You want to create a user and a workspace at the same time. Or you'll want to remove a user from the waitlist when they sign-up. Your users will also hope that when they make a payment to your product, that their credits show up.

Transactions are in the business of making these promises. A transaction lets you - the developer - run multiple requests as one. These requests are all guaranteed to succeed, or all guaranteed to fail. The database guarantees that a user and workspace will be created, that the user is removed from the waitlist, and it absolutely guarantees that your users' credits will show up in their account upon payment.

Transactions come with a lot of knobs and dials. Transactions give control over how operations are executed, as well as what is and is not allowed to happen in a database while the transactions is executing.

Let's begin with the initial Setup. We will code the example in Python. To use the [Python SDK](https://xata.io/docs/sdk/python/overview), we need to install it using pip:

```bash
pip install xata
```

Now let's import the xata module and configure it with [`Xata Client`](https://xata-py.readthedocs.io/en/latest/api.html#xata.XataClient). Grab your personal API Key in the accounnt settings and database url in your particular DB settings in which you want to perfrom the transaction.


```python
from xata.client import XataClient

xata = XataClient(api_key="api_key",
                  db_url="db_url", branch_name='main')
```

## How to use Xata's transactions endpoint

The [Xata transactions](https://xata.io/docs/sdk/transaction) API can be thought of as a way to wrap our existing insert, update, and delete operations into a single operation. The options for each operation are almost identical to their non-transactional counterparts.

### Request

To use the transactions endpoint, you need to have an Xata client instance with your API key, database URL, and branch name. Then, you can call the `records().transaction()` method with an object that contains an array of operations. Each operation is an object with a key that specifies the type of operation (insert, update, delete, or get) and a value that contains the parameters for that operation.


For example, let's create a table named songs with the columns: name, artist, and genre. Here we will try to perform transactions related to songs. Xata makes it easier for us to create the DB through UI intuitively. So go ahead and add columns as you like.

![Xata-Create-Table](/assets/media/xata-create-table.png)

Here is an example of a transaction request:

```python
from xata.client import XataClient

xata = XataClient(api_key="api_key",
                  db_url="db_url", branch_name='main')

response = xata.records().transaction({
    "operations": [
        {"insert": {"table": "songs", "record": {
            "name": "Lucid Dreams", "artist": "Juice Wrld", "genre": "Emo rap"}}},
        {"insert": {"table": "songs", "record": {
            "id": "music-0", "name": "Granade", "artist": "Bruno Mars", "genre": "Pop"}, "createOnly": True}},
        {"update": {"table": "songs", "id": "music-0",
                    "fields": {"name": "Grenade"}, "ifVersion": 0}},
        {"update": {"table": "songs", "id": "music-1",
                    "fields": {"name": "Closer", "artist": "The Chainsmokers", "genre": "Future bass"}, "upsert": True}},
        {"get": {"table": "songs",
                 "id": "music-0", "columns": ["id", "name"]}},
        {"delete": {"table": "songs", "id": "music-0"}}
    ]
})
```

This request performs six operations in one transaction:

- Insert a record into the songs table with the name: Lucid Dreams, artist: Juice Wrld, and genre: Emo rap.

- Insert a record into the songs table with the id: music-0, name: Granade (misspelled), artist: Bruno Mars, and genre: Pop. The createOnly option ensures that this operation will fail if there is already a record with the same id.

- Update the record with the id: music-0 in the songs table by changing its name from Granade to Grenade (correct spelling). The ifVersion option ensures that this operation will fail if the record has been modified by another transaction.

- Update the record with the id music-1 in the songs table by setting its name to Closer, artist to The Chainsmokers, and genre to Future bass. The upsert option ensures that this operation will insert the record if it does not exist.

- Get the record with the id music-0 from the songs table and return its id and name columns.

- Delete the record with the id music-0 from the songs table.


### Response

If successful, you can be certain that all operations have succeeded. You will receive a response like below:

```
{'results': [{'id': 'rec_ck82ovnkhed8birq1e2g', 'operation': 'insert', 'rows': 1}, {'id': 'music-0', 'operation': 'insert', 'rows': 1}, {'columns': {}, 'id': 'music-0', 'operation': 'update', 'rows': 1}, {'columns': {}, 'id': 'music-1', 'operation': 'update', 'rows': 1}, {'columns': {'id': 'music-0', 'name': 'Grenade'}, 'operation': 'get'}, {'operation': 'delete', 'rows': 1}]}
```

The response contains an array of data that corresponds to each operation in the request. For insert and update operations, the response contains the full record that was inserted or updated. For get operations, the response contains the requested columns of the record. For delete operations, the response contains null Or, in case of error, you know that all operations have been rolled back for you.

Once you perform the above transaction, you will be able to see the values in the UI just like the below:

![Xata-acid-transaction-music-table-view](/assets/media/Xata-music-table-view.png)

In this article, I have introduced Xata, a platform that lets you build and iterate on your product faster with a simple and powerful API to access your data. I have focused on one of the features that Xata offers: the transactions endpoint, which allows you to execute multiple operations together as a single unit.

I hope that you have found this article useful and informative. If you want to learn more about Xata and its other features, you can visit their website: [Xata.io](https://xata.io/) and join their amazing community on [discord](https://xata.io/discord).

Thanks for the read!