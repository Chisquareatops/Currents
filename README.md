# Sea Currents Visualization
### a time-dependent view of speed and direction of tidal currents in the Salish Sea

## Summary
This visualization uses collected data and predicted future data for ten current stations located in the Salish sea. Station locations are displayed on a zoom-and-pan ready nautical map, allowing users to select the locations for which they would like to see tidal information. Users can also easily control the time frame of data to be displayed. Tooltips contain additional information about a specific data point and its station.

## User Research
User research was extensive. Numerous features were included based on UI testing and user requests:
- Date ranges can be set using sliders, calendar selection, or by typing specific dates
- Users can view data for multiple stations simultaneously
- Each station has an individual page utilizing a dynamic query, so users may view current data for unique times on each page
- Water flow direction is depicted visually using arrows
- Water flow speed is depicted visually using the size of the arrows

## Other Considerations
Natively, Tableau is only able to display a simple linear connection between ebb, slack, and flow data points, which is a poor representation of changing current speed. Using the TabPy API to execute Python dynamically within Tableau, more accurate curves could be modeled using a Piecewise Cubic Hermite Interpolating Polynomial (PCHIP) interpolation via SciPy functions. 

Unfortunately, TabPy is an external service implementation which requires a connection to the TabPy server (which is not supported in Tableau Online). For this reason, the packaged notebook in this folder does not feature curves modeled using PCHIP. However screenshots featuring the curved lines have been included.

## Data
Data for ten current stations for 2018 and 2019 from NOAA.gov
Current station information including name, latitude, and longitude from NOAA.gov

13.4 mb of data, 55,950 rows
447,600 data points used for final notebook

Data has been cleaned since download.

## Repository Structure

- Currents_12_10_Packaged.twbx
- data
	- PUG1501_6_Annual_2018.csv
	- PUG1501_6_Annual_2019.csv
	- PUG1513_10_Annual_2019.csv
	- station_data_2019.csv
	- station_data_2019_2.csv
- images
	- current_speed_smoothed_curve.png
	- current_speed_wtooltip_smoothed_curve.png
	- map_and_current.png
	- map_overview.png
	- single_station_view.png
	- station_picker.png
	- station_picker_smoothed_curve.png

## Image Descriptions

- current_speed_smoothed_curve.png
Snapshot of current data being displayed for two stations over a two day time frame, featuring smoothed curves

- current_speed_wtooltip_smoothed_curve.png
Snapshot of current data for one station being displayed while mouseover tooltip is displayed, featuring smoothed curves

- map_and_current.png
Snapshot of map view using arrows to display station location and current direction and speed, while unsmoothed lines display ebb, slack, and flow data points for six selected stations over a three day time frame overlayed on one scale. This page uses color to encode station identity.

- map_overview.png
Snapshot of the map overview using arrows to display station location and current direction and speed for five selected stations.

- single_station_view.png
Snapshot of the station overview page, displaying ebb, slack, and flow data points using unsmoothed lines for one station, during a 47 day time frame, while mouseover tooltip is displayed.

- station_picker.png
Snapshot of ebb, slack, and flow data points for six selected stations being displayed for comparison using unsmoothed lines on separate but aligned scales, while mouseover tooltip is displayed.

- station_picker_smoothed_curve.png
Snapshot of the same data ebb, slack, and flow data points for six selected stations being displayed for comparison using smoothed curves on separate but aligned scales.
