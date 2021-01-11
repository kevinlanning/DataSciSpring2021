---
title: "Tracking the Novel Coronavirus"
author: "Kevin Lanning, Wilkes Honors College"
date: "02022020 :)"
output: html_document
---

This is an educational script for students learning R with the tidyverse. It reads data provided by the Johns Hopkins Center for Systems Science and Engineering (JHU/CSSE) using the Googlesheets4 package written by Jenny Bryan.  

It was modified February 3 because of new GoogleSheet link and altered variable names, on Feb 5 because of a new URL for the data and additional changes in the variable name for date, and Feb 7 to (a) remove need for OAuth and (b) separate Wuhan from other China. On Feb 9, additional data cleaning was performed and interactive plots were added.


```r
library(googledrive)
library(googlesheets4)
library(tidyverse)
library(magrittr)
library(lubridate)
library(plotly)
library(htmlwidgets)
drive_deauth()
sheets_deauth()
```

```
## Warning: `sheets_deauth()` is deprecated as of googlesheets4 0.2.0.
## Please use `gs4_deauth()` instead.
## This warning is displayed once every 8 hours.
## Call `lifecycle::last_warnings()` to see where this warning was generated.
```

```r
coronaURL <- "https://docs.google.com/spreadsheets/d/1wQVypefm946ch4XDp37uZ-wartW4V7ILdg-qYiDXUHM" 
nsheets <- sheets_get(as_id(coronaURL)) %>% 
    extract2(6) %>% # gets the sixth element in a list  
    nrow() 
```

```
## Warning: `sheets_get()` is deprecated as of googlesheets4 0.2.0.
## Please use `gs4_get()` instead.
## This warning is displayed once every 8 hours.
## Call `lifecycle::last_warnings()` to see where this warning was generated.
```

```r
# j <- sheets_read(as_id(coronaURL), sheet = i) 
```

### Reading the data

The Novel Coronavirus data consists of a series of tabs in a Google Sheet. This finds them and combines them into a single sheet in R. 















