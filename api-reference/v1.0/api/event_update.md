# Update event

Update the properties of event object.
### Prerequisites
One of the following **scopes** is required to execute this API:
*Calendars.ReadWrite*
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/events/<id>
PATCH /users/<id | userPrincipalName>/events/<id>
PATCH /groups/<id>/events/<id>

PATCH /me/calendar/events/<id>
PATCH /users/<id | userPrincipalName>/calendar/events/<id>
PATCH /groups/<id>/calendar/events/<id>

PATCH /me/calendars/<id>/events/<id>
PATCH /users/<id | userPrincipalName>/calendars/<id>/events/<id>

PATCH /me/calendargroup/calendars/<id>/events/<id>
PATCH /users/<id | userPrincipalName>/calendargroup/calendars/<id>/events/<id>

PATCH /me/calendargroups/<id>/calendars/<id>/events/<id>
PATCH /users/<id | userPrincipalName>/calendargroups/<id>/calendars/<id>/events/<id>
```
### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer <token>. Required. |

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|attendees|[Attendee](../resources/attendee.md)|The collection of attendees for the event.|
|body|[ItemBody](../resources/itembody.md)|The body of the message associated with the event.|
|categories|String|The categories associated with the event.|
|end|[DateTimeTimeZone](../resources/datetimetimezone.md)|The date and time that the event ends.<br/><br/>By default, the end time is in UTC. You can specify an optional time zone in EndTimeZone, express the end time in that time zone, and include a time offset from UTC. Note that if you use EndTimeZone, you must specify a value for StartTimeZone as well.<br/><br/>This example specifies February 25, 2015, 9:34pm in Pacific Standard Time: "2015-02-25T21:34:00-08:00". |
|importance|String|The importance of the event: Low = 0, Normal = 1, High = 2. Possible values are: `Low`, `Normal`, `High`.|
|isAllDay|Boolean|Set to true if the event lasts all day.|
|isReminderOn|Boolean|Set to true if an alert is set to remind the user of the event.|
|location|[Location](../resources/location.md)|The location of the event.|
|recurrence|[PatternedRecurrence](../resources/patternedrecurrence.md)|The recurrence patern for the event.|
|reminderMinutesBeforeStart|Int32|The number of minutes before the event start time that the reminder alert occurs.|
|responseRequested|Boolean|Set to true if the sender would like a response when the event is accepted or declined.|
|sensitivity|String| Possible values are: `Normal`, `Personal`, `Private`, `Confidential`.|
|showAs|String|The status to show: Free = 0, Tentative = 1, Busy = 2, Oof = 3, WorkingElsewhere = 4, Unknown = -1. Possible values are: `Free`, `Tentative`, `Busy`, `Oof`, `WorkingElsewhere`, `Unknown`.|
|start|[DateTimeTimeZone](../resources/datetimetimezone.md)|The start time of the event. <br/><br/>By default, the start time is in UTC. You can specify an optional time zone in StartTimeZone, express the start time in that time zone, and include a time offset from UTC. Note that if you use StartTimeZone, you must specify a value for EndTimeZone as well.<br/><br/>This example specifies February 25, 2015, 7:34pm in Pacific Standard Time: "2015-02-25T19:34:00-08:00".  |
|subject|String|The text of the event's subject line.|

### Response
If successful, this method returns a `200 OK` response code and updated [event](../resources/event.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_event"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me/events/<id>
Content-type: application/json
Content-length: 285

{
  "originalStartTimeZone": "originalStartTimeZone-value",
  "originalEndTimeZone": "originalEndTimeZone-value",
  "responseStatus": {
    "response": "",
    "time": "datetime-value"
  },
  "iCalUId": "iCalUId-value",
  "reminderMinutesBeforeStart": 99,
  "isReminderOn": true
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.event"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 285

{
  "originalStartTimeZone": "originalStartTimeZone-value",
  "originalEndTimeZone": "originalEndTimeZone-value",
  "responseStatus": {
    "response": "",
    "time": "datetime-value"
  },
  "iCalUId": "iCalUId-value",
  "reminderMinutesBeforeStart": 99,
  "isReminderOn": true
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update event",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
