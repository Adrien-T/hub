# PostgreSQL Workshop

### Step 1: Setup

First you need to run a postgres database on your machine, you can do this by installing it or by running it through docker.

You can  go on the official site to download it here: https://www.postgresql.org/

if you do this, you want to also create a database by running:

> sudo su - postgres
> psql
> CREATE ROLE root WITH SUPERUSER LOGIN;
> CREATE DATABASE db;

you can replace "db" with the name of your database.

Or run the docker image that you can find here: https://hub.docker.com/_/postgres

### Step 2: Test the connection

We need to make sure that the DB us running, to do this there are many ways but we'll use a simple terminal command, here's how you install it:

> sudo apt install -y postgresql-client

And to check the connection, run this command, changing parameters if necessary:

> pg_isready -d db -h localhost -p 5432 -U user

If your database is setup properly and you ran the command with the correct parameters, you should recieve this message:

> localhost:5432 - accepting connections

### Step 3: access the DB

This is done with a simple command where db is the name of your database:

> psql db

If you are using docker, you need to run the following command to enter the image:

> sudo docker ps
>
> sudo docker exec -it image_name sh
>
> psql -U user  db
