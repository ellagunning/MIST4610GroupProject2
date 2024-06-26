# MIST4610GroupProject2

TEAM NAME:
------
Sp24_21484_Group3


TEAM MEMBERS:
----
1. Brendan Rice | [@brendanr14](https://github.com/brendanr14/MIST4610GroupProject2)
2. Roshan Maganti | [@rmaganti6](https://github.com/RMAGANTI6/MIST4610GroupProject2)
3. Areez Shaikh | [@areezshaikh](https://github.com/areezshaikh/MIST4610GroupProject2)
4. Jack Gannon | [@jackgannonn](https://github.com/JackGannonn/MIST4610GroupProject2)
5. Brayden Keller | [@braydok12](https://github.com/braydok12/MIST4610GroupProject2)
6. Ella Gunning | [@ellagunning](https://github.com/ellagunning/MIST4610GroupProject2)


DESCRIPTION OF DATASET:
----
Our dataset includes the sale data for hundreds of thousands of car sales. We obtained our dataset through the Kaggle website (https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data). This vast dataset has many different attributes that we can use to visualize this data. Each sale includes data about the car's make, model, trim, year, state of sale, odometer, color, sale price, and sale date, among a few others that were not used fully in our analysis. The numeric type data includes the dimensions year, odometer, and sale price. These are numbers that we can look at sums, averages, or counts of which may be useful in our analysis. The string data includes those with characters such as make, model, color, etc. State of sale is a string but has a geographic role, which can allow us to visualize our data on a map with the generated latitude and longitude fields. We also transformed the sale date data column from a string to a date, which is described below in data manipulation. A combination of this dataset's size and description of each sale can help us look at different trends in the car market. The data is diverse and includes a broad range of makes, models, and years which will allow for more accurate aggregate data that limits the effect of outliers.

QUESTION 1:
---
For the Southeast region (for our defintion - Georgia, Florida, Tennessee, South Carolina, and North Carolina), how do the average sale prices of the 5 most popular manufacturers differ? We want to separate them by under 50,000 miles, between 50-100,000 miles, and over 100,000 miles to account for depreciation.

IMPORTANCE:

Say you're looking at this data from a consumer perspective. Dealerships can sometimes mark up their cars, so you want to see what you should be paying for a certain kind of car. This kind of dashboard can show you what the average price is of each of the top 5 most popular car brands at different mileage points. Additionally, you can also use this table as a prospective car buyer to see how depreciation affects each of these car brands. If you want to buy a car that holds it's value, you can look at the price difference between those under 50k miles and those over 100k miles. 

This table would also be helpful for someone like a car dealership. For example, a used car dealership could look at these average sale prices among different makes in the southeast and see which ones are worth buying and what they could potentially sell it for. 

ANALYSIS:

<img width="976" alt="Screenshot 2024-04-21 at 5 46 05 PM" src="https://github.com/brendanr14/MIST4610GroupProject2/assets/149964823/6ecfc9d4-be8f-4482-951f-4b97e7ecf13e">


Additionally, here is a map of the biggest car markets in the Southeast for these 5 brands.

<img width="1426" alt="Screenshot 2024-04-21 at 9 10 34 PM" src="https://github.com/brendanr14/MIST4610GroupProject2/assets/149964823/7ec128bb-1734-432b-96e7-7a2920748d67">


Both of these visualizations show the top 5 most sold car brands in the Southeast region. These brands are BMW, Chevrolet, Ford, Mercedes-Benz, and Toyota. We can see here the average selling price of each of these makes at different mileage points. This allows us to get a better view at which popular brands hold their value better as they age and are driven more. From a quick glance, we can see BMW has the biggest selliing price difference while Toyota maintains its value much better. This visualization also has a heatmap element that shows which cars are selling for higher prices on average based on mileage. The map is also a handy data visualization to see the largest car markets in the southeast. This may be a good map for a national auto dealer looking to expand in a new market. 



QUESTION 2:
---
Of the most common four body types of cars sold in each state (SUV, Sedan, Hatchback, and Wagon), how does condition affect the average selling price of the car, and in which states would consumers get the best value?


IMPORTANCE:

This data is important for consumers to understand as it represents the best states to purchase a car in based on the average condition to price ratio. In states like Massachusetts, Maryland, and Oklahoma, the average price is low while the average condition is high indicating that these states have the best value for consumers on average for the most common types of cars. This data can also be used by prospective car dealership owners. They would be able to see which states they should avoid opening a dealership in as they would make less profit from selling cars in higher condition. They can also see which states on average have cars with higher condition and lower condition, which may have deeper meaning when it comes to the car market of that state.

ANALYSIS:

![Screenshot (61)](https://github.com/RMAGANTI6/MIST4610GroupProject2/assets/163043852/a6fce534-a671-45c1-a565-c8f56771c6fb)


This visualization illustrates the average condition and average selling price by each state. Since the two bar graphs are stacked on top of each other, we can clearly see which states have the biggest difference based on the height of the bars. The difference in height of the bars is where we can assess the best value to purchase a car from the consumer perspective. For example if you look at the states of Alabama and Massachusetts, they have a large difference between condition and selling price. Since the height of the condition bar is higher, this indicates that consumers would receive the greatest value in purchasing a car in these states as it included low selling price with relatively high quality. This would a great data visualization image for consumers who are looking to buy a car as they can determine which state to purchase the car from. 






DATA MANIPULATION:
---
There were a few different manipulation procedures we had to go through before visualizing our data. First, the first column in the table was all null. This was an easy fix, as we simply excluded the data. We also had to manipulate the data by creating calculated fields. The first of those is NormMake. The original Make column had some inconsistencies and resulted in multiple different rows for the same make (ex: bmw and BMW). Additionally, there were also some duplicate makes, such as Ford and Ford Truck, or VW and Volkswagen. To fix this, we created a calculated that first set all the Make strings to all uppercase. This would combine the rows that had a difference in capitalization. Then, we used a nested if/else statement to convert any additional Makes to their original (Ford Truck combines with Ford). Because of this, we can now look at all the data together and more cleanly.


TABLEAU PACKAGED WORKBOOK:
---
The packaged Tableau Workbook is attached to the GitHub Repository.

The next calculated field we made was NormState. After filtering out the data that align well with our column, it was as simple as using the UPPER command to get all states to be uppercase. There was the same issue where for example there would be both 'ga' and 'GA'. This calculated field fixed that issue of separation. 

Lastly, the most difficult manipulation was the date data. Using the DATEPARSE function, we had to code the format of the string to allow Tableau to convert it to date data. We also had to include nested function that ignored the time zone part of the original string, as it was in a format that Tableau would not recognize.
