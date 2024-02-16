# Global method global   - puppeteerApp

## openApp(packageName)
Open the app

**Kind**: global function

| Param | Type |
| --- | --- |
| packageName | <code>string</code> |


## openAppName(appName)
Open the app（by name）

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="closeApp"></a>

## closeApp(packageName)
Close the app

**Kind**: global function

| Param | Type |
| --- | --- |
| packageName | <code>string</code> |

<a name="getApps"></a>

## getApps() ⇒ <code>Array.&lt;Object&gt;</code>
Get all apps

**Kind**: global function
<a name="getPackageName"></a>

## getPackageName(appName) ⇒ <code>string</code>
Get package name

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="getApp"></a>

## getApp(appName) ⇒ <code>string</code>
Get app name

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="version"></a>

## version() ⇒ <code>string</code>
Get version information

**Kind**: global function
<a name="isEnabled"></a>

## isEnabled() ⇒ <code>string</code>
Get version information

**Kind**: global function
<a name="requestPermission"></a>

## requestPermission(options) ⇒ <code>Promise.&lt;boolean&gt;</code>
Request permission

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| options | <code>Object</code> |  |
| [options.timeout] | <code>number</code> | <code>60000</code> |

<a name="back"></a>

## back()
Back operation

**Kind**: global function
<a name="home"></a>

## home()
Home screen operation

**Kind**: global function
<a name="recent"></a>

## recent()
Recent app operation

**Kind**: global function
<a name="powerDialog"></a>

## powerDialog()
Recent app operation

**Kind**: global function
<a name="notificationBar"></a>

## notificationBar()
Notification bar operation

**Kind**: global function
<a name="quickSettings"></a>

## quickSettings()
Quick settings operation

**Kind**: global function
<a name="lockScreen"></a>

## lockScreen()
Lock screen operation

**Kind**: global function
<a name="splitScreen"></a>

## splitScreen()
Lock screen operation

**Kind**: global function
<a name="setVolume"></a>

## setVolume(volumeLevel, streamType)
Set volume

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| volumeLevel | <code>number</code> |  |
| streamType | <code>number</code> | <code>1</code> |

<a name="getVolume"></a>

## getVolume(streamType) ⇒ <code>number</code>
Get volume

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| streamType | <code>number</code> | <code>1</code> |

<a name="startActivity"></a>

## startActivity(streamType) ⇒ <code>number</code>
Get volume

**Kind**: global function

| Param | Type |
| --- | --- |
| streamType | <code>number</code> |

<a name="openUrl"></a>

## openUrl(url)
The function to open web pages, supporting both http and https protocols.
If the URL doesn't start with http or https, https:// will be added.
URL scheme won't be added, such as weixin://.

**Kind**: global function

| Param | Type |
| --- | --- |
| url | <code>string</code> |

<a name="encodeURIComponent"></a>

## encodeURIComponent(str) ⇒ <code>string</code>
encodeURIComponent encodes the string

**Kind**: global function

| Param | Type |
| --- | --- |
| str | <code>string</code> |

<a name="encodeURI"></a>

## encodeURI(uri, allowedChars) ⇒ <code>string</code>
encodeURI encodes the URL

**Kind**: global function

| Param | Type |
| --- | --- |
| uri | <code>string</code> |
| allowedChars | <code>string</code> |

<a name="decodeURIComponent"></a>

## decodeURIComponent(str) ⇒ <code>string</code>
decodeURIComponent decodes the string

**Kind**: global function

| Param | Type |
| --- | --- |
| str | <code>string</code> |

<a name="decodeURI"></a>

## decodeURI(uri) ⇒ <code>string</code>
decodeURI decodes the URL

**Kind**: global function

| Param | Type |
| --- | --- |
| uri | <code>string</code> |


