## Connected Vehicle Basic Safety Message Visualization

This project is an example of how to use anonymized Basic Safety Messages in aggregate to visualize roadway conditions using Open Data provided by the United States Department of Transportation through the ITS Public Data Hub. The data used for this project was the Advanced Concept Message Development Basic Safety Messages available on [data.transportation.gov](https://data.transportation.gov/Automobiles/Advanced-Messaging-Concept-Development-Basic-Safet/eezi-v4pm). The video below shows the visualization in Google Earth, with hypothetical vehicle trajectories representing traffic over a defined route every five minutes. Routes increase in altitude as time increases, so that the viewer can quickly see how traffic dynamics changed over an entire rush hour. 

The interactive Jupyter notebooks below walk through the steps of how to download the time-filtered Basic Safety Messages through the Socrata API, aggregate them into hypothetical vehicle trajectories, write the hypothetical vehicle trajectories to KML to be visualized in Google Earth and optionally creating additional network statistics as an overlay. 

### Jupyter Notebooks

1. [Basic Safety Messages to Synthetic Trajectories](https://usdot-its-jpo-data-portal.github.io/CV-BSM-Visualization/githubpages/Basic%20Safety%20Messages%20to%20Synthetic%20Trajectories.html)  
1a. [Calculating Network Statistics](https://usdot-its-jpo-data-portal.github.io/CV-BSM-Visualization/githubpages/Basic%20Safety%20Messages%20Statistics.html)  
2. [Creating Visualizations from BSM-generated Synthetic Trajectories](https://usdot-its-jpo-data-portal.github.io/CV-BSM-Visualization/githubpages/Connected%20Vehicles%20Visualizations.html)  
2a. [Creating Charts for Network Statistics Overlay](https://usdot-its-jpo-data-portal.github.io/CV-BSM-Visualization/githubpages/Connected%20Vehicles%20Charts.html)  
