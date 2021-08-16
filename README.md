# Module 11 Challenge - UFOs - JavaScript

## Overview

The purpose of this project is to update and republish a previously created webpage.

Both versions of the webpage display an HTML Table containing summary information
about UFO Sightings.

Version 1.0 of the webpage included a dynamic HTML Table with a date filter entry box
and a `Filter Table` action button that filtered and refreshed the table on `<Click>`.

Version 2.0 specifications indicated that the webpage should be updated to include
additional filters for `City`, `State`, `Country`, and `Shape`.
The HTML Table should be filtered and refreshed whenever new values are entered
into any of these filter entry boxes. For a cleaner interface, the original
`Filter Table` action button was removed.

### Deliverables

1. Updated Version 2.0 of webpage which filters UFO Sightings on multiple criteria.
2. This written report (README.md)

### Resources

- Software:
	- Bootstrap 3 CSS Components loaded from Cloud via HTML
	- D3.js JavaScript Library loaded from Cloud via HTML
- Data:
	- `data.js`: ANSI-ASCII Data File provided by client. Contains a single JavaScript Array `data`, which itself contains information pertaining to 111 purported UFO Sightings between January 1, 2010 and January 13, 2010. Each entry is described in 7 Fields: `datetime`, `city`, `state`, `country`, `shape`, `durationMinutes`, and `comments`. Additional information about these fields is summarized below in Table 1.
- Other Resources:
	- `index.html`: Webpage created in Module 11 Exercises. Copied and modified to remove `Filter Table` action button, and to add filter entry input boxes for additional criteria indicated in Version 2.0 webpage specifications.
	- `ufo_starterCode.js`: JavaScript code template provided by client. Copied and renamed `app.js`. `app.js` was modified to include source code to perform functions indicated in Version 2.0 webpage specifications.
	- `nasa.jpg`: Image provided by client for use as webpage Jumbotron background. Presumably obtained from NASA from the filename, but source is unattributed.

**Table 1: data.js Fields**
| Field Name               | Brief Description of Field and Contents|
|--------------------------|----------------------------------------|
| `datetime`               | Gregorian Calendar date, Formatted as 'mm/dd/yyyy'
| `city`                   | City of observation [lowercase]
| `state`                  | State or Province of observation [lowercase]
| `country`                | Country of observation [lowercase]
| `shape`                  | Shape of observation [lowercase]
| `durationMinutes`        | Description of duration of observation, in minutes. Field is free text, and standards on original input have been loosely enforced. [lowercase, limited format orthodoxy]
| `comments`               | Free Text comment providing additional information on observation. [Mixedcase, limited format orthodoxy]

#### Data Quality
One drawback as far as data quality is concerned of `data.js` is that the last three fields (`shape`, `durationMinutes`, and `comments`) are free text. This limits the possibilities for consistent analysis due to the wide-range of possible entries at the source. `shape`, for instance, currently has 18 different unique entries, one of which is 'unknown'. While this certainly may reflect the recollection of the UFO observer, it gives no useful information to the analyst. `durationMinutes` has entries as widely varying as 'unknown', 'not sure', '3 min', 'several hours', '10-15 seconds', to 'noticed from dusk to dawn'. If these time values are to be at all useful in future analysis, they should be significantly cleaned in a semi-automatic/manual process, and standards on input format should be more strictly enforced at time of collection. Furthermore it should be noted that there are Two (2) data entries in `durationMinutes` that are not enclosed in quotes to conform with the rest of the standard within `data.js`. They are presented as bare integers in the dataset. At present this causes no complication, but if they were attempted to be parsed as Strings, an unexpected result may occur.

## Results

With the new Version 2.0 of the webpage working as requested, a user now has much greater flexibility to perform their own explorations of the provided data, at will.

The filter entry boxes are designed to be flexible and intuitive. If no user-specified filters are entered, the entire table of data is shown. If additional filtering is desired,
any combination of the filter boxes can be used in concert to show only observations of interest. The HTML Table is refreshed on `<Enter>` or `<Tab>`. To re-display the original table, clear the text in all the filter boxes, or refresh the page. Figures 1 & 2 below gives an example of what this looks like in practice.

**Figure 1: Webpage with No Filters Applied**

![Figure 1](/Resources/Figure_01.png "Figure 1")

**Figure 2: Webpage with Filter Applied**

![Figure 2](/Resources/Figure_02.png "Figure 2")

## Summary

One drawback of the current version of the webpage, is there is no export functionality. If a user finds some results they find particularly interesting and would like to investigate further at a later time, they must either record it manually, or resort to copying the HTML Table directly. Some more tech-savvy users may have no problem performing this task, but it may be less obvious to someone less familiar. A nice feature of the webpage would be to export the current view to a CSV and allow the user to save it locally to their computer.

Another drawback is in the quality of the original data itself. As noted in the ***Data Quality*** Section above, the last three Fields are free text with loosely enforced standards of data consistency. In Version 2.0 of the webpage, these fields are not incorporated into the Filter Search; however, if a future version of the webpage incorporated any or all of these fields into the search capability, there would have to be much more consistent formatting of records in order to achieve consistent and accurate search results. Alternatively, the parsing of these records would have to include more sophisticated pattern-matching on filter rather than simple equivalency.

### Recommendations for Further Development

1. Incorporate a File Export Functionality for End Users
2. Re-Incorporate at least one Button to improve the User Experience. It may not be immediately clear to new users how to clear their filters and re-display the original dataset. If a `Clear Filters` button was incorporated below the search boxes, it would be immediately clear what its function was. Additionally, *role* descriptive text could be included with the button to improve Accessibility of the webpage for visually impaired users.
