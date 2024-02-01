https://www.kaggle.com/datasets/nelgiriyewithana/billionaires-statistics-dataset

# interpretation of outputs


## 1)Wealth distribution analysis: Explore the distribution of billionaires' wealth across different industries, countries, and regions.

For data visualization, the ggplot2 package is used in R Studio. After downloading the package, I made it ready for use with library(ggplot2).
I plotted a column chart using geom_col. With show.legend=FALSE, I opted not to show legends.
I changed the positions of the axes with coord_flip(), making the graph more readable.
I selected the background theme using theme_minimal().

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/7da4796d-7d1f-4a26-bef2-966ee51f8cee)
According to the output, the sector with the highest billionaire wealth is finance & investments. This suggests that individuals working in this sector are the wealthiest. Conversely, the sector with the lowest billionaire wealth appears to be gambling and casinos.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/db0104fa-8081-41be-acb8-83b50f489b21)

According to the output, the United States is the country with the highest billionaire wealth. This indicates that billionaires residing in the United States have earned more wealth.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/6ee61255-a110-495d-a9fe-6f8988f21269)

## 2)Demographic analysis: Investigate the age, gender, and birthplace demographics of billionaires.

.age:

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/5ef03aaf-b45e-42ff-9790-2d1ee468c215)

• This histogram graph shows the age distribution of billionaires. In this histogram, it can be observed that billionaires aged between 50-70 years are more prevalent compared to other age groups.

• The mean value of the data in this histogram is approximately around 60 years old. The median value, on the other hand, is the value that lies in the middle of the data. In this histogram, the median value falls within the range of 60-70 years old. The mode value is the most frequently occurring value in the data. In this histogram, the mode value lies within the range of 50-60 years old.

• Measures such as standard deviation, variance, or range can be used to measure the spread of the data. In this histogram, the range of the data is determined by subtracting the smallest value from the largest value. Range = 100-20 = 80. This indicates that the data is spread over an 80-year range. Standard deviation and variance indicate how far the data deviates from the mean value. In this histogram, standard deviation and variance values can be calculated, but visually, it is also possible to see how much the data is spread around the mean value. As the data deviates further from the mean value, the height of the columns decreases. This indicates that the data is close to the mean value, implying a low standard deviation and variance.

• This indicates that the data is right-skewed. In right-skewed distributions, the mean value is greater than the median value. In this histogram, the mean value is approximately 60, while the median value falls within the range of 50-60 years old. This confirms that the mean value is greater than the median value.

.gender:

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/aea56757-e5d6-4cad-97f2-9696bfc6fd2b)

.birthplace:

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/5735f271-1074-42b2-bdf9-f67f0708c4a5)


According to this graph, we can say that the United States has the highest number of billionaires. Here, we see many countries represented. Let's use the following code to examine the number of billionaires in each of the 66 countries:

I used the dplyr package for manipulation.

Here, there are many countries, and the number of billionaires in some countries is low, such as 1, 2, or 3. Let's take the top 15 countries with the highest populations and name it "top_15_countries", and label the remaining countries as "Other Countries"(diger ulkeler) .This way, our graph will be more streamlined.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/9b44a73a-02bc-402f-90fa-6bc5c5c3cb91)

According to the data, the country with the highest number of billionaires is the United States. The second country with the most billionaires is China, followed by India in the third position.

## 3)Self-made vs. inherited wealth: Analyze the proportion of self-made billionaires and those who inherited their wealth.

I created a dataframe named "veri3_soru". This dataframe contains a class named "category" and a count named "count". The "category" column includes two categories: "Self-Made Billionaires" and "Inherited Wealth", while the "count" column contains the number of individuals belonging to these categories. It is derived from the "status" column of the "data_f" dataset. The "status" column denotes whether the wealth is self-made (D) or inherited (U).

The geom_bar() function is used to create a bar chart. The parameter "stat = "identity"" ensures that the "count" column in the dataframe directly corresponds to the heights of the bars. I assigned the "category" and "count" variables from the veri3_soru variable into aes.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/26932385-c80d-4568-bf9e-81e97f7817a1)

