# Rainbow Colormap Haters - CS732 - A2
- Images in the `/images` folder correspond to the figure numbers in the report.
- GIFs in the `/gifs` folder correspond to the generated GIF files.

- Note that the `Files` subheading indicates only the important files in the repository.

# Scientific Visualization

## Color Mapping
### Files
| File Path | Description |
| -- | -- |
| /ScientificVisualizations/ColorMapping/data/\*.nc | Dataset in the netCDF4 format for a particular date in 2013, sourced from the AMSR2 dataset |
| /ScientificVisualizations/ColorMapping/images/{strategy}/\*.png | Single plot image for each date using {strategy = 'discrete', 'continuous', 'log'}, corresponding to /ScientificVisualizations/ColorMapping/data/\*.nc |
| /ScientificVisualizations/ColorMapping/Notebook.ipynb | Source code used to process and visualize scalar field data |

### Dataset
We use the AMSR2 Ocean Dataset to visualize surface rain rate. The dataset consists of the daily data, sampled in a 3-day wise methodology for a period of 10 years. We choose a contiguous period of three months starting from May, 2013 till July, 2013. Ten dates are sampled from this period, each being 8 to 10 days apart from others. The team decided on this period, as it covers a significant portion of monsoon for the Indian subcontinent. The choice of year was made arbitrarily.
### Data Processing
The data for specific dates was downloaded in the netCDF format, and was processed using the netCDF4 library in python. The surface rain rate variable was extracted, giving us the scalar values corresponding to 1440 longitudes and 720 latitudes. Furthermore, the bad values (indicated by -999) were replaced with NAN using the numpy library.
### Requirements
- Python 3.10 +
- Installing the dependencies.

```sh
pip install netCDF
pip install numpy
pip install pandas
pip install matplotlib
```


- If you wish to run a live server and view the results on an HTML page, you can do so in an easy way by installing the following vsCode extension.


Name: Live Server
Id: ritwickdey.LiveServer
Description: Launch a development local Server with live reload feature for static & dynamic pages
Version: 5.7.9
Publisher: Ritwick Dey
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