<dl>
<dt><a href="#toast">toast(value)</a></dt>
<dd><p>Show toast message
Displays a toast message with the given value.</p>
</dd>
<dt><a href="#alert">alert(message)</a> ⇒ <code>Promise.&lt;void&gt;</code></dt>
<dd><p>Show alert dialog
Displays an alert dialog containing the given message and returns a promise that resolves when the user closes the dialog.</p>
</dd>
<dt><a href="#confirm">confirm(title, [content], [callback])</a> ⇒ <code>Promise.&lt;boolean&gt;</code></dt>
<dd><p>Show confirm dialog
Displays a confirm dialog with the given title and content. If a callback function is provided, it will be called with the result of the dialog.
If no callback function is provided, it returns a promise that resolves based on the result of the dialog.</p>
</dd>
<dt><a href="#prompt">prompt(title, [defaultValue], [callback])</a> ⇒ <code>Promise.&lt;string&gt;</code></dt>
<dd><p>Show prompt dialog
Displays a prompt dialog with the given title and default value. If a callback function is provided, it will be called with the result of the dialog.
If no callback function is provided, it returns a promise that resolves based on the result of the dialog.</p>
</dd>
<dt><a href="#copyToClipboard">copyToClipboard(text)</a></dt>
<dd><p>Copy text to clipboard
Copies the given text to the device's clipboard.</p>
</dd>
<dt><a href="#getClipboard">getClipboard()</a> ⇒ <code>string</code></dt>
<dd><p>Get clipboard content
Gets the current content of the device's clipboard.</p>
</dd>
</dl>

<a name="toast"></a>

## toast(value)
Show toast message 
Displays a toast message with the given value.

**Kind**: global function

| Param | Type | Description |
| --- | --- | --- |
| value | <code>string</code> | The message to be displayed in the toast. |

<a name="alert"></a>

## alert(message) ⇒ <code>Promise.&lt;void&gt;</code>
Show alert dialog 
Displays an alert dialog containing the given message and returns a promise that resolves when the user closes the dialog.

**Kind**: global function
**Returns**: <code>Promise.&lt;void&gt;</code> - - The promise that resolves when the user closes the dialog.

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The message to be displayed in the alert dialog. |

<a name="confirm"></a>

## confirm(title, [content], [callback]) ⇒ <code>Promise.&lt;boolean&gt;</code>
Show confirm dialog 
Displays a confirm dialog with the given title and content.If a callback function is provided, it will be called with the result of the dialog. 
If no callback function is provided, it returns a promise that resolves based on the result of the dialog.

**Kind**: global function
**Returns**: <code>Promise.&lt;boolean&gt;</code> - - If no callback function is provided, it returns a promise that resolves based on the result of the dialog.

| Param | Type | Default | Description                                                     |
| --- | --- | --- |-----------------------------------------------------------------|
| title | <code>string</code> |  | The title of the confirm dialog.                                | |
| [content] | <code>string</code> | <code>&quot;&#x27;&#x27;&quot;</code> | The content displayed in the confirm dialog |
| [callback] | <code>function</code> |  | Optional callback function that will be called with the result of the dialog.                                        |

<a name="prompt"></a>

## prompt(title, [defaultValue], [callback]) ⇒ <code>Promise.&lt;string&gt;</code>
Show prompt dialog 
Displays a prompt dialog with the given title and default value. If a callback function is provided, it will be called with the result of the dialog. 
If no callback function is provided, it returns a promise that resolves based on the result of the dialog.

**Kind**: global function
**Returns**: <code>Promise.&lt;string&gt;</code> - - If no callback function is provided, it returns a promise that resolves based on the result of the dialog.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| title | <code>string</code> |  | The title of the prompt dialog.  |
| [defaultValue] | <code>string</code> | <code>&quot;&#x27;&#x27;&quot;</code> | The default value displayed in the prompt dialog. |
| [callback] | <code>function</code> |  | Optional callback function that will be called with the result of the dialog. |

<a name="copyToClipboard"></a>

## copyToClipboard(text)
Copy text to clipboard 
Copies the given text to the device's clipboard.

**Kind**: global function

| Param | Type | Description |
| --- | --- | --- |
| text | <code>string</code> | The text to be copied to the clipboard. |

<a name="getClipboard"></a>

## getClipboard() ⇒ <code>string</code>
Get clipboard content
Gets the current content of the device's clipboard.

**Kind**: global function
**Returns**: <code>string</code> - - the current content of the clipboard
