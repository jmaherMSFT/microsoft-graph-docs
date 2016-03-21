# Update message

Update the properties of message object.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/messages/<id>
PATCH /users/<id>/messages/<id>
PATCH /me/mailFolders/<id>/messages/<id>
```
### Optional request headers
| Name       | Description|
|:-----------|:-----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | Workbook session Id that determines if changes are persisted or not. Optional.|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|bccRecipients|recipient||
|body|itemBody||
|bodyPreview|string||
|categories|string||
|ccRecipients|recipient||
|changeKey|string||
|conversationId|string||
|conversationIndex|binary||
|createdDateTime|dateTimeOffset||
|flag|followupFlag||
|from|recipient||
|hasAttachments|boolean||
|importance|string| Possible values are: `low`, `normal`, `high`.|
|inferenceClassification|string| Possible values are: `focused`, `other`.|
|internetMessageId|string||
|isDeliveryReceiptRequested|boolean||
|isDraft|boolean||
|isRead|boolean||
|isReadReceiptRequested|boolean||
|lastModifiedDateTime|dateTimeOffset||
|parentFolderId|string||
|receivedDateTime|dateTimeOffset||
|replyTo|recipient||
|sender|recipient||
|sentDateTime|dateTimeOffset||
|subject|string||
|toRecipients|recipient||
|uniqueBody|itemBody||
|unsubscribeData|string||
|unsubscribeEnabled|boolean||
|webLink|string||

### Response
If successful, this method returns a `200 OK` response code and updated [message](../resources/message.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_message"
}-->
```http
PATCH https://graph.microsoft.com/beta/me/messages/<id>
Content-type: application/json
Content-length: 272

{
  "receivedDateTime": "datetime-value",
  "sentDateTime": "datetime-value",
  "hasAttachments": true,
  "internetMessageId": "internetMessageId-value",
  "subject": "subject-value",
  "body": {
    "contentType": "contentType-value",
    "content": "content-value"
  }
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.message"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 272

{
  "receivedDateTime": "datetime-value",
  "sentDateTime": "datetime-value",
  "hasAttachments": true,
  "internetMessageId": "internetMessageId-value",
  "subject": "subject-value",
  "body": {
    "contentType": "contentType-value",
    "content": "content-value"
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update message",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->