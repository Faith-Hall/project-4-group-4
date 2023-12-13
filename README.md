# Project 4: Group 4
### Contributors: Thomas Keene, Faith Hall, Angela Gosewehr, and Raeshawn Mcallister
---
Project slideshow link: https://www.canva.com/design/DAF1m1CgodU/d5s7yap5oSPx3qMLeuGY7Q/edit?utm_content=DAF1m1CgodU&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
---
# Tableau story link: https://public.tableau.com/app/profile/angela.gosewehr/viz/housepriceswithstory/NewYorkhousesalestats?publish=yes
The link contains several visualizations in a tableau story. These include: A map of New York with hover detail of the average price in that city and two stacked bar graphs showing the relationship between bedroom count with price point and bathroom count with price point.

---
# Project Overview: 
The aim of our project is to develop a machine learning algorithm to sort through the New York realtor data set to establish a relationship between the house features (house size (square feet), number of bedrooms, number of bathrooms, lot size (acres), and city) and price of the home.

### Research Question: 
#### Which features have the greatest impact on home price (house size (square feet), number of bedrooms, number of bathrooms, lot size (acres), and city)?
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
After cleaning the data, three options were selected as potential candidates for our machine learning model:
- Linear Regression
- Decision Tree
- Random Forest Regression

A test of the three options showed that the Random Forest Regression model would be the best option for predicting home prices based on home features:
![image](https://github.com/Faith-Hall/project-4-group-4/assets/137319054/f1b68818-d832-41e8-b966-ded8572c900d)




### Resources: 
- Dataset Used: https://www.kaggle.com/datasets/ahmedshahriarsakib/usa-real-estate-dataset
- Image of New York City Boroughs Map: https://www.worldatlas.com/articles/the-boroughs-of-new-york-city.html

### Web Resources:   
- https://seaborn.pydata.org/index.html
- https://www.youtube.com/watch?v=llYimxlsMf4&t=2380s
- https://medium.com/data-science-at-microsoft/out-of-bag-validation-for-random-forests-378f2b292560#:~:text=OOB%20validation%20is%20much%20faster%20than%20k%2Dfold%20cross%2Dvalidation&text=In%20general%2C%20you%20can%20think,huge%20difference%20in%20compute%20time
 
### Acknowlegements
Thank you to our instructional staff: 
- Hunter Hollis
- Sam Espe
- Randy Sendek
