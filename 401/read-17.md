# What is Web Scraping ?

Web scraping refers to the extraction of data from a website. This information is collected and then exported into a format that is more useful for the user. Be it a spreadsheet or an API.
Although web scraping can be done manually, in most cases, automated tools are preferred when scraping web data as they can be less costly and work at a faster rate.
But in most cases, web scraping is not a simple task. Websites come in many shapes and forms, as a result, web scrapers vary in functionality and features.
If you want to find the best web scraper for your project, make sure to read on.

# How do Web Scrapers Work ?

Automated web scrapers work in a rather simple but also complex way. After all, websites are built for humans to understand, not machines.
First, the web scraper will be given one or more URLs to load before scraping. The scraper then loads the entire HTML code for the page in question. More advanced scrapers will render the entire website, including CSS and Javascript elements.
Then the scraper will either extract all the data on the page or specific data selected by the user before the project is run.
Ideally, the user will go through the process of selecting the specific data they want from the page. For example, you might want to scrape an Amazon product page for prices and models but are not necessarily interested in product reviews.
Lastly, the web scraper will output all the data that has been collected into a format that is more useful to the user.
Most web scrapers will output data to a CSV or Excel spreadsheet, while more advanced scrapers will support other formats such as JSON which can be used for an API.
![](https://www.edureka.co/blog/wp-content/uploads/2018/11/Untitled-1.jpg)

### How Do You Scrape Data From A Website?

  a. Find the URL that you want to scrape
  b. Inspecting the Page
  c. Find the data you want to extract
  d. Write the code
  e. Run the code and extract the data
  f. Store the data in the required format

### Libraries used for Web Scraping

* `Selenium`: Selenium is a web testing library. It is used to automate browser activities.
* `BeautifulSoup`: Beautiful Soup is a Python package for parsing HTML and XML documents. It creates parse trees that is helpful to extract the data easily.
* `Pandas`: Pandas is a library used for data manipulation and analysis. It is used to extract the data and store it in the desired format.

### Example: Scraping Flipkart Website

* Step 1: Find the URL that you want to scrape

```
 https://www.flipkart.com/laptops/~buyback-guarantee-on-laptops-/pr?sid=6bo%2Cb5g&uniqBStoreParam1=val1&wid=11.productCard.PMU_V2.
 ```

* Step 2: Inspecting the Page
* Step 3: Find the data you want to extract
* Step 4: Write the code

```
from selenium import webdriver
from BeautifulSoup import BeautifulSoup
import pandas as pd
```

```
driver = webdriver.Chrome("/usr/lib/chromium-browser/chromedriver")
```

```
products=[] #List to store name of the product
prices=[] #List to store price of the product
ratings=[] #List to store rating of the product
driver.get("<a href="https://www.flipkart.com/laptops/">https://www.flipkart.com/laptops/</a>~buyback-guarantee-on-laptops-/pr?sid=6bo%2Cb5g&amp;amp;amp;amp;amp;amp;amp;amp;amp;uniq")
```

```
content = driver.page_source
soup = BeautifulSoup(content)
for a in soup.findAll('a',href=True, attrs={'class':'_31qSD5'}):
name=a.find('div', attrs={'class':'_3wU53n'})
price=a.find('div', attrs={'class':'_1vC4OE _2rQ-NK'})
rating=a.find('div', attrs={'class':'hGSR34 _2beYZw'})
products.append(name.text)
prices.append(price.text)
ratings.append(rating.text) 
```

* Step 5: Run the code and extract the data
* Step 6: Store the data in a required format

```
df = pd.DataFrame({'Product Name':products,'Price':prices,'Rating':ratings}) 
df.to_csv('products.csv', index=False, encoding='utf-8')
```
