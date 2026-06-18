# Dashboard Pages

This document summarizes the report pages and main interactions used in the Great British Bake Off Power BI dashboard. The report uses slicers, cross-filtering, drill-through pages, reset buttons, navigation buttons, and bookmarked insight views.

## Report Navigation Summary

| Page                   | Purpose                                                  | Main Interaction                                           |
| ---------------------- | -------------------------------------------------------- | ---------------------------------------------------------- |
| Home                   | Navigate the report and access saved views               | Use buttons for page navigation, resets, and insights      |
| Viewership & Ratings   | Explore rating and viewership trends                     | Drill down by air date, year, and season                   |
| Baker Directory        | Browse bakers by season                                  | Select a baker and drill through to Baker Profile          |
| Baker Profile          | Review detailed baker-level stats                        | View one baker’s performance, episodes, ratings, and views |
| Handshake Demographics | Analyze handshakes by gender, age, season, and placement | Use slicers and visual selections to cross-filter patterns |
| Baker Outcomes         | Compare baker performance outcomes                       | Filter baker stats and drill through to Baker Profile      |
| Theme Explorer         | Explore episode themes and theme groups                  | Filter by season, episode, theme, and theme group          |
| Handshake Deep Dive    | Review detailed handshake records                        | Filter individual handshake records and outcome totals     |

## Home

### Purpose

The `Home` page is the main navigation hub. It provides page descriptions, quick navigation, reset controls, and bookmarked insight views.

### Key Visuals

* Page description cards
* Navigation buttons
* Reset buttons
* Insight buttons

### Interactions

* Navigation buttons move users between report pages.
* Reset buttons return pages to their default state.
* Insight buttons apply bookmarked views for guided exploration.

### Metrics Shown

* None. This page is used for navigation.

### Drill-through / Bookmarks

* Uses bookmarks for reset states and insight views.
* Does not use drill-through.

## Viewership & Ratings

### Purpose

The `Viewership & Ratings` page shows how episode ratings and viewership changed across seasons and air dates.

### Key Visuals

* Viewership trend by air date and season
* Rating trend by air date and season
* Summary cards for selected time periods

### Interactions

* Users can drill down through time-based visuals.
* Selecting a year, season, or date range cross-filters the page.
* Summary cards update based on the selected context.

### Metrics Shown

* Average rating for selected episodes
* Total viewership for selected episodes

### Drill-through / Bookmarks

* Uses visual drill-down.
* Does not use drill-through to another page.

## Baker Directory

### Purpose

The `Baker Directory` page lets users browse bakers by season and open detailed baker profiles.

### Key Visuals

* Baker list or table
* Season filter
* Baker summary fields
* Rating and viewership cards for selected seasons

### Interactions

* Users can filter bakers by season.
* Selecting a baker cross-filters related visuals.
* Users can drill through to the `Baker Profile` page.

### Metrics Shown

* Average rating for selected seasons
* Total viewership for selected seasons
* Baker identifying information

### Drill-through / Bookmarks

* Right-click a baker and select the Baker Profile drill-through option.

## Baker Profile

### Purpose

The `Baker Profile` page provides a detailed view of one baker’s season performance and episode history.

### Key Visuals

* Baker information summary
* Outcome stats
* Episode-level bake and status table
* Season winner reference
* Episode rating and viewership cards

### Interactions

* The page is filtered by the selected baker from drill-through.
* Tables and cards update to show that baker’s season record.

### Metrics Shown

* Season, gender, and age
* Handshakes, Star Baker, Did Well, At Risk, and Absent counts
* Episode theme, bake details, challenge time, and episode status
* Winner for the baker’s season
* Average rating and total viewership for episodes the baker appeared in

### Drill-through / Bookmarks

* Serves as a drill-through destination from baker-focused pages.
* Users can return to the previous page after reviewing the profile.

## Handshake Demographics

### Purpose

The `Handshake Demographics` page explores how Paul Hollywood handshakes are distributed by gender, age, season, and placement.

### Key Visuals

* Handshake totals by gender
* Handshake patterns by age bin
* Handshake patterns by season
* Demographic summary cards

### Interactions

* Slicers filter by placement and other demographic fields.
* Selecting gender, age bin, or season cross-filters related visuals.
* Cross-filtering helps compare overall baker demographics with handshake patterns.

### Metrics Shown

* Average age for the selected group
* Total handshakes by selected gender, age bin, season, and/or placement
* Handshake distribution across demographic groups

### Drill-through / Bookmarks

* Users can drill through from gender, age bin, or season to the `Handshake Deep Dive` page.

## Baker Outcomes

### Purpose

The `Baker Outcomes` page compares baker performance outcomes across demographic groups, seasons, and placements.

### Key Visuals

* Baker outcome table
* Gender, age bin, season, and placement slicers
* Baker performance fields

### Interactions

* Slicers filter the baker outcome table.
* Table selections cross-filter visible records.
* Users can drill through from a baker to the `Baker Profile` page.

### Metrics Shown

* Handshakes received
* Star Baker count
* Did Well count
* At Risk count
* Placement and demographic fields

### Drill-through / Bookmarks

* Right-click a baker and select the Baker Profile drill-through option.

## Theme Explorer

### Purpose

The `Theme Explorer` page shows how episode themes and broader theme groups appear across the show.

### Key Visuals

* Season slicer
* Episode slicer
* Theme group treemap
* Theme-level filtering visuals

### Interactions

* Users can filter by season, episode, theme, or theme group.
* Selecting a theme group cross-filters related visuals.

### Metrics Shown

* Number of episodes by theme group
* Theme and theme group distribution across selected seasons or episodes

### Drill-through / Bookmarks

* Uses slicers and cross-filtering.
* Does not use drill-through as a main interaction.

## Handshake Deep Dive

### Purpose

The `Handshake Deep Dive` page provides a detailed record-level view of individual handshakes and related baker outcomes.

### Key Visuals

* Gender, age bin, season, and placement slicers
* Handshake detail table
* Baker-level handshake totals
* Outcome summary totals

### Interactions

* Slicers and table selections cross-filter handshake records.
* Users can review both individual handshakes and baker-level totals.
* The page connects handshakes to placement outcomes.

### Metrics Shown

* Theme, season, episode, baker, and placement
* Individual handshake records
* Baker handshake totals
* Total handshakes
* Winner, runner-up, and Did Not Win handshake totals

### Drill-through / Bookmarks

* Serves as a drill-through destination from the `Handshake Demographics` page.
