# CRUD Quiz

Use the solution to this afternoon's Property Tracker lab to answer the following questions. Please write your answers under each question, push the file to GitHub, and submit in the usual way.

## MVP Questions

In our Property Tracker application:

Q1. Where are we instantiating instances of the `Property` class?
In the console.rb file.

Q2. Where are we defining the SQL that enables us to save the ruby `Property` object into the database?
In the properties.sql file.

Q3. In `console.rb`, which lines modify the database?
4, 13, 22, 31, 33.

Q4. Why do we not define the id of a `Property` object at the point we instantiate it (‘new it up’)?
Because Ruby only receives the id after SQL creates it.

Q5. Where and how do we assign the id (that is generated by the database) to the ruby `Property` object?
In the method .save: it will return the SQL id to the instance on which we use it.

Q6. Why do we put a guard (an `if` clause) on the `@id` attribute in the constructor?
Because @id is optional: it will not be returned by SQL if we don't create the id column in the database.

Q7. Why are some of the CRUD actions represented by instance methods, and others by class methods?
Because some methods can only be used at a database entry level (.update, .delete) and will thus correspond to instance methods, while others make sense only at a database table level (.find, .find_all, .delete_all, .all) corresponding to class methods.

Q8. What type of data structure is returned by calls to `db.exec_prepared()`? In the `save` method, how do we access the id from the returned data structure?
It is an array of hashes containing key(column in database)-value(row's value) pairs: we access the id by its index position, ie. if the @id value is the first column in the SQL database (and thus in the array returned by calls to 'db.exec_prepared()') we use [0].

Q9. Why do we use prepared statements when performing database operations?
Because they are intelligible to both Ruby and SQL.

## Extension Questions

Look at the `find_by_id` and `find_by_address` methods in the `Property` class.

Q10. What do they take in as their arguments?
The value of the instance variable in Ruby/its corresponding value in the database.

Q11. What are their return values?
Arrays of hashes each with one database entry key-value pairs.
