# Data dictionary: places.csv

One row per property. UTF-8 with a byte order mark (so Excel reads accented letters correctly), comma separated, rows end with CRLF, text fields with commas are quoted. A text cell that begins with =, +, @ or a dash followed by a letter has a leading apostrophe added so spreadsheets do not read it as a formula. Blank means no value.

| Column | Meaning |
|---|---|
| nrhp_reference | National Park Service reference number, 8 digits (more for newer listings). Keep it as text: leading zeros matter. |
| name | Name as listed |
| category | building, district, site, structure or object, as in the source. Case varies between rows (for example BUILDING and building) and 427 rows have no category, so lower-case it before counting. |
| street | Address as listed. Blank where the location is restricted, including places the source marks "Address Restricted". |
| city | Town as listed. Blank where the location is restricted. |
| county | County as listed |
| state | State, territory or district as listed (62 values: states, territories, the District of Columbia and a few other areas such as Morocco and Territorial Waters) |
| listed_date | Date listed, YYYY-MM-DD. Blank for 154 rows with no listing date in the source. |
| landmark_designated | National Historic Landmark designation date, YYYY-MM-DD, where there is one |
| status | `listed`, or `removed` if the National Park Service has removed it from the Register |
| removed_date | Date of removal, YYYY-MM-DD, where known |
| latitude, longitude | Decimal degrees, WGS 84, six decimals. Blank where the location is restricted, not available or did not pass our checks. |
| coordinates_source | `NPS point` (a point in National Park Service spatial data), `NPS boundary centre` (centre of the property boundary), or `Atlas correction` (the source point was wrong; replaced by a checked point from a named public source) |
| location_restricted | `yes` where the National Park Service restricts the location, otherwise `no` |
| wikidata_id | Matching Wikidata item, for example Q108780739. Blank where restricted or not matched. |
| nomination_url | Link to the digitized nomination in the National Archives catalog. Blank where restricted or not available. |
| atlas_url | The place's page on Historic Places Atlas |

## Notes

- Restricted places keep their name, category, county, state and dates. Nothing that points to the location is given.
- A row is a National Register record. 203 duplicate records are removed, but about 1,000 rows are boundary increases, decreases or additional documentation for another listing, so a place can have related rows and shared Wikidata IDs.
- Removed places: only removals since 22 May 2026 (36). Earlier removals are not included.
- Places added from the National Park Service weekly lists (381 since 22 May 2026) have no coordinates or Wikidata ID yet. In total 1,569 unrestricted rows have no coordinates.
- Coordinates are checked against the listed state and county, and a point outside either is not published unless we checked it by hand (some listed counties in the source are wrong, so a few points sit outside their listed county).
- Nothing here is a legal or official statement of Register status.
