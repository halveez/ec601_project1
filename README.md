# ec601_project1
Detection and elimination of shadows in multi-spectral images (Do a literature review of shadow detection and removal with focus on multispectral images)

From Lecture 01 Slides:
Problem Statement:  
What does the topic cover?
Why it is important?
Applications
What are applications of the topic?
What is the societal significance of the research?
Pick an area of focus that interests you in the topic
Literature review
As comprehensive as you can, research the different approaches and solutions in research community and industry
Open Source research
Research the different open source projects that touch the topic of your interest
Duplicate the results


Difference between hyper and multi spectral imaging


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

Some methods include detection of increased hue values in shadow regions compared to non-shadow regions. (https://ieeexplore.ieee.org/abstract/document/1343090)

Some other methods use green and blue color detection, however with manual thresholds.

Additionally, some other methods use different color spaces from RGB, including HSV, C1C2C3, etc. https://towardsdatascience.com/understand-and-visualize-color-spaces-to-improve-your-machine-learning-and-deep-learning-models-4ece80108526

Look at OS options - licenses, etc.

First found on GitHub:

Cloud-Shadow-Detection-Based-on-Spectral-Indices

Python -> OpenCV packages -> Rasterio (geospatial data formatted as rasters - bitmaps)

NASA open data

OpenCV (Apache2 License)
https://opencv.org/license/
OpenCV automatically includes FFmpeg, which is licensed under LGPLv2.1
Also includes other binaries:

Rasterio:
https://rasterio.readthedocs.io/en/latest/intro.html#rasterio-license


https://scihub.copernicus.eu/

Email Osama to ask for the data from Norway (wheat, strawberry, etc.)