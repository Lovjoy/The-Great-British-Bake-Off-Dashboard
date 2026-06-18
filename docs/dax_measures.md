# DAX Measures and Calculated Columns

This document lists the key DAX measures and calculated columns used in the Great British Bake Off Power BI dashboard. These calculations support baker-level outcomes, handshake analysis, placement tracking, selected episode ratings, and viewership summaries.

## Bakers Table

### Calculated Columns

#### Last Episode

Identifies the final episode reached by each baker in their season. Episode 10 represents the final.

```DAX
Last Episode = 
VAR CurrentKey = Bakers[BakerSeasonKey]
RETURN
    CALCULATE(
        MAX(ChallengeBakes[Episode]),
        FILTER(
            ChallengeBakes,
            ChallengeBakes[BakerSeasonKey] = CurrentKey
        )
    )
```

#### Placement

Classifies each baker as the season winner, runner-up, or did not win.

```DAX
Placement = 
VAR BakerName =
    TRIM(UPPER([Baker]))

VAR WinnerName =
    TRIM(UPPER('Seasons'[Winner for Selected Baker Season]))

VAR LastEp =
    [Last Episode]

RETURN
    SWITCH(
        TRUE(),
        BakerName = WinnerName, "Winner",
        LastEp = 10, "Runner-up",
        "Did Not Win"
    )
```

#### Received Handshake

Flags whether a baker received at least one handshake during their season.

```DAX
Received Handshake = 
VAR CurrentKey = Bakers[BakerSeasonKey]

VAR TotalHandshakes =
    CALCULATE(
        SUM(Outcomes[Handshake]),
        FILTER(
            Outcomes,
            Outcomes[BakerSeasonKey] = CurrentKey
        )
    )

RETURN
    IF(
        COALESCE(TotalHandshakes, 0) > 0,
        1,
        0
    )
```

### Measures

#### Total Bakers

Counts the total number of unique baker-season records.

```DAX
Total Bakers = 
DISTINCTCOUNT(Bakers[BakerSeasonKey])
```

#### Bakers With Handshakes

Counts only bakers who received at least one handshake.

```DAX
Bakers With Handshakes = 
COUNTROWS(
    FILTER(
        VALUES(Bakers[BakerSeasonKey]),
        CALCULATE(SUM(Outcomes[Handshake])) > 0
    )
)
```

## Episodes Table

### Measures

#### Average Rating for Selected Episodes

Calculates the average rating for the episodes selected through challenge-level filters.

```DAX
Average Rating for Selected Episodes = 
VAR SelectedEpisodes =
    VALUES(ChallengeBakes[SeasonEpisodePad])
RETURN
    CALCULATE(
        AVERAGE(Episodes[My Rating]),
        TREATAS(SelectedEpisodes, Episodes[SeasonEpisodePad])
    )
```

#### Total Views for Selected Episodes

Calculates total viewership for selected episodes and converts the stored viewership value into full view count scale.

```DAX
Total Views for Selected Episodes = 
VAR SelectedEpisodes =
    VALUES(ChallengeBakes[SeasonEpisodePad])
RETURN
    CALCULATE(
        SUM(Episodes[My Viewership]) * 1000,
        TREATAS(SelectedEpisodes, Episodes[SeasonEpisodePad])
    )
```

## Seasons Table

### Measures

#### Winner for Selected Baker Season

Returns the winner for the selected baker’s season.

```DAX
Winner for Selected Baker Season = 
VAR SelectedSeason =
    SELECTEDVALUE(Bakers[Season])
RETURN
    IF(
        ISBLANK(SelectedSeason),
        "Select one baker",
        CALCULATE(
            SELECTEDVALUE('Seasons'[Winner]),
            TREATAS({SelectedSeason}, 'Seasons'[Season])
        )
    )
```
