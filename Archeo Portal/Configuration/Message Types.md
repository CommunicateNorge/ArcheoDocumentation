
# Message Types

- [Message Types](#message-types)
  - [About Messagetypes](#about-messagetypes)
  - [Create Messagetype](#create-messagetype)
  - [Edit Messagetype](#edit-messagetype)
  - [Delete Messagetype](#delete-messagetype)
  - [Example](#example)

## About Messagetypes

A message type is the type of the message logged in a transaction. One transaction may consist of many message types.
The message types are created in the administration web interface and used when logging to the logging API.
Click Administration menu → Message Types. CRUD operations is also available from the [configuration api](../../Archeo%20API/Archeo£20Configuration%20API.md)

## Create Messagetype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Messagetype-New.png)

To add a new message type enter a name and click "add". If using messagetype when logging the type must be pre-created in the subscription or a error will be thrown from the [logging API](../../Archeo%20API/Archeo%20Logging%20API.md).

## Edit Messagetype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Messagetype-Edit.png)

To edit a existing message type  click "edit". Since the logging API are using name, remember that a change of name may affect the logging.

## Delete Messagetype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Messagetype-Delete.png)

To delete an existing message type  click "delete". Remember that a deleting may affect the logging ig the massage type is used when logging.

## Example

Example value for the messagetype used in the json data format supplied to the API.

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
