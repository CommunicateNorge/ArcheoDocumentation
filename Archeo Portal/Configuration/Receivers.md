
# Receivers

- [Receivers](#receivers)
  - [About Receiver](#about-receiver)
  - [Create Receiver](#create-receiver)
  - [Edit Receiver](#edit-receiver)
  - [Delete Receiver](#delete-receiver)
  - [Example](#example)

## About Receiver

Receivers are automatically created if they do not exist in Archeo. You may add or edit receiver manually. Reveivers are typically used to name the endpoint for this log.
Click Administration menu → Receivers

## Create Receiver

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Receiver-New.png)

To add a new receiver type enter a name and click "add".

## Edit Receiver

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Receiver-Edit.png)

To edit a existing receiver click "edit".

## Delete Receiver

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Receiver-Delete.png)

To delete an existing receiver click "delete".

## Example

Example value for the receiver used in the json data format supplied to the API.

```json
[
  {
    "transactionId": "4163EBF5-0489-4569-B3BF-9D779593EE7B",
    "transactionType": "DeliveryMessage",
    "messageType": "PapinetEnvelope",   
    "processed": "2022-01-15T10:23:32.2407737+00:00",   
    "status": "Success",
    "Receiver": "SAP"
  }
]
```
