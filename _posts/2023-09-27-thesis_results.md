---
layout: post
title: "MS Thesis"
author: "Madeleine Henderson"
categories: journal
tags: [thesis]
image: Slide1.PNG
---

## Academic Abstract
Resilience, or the ability to quickly recover from shocks, is a critical quality for natural and social systems in the face of climate change which is increasing the frequency and severity of natural disturbances such as drought. Smallholder farmers are particularly exposed to the risks of climate change. Thus, identifying resilience-building practices and quantifying their effects can guide management in agro-ecological systems. Community-driven tree planting for carbon credits is a growing program in the Mount Kenya region of Kenya. Tree planting and agroforestry are known to have ecological benefits that improve soil quality, microclimate, and water retention, as well as economic benefits to farmers. To evaluate the benefits of these practices on resilience to drought, remotely sensed vegetation greenness (NDVI) was used to assess the state of the agro-ecological systems around Mt. Kenya during and after droughts within the last decade. Droughts were identified by the Kenyan government based on surveys of community members and remotely sensed data. Resilience was estimated using the rate term of a fit exponential curve to the vegetation recovery after a drought. The resilience estimation method was successful and found proven patterns of resilience with precipitation and landcover. Planted tree groves and immediate neighboring pixels have higher resilience to drought events than comparable pixels in the area, and they see less decrease in resilience to subsequent drought events than other pixels. Agroforestry programs are thus an important tool for building resilience to drought for smallholder farmers in Kenya who are increasingly threatened by climate change.

## Non-academic summary 

### Introduction
See the [intro post](https://ml-henderson.github.io/thesis_intro). 

![Introduction](assets\files\TIST_Resilience_final\Slide3.PNG)

The research questions were: 
1. Can resilience to drought be estimated with vegetation recovery rate via remotely sensed data in Kenya?
2. Do farms engaged in agroforestry with TIST exhibit greater resilience, as measured by recovery rate, to drought than non-TIST land?
3. Does TIST affect the recovery from subsequent drought events? 
4. Are there any spillover effects on resilience from TIST into the surrounding areas? 

### Methods
Four counties were selected because of their density of TIST groves, comparable agricultural practices, and classification as arid and semi-arid land counties (ASALs) by the Kenyan government. 
![Study Area](assets\img\study_area.png)

The study timeframe encompassed the last decade because of the availability of high-quality satellite data and the number of droughts during that time.
Droughts were classified using reports from the Kenyan National Drought Management Authority (NDMA) beginning in 2016. Besides quantitative measures of drought such as precipitations, the NDMA uses surveys of residents covering livestock forage quality, water access, crop prices, and crop success to capture the multi-dimensional aspects of drought. 
![Drought](assets\img\drought_class.PNG)
_A subset of the drought categorizations from the start of the availability of the NDMA reports (Month 40, September 2016) until Month 80, January 2020. The highlighted months (54, 59, and 77) represent the start of recovery periods._

To quantify the vegetation greeness and have a proxy measurement for the state of the agro-ecological system, NDVI derived from Landsat-8 was used (see the PDF below for details, page 20). Data was filtered, cleaned, and detrended as shown below to obtain the residuals of the greeness data, which removes seasonal cycles and long term trends, leaving only the fluctuations of the 'base state' of the system. There were still many pixels with large gaps of missing data due to cloud coverage. 

![Preprocessing](assets\img\preprocessingmethods.png)
_Data preprocessing._

To estimate the resilience of the system, the recovery rate after each drought was estimated by fitting an exponential curve to the residuals as shown below.

![Curve Fit](assets\img\ex_graph1.png)

For all pixels with enough data to estimate a recovery rate, the rate was saved. If there was no significant dip in the residuals, the pixel was marked as No Disturbance. If a disturbance was found but the curve fit could not converge, the pixel was also marked as No Curve Fit. 

### Results 
hmm 

<iframe src="assets\files\tharaka_interactive_map.html" loading="lazy" style="width: 100%; height: 400px; border: 0px none;"></iframe>

_Results from Tharaka-Nithi county. Example recovery curves shown at purple marker. (If it's not loading, try opening this page in a different browser.)_

### Discussion

### Limitations
![Limitations](assets\files\TIST_Resilience_final\Slide17.PNG)

### Conclusions 
![Summary](assets\files\TIST_Resilience_final\Slide18.PNG)

Here's the entire thing if you're a truly interested reader! 

<embed src="https://ml-henderson.github.io/assets/files/Henderson_dissertation_PDF2.pdf"
    type="application/pdf" 
    width="100%"
    height="800"/>