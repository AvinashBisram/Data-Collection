RottenTomatoes Web Scraping
===========================

**Description:** This project uses Web Scraping to collect data on 140 movies featured in a [RottenTomatoes article ](https://editorial.rottentomatoes.com/guide/140-essential-action-movies-to-watch-now/) including their titles, release years, scores, cast members, and more.

**Language(s):** Python  
**Package(s):** Requests, BeautifulSoup4, Pandas

**Motivation:** This project was created to demonstrate skills in scraping relatively static web pages (pages that contain most or all data in the raw HTML code instead of being generated with JavaSript).

<br>

About the Article:
------------------
The article scraped in this project was one published on RottenTomatoes.com titled "140 Essential Action Movies To Watch Now" (a link to the article can be found [here](https://editorial.rottentomatoes.com/guide/140-essential-action-movies-to-watch-now/)).

For each of the 140 movies listed, the article displayed various information about them in the following format:
![Example Movie Entry](./readMe%20images/RT%20Movie%20Entry.PNG)
<br><br>

Collecting the Data:
----------------
Python's **request** module was used to extract the raw HTML code of the web page.  
The **BeautifulSoup4** module was then used to parse through that HTML code and retrieve the desired information. (The HTML code parsed with the LXML parser can be found [here](./Rotten-Tomatoes-LXML-Parser.html))

Data collected about each movie include their:
* Title
* Release Year
* Score (displayed in the article i.e. "57%")
* Critics Consensus
* Directors
* Cast Members ("Starring")
* Adjusted Score (an extra score hidden in the site's HTML)
* Synopsis (the truncated synopsis included in this article)

Note: Minor data cleaning was performed on the collected data (text stripping and dtype recasting) but that wasn't the focus of this project.
<br><br>

Saving the Data:
----------------
Python's **Pandas** module was used to combine the collected data (into a DataFrame) and save it as a CSV file. You can view that file [here](./Scraped_RottenTomatoes_Data.csv).
