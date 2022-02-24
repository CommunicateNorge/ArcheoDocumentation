
# Archeo logging API

- [Archeo logging API](#archeo-logging-api)
  - [About logging API](#about-logging-api)
  - [Generate API Key](#generate-api-key)
  - [Logging to Archeo API](#logging-to-archeo-api)
  - [How to log to Archeo with Postman](#how-to-log-to-archeo-with-postman)
  - [How to log to Archeo using C](#how-to-log-to-archeo-using-c)
  - [API Responses](#api-responses)

## About logging API

This is the public Archeo API. This is the primary interface for supplying logs to your Archeo subscription. Don't have a subscription? Create your free trial today at <http://www.archeo.no>.

## Generate API Key

If you do not have a Archeo user, you need to create this as a first step. A trial subscription will be created alongside with this registration. The API Key is created in the Archeo Portal see [API Keys](../Archeo%20Portal£API%20keys.md)

## Logging to Archeo API

The public API: <https://api.archeo.no/swagger/>

Model of the logstep data model used in logging:

```json
[
  {
    "transactionId": "string",
    "transactionType": "string",
    "messageType": "string",
    "transactionTag": "string",
    "processed": "2022-02-03T10:43:59.399Z",
    "sender": "string",
    "receiver": "string",
    "description": "string",
    "fileName": "string",
    "bodyContent": "string",
    "contentURI": "string",
    "status": "string",
    "metadata": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    }
  }
]
(Required: transactionId, transactionType and processed) 
```

The API consumes a list of the log steps. Note, that if any steps fail validation, the entire batch will be discarded.

JSON example:

```json
[
  {
    "transactionId": "Unique chosen id for this transaction.",
    "transactionType": "My Transaction Type",
    "messageType": "My Message Type",
    "transactionTag": "Unique self chosen id for this message log",
    "processed": "2019-01-25T09:08:42.3761485+00:00",
    "sender": "Sender of the message",
    "receiver": "Receiver of the message",
    "description": "(Optional) Descriptive info message",
    "fileName": "Filename of transaction",
    "contentURI": "https://myaccount.blob.core.windows.net/sascontainer/sasblob.txt?sr=b&sp=rw&sig=Z%2FRHIX5Xcg0Mq2rqI3OlWTjEg2tYkboXr1P9ZUXDtkk%3D",
    "status": "Success",
    "metadata": {
      "InboundAdapter": "REST",
      "OnboundAdapter": "FTP"      
    }
  }
]

```

## How to log to Archeo with Postman

Add the API-Key in header:

![img](https://archeodocstorage.blob.core.windows.net/images/Logging-Postman.png)

Post to the API based on the model. Note; the transaction type and the status needs to be pre-configured in Archeo as described earlier.

![img](https://archeodocstorage.blob.core.windows.net/images/Logging-Postman02.png)

## How to log to Archeo using C#

Create a class to represent the Model

```c#
public class LogStep
  {
      public string AuthGuid { get; set; }
      public string TransactionId { get; set; }
      public string TransactionType { get; set; }
      public string MessageType { get; set; }
      public string TransactionTag { get; set; }
      public DateTime Processed { get; set; }
      public string Sender { get; set; }
      public string Receiver { get; set; }
      public string Description { get; set; }
      public string FileName { get; set; }
      public byte[] BodyContent { get; set; }
      public string Status { get; set; }
  }
```

Add data to the model:

```c#
  LogStep step = new LogStep();
  step.TransactionId = tranid;
  step.TransactionType = "Ordre";
  step.MessageType = "Ordre";
  step.Processed = DateTime.Now;
  step.Status = "Started";
  step.BodyContent = GetContent(@"C:\Demo\Order.xml");
  step.FileName = "ordre.xml";
  step.Description = "Ordre mottat MessageHub";
  step.Sender = "Nille";
  step.Receiver = "Message Hub";
  step.TransactionTag = "10001";
  listOfSteps.Add(step);
```

Add item(s) to a list, set APIKey and Log to REST service:

```c#
  HttpClient.BaseAddress = new Uri("https://api.archeo.no/api/v1.1/");
  HttpClient.DefaultRequestHeaders.Accept.Clear();
  HttpClient.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue(“application/json”));
  HttpClient.DefaultRequestHeaders.Add(“APIKEY”, APIKey);
  var response = HttpClient.PostAsync(“Log”, new StringContent(JsonConvert.SerializeObject(LogItemAsList), Encoding.UTF8, “application/json”)).Result;
```

## API Responses

![img](https://archeodocstorage.blob.core.windows.net/images/Logging-APIResonse.png)
