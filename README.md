# Assignement
NDVI calculation
---
title: "Assignement_Pilar"
author: "Pilar"
date: "29 de noviembre de 2016"
output: slidy_presentation
---
```{r setup, include=FALSE}
library(raster)
library(sp)
library(rgdal)


setwd("C:/Users/Pilar/Documents/02_Raster/TAREA")

list.files()
red_band<-raster("LT51930272003195MTI01_B4.TIF")
nir_band<-raster("LT51930272003195MTI01_B5.TIF")
stack_1<-stack(red_band,nir_band)

knitr::opts_chunk$set(echo = T)
```

## R Markdown

-library(raster)
-library(sp)
-library(rgdal)


## LaterStack
-Plotting the LayerStack, bands 4 and 5

## Slide with R Output

```{r , echo = TRUE}
plot(stack_1)
eq_ndvi <- function(nir,red){
  ((nir-red)/(nir+red))
}

```
## Slide with Plot

```{r , echo = T }
ndvi_func <- eq_ndvi(stack_1$LT51930272003195MTI01_B5,stack_1$LT51930272003195MTI01_B4)
plot(ndvi_func)
```
