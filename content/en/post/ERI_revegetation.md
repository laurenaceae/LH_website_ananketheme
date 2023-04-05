---
date: "2022-10-06T10:58:08-04:00"
description: Revegetation of plant functional groups in the San Joaquin Valley
featured_image: /images/IMG_5189_edit.JPG
tags: 
- Research
- Agriculture
- Landscape Ecology
- GIS
title: 'ERI Revegetation Project'
---

During the Summer of 2022 we investigated the following research questions: (1) What plant communities were present pre-industrial agriculture? (2) What plant communities are present on fallowed/retired lands? (3) What is likely to recover with active vs. passive restoration? (4) How do abiotic factors and disturbance history influence this recovery? These questions are intended to explore the links between plant functional groups, fallowing, revegetation, and disturbance, and allow for the use of remote sensing techniques in the process. The area of interest for this project is the southern San Joaquin Valley (the Great Valley Ecoregion within the bounds of Kern County, California, for analytical purposes). A number of paths were tested to answer the research questions listed above, a few of which are detailed below.

__Spreadsheet: Plant Macrogroups__

This spreadsheet was created for the purpose of tracking down which characteristics of plant macrogroups can be viewed with remote sensing techniques. Before deciding on what level of plant community taxon to use, I considered Level 3 and 4 Ecoregions (Figure 1, 2), and alliances, groups, macrogroups, and divisions, and WHR groups. I selected macrogroups as the unit of study because they are at the right level of abundance and they group plant communities to a level which I thought likely to have physiological and physical similarities. To determine which macrogroups were present and abundant in Kern County, I used the GAP/LANDFIRE dataset to map out the different USNVC 2.04 macrogroups and determine their cover within the ROI (Figure 3). 

To verify that the GAP/LANDFIRE data was accurate, I compared the plant groups found in GAP/LANDFIRE at Sedgwick Reserve with a Sedgwick dataset of plant communities from aerial photography taken in 2017. The plant communities in Sedgwick for GAP/LANDFIRE and the Sedgwick data mostly match, save for California Montane Conifer Forest & Woodland, which is very prominent in GAP/LANDFIRE and non-existent in the 2017 dataset. Despite this discrepancy, I decided to use the GAP/LANDFIRE categories to choose the relevant plant macrogroups for San Joaquin Valley. 

All macrogroups with a size of more than 200 HA were included in the spreadsheet. The rows in this sheet represent different plant macrogroups, and the columns represent the characteristics which represent those macrogroups. Columns include: Scientific Name, Division (above macrogroup), Elevation, Size (HA, LANDFIRE), Description, Predominant Vegetation, Diagnostic Vegetation,  Reproductive Phenology, Vegetative Phenology, Soil Type, Vertical Structure, Leaf Characteristics, Woody vs. Herbaceous, and Photosynthesis Type. The primary columns are more complete than columns near the end of the list due to information availability. 

{{< figure src="/images/l3_ecoregions.png" title="Figure 1" >}}

{{< figure src="/images/l4_ecoregions.png" title="Figure 2" >}}

{{< figure src="/images/macrogroups.png" title="Figure 3" >}}

__Spreadsheet: Grassland Alliances__

Similar to the Plant Macrogroups spreadsheet, the Grassland alliances spreadsheet records characteristics of plant communities, but for all the grassland alliances. All of the potential grassland alliances in California are included in this spreadsheet — this deviates from the methods for the Plant Macrogroups spreadsheet. This spreadsheet includes columns which specify whether or not the alliance is likely to be found in the San Joaquin Valley: Present in GV PDF, Atwell Spp. List Verdict, Atwell Spp. List (dominant spp. 1st, other occurrences 2nd, * = different sp. in genus). 

The column “GV PDF” refers to a 2012 document from the California Native Plant Society. This document tracks the plant alliances and other taxonomic plant community groups within the Great Valley. For alliances marked as present in this document, the cell in this column reads “Yes”. 

The next two columns, “Atwell Spp. List Verdict” and “Atwell Spp. List”, were also to determine alliance presence in the San Joaquin Valley. I examined the Atwell species list from E. Cypher, which contained information on whether each species was found during plant surveys in recent years. For a given grassland alliance, I listed species that are necessary for that alliance and also found on the Atwell species list. Below a line break here would be any species sometimes present in the alliance. In parentheses after this are any notes next to that species in the list. An asterisk represents a taxon of the same genus but different species. Below this section, I listed species that should be present in the alliance that were not found in the Atwell species list. The top of this section is species that are necessary to form this alliance, and one line break after that is species that were not present which are commonly found in this alliance but not necessary for its delineation. Based on this information, I filled in the column Atwell Spp. List Verdict column, where I entered my opinion and other thoughts on the likelihood of each alliance’s presence in the San Joaquin Valley. 

Additionally, I also mapped all plant groups at Atwell Island and the Semitropic Ecological Reserve using GAP/LANDFIRE data (Figure 4). The purpose of this visual mapping and coverage information is to check whether grasslands are common in these areas according to GAP/LANDFIRE. This works to verify GAP/LANDFIRE data as well as provide insight on the coverage of various grassland types in the region. 

The columns in this spreadsheet include: Alliance, Link and Photos, Group, Common Name, Macrogroup, Present in GV PDF, Atwell Spp. List Verdict, Atwell Spp. List (dominant spp. 1st, other occurrences 2nd, * = different sp. in genus), Ruderal, Elevation, Spp., Reproductive Phenology, Vegetative Phenology, Soil Type (or Habitat, for ruderal alliances), Vertical Structure, Leaf Characteristics, Herbaceous vs. Woody, Notes. 

{{< figure src="/images/atwell.png" title="Figure 4" >}}

__Soils Analysis__

The goal of the soils analysis is to determine which soil types the different grassland alliances trend towards growing on. This will support our efforts to find where different alliances are located within the San Joaquin Valley. This information can be used to differentiate grasslands in remote sensing data, given that the majority of grassland alliances appear very similar in this data source. The input data for this analysis comes from STATSGO2 and GBIF species observation data from the `rgbif` package in R. 

There are two main documents within the soils analysis R project. The first document explores the geography of soil taxonomy in Kern County and the Great Valley. This code maps soil orders, suborders and great groups within Kern and the GV, as well as MUKey (a unique code for the map unit) and the soil series. This information was used to choose a taxonomy level with which to run the second document. This next piece of code extracts soil types of the soil order beneath the observation points for these grassland species. These species observations are then matched to their alliance and graphed as a stacked barplot with the soil order on the x axis, the frequency of observation on the y axis, with the fill as the species. Each alliance is a single plot. 

The output of the second document showed that most alliances tend towards the soil order Xerolls, followed by Orthents and other soil orders. Eight out of fifteen alliances were most commonly found on Xerolls. There was one outlier, Alliance A3871, the Lolium perenne Ruderal Grassland Alliance. This alliance showed a preference for soils in the order Fluvents, followed by Orthents. I would recommend fixing the rgbif issue that prevented plotting for the other six alliances, and performing the same analysis with a soil taxonomy at a level finer than orders. Future analyses should also compare these outputs to the frequency of each soil type in the wider landscape. 

A selection of soil/alliance plots:

{{< figure src="/images/A3870.png" title="Figure 5" >}}

{{< figure src="/images/A4238.png" title="Figure 6" >}}

{{< figure src="/images/A4153.png" title="Figure 7" >}}

PIs: Dan Sousa (SDSU), Ashley Larsen (Bren)

Funding source: Earth Research Institute (ERI) at UCSB