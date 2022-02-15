# Statuses

- [Statuses](#statuses)
  - [About Status](#about-status)
  - [Create Status](#create-status)
  - [Edit Status](#edit-status)
  - [Delete Status](#delete-status)
  - [Example](#example)

## About Status

Logging with Status is not mandatory but recommended. The main status for a transaction is set based on latest status logged.
Click Administration menu → Status. CRUD operations is also available from the [configuration api](../../Archeo%20API£Archeo%20Configuration%20API.md)

## Create Status

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Status-New.png)

To add a new status type enter a "Name" (required) and set "Immutable" then click "add". If the "Immutable" flag is set, this status will be immutable to change by a status logged later. If both are "immutable" the last logged will be set on main transaction.  If using status when logging the status must be pre-created in the subscription or a error will be thrown from the [logging API](../../Archeo%20API/Archeo%20Logging%20API.md).

## Edit Status

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Status-Edit.png)

To edit a existing transaction type  click "edit". Since the logging API are using name, remember that a change of name may affect the logging. All existing statuses are listed with editing capabilities for the name, immutable and the color shown in a search result. 

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Status-EditColor.png)

When a user performs a search, rows will be highlighted with the rows status chosen color.

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Status-ColorInSearch.png)

## Delete Status

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Status-Delete.png)

To delete an existing status click "delete". Remember that a deleting may affect the logging if the status is used when logging.

## Example

Example value for the status used in the json data format supplied to the API.

```json
[
  {
    "transactionId": "4163EBF5-0489-4569-B3BF-9D779593EE7B",
    "transactionType": "DeliveryMessage",
    "messageType": "PapinetEnvelope",   
    "processed": "2022-01-15T10:23:32.2407737+00:00",   
    "status": "Success"
  }
]
```
