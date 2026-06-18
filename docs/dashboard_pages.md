# Dashboard Pages

This document summarizes the report pages and main interactions used in the Great British Bake Off Power BI dashboard. The report uses slicers, cross-filtering, drillthrough pages, reset buttons, navigation buttons, and bookmarked insight views.

## Report Navigation Summary

| Page                     | Purpose                                             | Main Interaction                                                             |
| ------------------------ | --------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Home**                 | Navigate the report and access guided insight views | Use buttons for page navigation, resets, and bookmarked insights             |
| **Viewership & Ratings** | Explore sample rating and sample viewership trends  | Drill down by air date, year, and season                                     |
| **Baker Directory**      | Browse bakers and compare outcome metrics           | Filter by season, placement, gender, and age; drill through to Baker Profile |
| **Baker Profile**        | Review detailed baker-level stats                   | View one baker’s bakes, outcomes, ratings, and viewership                    |
| **Demographics**         | Analyze baker demographics and handshake patterns   | Use slicers and visual selections to cross-filter demographic patterns       |
| **Theme Explorer**       | Explore episode themes and theme groups             | Filter by season, episode, theme, and theme group                            |
| **Handshake Deep Dive**  | Review detailed handshake records and totals        | Filter handshake records by baker, theme, placement, age, gender, and season |

## Home

### Purpose

The `Home` page is the main navigation hub. It provides page descriptions, report navigation, reset controls, and bookmarked insight views.

### Key Visuals

* Page descriptions
* Navigation buttons
* Reset buttons
* Bookmark-driven insight buttons

### Interactions

* Navigation buttons move users between report pages.
* Reset buttons return pages to their default states.
* Insight buttons apply bookmarked views for guided exploration.

### Metrics Shown

* None. This page is used for navigation and guided report access.

### Drillthrough / Bookmarks

* Uses bookmarks for reset states and insight views.
* Does not use drillthrough.

### Bookmarked Insight Views

Examples of guided bookmark views include:

* Highest Rated Episode
* Most Viewed Episode
* Weakest Winner
* Best Non-Winner
* Winner Age & Gender
* Most Handshakes
* Top Handshake Theme
* Most Common Theme Groups
* Oldest Bakers
* Female Handshake Ages
* Age 25-30 Demographics
* Age 25-29 Handshakes


## Viewership & Ratings

### Purpose

The `Viewership & Ratings` page shows how sample episode ratings and sample viewership changed across seasons and air dates.

### Key Visuals

* Sample viewership trend by air date and season
* Sample rating trend by air date and season
* Summary cards for selected time periods

### Interactions

* Users can drill down through time-based visuals.
* Selecting a year, season, or date range cross-filters the page.
* Summary cards update based on the selected context.

### Metrics Shown

* Average sample rating for selected episodes
* Total sample viewership for selected episodes

### Drillthrough / Bookmarks

* Uses visual drill-down.
* Does not use drillthrough to another page.

## Baker Directory

### Purpose

The `Baker Directory` page combines baker lookup and outcome analysis. It lets users browse bakers by season, placement, age, gender, handshakes, and key performance metrics.

### Key Visuals

* Baker outcome table
* Season selector and Baker input slicer
* Placement, gender, and age filters
* Rating and viewership cards for selected seasons

### Interactions

* Users can filter bakers by name, season, placement, gender, and age bin.
* Table selections cross-filter visible baker records.
* Users can drill through from a baker to the `Baker Profile` page.

### Metrics Shown

* Last episode reached
* Placement
* Age and gender
* Total handshakes
* Star Baker count
* Did Well count
* At Risk count
* Average sample rating for selected seasons
* Total sample viewership for selected seasons

### Drillthrough / Bookmarks

* Right-click a baker and select the `Baker Profile` drillthrough option.

## Baker Profile

### Purpose

The `Baker Profile` page provides a detailed view of one baker’s season performance, episode history, bakes, and outcomes.

### Key Visuals

* Baker information summary
* Baker image
* Outcome summary cards
* Episode-level Signature and Shostopper bake table
* Episode-level Technical bake and outcomes table
* Season winner reference
* Episode rating and viewership cards

### Interactions

* The page is filtered by the selected baker from drillthrough.
* Tables and cards update to show that baker’s season record.
* Users can return to the previous page after reviewing the profile.

### Metrics Shown

* Season, gender, and age
* Handshakes
* Star Baker count
* Did Well count
* At Risk count
* Absent count
* Episode theme
* Signature and Showstopper bakes
* Technical rank
* Challenge time
* Episode status
* Winner for the baker’s season
* Average sample rating for episodes the baker appeared in
* Total sample viewership for episodes the baker appeared in

### Drillthrough / Bookmarks

* Serves as a drillthrough destination from baker-focused pages.
* Uses a back button to return to the previous page.

## Demographics

### Purpose

The `Demographics` page analyzes bakers by age, gender, placement, and handshake-related demographic patterns.

### Key Visuals

* Baker totals by gender
* Baker totals by age bin
* Handshake totals by gender
* Handshake patterns by age bin
* Handshake patterns by season
* Demographic summary cards

### Interactions

* Slicer filter by placement.
* Selecting gender, age bin, season, or placement cross-filters related visuals.
* Cross-filtering helps compare overall baker demographics with handshake patterns.

### Metrics Shown

* Average age for selected bakers
* Total handshakes by cross-filters or slicer
* Handshake distribution across demographic groups

### Drillthrough / Bookmarks

* Users can drill through from selected gender or age bin views to the `Handshake Deep Dive` page.
* Reset buttons return the page to its default state.

## Theme Explorer

### Purpose

The `Theme Explorer` page shows how episode themes and broader theme groups appear across the show. It also supports analysis of where themes appear in the season and how challenge times vary by theme group.

### Key Visuals

* Season selector
* Episode selector
* Theme group treemap
* Theme and theme group tables
* Median challenge-time tool-tip

### Interactions

* Users can filter by season or episode.
* Selecting a theme group or theme cross-filters related visuals.
* Season and episode selectors narrow the theme analysis to specific parts of the show.

### Metrics Shown

* Number of episodes by theme group
* Theme and theme group distribution across selected seasons or episodes
* Signature, Technical, and Showstopper median challenge times

### Drillthrough / Bookmarks

* Users can drill through from selected Theme Group to the `Handshake Deep Dive` page.
* Uses slicers and cross-filtering.

## Handshake Deep Dive

### Purpose

The `Handshake Deep Dive` page provides a detailed view of individual handshake records and related baker outcomes.

### Key Visuals

* Season, placement, gender, and age filters
* Handshake detail table
* Baker-level handshake totals
* Handshake totals by theme group
* Outcome summary cards

### Interactions

* Slicers and table selections cross-filter handshake records.
* Users can review individual handshakes and baker-level handshake totals.
* The page connects handshakes to placement outcomes and demographic patterns.

### Metrics Shown

* Theme group
* Season and episode
* Baker
* Placement
* Individual handshake records
* Baker handshake totals
* Total handshakes
* Winner handshake totals
* Runner-up handshake totals
* Did Not Win handshake totals

### Drillthrough / Bookmarks

* Serves as a drillthrough destination from demographic, theme and handshake-focused views.
* Uses reset and back buttons for navigation.
