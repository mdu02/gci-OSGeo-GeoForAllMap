# gci-OSGeo-GeoForAllMap
Some code to parse Geo for All locations and display [a map](https://mdu02.github.io/gci-OSGeo-GeoForAllMap/)

# What I did

Python: I used requests to download the data from [the OSGeo wiki](https://wiki.osgeo.org/wiki/Edu_current_initiatives#Current_members_of_the_Geo_for_All_Labs_Network), BeautifulSoup to parse the HTML tags, and pandas to store and wrangle the data. I exported the completed file to CSV, and went through the CSV to fix a few problems. One site was crossed out in the wiki, but had its markup stripped during processing; I removed that row. One or two other sites had extra characters in their coords, which I manually removed. One site had multiple commas in its posted coords, which may have been regex'd out.

I used a [tool online](http://www.convertcsv.com/csv-to-geojson.htm) to convert the data to the required geoJSON used by leaflet, then removed the wrapping around the array of geographical features within. This stripped file is available in the repo.

HTML: I wrote a very basic HTML webpage, with just one div and no CSS. It uses the leaflet and jQuery libraries for its dynamic content.

JS: Used jQuery to GET the .json file from the repo. Used the coordinates and organization name attributes in the .json file to create the map, with the Leaflet library.
