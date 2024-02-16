
## Screen - puppeteerApp

屏幕类，用于获取屏幕截图、像素颜色等

<a name="Screen.requestPermission"></a>

## Screen.requestPermission ⇒ <code>Promise.&lt;boolean&gt;</code>
请求权限
Requests permission for the application screen with an optional timeout.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>Promise.&lt;boolean&gt;</code> - - A promise that resolves with a boolean indicating whether the permission was granted or not.     

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options | <code>Object</code> |  | Options for the permission request. |
| [options.timeout] | <code>number</code> | <code>30000</code> | Timeout in milliseconds for the permission request. |

<a name="Screen.screenshot"></a>

## Screen.screenshot ⇒ <code>\*</code>
获取屏幕截图
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
Checks if the application screen is enabled.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>boolean</code> - - A boolean indicating whether the screen is enabled or not.
<a name="Screen.setMetrics"></a>

## Screen.setMetrics
设置屏幕尺寸，用于统一不同设备屏幕尺寸下执行脚本的坐标，确保代码运行效果。不同屏幕尺寸下，坐标值会自动缩放；
Sets the metrics (width and height) of the application screen.

**Kind**: static property of [<code>Screen</code>](#Screen)

| Param | Type | Description |
| --- | --- | --- |
| width | <code>number</code> | The width of the screen. |
| height | <code>number</code> | The height of the screen. |

<a name="Screen.pixel"></a>

## Screen.pixel ⇒ <code>\*</code>
获取像素颜色，16 进制字符串，小写，如 #ffffff。
Retrieves the color of a pixel at the specified coordinates on the application screen.

**Kind**: static property of [<code>Screen</code>](#Screen)
**Returns**: <code>\*</code> - - The color of the pixel at the specified coordinates.

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | The x-coordinate of the pixel. |
| y | <code>number</code> | The y-coordinate of the pixel. |