## 4)Economic indicators: Study correlations between billionaire wealth and economic indicators such as GDP, CPI, and tax rates.
In this correlation matrix, there are NA values. To address this, we should remove the NA values and eliminate the dollar sign and comma from the "gdp_country" column.

Now that our matrix no longer contains NA values, let's visualize this correlation matrix. Firstly, we need to install the corrplot package, which we will use to visualize our correlation matrix. Then we write our code.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/eb10213a-59af-4cc8-9c26-bfc67d533531)


This output shows the correlations between finalWorth (billionaire wealth), gdp_country (GDP), cpi_country (CPI), and total_tax_rate_country (tax rate). The correlation coefficient is a value between -1 and 1.

A correlation close to 1 indicates a strong positive relationship between two variables. In a positive correlation, the variables move in the same direction.
A correlation close to -1 indicates a strong negative relationship between two variables. In a negative correlation, the variables move in opposite directions.
A value close to 0 indicates no relationship between the variables.
Here, the correlation coefficient of each variable with itself is 1.

The correlation between billionaire wealth (finalWorth) and GDP (gdp_country) is -0.02. This suggests a very weak negative relationship between the two variables.

The correlation between billionaire wealth (finalWorth) and CPI (cpi_country) is -0.02. This also suggests a very weak negative relationship between the two variables.

The correlation between billionaire wealth (finalWorth) and tax rate (total_tax_rate_country) is -0.08. Again, this indicates a very weak negative relationship between the two variables.

The correlation between GDP (gdp_country) and CPI (cpi_country) is 0, indicating no relationship between the two variables.

The correlation between GDP (gdp_country) and tax rate (total_tax_rate_country) is 0.11, suggesting a very weak positive relationship between the two variables.

The correlation between CPI (cpi_country) and tax rate (total_tax_rate_country) is 0.26, indicating a moderately strong positive relationship between the two variables.

## 5)Geospatial analysis: Visualize the geographical distribution of billionaires and their wealth on a map.

I have loaded the necessary libraries. I selected only two columns from the veri_f dataset (finalworth and region) and assigned them to a variable named "veri"

The "rvest" package is used for scraping information from websites.

The "magrittr" package facilitates data manipulation in a more readable and chainable (chaining) manner. This package enhances the clarity of the code and allows operations to be performed sequentially. We used it here to make necessary adjustments.

The "tidyverse" package is used for data filtering.

The "sf" package, also known as shapefile, is used for processing shapefiles in map files.

The "tmap" package is used to create and visualize thematic maps. This package aims to simplify the process of map creation and offers various customization options. The tmap package contains two main classes, "tmap" and "tm", for creating thematic maps.

We called the "st_read" function from the "sf" package to read geographic data from various formats. "Dsn" specifies the address of the data source. We assigned this data to the variable "dunya_df". This "dunya_df" data contains geographic data related to countries, including their names, dimensions, locations, and boundaries.

In the line "veri$region[veri$region=="Hong Kong"] <-"Hong Kong S.A.R.", we compared the country names (subunit column) in our "veri" dataset with those in the "dunya_df" dataset and adjusted them to be the same. In other words, we replaced the name "Hong Kong" in the "veri" dataset with "Hong Kong S.A.R.".

We used the "left_join" function from the "dplyr" package to merge two data frames. This merging operation is based on matching the values in the "SUBUNIT" column with those in the "region" column. In essence, it takes all the data from the "dunya_df" dataframe and only the matching ones from the "veri" dataframe and merges them based on matching "SUBUNIT" and "region" values.

"tmap_style("white")": This line of code sets the theme to be used for the map style. It sets the background color of the map to white.

When creating our data map, we use the "tm_shape" function to take the "harita_df" we defined earlier. This allows the "tm" library to create a data map for us. It needs to place latitude and longitude coordinates.

"tm_fill" fills the map with "finalworth". We used different parameters such as style, color palette, and title. "style = "quantile"" colors the values according to percentiles. "legend.is.portrait = TRUE" enables the color scale on the map to be displayed vertically (portrait).

