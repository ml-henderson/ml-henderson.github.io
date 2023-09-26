---
layout: post
title: "MS Thesis"
author: "Madeleine Henderson"
categories: journal
tags: [thesis]
image: Slide1.PNG
---

Resilience, or the ability to quickly recover from shocks, is a critical quality for natural and social systems in the face of climate change which is increasing the frequency and severity of natural disturbances such as drought. Smallholder farmers are particularly exposed to the risks of climate change. Thus, identifying resilience-building practices and quantifying their effects can guide management in agro-ecological systems. Community-driven tree planting for carbon credits is a growing program in the Mount Kenya region of Kenya. Tree planting and agroforestry are known to have ecological benefits that improve soil quality, microclimate, and water retention, as well as economic benefits to farmers. To evaluate the benefits of these practices on resilience to drought, remotely sensed vegetation greenness (NDVI) was used to assess the state of the agro-ecological systems around Mt. Kenya during and after droughts within the last decade. Droughts were identified by the Kenyan government based on surveys of community members and remotely sensed data. Resilience was estimated using the rate term of a fit exponential curve to the vegetation recovery after a drought. The resilience estimation method was successful and found proven patterns of resilience with precipitation and landcover. Planted tree groves and immediate neighboring pixels have higher resilience to drought events than comparable pixels in the area, and they see less decrease in resilience to subsequent drought events than other pixels. Agroforestry programs are thus an important tool for building resilience to drought for smallholder farmers in Kenya who are increasingly threatened by climate change.

# Extended Summary 

![Introduction](assets\files\TIST_Resilience_final\Slide3.PNG)

