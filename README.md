# 宝贝回家 (baobeihuijia)
Scraping and visualising missing people in China based on crowdsourced data from www.baobeihuijia.com. The map with searchable function can be found here (https://tunabellybella.github.io/baobeihuijia/).

## Rationale for creating this project

Baobeihuijia is a missing person's directory of lost children. Under this section, "family members looking for baobei (loved one)", it shows listing by family members hoping to reunite with their missing family members. I thought that visualising these missing persons, along with their other information—the missing person's birthday, when they went missing, any unique characteristics of theirs, and missing location—on a map will be a useful too for anyone who is looking for this information.

That's why I scraped the website to collect data of over 50,000 missing persons using BeautifulSoup and geocoded the location to get the latlong in order to map it on Mapbox. All of this information is available in my Jupyter notebook, as attached.

## Limitations of this project
1. The information is not updated live. I scraped the data at 6 August, 5.42pm, so additional listings following that are not included. 

2. I used Google Cloud to geocode the location. As all the information is crowdsourced and written in a naturalised way—for example someone might say the child is missing at a market near a certain road–the geocoded location might not be the most accurate. Moreover the information are all written in simplified Chinese, so Google Maps was not the best option. However I had to work within my means and geographical limitation. I wasn't able to access geocoding services from China as I didn't have a Chinese phone number, and Google Cloud had free credits that'll enable me to geocode for free.

3. When importing my .csv file into Mapbox's tileset, I encountered the error: "Tile size exceeds limit. At least one vector tile is larger than 5MB." To resolve that, I processed the file using tippecanoe's function, which drops the least visible features at each zoom level to make the tileset more lightweight. It worked, and the same number of datapoints remained, but it also went through a black box of code that I don't understand, so I'm not sure if the data has been compromised in any important way.

## Next steps

This personal project is an ongoing one for me. I'm planning to scrape the listings for "missing children looking for their families" in hopes that by plotting both of these categories on a map, it'll help people find their loved ones easier. 
