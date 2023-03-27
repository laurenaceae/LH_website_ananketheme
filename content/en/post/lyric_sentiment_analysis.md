---
date: "2023-03-26T10:58:08-04:00"
description: An R package for sentiment analysis of songs in the Top 100
featured_image: /images/IMG_5218_edit1.JPG
tags: 
- R Package
- Assignment
- Bren
title: 'Lyric Sentiment Analysis of Top 100 Songs'
---

For this assignment in ESM 262 Environmental Computing, we were asked to come up with a creative function, visualize the outputs, and then turn that function into a working package for public use. 

My partner and I created a function that conducts a sentiment analysis on lyrics for songs in the top 100. The required input is an artist name (e.g. Madonna), and the output is a data frame which contains a column for that artists' Top 100 song titles and a column for the sentiment values for those songs. Sentiment values range from -1 (negative sentiment) to 1 (positive sentiment).

Inputs include:
- artist: Artist name (required input)
- start_year: Start of date range
- end_year: End of date range
- dictionary: Dictionary for sentiment analysis (GI or QDAP)
- exact: Whether to look for exact artist match (impacts song features)
- duplicates: Whether to include duplicates (songs on top 100 for multiple years)

[Github link to package](https://github.com/laurenaceae/ESM262LH)

Installation: 
- devtools::install_github("laurenaceae/ESM262LH")
- library(ESM262LH)

Example outputs (post-processed):

{{< figure src="/images/oldies_lyrics.png" title="Pop Artists from '50s - '80s" >}}

{{< figure src="/images/modern_lyrics.png" title="Modern Pop Artists" >}}

Collaborators: Sarah Lam (for both the function and package), Deanna Elliott (for only the package)