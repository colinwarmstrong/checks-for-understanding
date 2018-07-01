## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
* _GET: Retrieve a resource from a URL_
* _POST: Create a new resource_
* _PUT: Update an entire resource_
* _PATCH: Update part of a resource_
* _DELETE: Destroy a resource_

2. What is Sinatra?

	_Sinatra is a Rack based web application framework for Ruby._

3. What is MVC?

    _MVC is a web design pattern.  The three elements of this design are the model, view, and controller.  The model provides logic and interacts with the database, the view is what the user sees and interacts with, and the controller is the middle man that coordinates everything._

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

	_Following conventions in our actions/path names in our Sinatra routes allows us to create RESTful (Representational State Transfer) routes for our web applications._

5. What types of variables are accessible in our view templates without explicitly passing them?

	_Instance variables are accessible in our view templates without explicitly passing them in via the controller.  Passing local variables into a view template requires the use of a locals hash._

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  	```ruby
  	get '/horses' do
    	erb :index
  	end
  	```

  	The following code will pass in an instance variable `count` with a value of `1`:
 	 ```ruby
 	 get '/horses' do
  		@count = 1
   	 	erb :index
  	end
   	```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

    The following code will pass in a local variable `name` with a value of `Mr. Ed` to the view:
    ```ruby
    get '/horses' do
      erb :index, locals: { name: 'Mr. Ed' }
    end
    ```


8. What's the purpose of ERB?

	_ERB is Embedded Ruby.  It allows us to embed Ruby code within an HTML document._

9. Why do I need a development AND test database?

	_The test database should be independent of the development database to allow for testing in a controlled, isolated environment.  If the two databases were the same, testing could pollute the devlopment database and vice versa._

10. What is CRUD and why is it important?

	_CRUD is an acronym which stands for Create, Read, Update, and Destroy.  These are the four actions we can perform on a resource._

11. What does HTTP stand for?

	_HTTP: Hypertext Transfer Protocol_

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

	_The two ways to interpolate Ruby in an ERB view template is `<%= %>` and `<% %>`.  A Ruby tag with an equals sign will render the return value of the Ruby block to the screen.  A Ruby tag without an equals sign will run the Ruby block but will not render anything to the screen._

13. What's an ORM? What does it do?

	_ORM: Object Relational Mapping.  An ORM framework essentially wraps a relational database within an object oriented programming language such as Ruby.  Tables can be converted to to an object class and individual rows can be converted to object instances._

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?

	_Active Record is the most commonly used ORM in Sinatra and Rails applications._

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

* _GET '/restaurants' : View all restaraunts_
* _GET '/restaraunts/:id' : View a specific restaraunt_
* _GET '/restaraunts/new' : View form for creating a new restaraunt_
* _POST '/restaraunts' : Create a new restaraunt_
* _GET '/restaraunts/:id/edit' : View a form for editting an existing restaraunt_
* _PATCH '/restaraunts/:id' : Update part of an existing restaraunt_
* _DELETE 'restaraunts/:id' : Destroy a specific film_


16. What's a migration?

	_A migration is a set of instructions used to generate a schema which is used to create and modify a database._

17. When you create a migration, does it automatically modify your database?

	_Creating a migration does not automatically modify a database.  A migration is used to generate and modify a schema.  The schema is what directly modifies our database._

18. How does a model relate to a database?

	_A model is related to a database via an ORM such as Active Record._

19. What is the difference between `#new` and `#create`?

	_`#new` will instantiate a new instance of a class but will not save it.  `#create` will both instantiate and save an instance of a class._   


### Review Questions:  
20. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?

	```ruby
    require 'CSV'
    CSV.open('films.csv', headers: true, header_converters: :symbol)    
    ```

21. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

	activities[:hiking][:supplies] << granola bar

22. What are the 4 Principles of OOP? Give a one sentence explanation of each.

* _Encapsulation: The attributes of an entity are enclosed within that entity._
* _Inheritance: An entity can inherit attributes from another entity._
* _Polymorphism: A method can take many forms.  A child entity can have a method which overrides the same method it inherited from a parent class._
* _Abstraction:  Abstraction is the idea of hiding the details of how something is done to allow the user to more easily accomplish tasks._


### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
