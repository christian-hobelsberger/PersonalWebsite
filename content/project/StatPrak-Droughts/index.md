---
title: Multivariate Analysis of Climatological and Hydrological Low Water Drivers in Bavaria (Statistical Internship)
summary: In our statistical internship, we conducted multivariate analysis on climatological and hydrological low water drivers in Bavaria using simulated and measured data from three river gauges between 1990 and 2020, focusing on predicting low water events through Generalized Additive Models (GAMs) with driver-specific splines and variable-specific quantile distribution analysis, highlighting the importance of groundwater level, precipitation group, and soil water as drivers, observing distinct north-south differences, and exploring the relationships between extreme events and relevant variables.
tags:
  - Data Science
  - Low Flow
  - Climate
  - Statistics
  - Statistical Internship
date: "2023-04-20T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Image by Wasser-Info-Team Bayern e. V.
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: github
    url: https://github.com/StatPrak-Droughts
url_code: ''
url_pdf: 'uploads/Poster_Climex2.pdf'
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---
## Data

Simulated and measured data at 3 river gauges in hydrological
Bavaria between 1990 and 2020.
The target variable **NM7Q**: lowest 7-day runoff mean of a year (typical
low water characteristic)

## Research Interests

* How can the occurrence of low water events be explained/predicted?
* Which drivers are relevant? 
* Are drivers of an extreme event themselves extreme? Or is it a combination of moderately pronounced drivers that leads to extreme low water?


## Findings 
* How can the occurrence of low water events be explained/predicted?
  - GAMs with binomial distribution assumption
  - Modeling drivers as splines and individual explanatory interactions
  - Variable-specific quantile distribution analysis
  
* Which drivers are relevant? 
  - Groundwater level, precipitation group, and soilwater appear important
  - Clear differences between north and south, e.g., in influence of snow and air temperature
  - Grouping of southern and northern areas seems reasonable

* Are drivers of an extreme event themselves extreme? Or is it a combination of moderately pronounced drivers that leads to extreme low water?
  - Differences between variables
  - Extreme events seem relevant for: Precipitation, relative near-surface soil moisture, infiltration, and groundwater level.

## Authors

- Christian Hobelsberger
- Max Lang
- Jonas Schernich
- Lisa Kleinlein