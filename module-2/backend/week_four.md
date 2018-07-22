## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?

 _A cookie is a piece of data stored in a web browser and transferred via HTTP requests._

2. What’s the difference between a session and a cookie?

 _A session is stored on the server while a cookie is stored in the browser._

3. What’s a flash and when do you want to use flashes?

 _A flash is a message that appears to a user to alert them about different actions._
4. Why do people say “HTTP is stateless”?

 _HTTP is stateless because it depends on requests that don't know about the current state of the system or the requests that cam before it._

5. What’s authentication? Explain.

 _Authentication is making sure someone is who they say they are.  This is usually implemented via usernames, email addresses, and passwords._

6. What’s the difference between authentication and authorization?

 _Authentication is making sure someone is who they say they are.  Authorization is establishing functionality restrictions based on different levels of users._

7. What’s a before filter?

 _A before filter is a restriction placed on controller methods to limit who has access to that function.  An example would be requiring the current user to be an admin before utilizing a delete method._

8. How do we keep track of a user once they’ve logged in?

 _We can keep track of a user one they've logged in using a helper methods and the sessions hash._

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

   _Namespacing a resource establishes a route which is scoped for specific users.  Nesting a resource establishes routes within other routes.  Namespacing is useful for authorizationl nesting resources is useful when one resource is dependent on another._

10. At a high level, what tools can you use to implement authorization? How would you use them?

 _A number of Ruby gems exist for implementing authorization.  These gems utilize hashing and encryption techniques to make data storage more secure while still allowing the data to be used for authentication.  Bcrypt does this using a password_digest attributes in the user table._

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

 _An enum is a way to convert integer values into more a more usable data type like a string.  It is more efficient for data storage and querying than storing the data as a string.  The data is stored as an integer and then interpreted by the enum._

12. What are some strategies you can use to keep your views DRY?

 _Utilizing partials is really helpful in keeping views DRY.  Putting elements you want to appear in all views in the application.html file is also helpful in keeping views DRY._


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
{holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
{holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
{holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```

```ruby
 alphabetical_holidays = holidays.sort_by { |holiday| holiday[:name] }
   alphabetical_holidays.each do |holiday|
       puts holiday[:name]
   end
```

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

   `cleaned_data = incoming_data.delete('$').to_i`


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
