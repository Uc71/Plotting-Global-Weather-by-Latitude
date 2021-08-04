# Plotting-Global-Weather-by-Latitude
With this project, I visualized correlations between latitude, maximum temperature, % humidity, % cloud cover, and wind speed. I also sought visual insight into how these correlations differ between the northern and southern hemispheres. This project is for understanding global weather as it stands on the day that the code is run.

To use my project, clone the repository to your computer, open the Today'sGlobalWeather.ipynb file in Jupyter Notebook, and press the play button next to each code block in sequence.

After importing my dependencies, I generated a list of several hundred cities from around the world. I did this by generating pairs of random latitudes and longitudes, then using the citipy module to find the city closest to the point specified by the lat and lon numbers. Then, for each city in the list, I called the openweathermap.org API to get today's maximum temperature, % humidity, % cloud cover, and wind speed. In order not to lock myself out of the API by performing too many times each minute, I incorporated a time.sleep() line which caused my code to wait slightly more than a second before doing the next call. For each call, I used a try and except code chunk to check whether data actually existed for each city in the list before appending any data to my data lists. Because the cities are randomly selected, citipy sometimes approximates different points with the same city, and there is not always every desired piece of weather data for a given city, the number of data points obtained for each weather variable data list may differ each time the code is run. Here is the beginning of the list of 612 random cities:
![image](https://user-images.githubusercontent.com/73863977/128100551-6969c275-b4bf-4d82-8388-976878e30e4c.png)

I used a line of code to convert all the temperatures from openweathermap.org from Celsius to Fahrenheit, then displayed all of the weather data, including the Fahrenheit temperatures, in a dataframe. The beginning of that df is shown here. Notice that, as certain cities were evidently lacking data for one or some of the desired weather variables, there are only 558 rows here.
![image](https://user-images.githubusercontent.com/73863977/128100632-6d7784a9-2179-4663-bcc2-05f8eee684db.png)

I run basic descriptive statistics on each of my variables: latitude, maximum temperatures, humidities, cloud covers, and wind speeds.
![image](https://user-images.githubusercontent.com/73863977/128100671-acd32cc4-bce5-42c5-bdca-183eedb97126.png)

I plot today's maximum temperature against % cloud cover. 
![latclo](https://user-images.githubusercontent.com/73863977/127946780-e5df5893-9961-4730-b985-84e73c91b05b.png)

I plot the current humidity level against latitude.
![lathum](https://user-images.githubusercontent.com/73863977/127946782-049131e8-02f4-419f-842e-52621378ce78.png)

I plot the current wind speed against latitude.
![latspe](https://user-images.githubusercontent.com/73863977/127946783-42c75812-bdb5-49ba-9ff5-e87f58e912ea.png)

I plot today's maximum temperature against latitude. As I would expect, I see temperatures peaking near the equatore and decreasing towards each pole.
![lattem](https://user-images.githubusercontent.com/73863977/127946785-f15cf629-36da-435f-a4f4-1d9421e4c1ae.png)

Now, I search for correlations between all of the variables. These are r values.
![image](https://user-images.githubusercontent.com/73863977/128100706-aad81ea2-4ef0-425d-a2c4-2851e5d34a11.png)

I constructed a 8 plots breaking down the previous 4 scatter plots by hemisphere and adding linear regression lines to each. For each plot, one of the variables will be latitude.
Here is the plot for maximum temperatures in the Northern Hemisphere. As I expected, temperatures decrease as latitude increases.
![image](https://user-images.githubusercontent.com/73863977/128100725-a86b7b2e-45fc-4160-bafa-bdb0605962ba.png)

Here is the plot for maximum temperatures in the Southern Hemisphere. As I expected, temperatures increase as latitude increases.
![image](https://user-images.githubusercontent.com/73863977/128100744-2cd0f824-c8dc-43ed-8e72-f89a08c3b55b.png)

Here is the plot for humidities in the Northern Hemisphere. As I expected, humidity decreases as latitude increases.
![image](https://user-images.githubusercontent.com/73863977/128107116-90a6e855-72aa-417b-983c-8bd13b2128c0.png)

Here is the plot for humidities in the Southern Hemisphere. As I expected, humidity increases as latitude increases.
![image](https://user-images.githubusercontent.com/73863977/128107146-5e3789fb-1589-4b72-8326-8f8478df1839.png)

Here is the plot for cloud cover in the Northern Hemisphere.
![image](https://user-images.githubusercontent.com/73863977/128107180-c729ed52-25a1-4e82-9084-73938190ae9a.png)

Here is the plot for cloud cover in the Southern Hemisphere.
![image](https://user-images.githubusercontent.com/73863977/128107206-acbf0e1b-e2fd-4594-843f-b0704b621f1f.png)

Here is the plot for wind speeds in the Northern Hemisphere.
![image](https://user-images.githubusercontent.com/73863977/128107228-7084e3c2-232a-429d-b49d-7671cca99404.png)

Here is the plot for wind speeds in the Southern Hemisphere.
![image](https://user-images.githubusercontent.com/73863977/128107257-52cf0ee2-4015-4b57-957f-839969fa116c.png)
