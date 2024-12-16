# NAGPUR WEATHER DATASET ANALYSIS 

### OBJECTIVE 
The objective of the dashboard is to analyze and visualize seasonal weather patterns in Nagpur, focusing on key metrics like wind chill, temperature, and humidity.

### INTRODUCTION
The dataset includes weather data recorded over a specific period for Nagpur. Each entry includes the exact date and time of recording, capturing variations in meteorological parameters such as temperature, dew point, and humidity. This detailed timestamping allows for in-depth analysis of daily and seasonal weather patterns, helping to identify trends and anomalies over the observed period.

### DATASET: NAGPUR WEATHER DATASET
 
![image](https://github.com/user-attachments/assets/c3e22a6e-4903-4f3a-9d3a-ae8737cb0be9)

**Number of rows:** 10,497

**Number of columns:** 19

### VARIABLE DESCRIPTION

**1. month:** The month of the recorded data (string format).

**2. time:** The time of the recorded data (string format).

**3. day/night:** Indicates whether the data was recorded during the day or night (string format).

**4. temperature:** The temperature in degrees Fahrenheit (integer format).

**5. condition:** The weather condition (e.g., Cloudy, Haze) (string format).

**6. dew_point:** The dew point temperature in degrees Fahrenheit (integer format).

**7. heat_index:** The heat index in degrees Fahrenheit (integer format).

**8. humidity_%:** The humidity percentage (integer format).

**9. pressure:** The atmospheric pressure in inches of Mercury (Hg) (float format).

**10. visibility:** The visibility in miles (float format).

**11. windchill:** The wind chill temperature in degrees Fahrenheit (integer format).

**12. Wind_direction:** The direction of the wind in degrees (integer format).

**13. gust:** The wind gust speed in miles per hour (integer format).

**14. wind_speed:** The wind speed in miles per hour (integer format).

**15. uv_desc:** The description of the UV index (e.g., Low) (string format).

**16. uv_index:** The UV index (integer format).

**17. clouds:** The cloud cover description (e.g., OVC - Overcast, SCT - Scattered) (string format).

**18. rain:** A boolean indicating if it rained (True/False).

**19. Rain_today:** A string indicating if it rained today (Yes/No).

### DASHBOARD 
https://github.com/user-attachments/assets/caf65f87-5998-4232-a1ce-6ba291b9cb60

### CHARTS

1. How does humidity change over time?

**Humidity Trends Over Time**
   
![image](https://github.com/user-attachments/assets/1f338092-7a1f-4de4-9fbe-6bcc4be53378)
   
**Query:** _SELECT MEAN(HumidityPercentage) FROM data GROUP BY time(1m)_
   
**Observation:** Humidity levels fluctuate throughout the observed period but remain within a moderate range
   
**Insights:** The humidity trends chart for Nagpur shows significant fluctuations within the observed hour, with notable peaks around 23:00 and 23:10, indicating periods of increased moisture. The frequent variability suggests dynamic weather conditions, potentially influenced by evening cooling or local meteorological events. Overall, the chart highlights the rapid changes in humidity, which could correlate with other weather parameters for deeper analysis.

2. How does the average heat index differ across various weather conditions?

**Average Heat Index by Weather Condition**

![image](https://github.com/user-attachments/assets/269410fd-fb5b-4644-87cc-99632118404e)

**Query:** _SELECT MEAN(HeatIndex) FROM data GROUP BY condition_
   
**Observation:** Cloudy conditions have an average heat index of 71.7, haze conditions rise to 86.3, and thunder conditions peak at 90.3, indicating increasing warmth and humidity.

**Insights:** Severe weather conditions, like Thunder, are linked to higher heat indices, while cloudy weather has the lowest heat index due to less sunlight and lower humidity.

3. What is the average temperature when humidity percentage is greater than 40?

**Average Temperature Over Time**

![image](https://github.com/user-attachments/assets/f132f29d-178b-472d-8e3c-d5c16f8f2641)

**Query:** _SELECT MEAN(temperature) FROM data GROUP BY time(1m)_
   
**Observation:** The average temperature shows cyclical spikes, aligning with time periods during the day.

**Insights:** This chart reveals significant temperature fluctuations within the observed period. The temperature peaks, reaching over 100°F around 22:40 and 22:50, indicate periods of intense heat. Frequent dips to around 80°F suggest intermittent cooling, possibly due to changes in weather conditions such as wind or cloud cover. This pattern of rapid temperature changes highlights the dynamic nature of the local weather, with substantial variations occurring within short time intervals.

4. How does average visibility vary across various cloud cover type?
 
**Average visibility by cloud cover type**

![image](https://github.com/user-attachments/assets/74078b78-d58b-457d-87c0-a20283ac72f6)

**Query:** _SELECT MEAN(visibility) FROM data GROUP BY clouds_
   
**Observation:** Clear skies (CLR) have the highest visibility, while broken clouds (BKN) and others slightly reduce visibility.
  
**Insights:** This chart shows that few clouds offer the highest visibility at 2.80 miles, followed by clear skies at 2.78 miles. Scattered and overcast clouds provide moderate visibility at 2.56 and 2.67 miles, respectively, while broken clouds have the lowest visibility at 2.21 miles. Visibility decreases as cloud cover increases.

5.  Is there a correlation between wind speed and visibility?

**Correlation Between Wind Speed and Visibility**

![image](https://github.com/user-attachments/assets/90ec8935-23aa-433c-be7e-e5c3a636c985)

**Query:** _SELECT MEAN(WindSpeed), MEAN(visibility) FROM data GROUP BY time(1m)_
   
**Observation:** Wind speed directly affects visibility, with higher speeds generally enhancing it. Understanding this correlation can help predict visibility based on wind forecasts.

**Insights:** This chart shows that few clouds offer the highest visibility at 2.80 miles, followed by clear skies at 2.78 miles. Scattered and overcast clouds provide moderate visibility at 2.56 and 2.67 miles, respectively, while broken clouds have the lowest visibility at 2.21 miles. Visibility decreases as cloud cover increases.

6. How does the heat index differ between day and night?

**Day vs Night Comparison of Heat Index**

![image](https://github.com/user-attachments/assets/215b7e51-36e0-42ba-b345-b7249d30941b)

**Query:** _SELECT MEAN(HeatIndex) FROM data GROUP BY DayNight_
   
**Observation:** The average heat index is higher during the day (91.0) and lower at night (82.9), indicating cooler nighttime temperatures.

**Insights:** The chart shows a clear difference in Nagpur's heat index, with daytime averaging 91.0°F and nighttime 82.9°F. This highlights significant cooling at night due to reduced solar radiation, impacting comfort levels and energy usage.

7. What is the average dew point over time?
   
**Average dew point over time**

![image](https://github.com/user-attachments/assets/998fc5b4-ff20-486c-8ccd-2dc76db7d8d6)

**Query:** _SELECT MEAN("DewPoint") AS "avg_dew_point" FROM "data" GROUP BY time(1m)_
   
**Observation:** The dew point steadily increases over time, peaking during specific hours.

**Insights:** The chart illustrates fluctuations in the average dew point over time. It shows a gradual increase from 22:40, peaking around 23:10, followed by a slight decline and variability thereafter. The peak values indicate higher moisture content in the air, suggesting a rise in humidity levels around that time. 

8. What are the maximum and minimum temperatures recorded each month?

 **Maximum and minimum temperatures over time**

 ![image](https://github.com/user-attachments/assets/90fa57eb-db21-4174-90af-45a65750d61e)

 **Query:** _SELECT MAX("temperature") AS "max_temp", MIN("temperature") AS "min_temp" FROM "data" GROUP BY time(1m) FILL(null)_
   
**Observation:**  Significant fluctuation in max and min temperatures suggests high variability in weather conditions during the observed period.

**Insights:** The chart shows fluctuations in maximum and minimum temperatures over time. Maximum temperatures consistently peak above 100°F, while minimum temperatures range between 70°F and 90°F. The variations indicate significant thermal oscillations, likely driven by environmental and meteorological factors

9. What is the average UV index for each UV description category?

**Average UV index by UV description**

![WhatsApp Image 2024-12-16 at 11 39 52 PM-11](https://github.com/user-attachments/assets/8adb72bc-82e6-44f5-90be-868969e042a2)

**Query:** _SELECT MAX(uvIndex) FROM data GROUP BY uvDesc_
   
**Observation:** UV index values are highest for "Extreme" and "Very High" categories, while "Low" levels are minimal.

**Insights:** The chart shows UV Index averages, with "Extreme" at 12.2, "Very High" at 9.07, and "High" at 6.61, posing significant risks. "Moderate" (3.87) and "Low" (0.294) indicate lower risks, highlighting the need for precautions during high UV levels in Nagpur.

10. What is the average Wind chill for each month?
**Average Wind Chill by Month**

![image](https://github.com/user-attachments/assets/5fdc4c5c-5a1f-44e2-aa0e-f31b0d38c6be)

**Query:** _SELECT MEAN(windchill) FROM data GROUP BY month_
   
**Observation:** Wind chill varies by month, with some months experiencing cooler conditions than others.

**Insights:** The chart shows UV Index averages, with "Extreme" at 12.2, "Very High" at 9.07, and "High" at 6.61, posing significant risks. "Moderate" (3.87) and "Low" (0.294) indicate lower risks, highlighting the need for precautions during high UV levels in Nagpur, reflecting a seasonal warming trend as the months progress, which aligns with the transition from winter to spring. The rising wind chill values reflect increasing temperatures or decreasing wind speeds, contributing to less chilling conditions.

### MANAGERIAL IMPLICATION 

**1. Weather-Dependent Operational Adjustments:** High variability in temperatures, dew point, and wind chill suggests the need for dynamic operational planning, especially for outdoor activities. For example, when the heat index is high, it's essential to implement safety measures like hydration and rest breaks for workers exposed to the elements.

**2. Safety Protocols:** The UV index insights imply a need for stronger safety protocols during peak UV conditions. During "Extreme" and "Very High" UV index levels, protective measures such as sunscreen, hats, and shaded areas should be enforced to reduce the risk of sunburn and heat-related illnesses.

**3. Transportation and Logistics:** The correlation between wind speed and visibility highlights the importance of adjusting transportation and logistics operations based on real-time weather data. Low visibility due to cloud cover or wind speed fluctuations could lead to delays or safety risks, requiring early forecasting and route optimization.

**4. Seasonal Planning:** Seasonal variations in wind chill and temperature emphasize the need for tailored strategies across different months. For example, in colder months, heating and weatherproofing systems may need to be emphasized, while during warmer months, cooling solutions should be prioritized.

**5. Energy Management:** The fluctuation in temperature and humidity levels calls for improved energy management practices. Cooling and heating systems should be optimized based on the time of day and seasonal changes, helping to reduce operational costs.

**6. Weather-Driven Resource Allocation:** The trends in humidity and temperature suggest that resources, such as water, cooling units, and safety equipment, should be allocated based on real-time weather predictions to minimize downtime and optimize productivity.

### CONCLUSION
The dataset provides valuable insights into how various meteorological parameters impact daily operations and safety. Temperature, humidity, wind speed, UV index, and visibility all show distinct patterns that can be leveraged for more informed decision-making. By understanding the relationships between these factors, businesses can enhance safety, optimize resource usage, and improve operational efficiency. Seasonal trends and day-night variations should be considered in planning, while weather conditions like high heat, humidity, and low visibility necessitate adaptive strategies. By integrating these insights into day-to-day operations, organizations can mitigate risks and ensure smoother functioning across weathe

