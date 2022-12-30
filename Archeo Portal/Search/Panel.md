
# Search panel

- [Search panel](#search-panel)
  - [About search panel](#about-search-panel)
  - [Search filters](#search-filters)
  - [Advanced search filters](#advanced-search-filters)
  - [Saved search](#saved-search)
  - [Create alert from search parameters](#create-alert-from-search-parameters)
  - [Copy search link to clipboard](#copy-search-link-to-clipboard)

## About search panel

Use search panel to identify your messages and flows. Search provides a set of filters with powerful freetext search to quickly find what you are looking for. Mix and match filter for most precise hits.

## Search filters

Use filters to narrow down your search. The "Search" button performs the search, and lists all results in a grid. The "Clear all" button clears the current filters to the default settings.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Filter.png)

|Filter  |Description   |
|------|---|
|Search|Search in all content, descriptions and metadata. Use double quotes to search for a phrase. "This is a quote" will search for the exact match. No quotation marks will show matches for all individual words. Punctuation or hyphen will act as space, use double quotes like "order123.xml" to address this in searches |
|From |Date/time first logging received|
|To |Date/time last logging received|
|Transaction Id|The id of the log, will return one or none rows. Discards all other filters |

## Advanced search filters

Advanced filters gives the user options to drill even more down in the results based on filters. The dropdown-boxes will only contain the selections you have rights to searches for.

The filters are available by the "burger" menu item "Show Advanced Search" top left:

![img](https://archeodocstorage.blob.core.windows.net/images/Search-BurgerMenu.png)

![img](https://archeodocstorage.blob.core.windows.net/images/Search-FilterAdvanced.png)

|Filter  |Description   |
|---------|---|
|Transaction Tag |Explicit search for the logged transaction tag|
|Transaction type |Dropdown with available transaction types. Filters transactions based on selection|
|Message type |Dropdown with available message types. Filters transactions based on selection|
|Sender  |Dropdown with available senders. Filters transactions based on selection|
|Receiver  |Dropdown with available receivers. Filters transactions based on selection|
|Status  |Dropdown with available statuses. Filters transactions based on selection|

## Saved search

To save a search, create a search using the available filters and save the created search through the three dots next to the search button:

![img](https://archeodocstorage.blob.core.windows.net/images/Search-SaveSearch.png)

Enter a name for the search and it will be available for quick searches in the future.
To edit a saved search, select the saved search, adjust the search filters and select "Save search", the "edit search" form will have pre-filled the name of the current saved search. Click "Save" and the current saved search will be updated. Note that if you rename the saved search it will be saved as anew.

## Create alert from search parameters

Available form the "burger" menu top right. Only available ig you are member of the "Administrator" or "Owner" usergroup.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-BurgerMenu.png)

Archeo support Alerts, for more details see [alerts](../Archeo%20Portal/Alerts.md). Alerting are based on a search and you can create an alert based on the search you have created. This will take you to the alert creation page, where all the filters and parameters are pre-filled, to swiftly create an Alert.  

## Copy search link to clipboard

Available form the "burger" menu top right

![img](https://archeodocstorage.blob.core.windows.net/images/Search-BurgerMenu.png)

This selection copy current search to your clipboard, this may come in handy if you want to share a specific search with a colleague.
