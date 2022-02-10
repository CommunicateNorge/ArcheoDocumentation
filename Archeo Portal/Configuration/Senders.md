
# Senders

- [Senders](#senders)
  - [About Sender](#about-sender)
  - [Create Sender](#create-sender)
  - [Edit Sender](#edit-sender)
  - [Delete Sender](#delete-sender)
  - [Example](#example)

## About Sender

Senders are automatically created if they do not exist in Archeo. You may add or edit Sender manually. Reveivers are typically used to name the endpoint for this log.
Click Administration menu → Senders

## Create Sender

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Sender-New.png)

To add a new Sender type enter a name and click "add".

## Edit Sender

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Receiver-Edit.png)

To edit a existing Sender click "edit".

## Delete Sender

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Receiver-Delete.png)

To delete an existing Sender click "delete".

## Example

Example value for the Sender used in the json data format supplied to the API.

```json
[
  {
    "transactionId": "4163EBF5-0489-4569-B3BF-9D779593EE7B",
    "transactionType": "DeliveryMessage",
    "messageType": "PapinetEnvelope",   
    "processed": "2022-01-15T10:23:32.2407737+00:00",   
    "status": "Success",
    "Sender": "ConnXio"
  }
]
```
