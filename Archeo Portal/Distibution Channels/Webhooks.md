# Webhooks

- [Webhooks](#webhooks)
  - [About Webhooks](#about-webhooks)
  - [Create Webhook](#create-webhook)
    - [Name](#name)
    - [Rest Endpoint](#rest-endpoint)
    - [Payload](#payload)
      - [Alert payload](#alert-payload)
      - [Resend payload](#resend-payload)
      - [Predefined templates](#predefined-templates)
    - [Apim Subscription Key](#apim-subscription-key)
    - [Authorization Header Type](#authorization-header-type)
      - [NONE](#none)
      - [Basic](#basic)
      - [Oauth2](#oauth2)
  - [Mange Webhooks](#mange-webhooks)

## About Webhooks

A webhook (also called a web callback or HTTP push API) is a way for Archeo to provide information. A webhook delivers data to other applications as it happens, and Archeo supports Resending and Alerts for the time being.

## Create Webhook

To create a new webhook, use hte button "Add new webhook".

![img](https://archeodocstorage.blob.core.windows.net/images/DistributionChannels-Webhooks-Create.png)

### Name

Give it a name, only used in the portal

### Rest Endpoint

The webhook endpoint, a REST Service Endpoint is an endpoint which services a set of REST resources

### Payload

The payload is the body in the HTTP request and response message. If not selected or select the "Default alert/resend template",  the default template is used. Dependent if the webhook is used for alerting og resend different default payload are used.

We are using Liquid template language for defining payload. See [liquid](https://shopify.github.io/liquid/) for more information.
The payload need to validate as Json when transformed.
We support some properties (caseinsensetive) depending on used in alerts or resend. You may define your own payload by using Liquid.

#### Alert payload

Properties:

- alertName
- description
- hits
- threshold
- alertTime
- searchUrl
- subscriptionName

Default alert payload:

```json
{ 
    "AlertName": "{{alertName}}",
    "Description": "{{description}}",
    "Hits": "{{hits}}",
    "Threshold": "{{threshold}}",
    "AlertTime": "{{alertTime}}",
    "SearchUrl": "{{searchUrl}}",
    "SubscriptionName": "{{subscriptionName}}" 
 }
```

#### Resend payload

Properties:

- transactionId
- contentSasUri
- resendDateTime
- logStepMetaData.Description
- logStepMetaData.Transaction_Type_Name
- logStepMetaData.Message_Type_Name
- logStepMetaData.Sender_Name
- logStepMetaData.Reciever_Name
- logStepMetaData.Status_Name
- logStepMetaData.File_Name
- logStepMetaData.Processed
- logStepMetaData.metadata
- logStepMetaData.metadata is a dictionary and can be used directly or by traversing and getting the Key and Value 

Default resend payload: 

```json
{
    "TransactionId": "{{transactionId}}",
    "ContentSasUri": "{{contentSasUri}}",
    "ResendDateTime": "{{resendDateTime}}",
    "LogStepMetaData": {
       "TransactionId": "{{transactionId}}",
       "Description": "{{logStepMetaData.Description}}",
       "TransactionTypeName": "{{logStepMetaData.Transaction_Type_Name}}",
       "MessageTypeName": "{{logStepMetaData.Message_Type_Name}}",
       "SenderName": "{{logStepMetaData.Sender_Name}}",
       "RecieverName": "{{logStepMetaData.Reciever_Name}}",
       "StatusName": "{{logStepMetaData.Status_Name}}",
       "FileName": "{{logStepMetaData.File_Name}}",
       "Processed": "{{logStepMetaData.Processed}}",
       "Metadata": {
            {% for metadata in logStepMetaData.metadata %}
               "{{metadata.Key}}": "{{metadata.Value}}",
             {% endfor %} }
       }
    } 
```

#### Predefined templates

For now we support and predefine Microsoft Teams template:

```json
{
    "@type": "MessageCard",
    "@context": "http://schema.org/extensions",
    "themeColor": "0076D7",
    "summary": "Received an alert from Archeo",
    "sections": [
        {
            "activityTitle": "{{alertName}}",
            "activitySubtitle": "{{description}}",
            "activityImage": "https://i.imgur.com/GYpdumD.png",
            "facts": [
                {
                    "name": "Alert Time",
                    "value": "{{alertTime}}"
                },
                {
                    "name": "Hits",
                    "value": {{hits}}
                },
                {
                    "name": "Threshold",
                    "value": {{threshold}}
                }
            ],
            "markdown": true
        }
    ],
    "potentialAction": [
        {
            "@context": "http://schema.org",
            "@type": "ViewAction",
            "name": "View search result",
            "target": [
                "{{searchUrl}}"
            ]
        }
    ]
}
```

and Slack template:

```json
{    
    "blocks": [
        {
    		"type": "section",
    		"text": {
    			"type": "mrkdwn",
    			"text": "*Received an alert from Archeo subscription* *{{subscriptionName}}*"
    		}
    	},
    	{
    		"type": "section",
    		"text": {
    			"type": "mrkdwn",
    			"text": " The alert {{alertName}} has been triggered at {{alertTime}}\n Description: {{description}}"
    		}
    	},
    	{
    		"type": "section",
    		"text": {
    			"type": "mrkdwn",
    			"text": "*Details:*\n Archeo has encountered {{hits}} hits, with a threshold of {{threshold}} "
    		}
    	},
    	{
    		"type": "section",
    		"text": {
    			"type": "mrkdwn",
    			"text": "Follow the link to get details <{{searchUrl}}}}|alert result>"
            }
    	}
    ]    
}
```

### Apim Subscription Key 

### Authorization Header Type

#### NONE
Use if no authorization is expected at REST endpoint

#### Basic

![img](https://archeodocstorage.blob.core.windows.net/images/DistributionChannels-Webhooks-Auth-Basic.png)

Expects, the username to use for basic authentication against the endpoint and the password to use for basic authentication against the endpoint.

#### Oauth2
![img](https://archeodocstorage.blob.core.windows.net/images/DistributionChannels-Webhooks-Auth-Oauth2.png)

| Field  | Description|
|---|---|
| Authentication Url   | The url to use when authenticating with oauth against the endpoint |
| Client Id  | The client id to use when contacting the endpoint  |
| Client Secret  |The client secret to use when contacting the endpoint   |
| Grant Type  |The grant type to use when contacting the endpoint. Eg. client_credentials   |
| Resource  | The resurce to use when contacting the endpoint.  |

## Mange Webhooks

All webhooks are listed, use the menu far right to edit or delete.

![img](https://archeodocstorage.blob.core.windows.net/images/DistributionChannels-Webhooks-Manage.png)
