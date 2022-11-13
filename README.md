# Stock-News-Scraper By - SHIBAM 💖

![ns](https://i.ytimg.com/vi/8kr-h0jQbEY/maxresdefault.jpg)


This financial news helps many traders in placing the trade in cryptocurrency, bitcoins, the stock markets, and many other global stock markets setting up of trading bot will help us to analyze the data. Thus all this can be done with the help of web scraping using python language that can fetch all the financial news from the given source. Before discussing let’s cover some basic concepts of web scraping.

## Module Needed:
#### Request: This module has several built-in methods to make HTTP requests to specified URI using GET, POST, PUT, PATCH, or HEAD requests. An HTTP request is meant to either retrieve data from a specified URI or push data to a server.
```html
pip install requests
```
#### Beautiful Soup: Beautiful Soup is a web scraping framework for Python. Web scraping is the process of extracting data from the website using automated tools to make the process faster.
```html
pip install bs4
```
## Steps Required:
#### Step 1: Import all the required libraries.
```html
from bs4 import BeautifulSoup as BS
import requests as req
```
#### Step 2: Find the best website for finance news to get daily updates seamlessly.
```html
https://www.businesstoday.in/latest/economy
```
#### Step 3: Inspect the tag in which news content is stored with the help of inspecting the HTML code.

![ns](https://media.geeksforgeeks.org/wp-content/uploads/20220529164045/Picture3.png)

#### Step 4: Now we will check the tag name and use that name in our code, i.e. Here, an anchor tag is used so we will use ‘a’ in our code.

![ns](https://media.geeksforgeeks.org/wp-content/uploads/20220529164239/Picture4.png)
 
#### Step 5: Specify the class in our code to get all the news heading in the anchor tag.
```html
# IMPORT ALL LIBRARIES
from bs4 import BeautifulSoup as BS
import requests as req
 
url = "https://www.businesstoday.in/latest/economy"
 
webpage = req.get(url)  # YOU CAN EVEN DIRECTLY PASTE THE URL IN THIS
# HERE HTML PARSER IS ACTUALLY THE WHOLE HTML PAGE
trav = BS(webpage.content, "html.parser")
 
# TO GET THE TPYE OF CLASS
# HERE 'a' STANDS FOR ANCHOR TAG IN WHICH NEWS IS STORED
for link in trav.find_all('a'):
    print(type(link.string), " ", link.string)
```    
##### Output:

The below output shows that it has two types of classes in its anchor tag that are “NoneType” and “bs4.element.NavigableString”.

![ns](https://media.geeksforgeeks.org/wp-content/uploads/20220529162635/Picture1.png)

Output for the type of classes in anchor tag
Output for the type of classes in an anchor tag

#### Step 6: To Fetch the news-related material we need only “bs4.element.NavigableString” class.

#### Step 7: Set the limit of the news character length to less than 35 characters.

##### Below is the complete implementation:
```html
# IMPORT ALL THE REQUIRED LIBRARIES
from bs4 import BeautifulSoup as BS
import requests as req
 
url = "https://www.businesstoday.in/latest/economy"
 
webpage = req.get(url)
trav = BS(webpage.content, "html.parser")
M = 1
for link in trav.find_all('a'):
   
    # PASTE THE CLASS TYPE THAT WE GET
    # FROM THE ABOVE CODE IN THIS AND
    # SET THE LIMIT GREATER THAN 35
    if(str(type(link.string)) == "<class 'bs4.element.NavigableString'>"
       and len(link.string) > 35):
 
        print(str(M)+".", link.string)
        M += 1
```        
        
Output:

![ns](https://media.geeksforgeeks.org/wp-content/uploads/20220529170332/Picture5compressed.jpg)
 


## BY -SHIBAM NATH

![ns](https://media.tenor.com/B34NF_toE8UAAAAd/breaking-news-news.gif)







