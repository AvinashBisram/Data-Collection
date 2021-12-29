EDAMAM API Data Collection
==========================

**Description:** This project uses EDAMAM's Nutrition Analysis API to collect data on 30 nutrients found in a sample recipe (sent to the API through a POST request). Information collected of each nutrient include their labels (descriptive names), quantities, and units. Collected data was saved to a CSV file.

**Language(s):** Python  
**Package(s):** Requests, JSON, Pandas  
**Software:** Jupyter Notebooks  

**Motivation:** This project was created to demonstrate skills in collecting data from APIs that require authentication and POST requests.

Viewing the Project:
--------------------
The main file for this project is located in the root of this repository named _[EDAMAM API Data Collection.ipynb](EDAMAM%20API%20Data%20Collection.ipynb)_. If you have **Jupyter Notebooks** installed, you can download the .ipynb file and view it there. If not, you can view the project using Google Colaboratory [here](https://colab.research.google.com/github/AvinashBisram/Data-Collection/blob/master/EDAMAM%20API%20Data%20Collection/EDAMAM%20API%20Data%20Collection.ipynb).
**Note:** Executing all cells in the project file will create a CSV file of collected data.

About the EDAMAM Nutrition Analysis API:
----------------------------------------
EDAMAM has several APIs that developers can use including a Food Database Lookup, Recipe Search, and Meal Recommendation Engine. A full list of the APIs they offer can be found in their [API Developer Portal](https://developer.edamam.com/).  

The API used in this project was the Nutrition Analysis API which takes in unstructured recipe text and returns information on the various nutrients contained in the food.

Documentation for the EDAMAM Nutrition Analysis API can be found [here](https://developer.edamam.com/edamam-docs-nutrition-api).


Collecting the Data:
--------------------
**Note:** Data was collected on 12/28/21.
Python's **Requests** module was used to send a POST request to the EDAMAM Nutrition Analysis API. The POST request contained the required header, as well as a dictionary of parameters (app_id and app_key) needed for authentication.  
Lastly, the request contained a json of the recipe being submitted to the API. It was constructed in the following format:  
![Post Request Body Structure](./readMe%20images/Post_Body.PNG)  
The two components of the body JSON were a recipe title, and "unstructured text" containing all ingredients with their respective quantities.  

The POST request was sent to the API route and the JSON response contained data on total nutrient quantities as well as nutrient quantites in relation to % Daily Value. For this project, data was collected on the total quantities of each nutrient.  

Each nutrient in the JSON response had a label, quantity, and unit. A for-loop was used to collect these fields for all provided nutrients.


Saving the Data:
----------------
Python's **Pandas** module was used to compile the lists of data containing nutrient labels, quantities, and units into a Data Frame. The first few rows looked like this:  
![EDAMAM_DataFrame_Snippet](./readMe%20images/EDAMAM_DataFrame_Snip.PNG)  
That data was then saved as a CSV file (_see [EDAMAM_API_Nutrient_Data.csv](./EDAMAM_API_Nutrient_Data.csv)_).