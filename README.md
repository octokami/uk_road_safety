# UK Road Safety Data Visualization project

Data sources: https://drive.google.com/drive/u/1/folders/1eJqYNzwgtQiLZiiTwfg8hfdU5oAHBk4v
This app allows an interactive analysis on the [UK Road Safety Data](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data) from 01/01/2016 to 31/12/2020.
    
On the [Road Casualties Map](/map), first there is an overview of the full UK following the rule of thumb "Overview First, Zoom and Filter, Detail on Demand". 
Another reason for this is because plotting all the precise locations of casualties made the map very cluttered, losing a clear view of the bigger picture. 
This also greatly impacted the responsiveness of the visualisation, since less dots needed to be plotted. As an intteractive tool, it is possible to:    
* **Choose Map aggregation:**
    * District: Overview of in which districts the most road casualties happen in the UK
    * Precise: Pinpoint the exact roads where most accidents happen in the chosen district
* **Filter:**
    * Accident severity level between Slight, Serious and Fatal according to the [Severity adjustment figure guidance 2020](https://data.dft.gov.uk/road-accidents-safety-data/severity-adjustment-figure-guidance-2020.docx)
    * Filter between EV and non-EV vehicles
        * EV vehicles are the ones with propulsion code in 'Electric', 'Hybrid electric', 'Electric diesel', 'New fuel technology'
    * If no option is selected, the filter is the same as selecting all categories.

On the right side, there is an accompanying attribute chart of the total number of casualties that is synched with the above mentioned filters. 
It is heavily based on the concepts by [Munzner, 2014](https://www.cs.ubc.ca/~tmm/vadbook/) for what idiom should be used according to the attribute type:
* Quantitative attributes ('accident_year', 'age_of_driver', 'age_of_vehicle', 'age_of_casualty', 'number_of_vehicles', 'number_of_casualties', 'speed_limit')
    * Idiom chosen: *line charts*
    * length is one of the most effective magnitude channels for quantitative values. The marks used for this are lines, because they make it easier to find trends, for example.
    * The x-axis is the value of the attribute
* Ordered attributes ('day_of_week',  'year-month',  'time' (rounded to the hour), 'age_band_of_driver', 'age_band_of_casualty')
    * In a similar manner as the quantitative attributes, the x-axis presents the attribute in the correct order, with it's respective name.
* Categorical attributes
    * Most attributes on the dataset are categorical. These can be subdivided for easier understading as:
        * The driver and their vehicle: 'sex_of_driver', 'vehicle_type', 'propulsion_code', 'ev', 'vehicle_manoeuvre', 'car_passenger', 'accident_severity'
        * The casualty: 'casualty_severity', 'casualty_class', 'casualty_type', 'sex_of_casualty', 'casualty_home_area_type'
        * The road: 'road_type', 'first_road_class', 'second_road_class', 'junction_location', 'junction_control', 'junction_detail', 'urban_or_rural_area', 'did_police_officer_attend_scene_of_accident'
    * About the idiom
        * Idiom chosen: *Horizontal bar charts*
        * Bars are used instead of lines because of the expressiveness principle.
        * Horizontal  bars for legibility of the categories
    * Ordered by quantity for easier comparison between categories as well as easier look up at the highest category
    * Since all attributes sum up to the total amount of casualties, in case there are less than five categories, the idiom chosen is a *pie chart* for faster Part-to-whole judgement. In this case the marks used are Separate colored areas with the channels: Color for categorical attribute; Angle for quantitative attribute
* Some attributes have an extensive amount of unknown or missing information. 
For full data transparency, it is possible to choose between 'All data' or 'Exclude' the data that is declared as 'Unknown', 'Undefined', 'Data missing or out of range'

More information about these attributes can be found at [Road Safety Open Dataset Data Guide](https://data.dft.gov.uk/road-accidents-safety-data/Road-Safety-Open-Dataset-Data-Guide.xlsx)

Authors: Camila Matoba and Sietske Wijffels
    
License of the data: [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
