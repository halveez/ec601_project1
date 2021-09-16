# EC601 Project 1
Zachary Halvorson
Boston University Fall 2021

test[[1]](#1)


## Multi-Spectral Imaging and Shadows

Detection and elimination of shadows in multi-spectral imaging covers both the detection of shadows in images, as well as the subsequent incorporation of that information with post-capture, and possible pre-capture processing of aerial imaging. These processes also apply to ground based images with shadows, however depending on the implementation of the algorithm, separate tools must be developed to account for the vastly different image geometries when comparing ground based and aerial imaging. This project will focus on aerial images, including space, aerial, and ground based systems.

There is an important distinction between multi-spectral imaging, and hyper-spectral imaging, wherein multi-spectral imaging only detects limited wavelengths in discrete steps or bands, and where hyper-spectral imaging covers a broader range of wavelengths, often with much higher resolution and a greater number of spectral bands. 

Generally for hyper-spectral imaging, the more narrow and greater number of total bands leads to significantly more information that can then be used to inform later analysis. Multi-spectral imaging can still provide interesting data, but is comparatively limited. Of course, this trade off coincides with hyper-spectral systems being much more expensive and rare in practice, where multi-spectral imaging systems are more affordable and arleady exist in many circumstances (orbitting satellites).


## Applications

Some of the most common applications of hyper spectral imaging include agricultural monitoring, 
What are applications of the topic?
What is the societal significance of the research?


## Literature review

Some methods include detection of increased hue values in shadow regions compared to non-shadow regions. (https://ieeexplore.ieee.org/abstract/document/1343090)

Some other methods use green and blue color detection, however with manual thresholds.

Additionally, some other methods use different color spaces from RGB, including HSV, C1C2C3, etc. https://towardsdatascience.com/understand-and-visualize-color-spaces-to-improve-your-machine-learning-and-deep-learning-models-4ece80108526

As comprehensive as you can, research the different approaches and solutions in research community and industry
## Open Source Research

### Open Source Data

NASA's Open Data Portal includes datasets such as the Global Hyperspectral Imaging Spectral-library of Agricultural crops for Central Asia V001 (https://data.nasa.gov/dataset/Global-Hyperspectral-Imaging-Spectral-library-of-A/gd67-qfeb)



### Open Source Implementations

Research the different open source projects that touch the topic of your interest


Cloud-Shadow-Detection-Based-on-Spectral-Indices

Python -> OpenCV packages -> Rasterio (geospatial data formatted as rasters - bitmaps)

OpenDroneMap -> supports TIFFs where each layer is a specific spectral image
NASA open data

OpenCV (Apache2 License)
https://opencv.org/license/
OpenCV automatically includes FFmpeg, which is licensed under LGPLv2.1
Also includes other binaries:

Rasterio:
https://rasterio.readthedocs.io/en/latest/intro.html#rasterio-license


https://scihub.copernicus.eu/

## Reproduction of OS Results





## References
<a id="1">[1]</a> 


Google query dump for "multispectral imaging shadow" keyword search

https://www.sciencedirect.com/science/article/abs/pii/S0168169912000270
https://www.researchgate.net/publication/225158053_Multi-spectral_False_Color_Shadow_Detection
https://www.spiedigitallibrary.org/ebooks/PM/Computational-Color-Technology/14/Multispectral-Imaging/10.1117/3.660835.ch14?SSO=1
https://www.spiedigitallibrary.org/conference-proceedings-of-spie/10004/100040A/A-novel-method-to-detect-shadows-on-multispectral-images/10.1117/12.2241938.short?webSyncID=49a28531-ab0d-3a6b-03c9-7c009b6bcd74&sessionGUID=6b80d8e8-abee-aed6-ae05-c117aac5a919
https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.46.6384&rep=rep1&type=pdf
https://link.springer.com/chapter/10.1007/978-3-642-24393-6_10
https://core.ac.uk/display/29409652
http://etd.lib.metu.edu.tr/upload/12619166/index.pdf

https://github.com/ThomasWangWeiHong/Cloud-Shadow-Detection-Based-on-Spectral-Indices

Topic

Shadows in aerial imaging can cause serious issues in 3D imaging -> leading to errors in object detection, agricultural analysis, building geometry detection, etc.

Shadows arise both physical objects (trees, buildings, power lines, towers, diffuse shadows from trees, etc.) and cloud cover - much larger area of effect.

