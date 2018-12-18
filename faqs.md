
<!-- README.md is generated from README.Rmd. Please edit that file -->
Frequently asked questions
--------------------------

Here, you'll find a subset of FAQs related to the data.

**Question 1:** I often use the [`nflscrapR`](https://github.com/ryurko/nflscrapr) package & data for NFL analysis. Can I merge data from this contest to that data?

Yes! Here's one example.

``` r
library(tidyverse)
file.tracking <- "https://raw.githubusercontent.com/nfl-football-ops/Big-Data-Bowl/master/Data/tracking_gameId_2017090700.csv"
tracking.example <- read_csv(file.tracking)

file.nflscrapr <- "https://raw.githubusercontent.com/ryurko/nflscrapR-data/master/play_by_play_data/regular_season/reg_pbp_2017.csv"
pbp.scrapr <- read_csv(file.nflscrapr) 

tracking.merge <- tracking.example %>% inner_join(pbp.scrapr, by = c("gameId" = "game_id", "playId" = "play_id"))
```

**Question 2:** Why are there are only 15 games in week 1? Aren’t there usually 16?

The Tampa Bay/Miami game was pushed back due to Hurricane Irma, giving each team a week 1 bye.

**Question 3:** Can I publish my work on my blog or in an academic journal?

Yes. See the official rules for further detail, but participants are invited to share ideas and findings that stem from this contest.

**Question 4:** Is there anything else about the data that I should know about?

Player tracking data comes from chips embedded in player shoulder pads. Given this technology, as well as technological interferences that occasionally occur at NFL stadia, certain plays may feature insufficient or imperfect data.

**Question 5:** Who should I contact with questions?

Reach out to us at <BDBHelp@nfl.com>.
