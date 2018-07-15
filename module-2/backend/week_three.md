## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?

	`rails new project_name -T -d='postgresql' --skip-spring --skip-turbolinks`
2. What do Models generally inherit from in rails?

	_In Rails, models generally inherit from ApplicationRecord_
3. What do Controllers generally inherit from in a rails project?

	_In Rails, controllers generally inherit from ApplicationController?_
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

	`resources: horses, only: [:show]`
5. What rake task is useful when looking at routes, and what information does it give you?

	`rake routes` gives you a list of all available routes in a Rails application.  The information includes the route helper prefix, HTTP verb, URI pattern, and controller action associated with each route.
6. What is an example of a route helper? When would you use them?

	`horse_path(horse)` is a route helper corresponding to a horse show page.  Route helpers are useful shortcuts to identify a URL in a Rails application.
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

	`_url` returns the same path as `_path` but it is prefixed with the current host, port and path prefix
8. What are strong params and why are they necessary?

	_Strong params are params that come from a private method which sets what params are allowed to be passed to an object.  This helps improve security._
9. What role does `form_for` play in helping us create our forms?

	`form_for` is a Rails helper method which allows HTML forms to be created more easily.
10. How does `form_for` know where to submit the user's input?

	`form_for` knows where to submit the user's input because of the controller method that renders the form.
11. Create a form using a `form_for` helper to create a new `Horse`.

```ruby
<%= form_for @horse do |f| %>
	<%= f.label :name %>
    <%= f.text_field :name %>

     <%= f.label :color %>
     <%= f.text_field :color %>

     <%= f.label :breed %>
     <%= f.text_field :breed %>

     <%= f.submit %>
<% end %>
```
12. Why do we want to validate our models?

	_Validating our models helps ensure objects in our database are created with the intended attributes and relationships._
13. What are the steps of the DNS lookup?
	* User submits a query
	* Query gets passed to the resolving name server
	* Resolving name server sends query to the root server
	* The query is directed to the top level domain server via the resolving name server
	* The query is directed to the authoritative name server via the resolving name server
	* The correct URL is returned to the user


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?

```ruby
class Horse

	def move
    	prance
    end

    def prance
    	"I'm prancing"
    end
end
```
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?

	furniture[:purchased] => true
    furniture[:table][:height] => 3
16. What is inheritance?

	_Inheriance is when a subclass inherits methods and/or attributes from a superclass._

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
