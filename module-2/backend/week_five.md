### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?

	_Flash messages are stored in the flash hash.  Typically, a conditional is put into the application.html to print out any flash messages present in the flash hash._

2. Where is cart information/temporary information usually stored?

	_Cart information/temporary information is usually stored in the sessions hash.  The session hash functions in a similar way to cookies but it is stored locally._

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?

	_Storing cart information could lead to our database growing too big to be functional.  We may end up storing unnecessary data in our database._

   _However, in many instances it makes sense to persist cart information.  For one, it allows our users to logout and then log back in and still have loaded cart available.  It also allows us to analyze data and trends for the items our users are putting in their cart._

4. What is the purpose of the asset pipeline?

	_The asset pipeline is an attempt to speed up the loading of resources in Rails applications.  The asset pipeline helps streamline the loading of resources both from the application itself and the cache.  This helps improve the load times and performance of Rails applications._

5. Why do we precompile our assets?

	_Precompiling compiles all the assets in the asset pipeline into languages our browser can understand such as HTML, CSS, and Javascript.  This helps the assets load more quickly and efficiently._

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

* The first tag links a stylesheet named 'application.css' from the stylesheets folder in our assets subdirectory.
* The second tag links a javascript file name 'application.js' from the javascripts folder in our assets subdirectory.
* The third tag links an image named 'rails.png' from the images folder in our assets subdirectory.

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

	_A good readme should explain what your project does, how to install it, examples of usage, how to set up the dev environment, and ways to suggest changes.  A good readme can get people interested in a project and make it easier and more accessible to them._

8. What are the top four accessibility issues that we as developers should be aware of?

* Vision disability
* Hearing disability
* Navigation without a mouse
* Navigation without a keyboard

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

	`before_save` is an example of  callback.  We can use a `before_save` callback to generate slugs while creating objects.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

```ruby
before_action :require_active_user

def require_active_user
  render file: '/public/404' unless current_user.active
end
```


11. What is the difference between a scope and a class method?

	_A scope method restricts who and what can access certain methods.  A class method is a method that is run on an entire class._


### Review Questions:
12. Given the following hash:

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?

  `hash[:cart]['48'] = 4`

  12b. How would you increase the quantity of item 29?

  `hash[:cart]['29'] += quantity`

  12c. How would you find out how many items your user is thinking about purchasing?

  `hash[:cart].values.sum`

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?

	_Polymorphism is the ability for subclasses to overwrite methods defined in superclasses.  Duck typing means code will accept any object that has a certain method defined for it._
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?

```ruby
	string.delete!('(')
    string.sub!(')', '.')
    string.sub!('-', '.')
```


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
