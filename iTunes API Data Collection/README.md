iTunes API Data Collection
==========================

**Description:** This project uses the iTunes API to collect data on 200 tracks by The Beatles (from the US iTunes store). Information collected of each track include their artist's names, collection and track names, track ID, respective iTunes URL, track price, and more. Collected data was saved to a CSV file.

**Language(s):** Python  
**Package(s):** Requests, JSON, Pandas  
**Software:** Jupyter Notebooks  

**Motivation:** This project was created to demonstrate skills in collecting data from APIs (that do not require authentication).

Viewing the Project:
--------------------
The main file for this project is located in root of the repository named _[iTunes API Data Collection.ipynb](iTunes%20API%20Data%20Collection.ipynb)_. If you have **Jupyter Notebooks** installed, you can download the .ipynb file and view it there. If not, you can view the project using Google Colaboratory [here](https://colab.research.google.com/github/AvinashBisram/Data-Collection/blob/master/iTunes%20API%20Data%20Collection/iTunes%20API%20Data%20Collection.ipynb).  
**Note:** Executing all cells in the project file will create a CSV file of collected data.

About the iTunes API:
---------------------
Documentation for the iTunes API can be found [here](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI).



Collecting the Data:
--------------------
**Note:** Data was collected on 12/27/21.  
Python's **Requests** module was used to send a GET request to the iTunes API with the specified parameters:  
* term = "the+beatles"
* country = "US"
* media = "music"
* limit = 200

These parameters were used to search the US iTunes store for up to 200 songs by The Beatles.
<br><br>
Python's **json** module was used to retrieve the data sent by the API. Each of the 200 results shared a similar structure:  
![Example iTunes API Result Structure](./readMe%20images/Example%20Result%20Structure.PNG)  

A subset of this information (8 fields) was collected for each result including:
* artistName,
* collectionName,
* trackName,
* trackViewUrl,
* trackPrice,
* releaseDate,
* currency,
* and primaryGenreName

List comprehension was used to contain data relating to these fields.


Saving the Data:
----------------
Python's **Pandas** module was used to combine the lists of collected data into a single Data Frame.  
That data was then saved as a CSV file (_see [iTunes_API_Data.csv](./iTunes_API_Data.csv)_).