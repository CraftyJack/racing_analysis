# racing_analysis
The goal of this project is to do some analysis on running races. This is a personal interest as a runner, and also an interesting project for trying some new things.

Note that there are some additional Tableau Public visualizations for the 2019 NYC 60K over [here.](https://public.tableau.com/profile/jack.craft#!/vizhome/2019NYC60K/Story1 "2019 NUC 60K in Tableau")

## Questions
1. Where did all the runners come from? Can we map it? (Yes, see below.)
2. Where did the runners close to me (or any particular individual) come from? Can we map it?

## Data Acquisition
Race results are publicly available, and the level of detail varies from race to race. This repository includes a Selenium-based scraper for getting race data. Because the available data can vary from race to race, the scraper is designed to be flexible in what data it looks for. It works by requesting results for a specific race by bib number, which presumes that we already know a range of bib numbers for the finishers. The races range from a few hundred finishers, to more than 55,000 finishers.

## Geocoding
I used geopy with nominatim (because it's free). One helpful lesson here: Nominatim does a much better job with international addresses if the country name is spelled out rather than abbreviated, e.g. 'Italy' is better than 'ITA'.  

The addresses as scraped are not validated, and there's plenty of opportunities for cleaning there. Issues include non-standard country codes, incorrect countries, and simple misspellings.

## Clustermap
Here's a screenshot of a clustermap for the 2019 NYC Marathon, generated using folium. (Check out the one runner from Nuussuaq, Greenland!)
![Clustermap](https://github.com/CraftyJack/racing_analysis/blob/main/2019_NYCM_finishers_clustermap.png?raw=true)

