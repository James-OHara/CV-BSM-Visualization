## Connected Vehicle Basic Safety Message (BSM) Visualization

This project is a [Noblis Sponsored Research Project](https://noblis.org/r-d/) that provides an example of how to use anonymized  [Connected Vehicle (CV)](https://www.its.dot.gov/pilots/) Basic Safety Messages (BSM) in aggregate to visualize roadway conditions using Open Data provided by the United States Department of Transportation through the [ITS Public Data Hub](https://www.its.dot.gov/data/).  The video below shows the visualization in Google Earth, with hypothetical vehicle trajectories representing traffic over a defined route every five minutes.

[![Visualization Example](https://james-ohara.github.io/CV-BSM-Visualization/examples/videopreview.png)](https://vimeo.com/270109984)

The project creates hypothetical vehicle trajectories from the real BSMs data for analysis and visualize them in Google Earth to provide a complete holistic view of the traffic conditions in the area. 

## Table of Contents

[I. Background](#background)

[II. Problem](#problem)

[III. Solution](#solution)

[IV. Getting Started](#getting-started)

[V. Jupyter Notebooks](#jupyter-notebooks)

[VI. Conduct Anaylsis](#conduct-anaylsis)

[VII. Release_Notes](#release-notes)

<a name="background"/>

## Background

The goal of this project is to promote the use of CV data by researchers by creating an example of how the data can be used and visualized to support measurements of the transportation system. 

We encourage others to redo and modify this work to meet their own research needs and welcome your feedback and ideas. To reach us please [Open an Issue](https://github.com/James-OHara/CV-BSM-Visualization/issues)

<a name="problem"/>

## Problem

Many high resolution transportation data sources require data to be scrubbed of any identifiable information (location data, vehicle ids, speed, etc..) to protect user privacy before sharing that data with the public for research. This is true for connected vehicle data. 

This data scrubbing can make it difficult for researchers that are working with the data to understand it because they cannot make direct correlations between the various data points. To resolve this issue, new methods need to be explored to analyze the data to still be able to conduct effective research without having identifiable information.

<a name="solution"/>

## Solution

To solve this problems, the Noblis team modified the open source [Connected Vehicle Data-Driven Measures Estimation Travel Time Algorithm](https://itsforge.net/index.php/community/explore-applications#/31/74) to output the intermediate steps of the algorithm (the synthetic vehicle trajectories) rather than the travel time estimates. The algorithm was also modified to work with latitude/longitude points rather than VISSIM XY coordinates.

Using APIs from the [ITS Public Data Hub](https://www.its.dot.gov/data/) and [data.transportation.gov](https://data.transportation.gov) the code streams data from the [Advanced Messaging Concept Development Basic Safety Message](https://data.transportation.gov/Automobiles/Advanced-Messaging-Concept-Development-Basic-Safet/eezi-v4pm) dataset. Noblis worked with approximately 165,000 BSM messages to produce new hypothetical vehicle trajectories based on the actual data. 

With these new trajectories, Noblis was able to visualize traffic conditions including speeds and travel times for the full test period using Google Earth to see how traffic changed throughout the day. To provide a holistic view, Noblis mapped altitude as time increases, so that the viewer can quickly see how traffic dynamics changed over the time period.

Below are a set of interactive [Jupyter](http://jupyter.org) notebooks coded in [Python] (https://www.python.org) that walk through the steps of how to download the time-filtered Basic Safety Messages, aggregate them into hypothetical vehicle trajectories, write the hypothetical vehicle trajectories to KML to be visualized in Google Earth and optionally creating additional network statistics as an overlay. 

<a name="getting-started"/>

## Getting Started

- **Step 1**: Install required applications
    - [Python 3.6.5](https://www.python.org/downloads/)
    - [Google Earth](https://www.google.com/earth/desktop/) *Note Google Earth is only needed if you plan to also do the visualization within Google Earth.*
- **Step 2**: Download This GitHub Repository to your local computer
- **Step 3**: Install Python virtual environment tool. Run the following from the terminal:
```
> pip install pipenv
```
- **Step 4**: Create virtual environment and install required Python libraries. From the folder you downloaded the GitHub repository, run the following:
```
> pipenv install
```

<a name="jupyter-notebooks"/>

## Jupyter Notebooks

#### Step 1 Downloading data and creating trajectories 

- Part 1: [Basic Safety Messages to Synthetic Trajectories](https://james-ohara.github.io/CV-BSM-Visualization/githubpages/Basic%20Safety%20Messages%20to%20Synthetic%20Trajectories.html)  - download and create synthetic trajectories based on BSM data

- Part 2: [Calculating Network Statistics](https://james-ohara.github.io/CV-BSM-Visualization/githubpages/Basic%20Safety%20Messages%20Statistics.html)  - Develop network statistics based on new trajectories

*Note: At this point users can conducted their own analysis or visualization of the data from the newly created trajectories*

#### Step 2 Data visualization and Google Earth integration  

- Part 1: [Creating Visualizations from BSM-generated Synthetic Trajectories](https://james-ohara.github.io/CV-BSM-Visualization/githubpages/Connected%20Vehicles%20Visualizations.html)  - Create KML file of new data to view within Google Earth.

- Part 2: [Creating Charts for Network Statistics Overlay](https://james-ohara.github.io/CV-BSM-Visualization/githubpages/Connected%20Vehicles%20Charts.html) - Create graphics of data over time to use as statistic overlay

<a name="conduct-anaylsis"/>

## Conduct Anaylsis
-  **Step 1**: Start and enter the new virtual environment. From the folder you downloaded the GitHub repository, run the following:
```
> pipenv shell
```
-  **Step 2**: Start up Jupyter Notebook. From the folder you downloaded the GitHub repository, run the following:
```
> jupyter notebook
```
-  **Step 3**: Once Jupyter Notebook opens in your browser move to ‘’notebook’’ folder and begin your work.

-  **Step 4**: Close Environment.  Once you have completed your work, save current notebooks in Jupyter and quit Jupyter. Go back to your original terminal window and run the following to close the environment:
```
> exit
```
-  **Step 5**: (Optional) If you want to remove the environment from your computer (warning this will require you to reinstall all Python libraries on your computer). Run the following command from the from the folder you downloaded the GitHub repository:
```
> pipenv --rm
```

<a name="release-notes"/>

## Release Notes

- May 24, 2018 - Initial Release
