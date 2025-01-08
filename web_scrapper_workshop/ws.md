# Web Scraping

### What is web scrapping?

When you go on a website, you can find information, and information is valuable, sometimes we need to gather it to train an AI or to fill a database. Whatever your reasons, websites have a lot of cool information, but you don't want to gather the information by hand, we can automate this, and that's what scrapping is: gatherring data from websites.

Let's take a look at *http://books.toscrape.com/* a website made for learning to scrape with lots of information we can gather.

### Step 1: Python setup

If you don't have python on your machine, please download it. https://www.python.org/

You put your python code in a .py file and you can execute it by running

> python filename

You can also just type python in your terminal and get an interractive shell to help you debug like this:

> python

### Step 2: Making a request

Python has a request library that allows you to get web data.

> import requests
>
> resp = requests.get("http://books.toscrape.com/")
>
> print(resp)

This should print a **<Response [200]>** which means that you got the data correctly. We can print the website's contents like this:

> print(resp.text)

Wow, we got the website's contents, but it's very chaotic.

### Step 3: Time to scrape

Alright, well we have a bunch of data but we want to organise it, it's up to you to store all te book titles, ratings, and prices in an organised way.

To help you, there are libraries you can use like **BeautifulSoup**.

HINT: If you look in the html maybe the classes can help you.

### Step 4: Store your data

After running a scraper, you want to store your data somehow. You could put it in a database, or create a CSV file which is what we will do.

Python has a library called **csv** that allows you to easily put well organised data in a CSV file. Now it's up to you to generate this file with a column for the names, one for the prices, and one for the ratings of each book.
