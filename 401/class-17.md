# Class 17 Reading Notes

## How to web scrape with Py in 4 minutes

### Web Scraping

- techniquie to auto access and extract large amounts of info form a website, which can save a huge amount of time and effort

### Important Notes

1. Read through the websites terms to understand legal aspects of data usage

2. Make sure you are not downloading data at too rapid a rate, because that can break the website

### Inspecting the Website

- use web inspect, click on arrow tool in top left

### Python Code

- import the following

```py
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

```

- set url to the website and access the site with our requests library

```py
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

- should see respone 200

- next, parse the html with *** BeautifulSoup ***

```py
soup = BeautifulSoup(response.text, “html.parser”)
```

- use soup.findAll('a') to find all the anchor tags

## Web Scraping - Wiki

- extracting data from websites

- uses HTTP

- form of copying in which specfici data is gathered and copied from the web, typically into a local DB or spreadsheet

### Legal Issues

- may be against websites terms, but I mean, who cares about that lol

## How to scrape websites without getting blocked

### Basic Rule: "Be Nice"

- follow websites crawling policies

- too fast and too many, will get you blocked

- following the same pattern

- too many requests from same IP in short sequence

### Make the crawling slower, do not slam the server, treat websites nicely

### Do not follow the same crawling pattern

### Make requests through Proxies and rotate them as needed (YAAAA)

- VPN TIME YEYE

### In general, use common sense, dont do it too much, too often, and avoid traps yo