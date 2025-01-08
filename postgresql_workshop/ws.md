# PostgreSQL Workshop

### Step 1: Setup

First you need to run a postgres database on your machine, you can do this by installing it or by running it through docker.

You can  go on the official site to download it here: https://www.postgresql.org/

if you do this, you want to also create a database by running:

> sudo su - postgres
> psql
> CREATE ROLE root WITH SUPERUSER LOGIN;
> CREATE DATABASE db;

you can replace "db" with the name of your database, and root with your username to connect without sudo.

Or run the docker image that you can find here: https://hub.docker.com/_/postgres

### Step 2: Test the connection

We need to make sure that the DB us running, to do this there are many ways but we'll use a simple terminal command, here's how you install it:

> sudo apt install -y postgresql-client

And to check the connection, run this command, changing parameters if necessary:

> pg_isready -d db -h localhost -p 5432 -U user

If your database is setup properly and you ran the command with the correct parameters, you should recieve this message:

> localhost:5432 - accepting connections

### Step 3: Access the DB

This is done with a simple command where db is the name of your database:

> psql db

If you are using docker, you need to run the following command to enter the image:

> sudo docker ps
>
> sudo docker exec -it image_name sh
>
> psql -U user  db

### Step 4: Create a table

Now it's up to you to figure out how to create a table.

Create a table called "user" which has a name column that takes a string of characters and an age column that takes an  integer.

### Step 5: Create a user

Now that you created a user table, it's time to create a user! Create a user by giving him a name and an age

### Step 6: Retrieve your user

Time to see if the user is stored properly, now you need to find a way to retrieve him.

Try creating more users and retrieving them all.

### Step 7: Edit a user

Try changing the age of one of your users and retieving it.

### Step 8: Delete user

Delete one of your users.

And that's the basics of Postgres, now we can try doing some more advanced things.

### Step 9: Filter

Create a request that gives you all the users that are older that are 20 years old.

Create a request that gives you all users that have a "b" in their name.

### Step 10: Foreign key

Make a new table called "Hat" with a color which is a string of characters and a user which is linked to the user table. Do do this, there are foreign keys, what are they?
