
<!-- README.md is generated from README.Rmd. Please edit that file -->
Frequently asked questions
--------------------------

Here, you'll find a subset of FAQs related to the data.

**Question 1** I often use the [`nflscrapR`](https://github.com/ryurko/nflscrapr) package & data for NFL analysis. Can I merge data from this contest to that data?

Yes! Here's one example.

``` r
library(tidyverse)
file.tracking <- "https://raw.githubusercontent.com/nfl-football-ops/Big-Data-Bowl/master/Data/tracking_gameId_2017090700.csv?token=ArYlP9Tyz03227j1NLLnn2EgDnG0hvjzks5cF8pqwA%3D%3D"
tracking.example <- read_csv(file.tracking)

file.nflscrapr <- "https://raw.githubusercontent.com/ryurko/nflscrapR-data/master/play_by_play_data/regular_season/reg_pbp_2017.csv"
pbp.scrapr <- read_csv(file.nflscrapr) 

tracking.merge <- tracking.example %>% inner_join(pbp.scrapr, by = c("gameId" = "game_id", "playId" = "play_id"))
```

**Question 2** Why are there are only 15 games in week 1? Aren’t there usually 16?

The Tampa Bay/Miami game was pushed back due to Hurricane Irma, giving each team a week 1 bye.

**Question 3** Can I publish my work on my blog or in an academic journal?

Yes. As an example, we encourage participants so submit their methods and findings to a special issue of the Journal of Quantitative Analysis of Sports that is devoted to the analysis of football tracking data.
