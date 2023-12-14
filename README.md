# Project 4: Group 4
### Contributors: Thomas Keene, Faith Hall, Angela Gosewehr, and Raeshawn Mcallister   

---
# Project slideshow link: https://www.canva.com/design/DAF1m1CgodU/d5s7yap5oSPx3qMLeuGY7Q/edit?utm_content=DAF1m1CgodU&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

---
# Tableau story links:
https://public.tableau.com/app/profile/angela.gosewehr/viz/housepriceswithstory/NewYorkhousesalestats?publish=yes   

The link contains several visualizations in a Tableau story. These include: A map of New York with hover detail of the average price in that city and two stacked bar graphs showing the relationship between bedroom count with price point and bathroom count with price point.

https://public.tableau.com/app/profile/raeshawn.mcallister/viz/acrelotcoloredbyzipcode/Story2?publish=yes

This link contains a treemap showing the correlation of acre lot to price in Tableau.

---
# Repository:
The final code is stored as two files in the "Code" folder and is described as follows:
- cleaning-dataset.ipynb = Initial data cleaning and scatter plots of the boroughs of New York
- Project_4_group_4_Machine_Learning_colab.ipynb = Final code for data cleaning, model selection, and model scoring

---
# Project Overview: 
The aim of our project is to develop a machine learning algorithm to sort through the New York realtor data set to establish a relationship between the house features (house size (square feet), number of bedrooms, number of bathrooms, lot size (acres), and city) and price of the home.

### Research Question: 
#### Which features have the greatest impact on home price (house size (square feet), number of bedrooms, number of bathrooms, lot size (acres), and zip code)?
---
# Analysis: 

---
## Visuals and Plots
### New York City Boroughs Map
![image](https://github.com/Faith-Hall/project-4-group-4/assets/135525815/9349b6da-1c03-4ff1-88f7-56b156c6491f)

<p float="left">
  <img src="/Visualizations/bronx_plot.png" width="300" />
  <img src="/Visualizations/manhattan_plot.png" width="300" />
  <img src="/Visualizations/brooklyn_plot.png" width="300" /> 
</p>
<p float="left">
  <img src="/Visualizations/staten_island_plot.png" width="300" />
  <img src="/Visualizations/queens_plot.png" width="300" /> 
</p>

---
## Model Selection and Optimization
After cleaning, the data was split into training and testing sets utilizing an 80/20 split and three options were selected as potential candidates for our machine learning model:
- Linear Regression
- Decision Tree
- Random Forest Regression

A test of the three options (based on model scores and explained variance scores) showed that the Random Forest Regression model would be the best option for predicting home prices based on home features:

![image](https://github.com/Faith-Hall/project-4-group-4/assets/137319054/f1b68818-d832-41e8-b966-ded8572c900d)

Once the Random Forest Regression model was selected, the data were split again into training and testing sets (this time using a 70/30 split) and an initial assessment of the model was performed. The results showed:
  
![image](https://github.com/Faith-Hall/project-4-group-4/assets/137319054/d892f00b-00e7-4bdb-8517-ca7c8e9d300a)   

- R^2 = 0.9831
- RMSE = 111967.66


Next, to optimize the model further, GridSearchCV was utilized to tune the hyperparameters of:
- n_estimators = number of trees in the forest (we selected 10, 100, & 500 as our initial options)
- max_features = max number of features considered for splitting a node (we selected sqrt & log2 as our initial options)
- max_depth = max number of levels in each decision tree (we selected 5, 10, & 20 as our initial options)

After hyperparameter tuning, GridSearchCV indicated that the best parameters (based on our inputs) were:   
- n_estimators = 100
- max_features = sqrt
- max_depth = 20

Utilizing these new parameters, the model was run once again, resulting in the following:

![image](https://github.com/Faith-Hall/project-4-group-4/assets/137319054/d9dc9fda-d197-49f9-b8c9-0454da0c8710)   

- R^2 = 0.9843
- RMSE = 111967.66


As noted from the R^2 values shown above, a slight improvement was obtained post optimization (hyperparameter tuning) with GridSearchCV.

Next, R^2 scores were obtained using cross validation and OOB scoring resulting in the following values:
- cross validation R^2 = 0.9535
- OOB R^2 = 0.9617

---
# Conclusion:
Based on our optimized model, the most important features in determining the price of a home are shown below:   

![image](https://github.com/Faith-Hall/project-4-group-4/assets/137319054/cea24c46-09bf-43a0-b520-d7bdd1859dc5)

---
### Resources: 
- Dataset Used: https://www.kaggle.com/datasets/ahmedshahriarsakib/usa-real-estate-dataset
- Image of New York City Boroughs Map: https://www.worldatlas.com/articles/the-boroughs-of-new-york-city.html

### Web Resources:   
- https://seaborn.pydata.org/index.html
- https://www.youtube.com/watch?v=llYimxlsMf4&t=2380s
- https://forums.fast.ai/t/oob-score-and-r2-score-when-to-use-each/29566
- https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74#:~:text=n_estimators%20%3D%20number%20of%20trees%20in,levels%20in%20each%20decision%20tree
- https://medium.com/data-science-at-microsoft/out-of-bag-validation-for-random-forests-378f2b292560#:~:text=OOB%20validation%20is%20much%20faster%20than%20k%2Dfold%20cross%2Dvalidation&text=In%20general%2C%20you%20can%20think,huge%20difference%20in%20compute%20time
 
### Acknowlegements:
Thank you to our instructional staff: 
- Hunter Hollis
- Sam Espe
- Randy Sendek
