
## Screen - puppeteerApp

Screen class, used to capture screenshots, pixel colors, etc.

<a name="Screen.requestPermission"></a>

## Screen.requestPermission ⇒ <code>Promise.&lt;boolean&gt;</code>
Request permission
Requests permission for the application screen with an optional timeout.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>Promise.&lt;boolean&gt;</code> - - A promise that resolves with a boolean indicating whether the permission was granted or not.     

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options | <code>Object</code> |  | Options for the permission request. |
| [options.timeout] | <code>number</code> | <code>30000</code> | Timeout in milliseconds for the permission request. |

<a name="Screen.screenshot"></a>

## Screen.screenshot ⇒ <code>\*</code>
get screenshots
Takes a screenshot of the application screen with the given options.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>\*</code> - - The result of the screenshot operation.

| Param | Type | Description |
| --- | --- | --- |
| options | <code>Object</code> | Options for the screenshot. |

<a name="Screen.isEnabled"></a>

## Screen.isEnabled ⇒ <code>boolean</code>
检查是否启用，如果启用则返回 true，否则返回 false。
启用后可以访问屏幕截图、像素颜色等功能。
Check if it is enabled. If enabled, return true, otherwise return false.
After enabling, you can access functions like screen capture, pixel color, etc.
Checks if the application screen is enabled.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>boolean</code> - - A boolean indicating whether the screen is enabled or not.
<a name="Screen.setMetrics"></a>

## Screen.setMetrics
Set the screen size to unify the coordinates of scripts executed on different device screens, ensuring the effect of code execution. Under different screen sizes, the coordinate values will be automatically scaled.
Sets the metrics (width and height) of the application screen.

**Kind**: static property of [<code>Screen</code>](#Screen)

| Param | Type | Description |
| --- | --- | --- |
| width | <code>number</code> | The width of the screen. |
| height | <code>number</code> | The height of the screen. |

<a name="Screen.pixel"></a>

## Screen.pixel ⇒ <code>\*</code>
Get pixel color, lowercase hexadecimal string, for example #ffffff。
Retrieves the color of a pixel at the specified coordinates on the application screen.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>\*</code> - - The color of the pixel at the specified coordinates.

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | The x-coordinate of the pixel. |
| y | <code>number</code> | The y-coordinate of the pixel. |
