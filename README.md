# Christina Lake
This repository contains data, R scripts and associated outputs, and other materials necessary for the Applied Conservation and Macro Ecology (ACME) laboratory's research program in the Christina Lake research area.
<hr>

### GENERAL INFORMATION

**Project Information**   
The Christina Lake research area is a region of boreal forest northeast of Lac La Biche, Alberta Canada, and part of the Canadian Oil Sands. Our research began here in 2011 and ran for three years using remote trail cameras. Several years later, the Alberta government institued a lethal wolf removal program, offering a unique before and after comparison of mammal ecology following the removal of an apex predator from the ecosystem. Cameras were redeployed in 2017 as close as possible to the original sites, again running for three years. Further details for the Christina Lake research program provided [here](http://www.acmelab.ca/christinalake.html), but also see our published papers from this camera area in the relevant literature folder. 

Also visit the [ACME website](http://www.acmelab.ca) more information about the ACME lab and other related projects

**Author Information (data):**  
 Principal Investigator Contact Information  
 Name: Jason T. Fisher, PhD   
 Institution: University of Victoria  
 Address: 3800 Finnerty Rd, Victoria, BC V8P 5C2  
 Email: [fisherj@uvic.ca](mailto:fisherj@uvic.ca) 

**Author Information (code):**  
 Data Analysis Contact Information  
 Name: Andrew Barnas, PhD   
 Institution: University of Victoria  
 Address: 3800 Finnerty Rd, Victoria, BC V8P 5C2  
 Email: [andrew.f.barnas@gmail.com](mailto:andrew.f.barnas@gmail.com) 

### DATA & FILE OVERVIEW
**inputs**

This folder contains both summarized and raw data data products (e.g. raw camera trap data csv files) used to produce key products in the outputs folder. 
*Files in main folder*
1) Boreal Deer Camera Station Check Data WITH LOSSES - 2015.csv : this is a messy file which contains the camera locations in the "pre" wolf control period. There is much information here on camera checks and other data, but all that is needed from this file is the camera locations. 
2) christina_camera_locations.csv : camera locations from the "post" wolf control period
3) Christina_covariates_prepost_250-5000_KBaillieDavid : Site covariates extracted at multiple spatial scales (250 - 2000m) for camera sites in the pre and post period. Covariates provided as percentage area within the circular buffer around each site. Further details on data below. 
4) CLcameradata_Jan2019-Oct2019.csv : binded timelapse files featuring detections of wildlife from cameras from January 2019 to October 2019 (raw individual timelapse files
5) CLcameradata_Oct2011-Oct2014.csv : binded timelapse files featuring detections of wildlife from cameras from October 2011 to October 2014
6) CLcameradata_Oct2017-Jan2019.csv : binded timelapse files featuring detections of wildlife from cameras from October 2017 to January 2019
7) CLcameradata_Oct2019-Oct2020.csv : binded timelapse files featuring detections of wildlife from cameras from October 2019 to October 2020

**outputs**

This folder contains the four key data products needed to move forward with additional analyses; 1) the raw detections recorded from cameras, 2) a summary of independent detections of wildlife species at each camera site to the standard 30 minute threshold, 3) the GPS locations of individual camera sites, and 4) covariates associated with each camera site extracted across multiple radius buffers (details below)

**relevant literature**  
This folder provides pdf copies of previously published papers using the Christina Lake remote camera dataset. The purpose of this folder is to provide background/information on previously published work using this dataset. Note that sample numbers may vary between individual manuscripts due to specifics of individual projects, as well as the multiple deployment designs within the Willmore dataset.
 * Baillie-David 2022 UVIC MSc Thesis - Examining shifts in boreal carnivore species' resource selection in response to predator control to conserve woodland caribou in western Canada
 * Barnas et al. 2024 How landscape traits affect boreal mammal responses to anthropogenic disturbance.
 * Burgar et al. 2018. The importance of considering multiple interacting species for conservation of
 * Darlington et al. 2022. Cumulative efects of human footprint, natural features and predation risk best predict seasonal resource selection by white-tailed deer
 * Fisher and Burton 2018. Wildlife winners and losers in an oil sands landscape
 * Fisher and Burton 2020. Spatial structure of reproductive success infers mechanisms of ungulate invasion in Nearctic boreal landscapes
 * Fisher and Ladle 2022. Syntopic species interact with large boreal mammals response to anthropogenic landscape change
 * Fisher et al. 2020. Influences of landscape change and winter severity on invasive ungulate persistence in the Nearctic boreal forest
 * Frey et al. 2022. Predator control alters wolf interactions with prey and competitor species over the diel cycle
 * Wittische et al. 2021 Community-level modelling of boreal forest mammal distribution in an oil sands landscape

