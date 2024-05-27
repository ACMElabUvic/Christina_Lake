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
3) Christina_covariates_prepost_250-5000_KBaillieDavid : Site covariates extracted at multiple spatial scales (250 - 5000m) for camera sites in the pre and post period. Covariates provided as percentage area within the circular buffer around each site. Further details on data below. 
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
2) HFI2010_Metadata.pdf - detailed description of human feature index used in the data extraction process (see below)

<hr>

### **DETAILS ON OUTPUTS** 
### Data specific information for : [outputs/willmore_camop.csv]  

* **Number of variables/columns:** 5
* **Number of observations/rows:** 115 (one per camera site) 

**Variable List:**
* **site** : camera site ID
* **Easting** : camera site Easting location
* **Northing** : camera site Northing location
* **start_date** : first day of camera operation as recorded by a camera trigger (no timelapse function used)
* **end_date** : last day of camera operation as recorded by a camera trigger (no timelapse function used)

### Data specific information for : [outputs/willmore_detections_raw.csv]  

* **Number of variables/columns:** 3
* **Number of observations/rows:** 151140

**Variable List:**
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each independent detection. Multiple images may be taken during a detection event, and this data has been sliced to the first image for simplicity. Note there was an error in the raw data resulting in no "seconds" being recorded from the timelapse data, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns" and some blanks, so this will need to be filtered/cleaned before any analysis.

### Data specific information for : [outputs/willmore_30min_independent_detections.csv]  

* **Number of variables/columns:** 5
* **Number of observations/rows:** 19072 (one row for each independent detection of a species at each site) 

**Variable List:**
* **site** : camera site ID
* **datetime** : the datetime (year-month-day hour:minute:second) of the first camera image of each independent detection. Multiple images may be taken during a detection event, and this data has been sliced to the first image for simplicity. Note there was an error in the raw data resulting in no "seconds" being recorded from the timelapse data, therefore all detections end at the top of the hour (e.g. 6:03:00 AM). This should be of little consequence, but is annoying. 
* **species** : the species in the independent detection. Note this still contains "Unknowns" and will need to be filtered/cleaned before any analysis.
* **timediff** : the difference in time between subsequent independent detections (mins). Note this could be calculated using the datetime column between subsequent detections. NA's represent the first detection of a species at a given camera, as there can be no difference in time from this event to a previous event. 
* **Event.ID** : a unique identifier for a species' independent detection at a camera site. 

### Data specific information for : [outputs/willmore_covariates.csv]  

* **Number of variables/columns:** 38
* **Number of observations/rows:** 2300 (115 camera sites, 20 repeat observations/one observation per radius measure)

**Variable List:**
* **site** : camera site ID
*  **radius** : the circular buffer (m) around which proportional cover for other covariates is measured
*  **bpsdl** : borrowpits, sump, dugouts and lagoons: Artificial holding or treatment ponds for industrial, agricultural or municipal wastewater. Human made water and sewage lagoons used for municipal purposes.
*  **cultivation** : Agricultural areas used for cultivation
*  **disturbedvegetation** : Disturbed vegetation that does not fit any other category of human footprint.
*  **harvestareas** : Areas where forestry operations have occurred (clearcut, selective harvest, salvage logging, etc.)
*  **industrial_sites** : a summary feature of many industrial sites (see pages 75-76 of other/HFI2010_Metadata.pdf)
*  **landfill** : Large area of raised land, indicating buried garbage. Some landfills have evidence of surface revegetation and garbage dispersed throughout designated extent. They may also have large perimeter berns or fences
*  **mine_sites** : a summary feature of many mine sites (see pages 60-61 of other/HFI2010_Metadata.pdf)
*  **othervegsurfacesrecreation** : a summary feature of many other vegetated surfaces (see pages 97 of other/HFI2010_Metadata.pdf)
*   **pipelines** : A line of underground and over ground pipes, of substantial length and capacity, used for the conveyance of petrochemicals. (Technically a summary feature, but basically the same, see page 167 of other/HFI2010_Metadata.pdf)
*   **railways**: a summary feature of many railway types, see page 48 of other/HFI2010_Metadata.pdf)
*   **resevoirs** : a body of water created by excavation or the man made damming of a river or stream
*   **residential_areas** : Rural developments (10 - 100 buildings per quarter section).
*   **roads** : a summary feature of road types (see pages 38-39 of other/HFI2010_Metadata.pdf)
*   **seismiclines** : a summary feature of different seismic lines (see page 174 of other/HFI2010_Metadata.pdf)
*   **transmissionlines** : A utility corridor >10 m wide with poles, towers and lines for transmitting high voltage electricity (voltage greater than 69 kV). (Technically a summary class, see page 112 of other/HFI2010_Metadata.pdf)
*   **verge** : no clear description - RECOMMEND REMOVAL OR NOT USING
*   **wellsites** : no clear description, but given there are two feature classes for active and abandoned wellsites, this is likely a combination of the two.
*   **wind_gen_facilities** : Wind turbines, operational or former, visible on imagery. Digitized to represent original land disturbance from construction.
*   **dense_conifer** : dense conifer
*   **moderate_conifer** : moderate conifer cover
*   **open_conifer** : open conifer cover
*   **mixed** : likely mixed tree species cover
*   **broadleaf** : deciduous tree cover
*   **treed_wetland** : wetlands with a high amount of trees
*   **shrub** : shrubs
*   **herb** : not sure, herbs? maybe oregano? (being cheeky, I can't find anything on this)
*   **open_wetland** : open wetlands lacking trees
*   **barren** : open landscape devoid of vegetation
*   **water** : open water, different from wetland.
*   **shadow_or_no_data** : error in the extraction process from shadows
*   **snow_or_ice** : snow or ice cover
*   **regeneration** : regenerating vegetation
*   **cloud_or_no_data** error in the extraction process from clouds
*   **mean_ndvi_2008** : mean ndvi value within a 1000m buffer of the camera sites from 2008
*   **mean_ndvi_2012** : mean ndvi value within a 1000m buffer of the camera sites from 2012
*   **mean_tri** : mean terrain ruggedness index at each camera site

