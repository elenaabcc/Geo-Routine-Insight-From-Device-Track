# GPS Route Mapping with Folium

# WHAT WE WANT TO ACHIEVE

The main goals of this project are:
1) Visualize the Points on a Map using a web-based interactive map. It leverages the `folium` library to display GPS points, draw routes, and indicate movement direction with arrows.
2) Determine which municipalities were crossed by the device using polygon.csv.




![Screen of the Maps](./img_readme/screen_maps_results.png)

## HOW WE GET THERE

### A Basic Map

   ```python
   m = folium.Map(location=[routine_df['lat'].mean(), routine_df['lon'].mean()], zoom_start=12)
   ```
   - **Purpose**: Initializes a `folium` map centered at the average latitude and longitude of the data points.
   - **Method**: Uses the mean of latitude (`lat`) and longitude (`lon`) columns to center the map.

### Municipalities Crossed

By performing a **spatial join**, we identified which municipalities the device's location points fell within. 
We then extracted and listed the unique municipalities that were crossed by the device and saved this information for further analysis.