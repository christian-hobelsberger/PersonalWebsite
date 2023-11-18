---
title: The impact of pandemic restrictions on mental health during COVID 19 in Germany (Bachelor Thesis)
summary: This project utilizes data from the Global COVID-19 Trends and Impact Survey (CTIS) and Corona data Germany to access the the impact of pandemic restrictions on mental health during COVID 19 in Germany.
tags:
  - Bachelor Thesis
  - Data Science
  - Mental Health
  - CTIS
  - Statistics
date: "2023-06-08T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Image by Freepik
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: github
    url: https://github.com/christian-hobelsberger/CTIS-Mental-Health-Restrictions
url_code: ''
url_pdf: 'https://doi.org/10.5282/ubm/epub.107255'
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---
This project utilizes data from the Global COVID-19 Trends and Impact Survey (CTIS) and Corona data Germany to access the **the impact of pandemic restrictions on mental health during COVID 19 in Germany**

## Paper Link

The complete paper can be accessed here: [https://doi.org/10.5282/ubm/epub.107255](https://doi.org/10.5282/ubm/epub.107255).

## Findings and Summary

### Results:

- The impact of pandemic restrictions on mental health was small to minimal, which is contrary and consistent with some studies.
- No clear associations were found between containment measures (covariates) and mental health variables.
- Significant associations were observed between age, gender, education level, and employment status with the likelihood of anxiety and depression, which is consistent with other mental health studies.

### Limitations:

- The presence of bias from the sample used in the study.
- The measurement of mental health and pandemic restrictions.

### Further research
- Inclusion of other variables
- Inclusion of pre-pandemic mental health data
- Inclusion of different cultural, social, and economic contexts.

## Data Used

- [The Global COVID-19 Trends and Impact Survey (CTIS)](https://covidmap.umd.edu/):
  - Primary data source for this project.
  - A global online survey conducted through Facebook during the COVID-19 pandemic.
  - United States data is not included, and countries without access to Facebook are also excluded.
  - The study was conducted from April 6, 2020, to June 25, 2022.

- [Corona data Germany](https://www.corona-daten-deutschland.de/):
  - Secondary data source for this project.
  - Provides small area data on the COVID-19 crisis in Germany.
  - Includes daily information on regional containment measures.
  - The data is available from 2020 to 2023.
My analysis covers the observation period from May 20, 2021, to June 25, 2022.

## Project Structure

This repository is organized as follows:
- [`data_analysis.Rmd`](https://github.com/christian-hobelsberger/CTIS-Mental-Health-Restrictions/blob/main/data_analysis.Rmd): R Markdown file containing the data analysis process.
- [`data_analysis_prep_tables.R`](https://github.com/christian-hobelsberger/CTIS-Mental-Health-Restrictions/blob/main/data_analysis_prep_tables.R): R script for preparing tables used in the data analysis.
- [`data_model_fit.Rmd`](https://github.com/christian-hobelsberger/CTIS-Mental-Health-Restrictions/blob/main/data_model_fit.Rmd): R Markdown file for fitting my models.
- [`data_preparation.Rmd`](https://github.com/christian-hobelsberger/CTIS-Mental-Health-Restrictions/blob/main/data_preparation.Rmd): R Markdown file for data preparation using the various data sources.

## Acknowledgments

I would like to express my sincere gratitude to Dr. Anna-Carolina Haensch for her invaluable support and guidance throughout the process of my Bachelor thesis. Her expertise and dedication greatly contributed to the successful completion of this research. Thank you for your valuable input and mentorship.

Thank you for visiting this repository and exploring my Bachelor thesis on the impact of pandemic restrictions on mental health during COVID-19 in Germany.