main.title: Specifies the title of the map.

main.title.position: Specifies the position of the title. The value "center" ensures that the title is centered on the map.

main.title.size: Specifies the font size of the title.

legend.height and legend.width: These values control the size of the color scale.

legend.outside: Specifies whether the color scale is outside the map. The value FALSE indicates that the color scale will be inside the map.

legend.position: Specifies the position of the color scale. In this case, it will be located in the bottom left corner ("left", "bottom").

legend.frame: We set this to TRUE to indicate that we want a frame around the color scale.

legend.bg.color and legend.bg.alpha: Specifies the background color and transparency of the color scale.

bg.color: Specifies the overall background color of the map. In this case, it is set to "skyblue".

inner.margins: Specifies the inner margins of the map. These values represent the margins on the left, top, right, and bottom edges, respectively.

The function "tm_borders" is used to draw country borders on the map. The "alpha" parameter determines the transparency of the borders. Here, by selecting alpha = 0.5, we ensured that the borders are displayed semi-transparently.

"tm_text("ISO_A3", size = "AREA")": This line adds country labels to the map. The "tm_text" function is used to print values from the "ISO_A3" column onto the map. The parameter "size = "AREA"" determines the size of the labels based on the "AREA" column, which represents the areas on the map. Therefore, the labels of larger countries will be larger, while the labels of smaller countries will be smaller.

The function "tm_grid(alpha = 0.2)" is used to add a grid to the map. By selecting alpha = 0.2, we determined the transparency of the grid. Here, the grid will be slightly transparent and visible under the map.

With "tm_compass", we can add a compass to the map in the desired shape and format.

- type = "8star": Specifies the type of compass. Here, "8star" indicates that an eight-pointed star compass will be used.

- position = c(.65, .15): Specifies the position of the compass. Using a two-element vector, the x and y coordinates of the compass are determined. Here, the compass will appear in the top-right corner (x = 0.65, y = 0.15).
 
- size = 3: Specifies the size of the compass.
 
- color.light = "grey90": Specifies the color of the lights on the compass. Here, shades of gray are used.
  
Let's execute the plot mode.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/085bd2d8-db98-469c-b827-14a1f30ff076)

Let's make it interactive:

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/c05a5892-bd99-4b12-aa23-56426a3df5f2)

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/181423df-203b-487c-a7a5-273c0c7bb69a)

## 6)Trends over time: Track changes in billionaire demographics and wealth over the years.
I checked for missing values in the "birthYear" column of the "veri_f" dataframe and assigned them to the variable "missing_years".
In the if-else part, if there are missing values, we determine the minimum and maximum years among the non-missing values. If there are no missing values, we determine the minimum and maximum years among all years.
The ts() function converts the "finalWorth" column in the "veri_f" dataframe into a time series.
The Start and end parameters specify the start and end dates of the time series.
The frequency parameter determines the frequency of the time series. (I set it to 12 since there are 12 months in a year.)
Finally, we use the plot() function to plot our time series graph. I also specify the color of the graph with the col parameter.

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/259ef557-3bbb-46ae-8855-dfdea07ff283)

According to this graph, there is an increase around the year 1950. Then, during the period up to 2000, the level of wealth has progressed almost steadily. However, there is a significant increase in wealth between 1990 and 2000. It could be assumed that there is a factor influencing wealth during these years, such as an increase in the number of billionaires affecting the increase in wealth. Following this increase, there is a significant decrease in wealth.

Change in gender distribution of billionaires over time:

![image](https://github.com/nurbanus/billionaires-data-analysis/assets/71226874/c374fee0-dc99-48a5-84b8-a8f42681e4d4)

The graph shows the gender distribution of billionaires over the years. Blue bars represent male billionaires, while pink bars represent female billionaires. According to this graph, we can say that the number of male billionaires is greater than the number of female billionaires. We observe a significant increase in both male and female billionaire numbers in 1962. Between 1930 and 1960, the number of male billionaires increased significantly. The number of female billionaires is consistently lower than the number of male billionaires across all years.

