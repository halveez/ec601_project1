# EC601 Project 1
Zachary Halvorson, Boston University Fall 2021


## Multi-Spectral Imaging and Shadows

Detection and elimination of shadows in multi-spectral imaging covers both the detection of shadows in images, as well as the subsequent incorporation of that information with post-capture, and possible pre-capture processing of aerial imaging. These processes also apply to ground based images with shadows, however depending on the implementation of the algorithm, separate tools must be developed to account for the vastly different image geometries when comparing ground based and aerial imaging. This project will focus on aerial images, including space, aerial, and ground based systems.

There is an important distinction between multi-spectral imaging, and hyper-spectral imaging, wherein multi-spectral imaging only detects limited wavelengths in discrete steps or bands, and where hyper-spectral imaging covers a broader range of wavelengths, often with much higher resolution and a greater number of spectral bands[[1]](#1). 

Generally for hyper-spectral imaging, the more narrow and greater number of total bands leads to significantly more information that can then be used to inform later analysis. Multi-spectral imaging can still provide interesting data, but is comparatively limited. Of course, this trade off coincides with hyper-spectral systems being much more expensive and rare in practice, where multi-spectral imaging systems are more affordable and arleady exist in many circumstances (orbitting satellites).


## Applications

Some of the most common applications of multi-spectral imaging include agricultural monitoring, environmental management, archaelogy, and large scale mining and production[[2]](#2). These industries will often use drone based imaging systems to monitor fertilization status, crop production, water retention in a field, and even the composition of the soil, among many other characteristics.

One of the most well-known multi-spectral imaging systems and programs is NASA's Landsat[[3]](#3). Landsat 1 was launched in 1972, and to this point, there have been 8 different Landsat sattelitles, with a 9th being planned for launch on September 27, 2021. 

The Landsat 8 for example has sensors that cover 11 different spectral bands, including blue, gree, red, NIR, SWIR, and thermal, among others. Not only do these projects provide data that benefits countless industries, but the production of these systems themselves (both the sensors and the carriers, whether satellites or drones) are massive economic projects that can help to sustain work in various industries directly (Landsat 9 was budgeted $650M by the US Congress).

PACE (Plankton, Aerosol, Cloud, ocean Ecosystem) is another NASA program utilizing hyperspectral satellite imagining for climate and environmental analysis, that also provides open access to calibrated sensor data[[4]](#4).


## Literature Review

Focusing on methods for shadow detection in multi-spectral imaging, one can consider traditional image processing methods, or methods that incorporate machine learning models (PCA, SVM, among others):

Ibrahim et al.(2021), describes the use of Copernicus Sentinel-2 satellites for multi-spectral imaging in the application of small-scale mine mapping, targeting soil and water composition for analysis[[5]](#5). Their method was tailored specifically for this context, and thus is not easily applied to other settings, however the general framework can still be valuable to study. A SVM was implemented to characterize clouds, cloud shadows, and clear pixels from the target images, following Scikit-learn, another paper for the implementation of machine learning in Python. The SVM is able to incorporate all of the spectral bands from the satellites easily as inputs, and their method then incporporates that data with geographic projection based on the known positions and imaging angles of the satellite in relation to the Earth. This is done to project the location of a cloud shadow from the presence of a detected cloud, and can be used to infer certain characteristics abou the ground being observed. Once initial estimates for clouds and shadows are made, they are refine through varoius parameterized filters, smoothing the output, and removing random pixels and holes in detected clouds. Other tools such as Sen2Cor are incorporated to attempt to account for other error sources, specific to the Sentinel-2 satellite data.

Zi et al.(2018) proposed a combined method of a spectral thresholding function and a subseqent double-branch PCANet with SVM as well[[6]](#6). The images are first segmented on a pixel basis into larger superpixel regions, clustered by SLIC (Simple Linear Iterative Clustering), which clusters pixels together dependent on their location and color in the image. Once the image has been segmented, the different clusters are segmented loosely based on overall brightness with an adjustable threshold, taking into account other known characteristics of clouds such as their absorption differences due to wavelength, brightness, and intensity. Their algorithm then utilizes a double-branched PCANet, a specific type of deep learning network often used for images, with inputs including the raw multi-spectral data, and the previously processed data using spectral thresholds and other methods. As described in their paper, PCANet is faster to implement than standard CNNs, and ultimately combined with their other techniques was more effective in the detection of clouds and cloud shadows in target images. The authors mention that future work needs to be carried out to adapt this algorithm for various types of clouds and other environmental features, such as the presence of ice or snow in the background image.


## Open Source Research

### Open Source Data

Some available sources for open access data include:

NASA's Open Data Portal includes datasets such as the Global Hyperspectral Imaging Spectral-library of Agricultural crops for Central Asia V001 [[7]](#7)

USDA Farm Service Agency National Agriculture Imagery Program [[8]](#8)

Copernicus Open Access Hub [[9]](#9)

United States Geological Survey Landsat Commercial Cloud Data Access [[10]](#10)

### Open Source Implementations

Fortunately, there are many openly available guides and courses for multi-sepctral image analysis, with a particulary detailed option being the Earth Data Analytics Online Certificate. Among other topics, this course includes a section on multi-spectral remote sensing, with many additional references for further learning[[11]](#11).

OpenDroneMap is an open source toolkit that in 2020 recently added support for multi-spectral imaging. Building upon this, FIELDimageR is an R package designed to take drone images from agricultural settings and perform crop analysis, including multi-spectral imaging for the use of vegetation growth, soil disturbance, and water retention. FIELDimageR even includes functions to remove clouds and weeds from composite images[[12]](#12).

Sourced from Zhai et al.(2018)[[13]](#13), a Python implementation of their algorithm was posted on GitHub for open access. This algorithm incorporates red, green, blue, and near infrared measurements to determine local thresholds for the presence of clouds, which are then optimized and filtered for most likely cloud artifacts, later used to produce a cloud mask that can be applied to the original set of input images for filtering. Components include median filters, cloud masks, shadow masks, spatial matching, reflective cloud indexing, and spectral indices.

#### Licensing Considerations

Many of these tools are built upon OpenCV, which is under the Apache2 license. OpenCV automatically includes FFmpeg, which is licensed under LGPLv2.1, and also includes many other binaries, with various licenses as well. For commercial products based on OpenCV, it is important and ultimately necessary to perform close evalutaion of licensing requirements for all tools used[[14]](#14).

Rasterio, another common software tool has their own license posted online[[15]](#15).

OpenDroneMap is licensed under GNU Affero General Public License v3.0, with specifications listed here[[16]](#16). 


## Reproduction of OS Results

For this project, I attempted to reproduce the results in [[11]](#11), first by downloading the Cold Springs Fire data from the NAIP and following their guide to establishing a working environment in Python.

First, I needed to install Microsoft Visual C++ 14.0 tools. I then ran into some Python issues, and was advised to reinstall using Anacadona, additionally for troubleshooting Rasterio package installation.

Ran into some additional issues with Anaconda and gdal, rasterio, and rioaxxary installation, and was ultimately unable to follow the guide to completion.


## References

<a id="1">[1]</a> 
ColourLex. (2020, May 12). Multispectral imaging. ColourLex. Retrieved September 17, 2021
https://colourlex.com/project/multispectral-imaging/

<a id="2">[2]</a> 
Rosalba Calvini, Alessandro Ulrici, José Manuel Amigo,
Chapter 3.9 - Growing applications of hyperspectral and multispectral imaging,
https://doi.org/10.1016/B978-0-444-63977-6.00024-9

<a id="3">[3]</a>
Jenner, L. (2015, April 1). Landsat overview. NASA. 
Retrieved September 16, 2021.
https://www.nasa.gov/mission_pages/landsat/overview/index.html

<a id="4">[4]</a> 
NASA. (n.d.). Data products table. 
NASA PACE - Data Products Table. Retrieved September 17, 2021
https://pace.oceansciences.org/data_table.htm. 

<a id="5">[5]</a> 
Ibrahim E, Jiang J, Lema L, Barnabé P, Giuliani G, Lacroix P, Pirard E. Cloud and Cloud-Shadow Detection for Applications in Mapping Small-Scale Mining in Colombia Using Sentinel-2 Imagery. Remote 
Sensing. 2021; 13(4):736. https://doi.org/10.3390/rs13040736

<a id="6">[6]</a> 
Zi Y, Xie F, Jiang Z. A Cloud Detection Method for Landsat 8 Images Based on PCANet. Remote Sensing. 2018; 10(6):877. https://doi.org/10.3390/rs10060877

<a id="7">[7]</a>
NASA. Global hyperspectral imaging Spectral-library of agricultural crops for Central ASIA V001.
NASA's Open Data Portal. Retrieved September 17, 2021
https://data.nasa.gov/dataset/Global-Hyperspectral-Imaging-Spectral-library-of-A/gd67-qfeb. 

<a id="8">[8]</a>
USDA. (n.d.). NAIP Imagery Information. NAIP imagery. Retrieved September 17, 2021
https://www.fsa.usda.gov/programs-and-services/aerial-photography/imagery-programs/naip-imagery/

<a id="9">[9]</a> 
European Commission. (n.d.). Open Access Hub. Copernicus. Retrieved September 17, 2021
https://scihub.copernicus.eu/dhus/#/home

<a id="10">[10]</a> 
USGS. (n.d.). Landsat Commercial Cloud Data Access User Guide.
Science Support. Retrieved September 17, 2021
https://www.usgs.gov/core-science-systems/nli/landsat/landsat-commercial-cloud-data-access?qt-science_support_page_related_con=1#qt-science_support_page_related_con. 

<a id="11">[11]</a> 
Earth Lab. (2018, April 14). Introduction to multispectral remote sensing data in Python.
Earth Data Science. Retrieved September 17, 2021
https://www.earthdatascience.org/courses/use-data-open-source-python/multispectral-remote-sensing/intro-multispectral-data/

<a id="12">[12]</a> 
OpenDroneMap. (n.d.). Fieldimager. FIELDimageR: A Tool to Analyze Orthomosaic Images From Agricultural Field Trials in R. Retrieved September 17, 2021
https://www.opendronemap.org/fieldimager/

<a id="13">[13]</a> 
ThomasWangWeiHong, Cloud-Shadow-Detection-Based-on-Spectral-Indices, (2020), GitHub repository,
https://github.com/ThomasWangWeiHong/Cloud-Shadow-Detection-Based-on-Spectral-Indices

<a id="14">[14]</a> 
OpenCV. (2020, October 20). License. OpenCV. Retrieved September 17, 2021
https://opencv.org/license/

<a id="15">[15]</a> 
Rasterio. (n.d.). Rasterio Documentation. Rasterio. Retrieved September 17, 2021
https://rasterio.readthedocs.io/en/latest/intro.html#rasterio-license

<a id="16">[16]</a> 
OpenDroneMap, ODM/License, (2016), GitHub repository,
https://github.com/OpenDroneMap/ODM/blob/master/LICENSE