## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

	_At a high level, ActiveRecord is a framework that allows us to interact with our database.  It provides methods that can simplify complex SQL commands._
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them

	Team.all, Team.where(), Team.find(), Team.find_by(), Team.order(), Team.maximum, Team.minimum, Team.pluck(), Team.sum()

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

	`Team.find(4).name`

    `Owner.find(team.owner_id))`

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

	Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

![Schema](https://i.imgur.com/dovcwHK.png)
6. Define foreign key, primary key, and schema.

	* Foreign Key: A key in on table that correlates with the primary key in a different table; this connection links the data in the two tables.
	* Primary Key: The primary key is used to identify a row of data in a table. It is unique to that row of data.
	* Schema: A schema is a representation of a database.

7. Describe the relationship between a foreign key on one table and a primary key on another table.

	_A foreign key of one table matches the primary key on another table; this is how the data in the two tables are connected._
8. What are the parts of an HTTP response?
	* Status Line: consists of the protocol and a numeric status code and the associated status message.
	* Response Headers: Allows the server to pass additional informational about the response.
	* Body: Contains the HTML associated with the resource.


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

	* .order( ): ranks the data by the values in a column; can be ascending or descending.
    * .where( ): selects all the data that matches the passed argument.
    * .pluck( ): selects all the values of a specific column
    * .find( ): finds the object associated with a row of data
    * .maximum( ): returns the maximum value from a column
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
	* rake db:seed, seeds the data
	* rake db:migrate, runs a migration to modify the database
	* rakde db:drop, destroys the database
3. What two columns does `t.timestamps null: false` create in our database?
	* created_at
	* updated_at
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?

	_A one-to-many relationship; a school has many students while a student belongs to a school._
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

	_Each student would have a foreign key of school_id to connect it to the specific school._
6. Give an example of when you might want to store information besides ids on a join table.

	_Created at and updated at might be columns you'd want to include in a join table. Quantity and unit_price were useful in our InvoiceItems join table for Little Shop._
7. Describe and diagram the relationship between patients and doctors.

	_This is a many-to-many relationship; a doctor has many patients while a patient can have many doctors._
8. Describe and diagram the relationship between museums and original_paintings.

    _This is a one-to-many relationship; a museum can have many original_paintings but a painting can only belong to one museum._
9. What could you see in your code that would make you think you might want to create a partial?

	_Repeated HTML would make me think about creating a partial to maintain the DRY principle._

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