### Implementation
To transform and visualize the data, we employed the pyplot API layer in in Matplotlib. Our implementation includes experimentation with different color palettes and color scales. Through multiple visualizations and  experimentation, we propose that for our particular usecase, a discrete color map based on Viridis color palette is appropriate.
### Running The Live Server
- **Install Visual Studio Code:** If you haven't already, download and install Visual Studio Code from the official website: [Visual Studio Code](https://code.visualstudio.com/).
- **Open Visual Studio Code:** Launch VS Code by clicking on its icon.
- **Install Live Server Extension:** Go to the Extensions view by clicking on the square icon on the left sidebar or by pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac). Search for "Live Server" in the Extensions Marketplace, select it, and click "Install".
- **Open a Project Folder:** Open the folder containing your HTML, CSS, or JavaScript files by selecting `File > Open Folder...` in the menu.
- **Start the Live Server:** Once you have your HTML file open in the editor, right-click anywhere within the HTML file or use the shortcut `Alt+L Alt+O` (Windows/Linux) or `Option+L Option+O` (Mac). From the context menu, choose "Open with Live Server".
- **Access the Live Server:** This action will automatically launch a web browser window displaying your HTML file using a local server. Any changes you make to the HTML, CSS, or JavaScript files will be instantly reflected in the browser without needing to manually refresh the page.
- **Stop the Live Server:** To stop the live server, you can either close the browser tab or right-click on the HTML file again and select "Stop Live Server".
- **Settings and Configuration:** You can configure certain settings for Live Server by going to `File > Preferences > Settings` or using the shortcut `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac). Search for "Live Server" in the settings search bar to find and adjust settings like port number, default browser, etc.
---

## Quiver Plotting
### Files
| File Path                             | Description                                                             |
| ------------------------------------- | ----------------------------------------------------------------------- |
| /ScientificVisualizations/QuiverPloting/data/*                   | Data files used in the experiments, in raw ASCII and .tsv formats       |
| /ScientificVisualizations/QuiverPloting/plots/{strategy}/\*.jpg | Single plot image for each date using {strategy = 'quiver', 'quiver_c'} |
| /ScientificVisualizations/QuiverPloting/quiver-plot.ipynb             | Source code used to process and visualize vector field data   |
| /ScientificVisualizations/QuiverPlotting/plots/{strategy}/\*.gif | Single plot image for each date using {strategy = 'quiver', 'quiver_c'} |

### Dataset
We picked 10 days between December 2011 - January 2012 uniformly from the [OSCAT wind dataset](https://las.incois.gov.in/). We picked this date so that we can visualize the cyclone [Thane](https://en.wikipedia.org/wiki/Cyclone_Thane) in the Bay of Bengal which hit South India between December 25 and December 31, 2011.
### Data Processing
After downloading the data for specific dates, we split the zonal and meridional data into different tsv files for easy processing. We import this data as a numpy array, convert to the right data types, check for null values, replace bad value flags and create a mesh grid corresponding to the latitudes and longitudes given.
### Requirements
- Python 3.10 +
- Installing the dependencies.
```sh
pip install numpy
pip install matplotlib
pip install basemap 
```


### Implementation
To transform and visualize the data, we employed the Basemap library in Matplotlib. Our implementation includes two variations: one with vector lengths varying based on magnitude and another where vector lengths are uniform, and magnitude is represented using color as a channel.

## Contour Mapping
### Files
| File Path | Description |
| -- | -- |
| /ScientificVisualizations/ContourMapping/water_vapor_data/\*.nc | Dataset in the netCDF4 format for May 2013, June 2013 and July 2013, sourced from the AMSR2 dataset |
| /ScientificVisualizations/ContourMapping/generated_images/water_vapor_*/\*.png | Single plot image for each date but different methods (Contour Fill in 'water_vapor' and 'water_vapor_fill_viridis', Marching squares in others)  |
| /ScientificVisualizations/ContourMapping/make.ipynb | Source code used to process and visualize scalar field data |
| /ScientificVisualizations/ContourMapping/generated_gifs/*gifs | Generated gifs for different methods (Contour Fill in 'water_vapor', Marching Squares in others) |

### Dataset
We use the AMSR2 Ocean Dataset to visualize water vapor. The dataset consists of the daily data, sampled in a 3-day wise methodology for a period of 10 years. We choose a contiguous period of three months starting from May, 2013 till July, 2013. Three dates are sampled from this period, each being a month apart from others. The team decided on this period, as it covers a significant portion of monsoon for the Indian subcontinent. The choice of year was made arbitrarily.
### Data Processing
The data for specific dates was downloaded in the netCDF format, and was processed using the netCDF4 library in python. The water vapor variable was extracted, giving us the scalar values corresponding to 1440 longitudes and 720 latitudes.
### Requirements
- Python 3.10 +
- Installing the dependencies.

```sh
pip install netCDF
pip install numpy
pip install pandas
pip install matplotlib
pip install xarray
pip install cartopy
pip install imageio
```

# Information Visualization

## Node-Link Diagrams

### Files
| File Path                                         | Description                                               |
| ------------------------------------------------- | --------------------------------------------------------- |
| /InformationVisualizations/NodeLink/data/*        | The "David Copperfield" dataset downloaded from konect.cc |
| /InformationVisualizations/NodeLink/images/\*.png | Screenshots of diagrams generated in gephi                |
| /InformationVisualizations/NodeLink/categorize-words.py  | Python program used to categorize the words between nouns and adjectives                                                          |
### Dataset
We visualized the "David Copperfield" network from konect.cc. The network consisted of common noun and adjective adjacencies present in the novel "David Copperfield" by Charles Dickens. Each node of the graph corresponds to a word (a noun or adjective) and an edge between two nodes represents the two words occur together. The graph is unweighted and undirected. There are 112 nodes and 425 edges connecting them. Of the 112 words, 59 are nouns and 53 are adjectives.

### Requirements

Gephi can be downloaded and installed from their official [website](https://gephi.org/).
### Implementation
We used gephi for visualizing the graphs using different layouts. We used a Part-Of-Speech tagger from the NLTK library in python to tag each word as either a noun or adjective to improve our analysis (please refer categorize_words.py).

## Parallel Coordinates Plot

### Files
| File Path                                         | Description                                               |
| ------------------------------------------------- | --------------------------------------------------------- |
| /InformationVisualizations/ParallelCoordinatesPlot/*.csv        | Processed data from the SHCC dataset |
| /InformationVisualizations/ParallelCoordinatesPlot/index.html  | Finished results on an HTML page |
| /InformationVisualizations/ParallelCoordinatesPlot/index1.html  | Experiments to improve the PCP implementation                                                          |
| /InformationVisualizations/ParallelCoordinatesPlot/app.js  | JavaScript source code for parallel coordinates plot                                                          |
| /InformationVisualizations/ParallelCoordinatesPlot/processing.ipynb  | Notebook for data processing using Python                                                          |

### Dataset
The dataset used is ”Attacks on Health Care in Countries in Conflict (SHCC) Data”. It provides various statistics pertaining to attacks on healthcare-related infrastructure across the world.

### Data Processing
The data was first cleaned and processed using Pandas by Sai Madhavan G for CS732 - A1. The resultant file had aggregated values for the number of incidents and the number of heath workers killed, kidnapped, injured, and arrested. Each data row in this file can be uniquely identified using (year, country) as the primary key. In other words, the data is aggregated in a country-wise manner, for all years (2017 - 2022). When sparse data is further excluded from the chosen subset of data using Tableau Prep, we are left with data for the years {2017, 2019, 2020, 2021, 2022}. 

**Finally, we group the data using two strategies:** 
- Country-wise grouping with aggregation across years.
- Year-wise grouping with aggregation across countries.  

These two sets of data are used to visualize interactive  
Parallel Coordinates Plots which support user interactions 
such as brushing (filtering) and axes-reordering.
### Requirements
#### For Data Processing
- Python 3.10 +
- Installing the dependencies.
sh
pip install numpy
pip install pandas

#### For D3.js and Plotly.js (PCP)
- All dependencies related to D3.js and Plotly.js, as well as Bootstrap, should work without any additional setup. These libraries are included using their CDNs as script tags in the HTML page. 

- If you wish to run a live server and view the results on an HTML page, you can do so in an easy way by installing the following vsCode extension.


Name: Live Server
Id: ritwickdey.LiveServer
Description: Launch a development local Server with live reload feature for static & dynamic pages
Version: 5.7.9
Publisher: Ritwick Dey
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

### Implementation
The project's codebase is predominantly in JavaScript but incorporates Python for some data processing tasks. The results are presented on an HTML page accessible via a VSCode live server. The visualization utilizes D3.js to read CSV data, then utilizes Plotly.js Parcoords API to generate a Parallel Coordinates Plot (PCP). This occurs twice: first, grouping data by year with aggregation across countries, and second, by country with aggregation across years. The API allows customization of color scales, utilizing the Jet colormap, where each data index (year or country) corresponds to a distinct color. A new column, colorVal, was introduced during preprocessing to map these colors linearly. These colors serve to differentiate data indices, though they don't represent quantitative values. For categorical data like countries, numerical country codes are assigned. Additionally, the API enables adding annotations and labels to the final plot using the layout parameter.
### Running The Live Server
- **Install Visual Studio Code:** If you haven't already, download and install Visual Studio Code from the official website: [Visual Studio Code](https://code.visualstudio.com/).
- **Open Visual Studio Code:** Launch VS Code by clicking on its icon.
- **Install Live Server Extension:** Go to the Extensions view by clicking on the square icon on the left sidebar or by pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac). Search for "Live Server" in the Extensions Marketplace, select it, and click "Install".
- **Open a Project Folder:** Open the folder containing your HTML, CSS, or JavaScript files by selecting `File > Open Folder...` in the menu.
- **Start the Live Server:** Once you have your HTML file open in the editor, right-click anywhere within the HTML file or use the shortcut `Alt+L Alt+O` (Windows/Linux) or `Option+L Option+O` (Mac). From the context menu, choose "Open with Live Server". Alter
- **Access the Live Server:** This action will automatically launch a web browser window displaying your HTML file using a local server. Any changes you make to the HTML, CSS, or JavaScript files will be instantly reflected in the browser without needing to manually refresh the page.
- **Stop the Live Server:** To stop the live server, you can either close the browser tab or right-click on the HTML file again and select "Stop Live Server".
- **Settings and Configuration:** You can configure certain settings for Live Server by going to `File > Preferences > Settings` or using the shortcut `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac). Search for "Live Server" in the settings search bar to find and adjust settings like port number, default browser, etc.


