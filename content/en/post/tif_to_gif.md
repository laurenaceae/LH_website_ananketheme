---
date: "2023-02-01T10:58:08-04:00"
description: An R package for turning raster files into an animated GIF file
featured_image: /images/foresce_pink_header.png
tags: 
- R Package
- Landscape Ecology
title: 'tif2gif R Package'
---

This R package was designed to turn TIF files into animated GIF files. The unique part is the customization: users can select a prefix and/or suffix of the files they want to use (in case of mixed-contents folders), the speed of the GIF in frames per second, the output and input file paths, an output name (which gets combined with any given prefix or suffix), and the color palette to color the GIF with. It is also simple to use this function with purrr::pmap to iterate over multiple combinations of files.

I made this R package to make the assignment outputs form ESM 215 Landscape Ecology easier to understand. We ran the LANDIS-II model in lab and I thought there were too many outputs to easily interpret, and the code provided to us for "animating" these outputs simply graphed them in order in R. I disseminated this code to our class to share a better way of visualizing the outputs. 

This package is available on Github: [tif2gif](https://github.com/laurenaceae/tif2gif)

Installation instructions are in the readme which can be found in  the Github link above. The package also contains a vignette with examples of use and outputs. 

Example Output:

Values represent the maximum age class for that species in a  given pixel. 

{{< figure src="/images/landis_modern_adenfasc_highhigh.gif" title="50 year run of Adenostoma fasciculatum, modern scenario (with urban/developed), high ignitions and high spread" >}}

{{< figure src="/images/landis_modern_adenfasc_lowlow.gif" title="50 year run of Adenostoma fasciculatum, modern scenario (with urban/developed), low ignitions and low spread" >}}
