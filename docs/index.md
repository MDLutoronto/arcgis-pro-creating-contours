---
title: "Creating contours using ArcGIS Pro"
layout: "home"
description: "Digital elevation models (DEMs) are geospatial datasets that contain elevation values sampled according to a regularly spaced rectangular grid. They can be used in terrain analysis, SD visualizations and hydrological modelling, among other applications. DEMs can be stored in several different formats; however, conversion into a raster dataset is often required for many processes. This tutorial explains how to derive contours from DEMs using ArcGIS Pro."
staff:
    - name: Nick Field
      link: https://library.utoronto.ca/staff/nick-field
created_date: 2024-01-17
permalink: "/"  #! Remove this if not the homepage
---

# Creating contours using ArcGIS Pro

Digital elevation models (DEMs) are geospatial datasets that contain elevation values sampled according to a regularly spaced rectangular grid. They can be used in terrain analysis, SD visualizations and hydrological modelling, among other applications. DEMs can be stored in several different formats; however, conversion into a raster dataset is often required for many processes. This tutorial explains how to derive contours from DEMs using ArcGIS Pro.

To download a DEM file from [GeoGratis](https://ftp.maps.canada.ca/pub/nrcan_rncan/vector/index/html/geospatial_product_index_en.html) as was done in this tutorial, follow the instructions in this [guide](https://mdl.library.utoronto.ca/technology/tutorials/downloading-data-geogratis) but select the Elevation tab instead of Raster.  
  
You may also find these related guides helpful as you work with DEM files:

**Working with digital elevation models in ArcGIS:** [https://mdl.library.utoronto.ca/technology/tutorials/working-digital-elevation-models-arcgis](https://mdl.library.utoronto.ca/technology/tutorials/working-digital-elevation-models-arcgis) 

**Selecting the right projection:** 
[https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection](https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection) 

**Projecting your data:** 
[https://mdl.library.utoronto.ca/technology/tutorials/projecting-your-data-arcgis-pro](https://mdl.library.utoronto.ca/technology/tutorials/projecting-your-data-arcgis-pro)

 

#### **Creating contours using ArcGIS Pro**

1. Open your DEM file. You can do this by clicking the **Add Data** button and selecting the ".tif" file you downloaded from GeoGratis. The DEM file is in black and white laid over a route map of Alberta with topographic information on it.

    <img src='{{ '/assets/images/DEM-overlay_0.JPG' | relative_url }}' alt='Overlay of DEM image over base map and Add Data button highlighted on menu bar' title='' width='2118' height='1367' />
2. Raster files, such as DEMs, are not projected when added to ArcGIS Pro, so you will need to set the projection before generating contours. Right click on **Layers** and select **Properties** from the drop down menu. From the menu on the left, select **Coordinate Systems**, under **Projected Coordinate Systems**, find and expand **UTM**. Under NAD 1983, select **NAD 1983 UTM Zone 12N.** 
(Most DEMs will have metadata that tells you which coordinate system to use. The Geogratis website outputs in NAD 1983 and Calgary is in zone 12N; therefore, this DEM is projected in NAD 2983 UTM Zone 12N)
3. In order to create contours, you will need to enable the Spatial Analyst toolbar, which can be found by going on to the **Geoprocessing Menu** on the right and searching for **"contour"** in the Search bar. Select **Contour (Spatial Analyst Tools)** 
  
    <img src='{{ '/assets/images/contour-tool_1.JPG' | relative_url }}' alt='Contour Spatial Analyst Tool highlighted in tool box' title='' width='2553' height='1370' />

4. After choosing Contour, a window will appear, prompting you for some settings:  
**Input raster:** Select the DEM file from which you want to generate contours by locating it on the dropdown menu.  
**Output feature class:** indicate where you want to save your output contours.  
**Contour Interval:** set the distance between contour lines in metres - the smaller the number, the greater the number of lines  
**Base Contour (optional):** the starting point from which the lines are generated - for example, the default is 0 so with an interval of 25 metres, the contours are generated at 25, 50, 70, 100..., but if the base contour is set at 40, then the contours are generated at 65, 90, 115, 140 and so on  
**Z factor (optional):** can be used to adjust the units of data; for example, if you have data in metres and you want to produce your contours in feet, use a z-factor of 3.28 because 3.28 feet equals one metre  
  
    <img src='{{ '/assets/images/parameters.JPG' | relative_url }}' alt='Spatial Analyst tool with parameters: Contour interval of 25, Base Contour of 0 and Z factor of 1' title='' width='319' height='427' />
5. After adjusting the parameters to your needs, press **Run**. The generated contours will be automatically added to the map.  
  
<img src='{{ '/assets/images/contour%20result.JPG' | relative_url }}' alt='contour lines over base map' title='' width='1332' height='812' />  
  
  
**Troubleshooting Tips:** 
Try experimenting with different contour intervals to find the one that works best for your needs. Always be sure to include the contour interval in filenames and any description of the image or polylines. The choice of contour interval is one that is informed by 1) how you will use contours, 2) changes in elevation within the extent of the DEM, 3) input resolution of the DEM, and 4) storage capacity on your computer.

Tools: [ArcGIS Pro](https://mdl.library.utoronto.ca/taxonomy/term/70) | Data Format: [DEM](https://mdl.library.utoronto.ca/data-format-tutorials/dem), [Raster](https://mdl.library.utoronto.ca/data-format/raster)
