# Plotting-Global-Weather-by-Latitude
With this project, I visualized correlations between latitude, maximum temperature, % humidity, % cloud cover, and wind speed. I also sought visual insight into how these correlations differ between the northern and southern hemispheres. This project is for understanding global weather as it stands on the day that the code is run.

To use my project, clone the repository to your computer, open the Today'sGlobalWeather.ipynb file in Jupyter Notebook, and press the play button next to each code block in sequence.

After importing my dependencies, I generated a list of 612 cities from around the world. I did this by generating pairs of random latitudes and longitudes, then using the citipy module to find the city closest to the point specified by the lat and lon numbers. Then, for each city in the list, I called the openweathermap.org API to get today's maximum temperature, % humidity, % cloud cover, and wind speed. In order not to lock myself out of the API by performing too many times each minute, I incorporated a time.sleep() line which caused my code to wait slightly more than a second before doing the next call. For each call, I used a try and except code chunk to check whether data actually existed for each city in the list before appending any data to my data lists. Because the cities are randomly selected and there is not always every desired piece of weather data for a given city, the number of data points obtained for each weather variable data list may be somewhat less than 612 each time the code is run. Here is the beginning of the list of 612 random cities:
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

Now, I search for correlations between all of the variables. These are r values
![image](https://user-images.githubusercontent.com/73863977/128100706-aad81ea2-4ef0-425d-a2c4-2851e5d34a11.png)


![image](https://user-images.githubusercontent.com/73863977/128100725-a86b7b2e-45fc-4160-bafa-bdb0605962ba.png)
![image](https://user-images.githubusercontent.com/73863977/128100744-2cd0f824-c8dc-43ed-8e72-f89a08c3b55b.png)
![image](https://user-images.githubusercontent.com/73863977/128100780-cc2bc7b4-188e-494b-b8d0-da4b53d3f69e.png)
![image](https://user-images.githubusercontent.com/73863977/128100801-2218fe65-7beb-46f8-ac77-2c2b770a1eb6.png)
![image](https://user-images.githubusercontent.com/73863977/128100823-3fb8cb5f-dac3-4650-99dc-7dd85d785e0d.png)
![image](https://user-images.githubusercontent.com/73863977/128100844-5dc39de0-cd24-456a-a56f-fa110b98b3fc.png)
![image](https://user-images.githubusercontent.com/73863977/128100873-74886500-9c8d-4b5c-aff3-8d2e0e71c033.png)
![image](https://user-images.githubusercontent.com/73863977/128100891-75fc3f36-cc78-4955-9168-2e190f3a5b25.png)
