# MongoDB


The purpose of this repository is to show a simple creation and setup of a MongoDB database, as well as the insertion of data into this table.
Shown below is the process of creating a database name and formatting a configuration string with the name and password.
~~~
PASSWORD='************'
DB_NAME = 'test'

client = pymongo.MongoClient('mongodb+srv://Lenovo5-Brandon:{}@cluster0.z5rdg.mongodb.net/{}?retryWrites=true&w=majority'.format(PASSWORD,DB_NAME))

db = client.test
~~~

Next, the process of inserting example documents is reflected with the count_documents() method.
~~~
db.test.insert_one({'x':1})

db.test.count_documents({'x':1})
~~~
The count_documents() method above should return 1.

~~~
db.test.insert_one({'x':1})

db.test.count_documents({'x':1})

db.test.find_one({'x':1})

personDocument = {
    "name": { "first": "Alan", "last": "Turing" },
    "birth": datetime.datetime(1912, 6, 23),
    "death": datetime.datetime(1954, 6, 7),
    "contribs": [ "Turing machine", "Turing test", "Turingery"],
    "views": 1250000
}
db.test.insert_one(personDocument)

db.test.insert_many([{'sample_key': 'sample_value', 'second_sample_key':2021}])
~~~
