# Analyzing Pet Adoptions

I completed this project as part of Metis Data Science Bootcamp. 

According to aspca.org 6.5 million dogs/cats end up in shelters each year in US, 1.5 million of them get euthenized each year. There are 300 million stray dogs and cats worldwide. 
Only very small number of pets gets to go home to their forever home. Most of the pets stay in the shelters, if they are lucky.

The goal of this project was to predict the number of days it takes for a pet to get adopt
ed.

## Data Source and Scraping

I scraped the data from petfinder.my website. I only focused on dogs and cats. I used Python library Beautiful soup to scrape the pet profiles, which included information on the pet's type, gender, age, health, vaccination, body size, color, region of country, price, the date posted and updated, pet description, and so on (the pet profile also contained a picture of a pet, which I didn't scrape). All of this information is saved in a csv file

## Data Cleaning

Most of the columns needed some kind of cleaning:
* some pet information was put together under one column, those needed to be separated into individual columns
* some of the columns had redundant words and punctuations whcich were removed
* posted and updated dates were converted into datetime format
* adoption length was found using the posted and updated dates (we assumed the updated date was when the pet got adopted)
* outliers were removed
* I created some categorical features from continous features 
* Categorical variables were converted into dummy variables for modeling purposes

## Modeling

I used Linear, Ridge and Laso Regression with k-fold cross validation. However, none of them had good results. 
Checking the linear regression assumptions, the residuals weren't normally distributed and the Q-Q plot was skewed which means that the relationship between the features and the target might not be linear. 

In the future, I would like to explore this project more and try to imporve the results:
* apply non linear models
* use NLP to analyize the pet descriptions to see if that could help with increasing the model accuracy
* scrape the actual pictures of the pets and use that in the prediction since I think picture of the pet is one of the important factors of pet adoption
* approach this as a classification problem instead of regression
* optimize the code
 
