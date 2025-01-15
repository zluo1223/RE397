---
layout: default
---
# RE 397 Lab Section A

[![.github/workflows/ci.yaml](https://github.com/pages-themes/architect/actions/workflows/ci.yaml/badge.svg)](https://github.com/pages-themes/architect/actions/workflows/ci.yaml) [![Gem Version](https://badge.fury.io/rb/jekyll-theme-architect.svg)](https://badge.fury.io/rb/jekyll-theme-architect)

![Thumbnail of Architect](https://www.thebalancemoney.com/thmb/FPww6Q4c7FzgNtwa0DA_lLEO160=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/real-estate-what-it-is-and-how-it-works-3305882-1f1ca22206274467862367e2dc59f25b.png)

## Introduction

About myself.

[Welcome to connect me on Linkedin](https://www.linkedin.com/in/zhongmin-luo-9b5400221/)


## Announcement
1. Grading policy
2. According to Canvas schedule this Lab session takes up 110 minutes, but it usually finishes up within 90 minutes.
3. I will set up a regular office hour on Friday between 2:00pm - 3:00 pm via [Zoom](https://washington.zoom.us/j/95676546990) to answer lab questions.
4. Lab will be recorded and you will find recording link on this webpage later!!

## Discussion: Why Data Modeling? 
![attachsytem](attachsystem.png)

## Lab 1
*January 14, 2025*
### Organize dataset
1. Assignment folder
### Download dataset
1. Net migration share
> Go to [Census annual net migration data and population estimates](https://www.census.gov/data/tables/time-series/demo/popest/2020s-total-metro-and-micro-statistical-areas.html)
Find **cbsa-est2023-alldata**
2. Population change rate
> same step as net migration share
3. Share of recent constructed residential
> select the table **Table B25127** then the year of 2023, then under “Geographies” -> “Metropolitan/Micropolitan Statistical Area” -> all metropolitan statistical areas in the US and PR

### A Few Reminders
1. **When you are downloading dataset from the Census website, you should click `ZIP` because using the zip option, the data format will come the way we need for this project. You do not need to remove the MOE or Transpose before downloading, although doing so will not have any issue for the final results.**
2. “OCC_Tittle” in the section of "Employment" is just a column name in the dataset. You do not need to worry about that for Lab1. This is for Thursday or next week’s lab.
3. we use `2020 5-year estimate` which is inconsistent with `2023 1-year estimate` because of COVID, the survey response was extremely low and `margin of error` was too high in many places to generate reliable/meaningful estimates, that is why Census only published `5-year estimates` for 2020.
