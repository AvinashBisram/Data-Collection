MyAnimeList Web Scraping
=======================

**Description:** This project uses Web Scraping to collect data on 90 recorded entries in a MyAnimeList user's "anime list". For each distinct entry listed in the user's profile, this program collects the anime names, user scores, type, progress, and redirect URLs. 

**Language(s):** Python  
**Package(s):**  Requests-HTML, Numpy, Pandas

**Motivation:**  This project was created to demonstrate skills in collecting data from a webpage that is primarily generated through JavaScript code and not found in the raw HTML of the page. I also intend on utilizing this data for a larger-scale Machine Learning project in the future.

Viewing the Project
--------------------
The main file for this project is located in root of the repository named _[MAL Data Collection (Scraping).ipynb](MAL%20Data%20Collection%20(Scraping).ipynb)_. If you have **Jupyter Notebooks** installed, you can download the .ipynb file and view it there. If not, you can view the project using Google Colaboratory [here](https://colab.research.google.com/github/AvinashBisram/Data-Collection/blob/master/MyAnimeList%20Web%20Scraping/MAL%20Data%20Collection%20(Scraping).ipynb).  
**Note:** Executing all cells in the main project file will create 1 CSV and 2 HTML files on your computer.


What is MyAnimeList?
------------------------
MyAnimeList is an "online anime and manga community and database" (Source: Google). Its most popular feature is the ability to track anime and manga a user has historically watched, is watching, or plans to watch in the future. This information is stored in a user's anime or manga "list" which is unique for each user.


About User "Anime Lists"
------------------------
MAL anime lists store information about the shows a user watches. An image of a user's anime list can be seen here:  
![Example MAL Anime List](./readMe%20images/MAL%20Example%20Anime%20List.PNG)

Information that can be found in this list include the shows' titles, score (given by the user), type (TV, Movie, etc.), how many episodes the user has watched so far, and the status (represented by the colored bar on the left of each entry).  
When a MAL user progress a show, changes will be reflected on their anime list.


Collecting the Data:
--------------------
**MyAnimeList API:**  MyAnimeList does have an API one can use to access their anime list (documentation can be found [here](https://myanimelist.net/apiconfig/references/api/v2)). However, I had difficulty accessing the desired data (and I would need to web scrape the HTML for additional data anyways) so I decided to look for alternatives.

**Reading the HTML Table:** Since MyAnimeList uses a regular HTML table to store user anime lists, I used **Pandas** _read_html_ method to access that data and see if it would suffice for the purposes of this project (I demonstrate that process in the [main project file](MAL%20Data%20Collection%20(Scraping).ipynb) as well). Unfortunately, the data stored in that format appeared quite messy and also lacked important details about the shows such as their statuses and URLs.

**Web Scraping:** I used Python's **Requests-HTML** module to scrape the HTML of the webpage (after JS rendering). The appropriate CSS selectors were used to access the elements storing relevant information and minor data cleaning was performed when necessary.


Saving the Data:
----------------
I used Python's **Pandas** module to combine the lists of show data into a DataFrame and exported it as a CSV file. You can view the final CSV containing the scraped and cleaned data [here](Scraped_MAL_Data.csv).  
**Note:** The data collection was performed on 12/26/2021.


Next Steps:
-----------
* The data collected in this project is a subset of the information needed to complete a larger Machine Learning project I have planned. Collecting that information would require navigating to and scraping the MAL page of each show. I plan on implementing the steps necessary for that soon.
* Since MAL anime lists share a common structure, it would be possible to expand on the code from this project to create a general script for scraping any user's anime list. That would make it easier to collect current data as MAL anime lists are typically updated once or multiple times each day.
