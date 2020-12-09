---
title: European Energy Data Analysis
author: ~
date: '2020-12-08'
slug: european-energy-data-analysis
categories: []
tags: []
---

```r setup, include=FALSE, message=FALSE
knitr::opts_chunk$set(echo = TRUE)

library(here)
library(ggplot2)
library(tidyverse)
library(readxl)
library(ggthemes)

energy_types <- readr::read_csv(here::here("data", "tidytuesday", "energy_types.csv"))
country_totals <- readr::read_csv(here::here("data", "tidytuesday", "country_totals.csv"))
```

```r
energy_types %>%
  left_join(country_totals, by = c("country", "country_name"))
```