`<apex:actionFunction>`

- Allows for controller methods to be called directly from ***Javascript***. Must be encapsulated in <apex:form> tags. Unlike actionSupport, these function<apex:actionPoller>s can be called directly from Javascript code

`<apex:actionPoller>`

- Sends an AJAX request according to the time ***interval*** you specify. If this ever gets re-rendered, it resets

`<apex:actionSupport>`

- Adds AJAX support to another component (e.g. ***onClick, onMouseUp, onFocus***, etc.)

`<apex:actionStatus>`

- Can be associated with an AJAX request (actionFunction/actionSupport/actionPoller) and shows content conditionally depending on the ***status*** of the request (in progress/complete). Use the "id" field to specify name; use "status" field on related components to connect them

`<apex:actionRegion>`

- Signifies which ***components*** should be processed by the server when an AJAX request is generated