### Conceptual Exercise

Answer the following questions below:

- What are important differences between Python and JavaScript?

Python allows for comparison of dictionaries and lists whereas Javascript doesn't. Python has tuples which is not in JS unless you use a package. Python and Javascript also have very different syntax. Another difference is that Python has out of the box testing with doctests unlike JS which requires writing tests in another file. Python will show more errors because the syntax in more strict.


- Given the following dictionary: `{"school": "Rithm"}`, list two ways you can access a key of "student" without your python programming crashing.

You can use the get method: `dict.get('student')`. This will return None if the key doesn't exist.
  
  ```py
  try:
    dict['student']
  ```
  One last thing you could do is use an if statement to check if the key exists before accessing:
  
```py
if student in dict:
  dict['student']
```
- What is a unit test?

A unit test is testing one small, isolated piece of functionality, a unit. Testing one function vs. testing the function in the whole program.

- What is an integration test?

An integration test is testing how pieces of functionality interact with each other and that they work correctly.

- What is the role of web application framework, like Flask?

It is a set of functions, classes, etc. that help define which requests to respond to as well as how to respond to requests.

- You can pass information to Flask either as a parameter in a route URL
(like '/foods/pretzel') or using a URL query param (like
  'foods?type=pretzel'). How might you choose which one is a better fit
  for an application? (like '/foods/pretzel') or using a URL query param (like
'foods?type=pretzel'). How might you choose which one is a better fit
for an application?

 You can generally use query string parameters if you are describing the object you are on vs using the route for the object itself. For example, in the above case I would use /foods/pretzel and then use a query string parameter if I am decribing the pretzel such as /foods/pretzel?type=salty or /foods/pretzel?type=sugar.

- How do you collect data from a URL parameter using Flask?

You can specify the variable in the app.route and then use that variable as a paramater in the routing function. Here is an example:

```py
  @app.route('/foods/<food>')
  def grocery(food):
      x = food
```

- How do you collect data from the query string using Flask?

With a query string the data can be found in the request.args dictionary:

```py
  @app.route('/foods')
  def grocery():
      x = request.args.get('type')
```

- How do you collect data from the body of the request using Flask?

You can get the data form a post request in the body using the request.form dictionary

```py
  @app.route('/foods')
  def grocery():
      x = request.form.get('type')
```

- What is a cookie and what kinds of things are they commonly used for?

A cookie is piece of information which stores the domain, "key", and "value" that gets sent from the server to the client. It allows the client to send back that information to the server, allowing the server to use that information.

- What is the session object in Flask?

The session object is built off of using cookies. It helps keep the number of cookies lower and encodes the information. Allows access to stored variables.

- What exactly does Flask's `jsonify()` do?

jsonify will take JSON serializeable data in python and convert it to a JSON string.