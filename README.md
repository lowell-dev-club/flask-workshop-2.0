# Flask Server 2.0
using an online [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment) **[REPL.it](https://repl.it)**

## Libraries and Flask

What is an Library?  

A library is a set of implenmentations written by previous programmers that we can use to perform mechanisms such as web scraping, which is what we'll be doing in this workshop. Now to explain webscraping is a method for extracting data usually in the form of text for our use. 

[Read more about Libraries!](https://en.wikipedia.org/wiki/Library_(computing))  

In this workshop we'll be using a library called Flask to host our website on a repl.it server.

## Repl.it

Create a new repl and choose python. Make sure its specified as Python or Python 3. **Do Not Use Python 2**

![repl it image](https://github.com/lowell-dev-club/python-text-game/blob/master/replit.png?raw=true)

## Creating the program

#### Imports

We start by importing the needed code from the Flask library.

```python
# import the Flask class from the flask module
from flask import Flask, render_template
```

#### Making website application and routes

The code below will create a Flask app, which we will run to start the website on a server. You can see this with the ```app.run()``` function at the very bottom. The ```@app.routes()``` sections off pieces of our code so that we can write programs for when some visits our website at a specific location. For example, ```mywebsite.com/myblogs```. **Feel free to copy and paste the code below the imports**


```python
# create the application object
app = Flask(__name__)

# use decorators to link the function to a url
@app.route('/')
def home():
    return "Hello, World!"  # return a string

@app.route('/welcome')
def welcome():
    return render_template('welcome.html')  # render a template

# start the server with the 'run()' method
if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```
#### Create the templates for our website

Now click the plus folder icon somewhere near the top left of you screen. Please add in a new folder called templates. This folder will store html files which holds the code for what the computer displays on the screen. After creating the folder, add a new file in the folder called ```welcome.html```. This is the html file that I was talking about. Now below there is some html code. Copy and paste it into the ```welcome.html``` file. After you're done, click the green run button you see at the top center of your screen. It should display another window on your screen showcasing your website. And you're done! You've created your own website which can be accessible to anyone. 

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Flask Intro</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    <div class="container">
      <h1>Welcome to Flask!</h2>
      <br>
      <p>Click <a href="/">here</a> to go home.</p>
    </div>
  </body>
</html>
```

#### Advanced steps

Create a new route that will display texts or notes

```
# Create a new route
@app.route("something here")
def notes():
  # something else here
  
# Don't forget to create the html file too
# Remember html files go in the templates folder
templates (folder)
|-- notes.html
|-- welcome.html
```

You can now view, process, and use information off any website!

Check out a functioning program [here](https://repl.it/@calee14/Youtube-Scraper)
