Data Collection Projects
========================

This repository contains projects related to data collection including Web Scraping and using APIs.  
**Language(s):** (Primary) Python, (Secondary) JavaScript, HTML, CSS  
**Package(s):** (Python) Requests, BeautifulSoup4, Requests-HTML, Json  
**Software:** Jupyter Notebooks

Project Descriptions:
---------------------
* [Rotten Tomatoes Web Scraping](./Rotten%20Tomatoes%20Web%20Scraping): Uses Python's **Requests** and **BeautifulSoup** modules to collect data on 140 movies featured in a RottenTomatoes article including their titles, release years, scores, cast members, and more.
* [MyAnimeList Web Scraping](./MyAnimeList%20Web%20Scraping): Uses Python's **Requests-HTML** module to collect data on 90+ shows listed in a MyAnimeList user's anime list including their titles, user scores, status, progress, and more. This data was **rendered using JavaScript** and could not be scraped with the raw HTML code.
* [iTunes API Data Collection](./iTunes%20API%20Data%20Collection): Uses Python's **Requests** and **JSON** modules to collect data on 200 tracks by The Beatles from the iTunes API (using a **GET** request). Information collected of each track include their artist's names, collection and track names, track ID, respective iTunes URL, track price, and more. Collected data is saved to a CSV file.
* [EDAMAM API Data Collection](./EDAMAM%20API%20Data%20Collection): Uses Python's **Request** and **JSON** modules to collect data on 30 nutrients found in unstructured recipe text (using EDAMAM's Nutrition Analysis API). Recipe text was sent in the body of a **POST** request along with headers and authentication parameters (App ID and App Key). Information collected of each nutrient include their label (descriptive name), quantity, and unit. Collected data is saved to a CSV file.

Projects Coming Soon:
---------------------
* Back-End Development of a REST API using Node.JS with an interactive Front-End Web Application (HTML,CSS,JS).