TIST (The International Small Group and Tree Planting Program) is the community tree planting program - see the [intro post](https://ml-henderson.github.io/thesis_intro) for more background.

The research questions are: 
1. Can resilience to drought be estimated with vegetation recovery rate via remotely sensed data in Kenya?
2. Do farms engaged in agroforestry with TIST exhibit greater resilience, as measured by recovery rate, to drought than non-TIST land?
3. Does TIST affect the recovery from subsequent drought events? 
4. Are there any spillover effects on resilience from TIST into the surrounding areas? 

## Methods
Four counties were selected because of their density of TIST groves, comparable agricultural practices, and classification as arid and semi-arid land counties (ASALs) by the Kenyan government. These counties are fairly internally heterogenous, with the agricultural and ecological conditions varying from the dry lowlands up to much wetter and cooler forested highlands near Mount Kenya. 
![Study Area](assets\img\studyarea.png)
_Purple points are TIST groves - small farms engaged in tree planting for carbon credits._

Droughts were classified using reports from the Kenyan National Drought Management Authority (NDMA) beginning in 2016. Besides quantitative measures of drought such as precipitations, the NDMA uses surveys of residents covering livestock forage quality, water access, crop prices, and crop success to capture the multi-dimensional aspects of drought.

![Drought](assets\img\drought_class.png)
_A subset of the drought categorizations from the start of the availability of the NDMA reports (Month 40, September 2016) until Month 80, January 2020. The highlighted months (54, 59, and 77) represent the start of recovery periods._

To quantify the vegetation greeness and have a proxy measurement for the state of the agro-ecological system, NDVI derived from Landsat-8 was used (see the full document below for details, page 20). Data was filtered, cleaned, and detrended as shown below to obtain the residuals of the greeness data, which removes seasonal cycles and long term trends, leaving only the fluctuations of the 'base state' of the system (diagram below). There were still many pixels with large gaps of missing data due to cloud coverage. 

![Preprocessing](assets\img\preprocessingmethods.png)

To estimate the resilience of the system, the recovery rate after each drought was estimated by fitting an exponential curve to the residuals as shown below.

![Curve Fit](assets\files\TIST_Resilience_final\Slide8.PNG)

For all pixels with enough data to estimate a recovery rate, the rate was saved. If there was no significant dip in the residuals, the pixel was marked as No Disturbance. If a disturbance was found but the curve fit could not converge, the pixel was also marked as No Curve Fit. 

## Results and Discussion 
![RQ1](assets\files\TIST_Resilience_final\Slide10.PNG)
Patterns can be seen in the recovery rates. Higher occurence of No Disturbance pixels in shrublands aligns with existing literature. Semi-arid areas tend to respond slower to droughts than arid or wet ecosystems because they tolerate a wider variety of water availability; thus, months of water stress may not have caused a detectable disturbance. Conversely, because of the slow reaction, drier areas also have lower recovery rates, while forested and wetter areas have the fastest recovery rates, which was also found by previous studies. These results validate the method as a useful way to measure resilience to specific disturbances. 

![examples](assets\img\recov_rate_examples.png)

You can explore the results in Tharaka-Nithi county in the map below.
<iframe src="assets\files\tharaka_interactive_map.html" loading="lazy" style="width: 100%; height: 400px; border: 0px none;"></iframe>
_Results from Tharaka-Nithi county. Example recovery curves shown at purple markers._

![Embu-Nyeri](assets\files\TIST_Resilience_final\Slide12.PNG)
Embu and Nyeri counties encountered issues leading to poor result quality and quantity, thus the rest of the research questions focus on results from Tharaka and Meru.

![RQ2](assets\files\TIST_Resilience_final\Slide13.PNG)
Because TIST farms tend to occur in more historically forested and wetter areas, comparing TIST pixel resilience against all other pixels would not isolate the effects of TIST itself. Thus, landcover classification (Treecover, Shrubland, Grassland, or Cropland) was used to stratify pixels. Comparing TIST groves and immediate neighboring pixels to non-TIST pixels of the same landcover showed that TIST and Neighbors ususally had faster recovery rates. 

Correlation is not indicative of causation, but it is plausible that TIST membership contributes to increased resilience because of the tree planting and conservation agriculture practices that TIST promotes. In semi-arid areas especially, groves of trees increase the amount of water stored in the soil by increasing the depth that water can infiltrate and obstructing runoff. Trees also create a cooler and wetter microclimate in their immediate area by providing shade and increasing the humidity through evapotranspiration. Conservation agriculture also improves the quality of the soil by reducing tillage, leaving crop residues on the fields, and rotating crops to replenish nutrients; all of these practices contribute to increased water use efficiency. In total, while higher resilience of TIST farms cannot be definitively or solely attributed to TIST membership, the practices of tree planting, agroforestry, and conservation agriculture likely contribute.  

![RQ3](assets\files\TIST_Resilience_final\Slide14.PNG)
The effect of TIST groves on resilience to subsequent drought is positive; however, the number of pixels with valid data is very limited and is skewed towards areas with less cloud cover and the area where Landsat tiles overlap. Treecover showed the least change in resilience overall, which is not surprising given the ability of trees to access deeper water sources and improve the soil and microclimate around them. There also may be an increasing benefit with time for TIST groves as the trees mature and land has been under conservation agriculture practices for longer, which tends to produce more benefits with time. 

![RQ4](assets\files\TIST_Resilience_final\Slide15.PNG)
The assumption underpinning the comparison of pixels within one kilometer of TIST pixels was that these areas likely experienced similar agro-ecological conditions as well as drought severity, despite the highly varied landscape; however, these assumptions may not hold across that distance. Also, these results are influenced by which pixels had calculated results, which can be seen in the differences in median characteristics with distance from TIST plots from one recovery to the next in the two counties. This does not mean that there is no TIST effect; TIST groves are greenest and recover fastest, followed by immediate neighbors; however, without further analysis, any spillover effect in resilience from TIST groves to farther neighboring areas is difficult to isolate. 

![Limitations](assets\files\TIST_Resilience_final\Slide17.PNG)
Given the methodological limitations such as sensitivity to missing months and the lack of complete timeseries in greener and more tree-covered locations due to cloud contamination, this study could provide further conclusions with additional data sources such as combining satellite sources for more complete NDVI series, fieldwork to localize drought severity, or information on the extent of TIST practices. 

![Summary](assets\files\TIST_Resilience_final\Slide18.PNG)
Because of the warming climate and pressures on planetary boundaries, ecosystems globally are exhibiting lower resilience while simultaneously the frequency and intensity of disasters like drought are increasing. Smallholder farmers are particularly exposed to the risks of climate change. TIST, a community-driven tree planting program for carbon credits, economically and environmentally benefits participating farmers, and the practices of agroforestry and conservation agriculture have previously been found to increase their resilience to climate change. This study supports the TIST program by quantifying that participants exhibit higher resilience to drought than comparable areas, and it corroborates farmers’ experiential understanding that agroforestry improves drought resilience. By assessing the resilience of agro-ecosystems such as the area surrounding Mt. Kenya and identifying resilience-increasing management methods such as TIST practices, this study contributes to the concept of resilience monitoring systems and supports the use of resilience-building agricultural techniques.

Here's the entire thing if you're a truly interested reader! 

<embed src="https://ml-henderson.github.io/assets/files/Henderson_dissertation_PDF2.pdf"
    type="application/pdf" 
    width="100%"
    height="800"/>