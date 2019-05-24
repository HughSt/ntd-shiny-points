# ntd-shiny-points
his application is designed to help understand whether having village level predictions of hotspots is useful to NTD programs. Given an input of infection/sero prevalence at villages, and locations of all other villages, the app is designed to automatically fit a geospatial model using climatological/environmental variables (currently elevation, distance to water, temperature, precipitation and seasonality) to provide two outputs:

- Location of likely hotspot villages and
- Optimal locations to next visit to collect more data in order to update your hotspot prediction map

To use the app, you need to provide a .csv file of point level data (e.g. villages or schools) containing at least the following columns

id - the ID code of the point (can be character or numeric)
lat - the latitude in decimal degrees
lng - the longitude in decimal degrees
n_trials - the number of people examined/tested 
n_positive - the number of people testing positive

You also need to set 2 parameters. 

**Set hotspot prevalence threshold** This sets the prevalence threshold that defines a hotspot. For example, a location might be considered a hotspot if prevalence of infection is >10%. In which case, set this threshold to 10%. 

**Select number of sites to adaptively select** If you are using this tool to obtain recommendations on the optimal locations to conduct further surveys, this sets the number of sites you wish to receive recommendations for. 

The application will make predictions at each location provided in the .csv file. If you wish to obtain predictions (preicted prevalence, probability of being a hotspot) you can include locations in the .csv file, leaving the n_trials and n_positive columns blank. An example of the expected input file is shown below.

![](https://www.dropbox.com/s/f6gmxcwrxpxmdii/demo_data.png?dl=1)

Once you hit 'Get predictions', the application will find the necessary climatological/environmental layers, fit a model and make predictions. These are then shown on the map and tables below. 

The map 




