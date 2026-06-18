# Power Query Notes

This document summarizes the main Power Query cleaning and transformation steps used to prepare the Great British Bake Off Power BI dashboard data model. Each query followed the same general pattern: source import, promoted headers, data type updates, key creation, and query-specific cleaning or transformation steps.

## Bakers Query

The `Bakers` query prepares baker-level information for the dashboard.

### Key Steps

* Imported the source data.
* Promoted the first row to headers.
* Updated column data types.
* Added `BakerSeasonKey` to uniquely identify each baker within a season.
* Used the key column to support model relationships and baker-level filtering across related tables.

## Episodes Query

The `Episodes` query prepares episode-level information, theme groupings, ratings, viewership, and time-related fields.

### Key Steps

* Imported the source data.
* Promoted the first row to headers.
* Updated column data types.
* Added padded key fields:

  * `EpisodePad`
  * `SeasonPad`
  * `SeasonEpisodePad`

* Standardized inconsistent theme values to make theme labels more uniform.
  * Standardized singular/plural theme wording such as  `Biscuits` / `Biscuit` and `Dessert` / `Desserts`.
  * Removed accent inconsistencies where the same theme appeared with and without an accent.

* Added `Theme Group` to combine related themes into broader categories for cleaner visuals.
* Created missing-value flags for each time field:

  * Signature time missing flag
  * Technical time missing flag
  * Showstopper time missing flag

* Merged with the `ThemeGroup Median Times` helper query.
* Filled null time values using the median time for the matching theme group.
* Added day name.
* Renamed rating and viewership fields for clearer dashboard use.

## Outcomes Query

The `Outcomes` query prepares baker outcome data for modeling relationships and analysis.

### Key Steps

* Imported the source data.
* Promoted the first row to headers.
* Updated column data types.
* Added key fields:

  * `Season`
  * `Episode`
  * `SeasonPad`
  * `EpisodePad`
  * `SeasonEpisodePad`
  * `BakerSeasonEpisodeKey`
  * `BakerSeasonKey`
* Used the key columns to connect outcome records to baker, season, episode, and challenge-level data.

## Seasons Query

The `Seasons` query prepares season-level information for the dashboard.

### Key Steps

* Imported the source data.
* Promoted the first row to headers.
* Updated column data types.
* Removed judge and host columns because they duplicated season-level records and were not used in the analysis.
* Removed duplicate rows to keep one clean record per season.

## ChallegeBakes Query

The `ChallegeBakes` query prepares challenge-level baking data for relationships, filtering, and visual analysis.

### Key Steps

* Imported the source data.
* Promoted the first row to headers.
* Updated column data types.
* Added padded key fields:

  * `EpisodePad`
  * `SeasonPad`
  * `SeasonEpisodePad`
* Added relationship keys:

  * `BakerSeasonEpisodeKey`
  * `BakerSeasonKey`
* Used these keys to connect challenge records to baker, season, episode, and outcome data.

## ThemeGroup Median Times Query

The `ThemeGroup Median Times` query is a helper query used to support missing-value handling for episode time fields.

### Key Steps

* Created the query by duplicating the source of the `Episodes` query.
* Removed unnecessary columns and kept only theme group and time-related fields.
* Grouped records by `Theme Group`.
* Calculated median time values for each theme group.
* Changed median time fields to integer data types.
* Used the resulting median values to fill null time fields in the `Episodes` query.
