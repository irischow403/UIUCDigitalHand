
> About the years covered by the data:
> * All testing data is from 2024
> * soil_data in training_data is 2015-2023
> * All other data in training_data is 2014-2023

## Existing Data formats
* meta_data:
  * **Year**
  * **Env**
  * **Experiment_Code**
  * Treatment
  * City
  * Farm
  * Field
  * Trial_ID (Assigned by collaborator for internal reference)
  * "Soil_Taxonomic_ID and horizon description, if known"
  * "Weather_Station_Serial_Number (Last four digits, e.g. m2700s#####)" [MAYBE]
  * Weather_Station_Latitude (in decimal numbers NOT DMS)
  * Weather_Station_Longitude (in decimal numbers NOT DMS)
  * Date_weather_station_placed
  * Date_weather_station_removed
  * **Previous_Crop**
  * Pre-plant_tillage_method(s) [MAYBE]
  * In-season_tillage_method(s) [MAYBE]
  * Type_of_planter (fluted cone; belt cone; air planter) [MAYBE]
  * System_Determining_Moisture
  * Pounds_Needed_Soil_Moisture
  * Latitude_of_Field_Corner_#1 (lower left)
  * Longitude_of_Field_Corner_#1 (lower left)
  * Latitude_of_Field_Corner_#2 (lower right)
  * Longitude_of_Field_Corner_#2 (lower right)
  * Latitude_of_Field_Corner_#3 (upper right)
  * Longitude_of_Field_Corner_#3 (upper right)
  * Latitude_of_Field_Corner_#4 (upper left)
  * Longitude_of_Field_Corner_#4 (upper left)
  * Cardinal_Heading_Pass_1
  * Irrigated
  * Issue/comment_#1
  * Issue/comment_#2
  * Issue/comment_#3
  * Issue/comment_#4
  * Issue/comment_#5
  * Issue/comment_#6
  * Issue/comment_#7
  * Issue/comment_#8
* Trait Data
  * Env - Code to reference the environmental conditions
  * Year
  * Field_Location - Code to reference location
  * Experiment - 
  * Replicate
  * Block
  * Plot
  * Range
  * Pass
  * Hybrid
  * Hybrid_orig_name
  * Hybrid_Parent1
  * Hybrid_Parent2
  * Plot_Area_ha
  * Date_Planted
  * Date_Harvested
  * Stand_Count_plants
  * Pollen_DAP_days
  * Silk_DAP_days
  * Plant_Height_cm
  * Ear_Height_cm
  * Root_Lodging_plants
  * Stalk_Lodging_plants
  * Yield_Mg_ha
  * Grain_Moisture
  * Twt_kg_m3


## Data Format Goals:
* Input for Envirotyping tool

| Variable | Description |
| --- | --- |
| Site | User Site Identifier |
| Planting | Planting Date (mm/dd/yyyy) |
| Latitude | Lat of trial point |
| Longitude | Lon of trial point |
| Crop | Soybean or Maize |
| Genetics | For soy: maturity group (0-6, by 1), For Maize: RM (80-130, by 5) |

## More Thoughts
* We could try to predict some of the other phenotypic data, but would it even be useful to do so? 
  * It may not improve the yield predictions anyway, since that itself is a Phenotypic variable we are predicting.
  * It is difficult, since we would have to run our own envirotyping tool, and to do so we have to estimate RM
* What data is useful for our model input?
  * From meta_data: 
    * Lat/Lon
    * Previous Crop
  * From trait_data:
    * Env
    * Year
    * Field_Location
    * Yield


* Check what information is available about the hybrids that are expected in the output template
* Try to get correlation matrices between E / G / P
* See about composing a matrix of P arrays for a GxE matrix
* For a GxE matrix, visualize Yield like a heatmap.
