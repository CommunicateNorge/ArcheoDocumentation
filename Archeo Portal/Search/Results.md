
# Search Result

- [Search Result](#search-result)
  - [About search results](#about-search-results)
  - [Search result details](#search-result-details)
  - [Open or download content](#open-or-download-content)
  - [Metadata](#metadata)
  - [Resend](#resend)
  - [Add logstep](#add-logstep)
  - [Delete logstep](#delete-logstep)

## About search results

Based on your search the results of all transactions matching the search will be listed her. The list is ordered by the "First Processed" descending always showing the latest logged transactions. The coloring of the row is controlled by the status. The Status is set based on the latest steps status, if not a status is set to immutable, see [status](../Archeo%20Portal/Configuration/Statuses.mk) for more details. See [API](../Archeo%20API/Archeo%20Logging%20API.md) for more details about the logged values.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-Main.png)

## Search result details

Click on a row to expand the current transaction. All steps logged for this transaction are shown order by the "Processed" column.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-Details.png)

## Open or download content

To open file content press the filename link and the content will bee shown in the Archeo default viewer. To download the file click the icon to the left of the link.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-Download.png)

## Metadata

By default the metadata is available tru the link "Show" under the Metadata colum. This will open a view showing all logged metadata. 

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-Metadata.png)

It is possible to preview the metadata directly in the Metadata column. Notice that the max number of metatada in preview is 10 and if the metadata value is long it will be truncated.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-MetadataPreview.png)

Go to [API](../Archeo%20API/Archeo%20Logging%20API.md) for more details about  how to log metadata.

## Resend

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-Resend.png)

Every step is possible to resend. All the properties for this step, including a SASURI to the content is by default resent. The resend link opens a form where you select what webhook to use.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-ResendForm.png)

Go to [status](../Distribution%20Channels/Webhooks.mk) for more detail for more details about how to setup a webhook.

It is also possible to resend a batch. By selecting all the messages You like to resend, and select "Resend selected" on the "burger" menu top right, you will be able to resend up to 100 messages in one batch.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-ResendBatch.png)

In the resend form you must choose, what steps to resend based on status and position.

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-ResendBatchForm.png)

## Add logstep
It is possible to manually add a step to a transaction flow. This can be useful if want to change the status or add addition information to a flow. Eg if you have handled an error manually and you like to reflect this to the flow. Select the transactions you want to add step to and select "Add logstep for selected" from the "burger" menu top right:

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-AddStepMenu.png)

In the form you can add a description and the Status for the added step:

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-AddStepForm.png)

## Delete logstep

To delete one or more transactions select them and click "Delete selected" from the "burger" menu top right:
(Note: The deletion can not be undone)

![img](https://archeodocstorage.blob.core.windows.net/images/Search-Result-DeleteMenu.png)
