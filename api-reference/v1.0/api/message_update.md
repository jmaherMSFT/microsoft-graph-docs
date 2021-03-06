# Update message

Update the properties of message object.
### Prerequisites
One of the following **scopes** is required to execute this API:
*Mail.ReadWrite*
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/messages/<id>
PATCH /users/<id | userPrincipalName>/messages/<id>
PATCH /me/mailFolders/<id>/messages/<id>
PATCH /users/<id | userPrincipalName>/mailFolders/<id>/messages/<id>
```
### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <token>. Required. |
| Content-Type | string  | Nature of the data in the body of an entity. Required. |
### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed. Writable/Updatable properties are

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|bccRecipients|Recipient|The Bcc recipients for the message. Updatable only if IsDraft = true.|
|categories|String collection|The categories associated with the message.|
|ccRecipients|Recipient collection|The Cc recipients for the message. Updatable only if IsDraft = true.|
|from|Recipient|The mailbox owner and sender of the message. Updatable only if IsDraft = true.|
|importance|String|The importance of the message. Possible values are: `Low`, `Normal`, `High`.|
|isRead|Boolean|Indicates whether the message has been read.|
|replyTo|Recipient collection|The email addresses to use when replying. Updatable only if IsDraft = true.|
|sender|Recipient|The account that is actually used to generate the message. Updatable only if IsDraft = true.|
|toRecipients|Recipient collection|The To recipients for the message. Updatable only if IsDraft = true.|
|body|ItemBody|The body of the message. Updatable only if IsDraft = true.|
|isDeliveryReceiptRequested|Boolean|Indicates whether a read receipt is requested for the message.|
|isReadReceiptRequested|Boolean|Indicates whether a read receipt is requested for the message.|
|subject|String|The subject of the message. Updatable only if IsDraft = true.|

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
PATCH https://graph.microsoft.com/v1.0/me/messages/<id>
Content-type: application/json
Content-length: 248

{
  "subject": "subject-value",
  "body": {
    "contentType": "",
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
Content-length: 248

{
  "receivedDateTime": "datetime-value",
  "sentDateTime": "datetime-value",
  "hasAttachments": true,
  "subject": "subject-value",
  "body": {
    "contentType": "",
    "content": "content-value"
  },
  "bodyPreview": "bodyPreview-value"
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
