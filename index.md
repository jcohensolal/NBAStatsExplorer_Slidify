---
title       : NBA Player Stats Explorer
subtitle    : Julien COHEN SOLAL
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap]   # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
logo        : nbaLogo.png
---

## About the Explorer

The *NBA Player Stats Explorer* aims to allow users to visually explore statistics related to the play during the 2015/2016 season of the [National Basketball Association](http://www.nba.com) (or *NBA*). 

NBA statistics are available in a number of places, but custom plotting of one statistic against another is nowhere to be found (to my admittedly limited knowledge). It will allow all NBA fans to get new insight on the abilities of their favorite players, and compare players against one another on various "profiles". For a *basic* example, you could ask "Who are the best inside-out players in the league?", and get a reasonable answer by plotting Rebounds against 3 point shots made.

--- &twocol

## Using the Explorer

*** =left
## 

You can choose which statistic to use on X and Y axes, and apply several filters on the data you want to show. On the right panel, the corresponding plot will show instantly. Mouse-over information is available to know which point represent which player. Means for both chosen X and Y variables are calculated on the fly on the current sample of players and shown right below the plot.


Filtering is done via the use of three sliders and one drop-down menu.

*** =right
## 
![](assets/img/NBAStatsExplorer.png) 

--- 

## The Data

All the statistics have been exported from [Basketball Reference](http://www.basketball-reference.com). Coverage starts on the first night of the season, and concludes with the games played on 2016, February 23rd. The list of Free Agents for the summer of 2016 has been exported from [ESPN](http://espn.go.com/nba). A consolidated CSV file has been created using both sources..




```r
# Retrieve and inspect data
nbaData <- read.csv(file = "data/nbastats_20160224.csv")
head(nbaData, 5)
```

```
##   Rk           Player Pos Age  Tm  G GS   MP   FG  FGA   FGP  TH  THA   THP  TW  TWA   TWP  eFGP  FT  FTA   FTP ORB DRB  TRB AST STL BLK TOV  PF  PTS FA
## 1  1    Stephen Curry  PG  27 GSW 53 53 33.8 10.0 19.6 0.508 4.9 10.8 0.455 5.1  8.8 0.574 0.633 4.9  5.4 0.909 0.9 4.4  5.3 6.6 2.2 0.2 3.3 2.0 29.8  0
## 2  2     James Harden  SG  26 HOU 57 57 37.4  8.3 19.2 0.429 2.8  7.9 0.349 5.5 11.3 0.486 0.501 9.0 10.4 0.866 0.8 5.6  6.4 7.0 1.6 0.6 4.5 2.8 28.3  0
## 3  3     Kevin Durant  SF  27 OKC 49 49 36.0  9.6 18.8 0.507 2.5  6.3 0.392 7.1 12.5 0.565 0.573 6.2  6.9 0.893 0.6 7.3  7.9 4.5 0.9 1.2 3.2 1.8 27.7  1
## 4  4 DeMarcus Cousins   C  25 SAC 46 46 34.4  9.3 20.5 0.452 1.2  3.3 0.362 8.1 17.2 0.469 0.481 7.5 10.3 0.728 2.3 9.0 11.3 3.1 1.3 1.4 3.8 3.7 27.3  0
## 5  5   Damian Lillard  PG  25 POR 50 50 36.0  8.5 19.9 0.427 3.1  8.2 0.372 5.4 11.6 0.466 0.504 5.1  5.9 0.862 0.7 3.6  4.2 7.2 1.1 0.3 3.3 2.4 25.1  0
```

```r
dim(nbaData)
```

```
## [1] 456  31
```

---

## Possible Improvements

* Automate the CSV creation, as to be able to always have up-to-date statistics, and also to be able to filter by dates.
* Load other categories of statistics, including *Advanced Metrics*. 
* Allow filtering with more variables. 
* Allow choice of color-coded legend (currently only with free agency status).
* Allow for statistics from previous seasons to be loaded. 
* Add positions to the data set for more filtering possibilities.


## For further information

* [The application hosted on shinyapps.io](https://jcohensolal.shinyapps.io/NBAStatsExplorer/)

* [The GitHub page for this project](https://github.com/juliencohensolal/NBAStatsExplorer)