## TreeMap

### Files
| File Path                                         | Description                                               |
| ------------------------------------------------- | --------------------------------------------------------- |
| /InformationVisualizations/Treemap/test_data/*.csv        | Processed data from the SHCC dataset |
| /InformationVisualizations/Treemap/trial.html  | Finished results on an HTML page |                                   |
| /InformationVisualizations/Treemap/val.js  | JavaScript source code for Treemap                                                          |
| /InformationVisualizations/Treemap/val.css  | Stylesheet for trial.html                                                          |
| /InformationVisualizations/Treemap/images | Image snips used for the report. |

### Dataset
The dataset used is ”Attacks on Health Care in Countries in Conflict (SHCC) Data”. It provides various statistics pertaining to attacks on healthcare-related infrastructure across the world.

### Data Processing
The data was cleaned and preprocessed. Initially, the incidents data for the year 2022 was available with individual dates and country information, which was then aggregated. Additionally, for a specific plot, a subset(columns) of the original 2022 incidents data was extracted, and subsequent plots were generated based on this subset. 

### Requirements

#### For AnyChart.js and FusionCharts.js (PCP)
- All dependencies related to AnyChart.js and FusionCharts.js, should work without any additional setup. These libraries are included using their CDNs as script tags in the HTML page. 

- If you wish to run a live server and view the results on an HTML page, you can do so in an easy way by installing the following vsCode extension.


Name: Live Server
Id: ritwickdey.LiveServer
Description: Launch a development local Server with live reload feature for static & dynamic pages
Version: 5.7.9
Publisher: Ritwick Dey
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

### Implementation
The treemap implementation is carried out in HTML using the AnyChart and FusionChart libraries. Initially, the data is extracted from a CSV file, and the user is prompted to input column values for treemap creation. The extracted data is then transformed into a hierarchical JSON format to visually represent the data hierarchy. Due to the limited inherent hierarchy in the data, only a few plots with hierarchical data were generated. Both AnyChart and FusionChart libraries were employed to account for missing features in each other. Additionally, various algorithms were tested using the FusionChart library.

### Running The Live Server
- **Install Visual Studio Code:** If you haven't already, download and install Visual Studio Code from the official website: [Visual Studio Code](https://code.visualstudio.com/).
- **Open Visual Studio Code:** Launch VS Code by clicking on its icon.
- **Install Live Server Extension:** Go to the Extensions view by clicking on the square icon on the left sidebar or by pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (Mac). Search for "Live Server" in the Extensions Marketplace, select it, and click "Install".
- **Open a Project Folder:** Open the folder containing your HTML, CSS, or JavaScript files by selecting `File > Open Folder...` in the menu.
- **Start the Live Server:** Once you have your HTML file open in the editor, right-click anywhere within the HTML file or use the shortcut `Alt+L Alt+O` (Windows/Linux) or `Option+L Option+O` (Mac). From the context menu, choose "Open with Live Server". Alter
- **Access the Live Server:** This action will automatically launch a web browser window displaying your HTML file using a local server. Any changes you make to the HTML, CSS, or JavaScript files will be instantly reflected in the browser without needing to manually refresh the page.
- **Stop the Live Server:** To stop the live server, you can either close the browser tab or right-click on the HTML file again and select "Stop Live Server".
- **Settings and Configuration:** You can configure certain settings for Live Server by going to `File > Preferences > Settings` or using the shortcut `Ctrl+,` (Windows/Linux) or `Cmd+,` (Mac). Search for "Live Server" in the settings search bar to find and adjust settings like port number, default browser, etc.