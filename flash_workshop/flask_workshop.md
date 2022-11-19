# Create a Flask Web Server

#### What is Flask?

Flask is a Python library used to create web servers.
You can find the documentation [here](https://flask.palletsprojects.com/).

#### Before you get started

Before you get started you want to make sure that you have **python** and **pip** installed on your computer.

#### Installation

Run this command to install Flask :
> pip install Flask

#### Create your app

Let's create our web app in a file we'll call *app&#46;py*. It's really easy, just 2 lines of code :
> from flask import Flask
> 
> app = Flask(\_\_name__)

#### Create a route

Routes are pages on your site that you can access. Let's create a *routes&#46;py* file to put our routes. Lets create the "/" route together :
>from app import app
>
> @app.route("/")\
> def hello_world():\
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "\<p>Hello, World!\</p>"

#### Run your server

It's time to run your server. Let's create a *run&#46;py* file that we will execute to run the server. We'll run it on your localhost. We'll be using the port 8000 but you can change it if you want. Here's how it's done :
>from routes import app
>
> port = 8000
>
> def main():
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;app.run(host="0.0.0.0", port=port)
>
> if \_\_name__ == "\_\_main__":
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;main()

You can now go in your terminal and execute run&#46;py to run your server :
> python3 run&#46;py

Your server is now running, you can access it by searching http://0.0.0.0:8000/ in your web browser.

Congratulations, you have created a web server!

#### Using HTML

Now, create a *templates* directory and a *index&#46;html* file in it. Fill this HTML file and make it so that http://0.0.0.0:8000/ will display the HTML file's contents.

#### Create your own route

Create a */donut* route that displays a donut.html file when you go to http://0.0.0.0:8000/donut&#46;
Here are the contents of the donut.html file :
> \<!DOCTYPE html>
> \<html>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<head>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<title>Donut\</title>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\</head>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<body>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<h2>Donuts are amazing\</h2>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<p>The donut of the day is : {{ Donut }}\</p>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<img src="https://www.biggerbolderbaking.com/wp-content/uploads/2020/11/Homemade-Dunkin-Donuts-WS-Thumb-scaled.jpg" alt="">
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\</body>
> \</html>

#### Using jinja

What's this {{ Donut }} in our HTML file? it's jinja, a way to send data from flask to our HTML file. Make {{ Donut }} equal to a donut flavour that changes daily.
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;donut_flavours = ["Chocolate", "Strawberry", "Fudge", "Sprinkles", "Vanilla", "Caramel"]

#### Database

Alright, we have a perfect flawless website. We could add a database to allow users to add comments about donuts and share them with other users. We will use **SQLAlchemy** to do this.
Create a *db&#46;py* file that will contain your database models. Good luck!
Here's a little line to get you started :
> from flask_sqlalchemy import SQLAlchemy

#### Using the database

Now that you have a database, let's use it!
In your *routes&#46;py* you'll want to import your database's class
> from db import ... (the name of your class) 

How can you access all the comments?
How can you add a comment?

Create a */comments* route that displays comments one by one.
*Remember jinja? it's quite usefull here.*

But we need a way to add comments! Lets add a form to our */comments* route :

> \<form action="" method="post">
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<input type="text" value="" placeholder="Comment" name="comment">
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<input type="submit" value="post comment">
> \</form>

This form will send a **POST** request to your */comments* route, retrieve it and add it to the database.

#### Authentication

Perfect, now users can comment about donuts, but there's no authentication. Create a */login* route where users can login, a */register* route where users can create a new account, and a */logout* route to logout.
Flask has a login manager to help you out.
> from flask_login import LoginManager

> from flask_login import current_user, login_user, logout_user, login_required

Users will be stored in our perfect database we created earlyer.

#### Dockerization

You got this far? Good job! Now is the time to make our app deployable on any server. Make a *Dockerfile* that installs the dependencies, creates your database, and runs your app.