**metadata**  
This folder contains information from the original data production necessary for producing key data products. 
1) Landscape Data Preparation 2016-02-26.docx : additional information on the data extraction process for the landscape covariates from 2011-2015
2) HFI2010_Metadata.pdf - detailed description example of human feature index used in the data extraction process (see below)
3) 2005-avi-abvegetation3-inventorystan-mar05.pdf : Alberta Vegetation Index

<hr>

### **DETAILS ON OUTPUTS** 
### Data specific information for : [outputs/christina_lake_camop.csv]  

* **Number of variables/columns:** 7
* **Number of observations/rows:** 361 (multiple checks per camera site) 

**Variable List:**
* **site** : camera site ID
* **UTME** : camera site UTME location
* **UTMN** : camera site UTMN location
* **treatment**: indicator for camera setup in the "pre" or "post" wolf control period
* **camera_check**: camera check period for the given year (cameras were checked mostly in October)
* **start_date** : first day of camera operation as recorded by a camera trigger (no timelapse function used)
* **end_date** : last day of camera operation as recorded by a camera trigger (no timelapse function used)

### Data specific information for : [outputs/christina_lake_detections_raw.csv]  

* **Number of variables/columns:** 4
* **Number of observations/rows:** 264,120

**Variable List:**
* **treatment**: indicator for camera setup in the "pre" or "post" wolf control period
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each detection. Note there was an error in the raw data resulting in no "seconds" being recorded for some of the cameras, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns", so this will need to be filtered/cleaned before any analysis. I have removed blanks as they took up a large proportion of the original dataset.

### Data specific information for : [outputs/christina_lake_30min_independent_detections.csv]  

* **Number of variables/columns:** 6
* **Number of observations/rows:** 37,633 (one row for each independent detection of a species at each site) 

**Variable List:**
* **treatment**: indicator for camera setup in the "pre" or "post" wolf control period
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each detection. Note there was an error in the raw data resulting in no "seconds" being recorded for some of the cameras, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns" and will need to be filtered/cleaned before any analysis.
* **duration** : the difference in time between subsequent independent detections (mins). Note this could be calculated using the datetime column between subsequent detections. NA's represent the first detection of a species at a given camera, as there can be no difference in time from this event to a previous event. 
* **Event.ID** : a unique identifier for a species' independent detection at a camera site. 

### Data specific information for : [outputs/christina_lake_covariates.csv]  
For further details and specifics of individual columns/data sources, it is recommended to read the methods section of K. Baillie-David's MSc thesis in the relevant literature folder. This will provide users further details on the sources used. 

* **Number of variables/columns:** 24
* **Number of observations/rows:** 976 (115 camera sites, 20 repeat observations/one observation per radius measure)

**Variable List:**
* **treatment**: indicator for camera setup in the "pre" or "post" wolf control period
* **site** : camera site ID
*  **radius** : the circular buffer (m) around which proportional cover for other covariates is measured
*  **uplanddeciduous** : Aspen, poplar, white birch, comprising >70% canopy cover, moisture dry or mesic
*  **uplandshrubs** : >25% shrub cover, with <6% tree cover. Moisture dry or mesic
*  **water** : standing or flowing water
*  **nonforest** : < 6% canopy cover
*  **lowlanddeciduous** :Aspen, poplar, white birch, comprising >70% canopy cover, moisture wet or aquatic
*  **uplandmixedwood** : 40-60% canopy cover, moisture dry or mesic
*  **lowlandmixedwood** : 40-60% canopy cover, moisture wet or aquatic
*  **uplandspruce** : Black spruce, white spruce, or balsam fir comprising > 70% canopy cover, moisture dry or mesic
*  **lowlandspruce** :Black spruce, white spruce, or balsam fir comprising > 70% canopy cover, moisture wet or aquatic
*  **pine** : jack pine comprising > 70% canopy cover
*  **tamarack** : tamarack/larch > 70% canopy cover
*  **openwetland** : wetlands with < 6% crown closure, moisture wet or aquatic
*  **cutblocks** : Areas where forestry operations have occurred (clearcut, selective harvest, salvage logging, etc.)
*  **pipeline** : A line of underground and over ground pipes, of substantial length and capacity, used for the conveyance of petrochemicals. (Technically a summary feature, but basically the same, see page 167 of other/HFI2010_Metadata.pdf)
*  **transmissionline** :A utility corridor >10 m wide with poles, towers and lines for transmitting high voltage electricity (voltage greater than 69 kV). (Technically a summary class, see page 112 of metadata/HFI2010_Metadata.pdf)
*  **wellsite** : wellsites (likely active)
*  **blockfeatures** : other block features such as industrial sites (not including wellsites or forestry cutblocks)
*  **road** : a summary feature of road types (see pages 38-39 of other/HFI2010_Metadata.pdf)
*  **trail** : a summary feature of recreational trails
*  **seismic_3d** : 3D seismic lines
*  **seismicline** : traditional seismic lines


