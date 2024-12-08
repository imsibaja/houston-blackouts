# Prioritizing Potential Aquaculture
## A Functional Analysis of West Coast Economic Zones
Author: Ian Morris-Sibaja

![Image](https://static01.nyt.com/images/2021/02/19/us/19texas-victims-new/merlin_183952452_17e0e49e-df85-4d90-bfac-3468a4ee3513-superJumbo.jpg?quality=75&auto=webp) Storm Damage in Austin, Texas [New York Times](https://www.nytimes.com/2021/02/19/us/texas-deaths-winter-storm.html)

## About
Climate change is driving more frequent and intense extreme weather events with severe consequences. For example, in February 2021, Texas experienced a major power crisis caused by three severe winter storms. In this assignment, I estimate the number of homes in the Houston metropolitan area that lost power during these storms and analyze whether the impacts were disproportionately distributed. This integrated approach leverages remote sensing and spatial analysis to understand the event's implications:

-   Using vector and raster data to analyze environmental impacts on household data.
-   Streamlining geospatial data collection, processing, and visualization.
-   Analyze intersection of environmental effects and income disparities.

## Repository organization
```
 houston-blackouts
|   houston-blackouts.html
|   houston-blackouts.qmd
│   README.md
|   houston-blackouts.Rproj
|   .gitignore 

```

## Data
###Night lights

Satellite data on 2021-02-07 and 2021-02-16 from [NASA’s Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/). Many NASA Earth data products are distributed in 10x10 degree tiles in sinusoidal equal-area projection. Tiles are identified by their horizontal and vertical position in the grid. Houston lies on the border of tiles h08v05 and h08v06. We therefore need to download two tiles per date.

Data files:

- VNP46A1.A2021038.h08v05.001.2021039064328.tif: tile h08v05, collected on 2021-02-07
- VNP46A1.A2021038.h08v06.001.2021039064329.tif: tile h08v06, collected on 2021-02-07
- VNP46A1.A2021047.h08v05.001.2021048091106.tif: tile h08v05, collected on 2021-02-16
- VNP46A1.A2021047.h08v06.001.2021048091105.tif: tile h08v06, collected on 2021-02-16


### Roads
Lights from highways and roads may affect our light rasters. We can pull road data from [Geofabrik](https://download.geofabrik.de/) to download [OpenStreetMap(OSM)](https://planet.openstreetmap.org/).

Data file: 
- gis_osm_roads_free_1.gpkg 

### Houses
Houses data is also from [Geofabrik](https://download.geofabrik.de/) to download [OpenStreetMap(OSM)](https://planet.openstreetmap.org/). 
Data file: 
- gis_osm_buildings_a_free_1.gpkg

### Socioeconomic
We can gather socioeconomic data from [U.S. Census Bureau’s American Community](https://www.census.gov/programs-surveys/acs). The database we download will hold a Texas file specifically that we will use for analysis.

Data file: 
- ACS_2019_5YR_TRACT_48.gdb
- - ACS_2019_5YR_TRACT_48_TEXAS

## References

- Night light data from Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)", "Menzel, W.P., Frey, R.A., and Baum, B.A. (2015). Terra/MODIS Cloud Product 5-Min L2 Swath 1 km and 5 km, C6, NASA Level-1 and Atmosphere Archive & Distribution System (LAADS) Distributed Active Archive Center (DAAC), Goddard Space Flight Center, Greenbelt, MD. [http://dx.doi.org/10.5067/MODIS/MOD06_L2.006], [LAADS DAAC](https://ladsweb.modaps.eosdis.nasa.gov/)
- Open Street Map (OSM) Buildings and Roads data, OpenStreetMap contributors. (2015) Planet dump North America. Retrieved from https://planet.openstreetmap.or, [OSM](https://planet.openstreetmap.org/)
- Socioeconomic data from the American Community Survey, U.S. Census Bureau. (2019). 2019 American Community Survey Public Use Microdata Samples.  Retrieved from https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t, [ACS](https://www.census.gov/programs-surveys/acs/data.html)

Oliver, Ruth. Homework Assignment 2 - EDS 223 - Identifying the impacts of extreme weather (n.d.). https://eds-223-geospatial.github.io/assignments/HW4.html
