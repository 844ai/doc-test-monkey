
## App - puppeteerApp
**Kind**: global class

Event handling class, used to manage event listening, triggering, and removal.

<a name="App.AppEvent+addEventListener"></a>

## App.AppEvent#addEventListener(event, listener)
Add an event listener, adding the listener function to the list of listeners for a specific event.

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description                                    |
| --- | --- |------------------------------------------------|
| event | <code>string</code> | Event name                                     |
| listener | <code>function</code> | The function of the event listener to be added |

<a name="App.AppEvent+removeEventListener"></a>

## App.AppEvent#removeEventListener(event, listener)
Remove the event listener, remove the specified listener function from the listener list of a specific event.
If no specific listener is provided, remove the entire listener list of the event.

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description |
| --- | --- | --- |
| event | <code>string</code> | Event name |
| listener | <code>function</code> | The function of the event listener to be removed |

<a name="App.AppEvent+dispatchEvent"></a>

## App.AppEvent#dispatchEvent(event, data)
Trigger a specific event, call all the listener functions corresponding to that event, and pass specific data.

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description |
| --- | --- | --- |
| event | <code>string</code> | The name of the event to be triggered |
| data | <code>any</code> | The data to be passed to the listener function |

<a name="App.AppEvent+removeAllEventListeners"></a>

## App.AppEvent#removeAllEventListeners()
Remove all event listeners, clear the listener object.

**Kind**: static method of [<code>App</code>](#App)
<a name="AppEvent"></a>

## AppEvent
**Kind**: global class
<a name="new_AppEvent_new"></a>

## new AppEvent()
Constructor, initialize an empty event listener object.
