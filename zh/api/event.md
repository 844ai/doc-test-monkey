
## App - puppeteerApp
**Kind**: global class

事件处理类，用于管理事件监听、触发和移除。

<a name="App.AppEvent+addEventListener"></a>

## App.AppEvent#addEventListener(event, listener)
添加事件监听器，将监听器函数添加到特定事件的监听器列表中。

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description |
| --- | --- | --- |
| event | <code>string</code> | 事件名称 |
| listener | <code>function</code> | 要添加的事件监听器函数 |

<a name="App.AppEvent+removeEventListener"></a>

## App.AppEvent#removeEventListener(event, listener)
移除事件监听器，从特定事件的监听器列表中移除指定的监听器函数。
如果未提供特定监听器，则移除整个事件的监听器列表。

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description |
| --- | --- | --- |
| event | <code>string</code> | 事件名称 |
| listener | <code>function</code> | 要移除的事件监听器函数 |

<a name="App.AppEvent+dispatchEvent"></a>

## App.AppEvent#dispatchEvent(event, data)
触发特定事件，调用该事件对应的所有监听器函数并传递特定的数据。

**Kind**: static method of [<code>App</code>](#App)

| Param | Type | Description |
| --- | --- | --- |
| event | <code>string</code> | 要触发的事件名称 |
| data | <code>any</code> | 要传递给监听器函数的数据 |

<a name="App.AppEvent+removeAllEventListeners"></a>

## App.AppEvent#removeAllEventListeners()
移除所有事件监听器，清空监听器对象。

**Kind**: static method of [<code>App</code>](#App)
<a name="AppEvent"></a>

## AppEvent
**Kind**: global class
<a name="new_AppEvent_new"></a>

## new AppEvent()
构造函数，初始化一个空的事件监听器对象。