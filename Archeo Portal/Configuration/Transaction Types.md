# Transaction Types

- [Transaction Types](#transaction-types)
  - [About Transactiontype](#about-transactiontype)
  - [Create Transactiontype](#create-transactiontype)
  - [Edit Transactiontype](#edit-transactiontype)
  - [Delete Transactiontype](#delete-transactiontype)
  - [Example](#example)

## About Transactiontype

Transaction types are the top level definition of a business process. The Transaction types are created in the administration web interface and used when logging to the logging API. The name you choose for your transaction type is the value you use when logging to Archeo using our API. The field in the API used for this is the TransactionType field.
Click Administration menu → Transaction Types. CRUD operations is also available from the [configuration api](../../Archeo%20API/Archeo%20Configuration%20API.md)

## Create Transactiontype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-TransactionType-New.png)

To add a new transaction type enter a "Name" (required) and "Data Retention Time" and click "add". Transactiontype is required when logging to Archeo and need to be predefined for the subscription before the [logging API](../../Archeo%20API/Archeo%20Logging%20API.md)  will accept the log. "Data Retention Time" is the time in days data for this transaction type will be kept in the system. All transactions older will automatically be deleted from Archeo.

## Edit Transactiontype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Messagetype-Edit.png)

To edit a existing transaction type  click "edit". Since the logging API are using name, remember that a change of name may affect the logging.

## Delete Transactiontype

![img](https://archeodocstorage.blob.core.windows.net/images/Configuration-Messagetype-Delete.png)

To delete an existing transaction type  click "delete". Remember that a deleting may affect the logging ig the massage type is used when logging.

## Example

Example value for the transactiontype used in the json data format supplied to the API.

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
