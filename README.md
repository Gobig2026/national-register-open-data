# National Register of Historic Places open data

One free CSV of records from the US National Register of Historic Places: 99,881 rows, covering 99,845 listed records and 36 removed from the Register since 22 May 2026. Removals before that date are not in the file. Reference number, name, category, address, county, state, listing date, National Historic Landmark date, status, coordinates where public, Wikidata ID and nomination link.

Snapshot made 20 November 2026. The National Park Service spreadsheets it is built on run to 22 May 2026. Later listings and removals come from the National Park Service weekly lists, which run to 13 November 2026.

## File

`places.csv` (UTF-8, comma separated, 18 columns). Columns are described in [DATA_DICTIONARY.md](DATA_DICTIONARY.md).

| | Rows |
|---|---|
| Listed | 99,845 |
| Removed from the Register (since 22 May 2026 only) | 36 |
| Location restricted (street, town, coordinates, Wikidata ID and nomination link left blank) | 5,696 |
| With coordinates | 92,616 |
| Not restricted but no coordinates | 1,569 |
| No listing date in the source | 154 |

## What is not here

- No photographs.
- No Wikipedia text.
- No email addresses or other contact details. Some place names include owners' names, as listed in the public Register.
- No street, town, coordinates, Wikidata ID or nomination link for places the National Park Service restricts.
- 203 later or extra National Register records of places already in the file are left out. A row is a National Register record, not always a separate place: about 1,000 rows are boundary increases, decreases or additional documentation for another listing, and some Wikidata IDs are shared by related records.
- 33 coordinates that did not pass our checks (outside the listed state or county, with no trusted replacement) are left blank.

## Coordinates

Most points come from National Park Service spatial data: a point, or the centre of the property boundary. 350 points were wrong in the source (for example a point in another county) and were replaced after checking against public sources: Wikidata (CC0), Wikipedia, the US Census Bureau geocoder, the Historical Marker Database, Waymarking, and state park, state agency and local historical society pages. We publish only the coordinate numbers, not text or maps from those sources. Those rows say `Atlas correction` in `coordinates_source`. We did not use OpenStreetMap or Google data.

No coordinates: 381 places added from the weekly lists, 33 points that failed our checks, and the rest have no point in the National Park Service data.

## Sources

- National Register listing data and most coordinates: National Park Service.
- Wikidata identifiers: Wikidata, CC0.

## Licence and credit

Creative Commons Attribution 4.0 International (CC BY 4.0), see [LICENSE](LICENSE). Please credit: "Data: Historic Places Atlas, CC BY 4.0. Built on National Register of Historic Places data from the National Park Service and Wikidata identifiers. Downloaded [date]." To cite the dataset, use [CITATION.cff](CITATION.cff).

## Accuracy and corrections

The official National Register is kept by the National Park Service, and its files are the authority. Check the official record before relying on a listing status, date or location. If you find an error, please open an issue on this repository.

## About

Maintained by [Historic Places Atlas](https://historicplacesatlas.com), an independent site. It is not affiliated with the National Park Service. The `atlas_url` column links each row to its place page there.
