# 全局方法global   - puppeteerApp

## openApp(packageName)
打开应用

**Kind**: global function

| Param | Type |
| --- | --- |
| packageName | <code>string</code> |


## openAppName(appName)
打开应用（通过名称）

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="closeApp"></a>

## closeApp(packageName)
关闭应用

**Kind**: global function

| Param | Type |
| --- | --- |
| packageName | <code>string</code> |

<a name="getApps"></a>

## getApps() ⇒ <code>Array.&lt;Object&gt;</code>
获取所有应用

**Kind**: global function
<a name="getPackageName"></a>

## getPackageName(appName) ⇒ <code>string</code>
获取应用包名

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="getApp"></a>

## getApp(appName) ⇒ <code>string</code>
获取应用包名

**Kind**: global function

| Param | Type |
| --- | --- |
| appName | <code>string</code> |

<a name="version"></a>

## version() ⇒ <code>string</code>
获取版本信息

**Kind**: global function
<a name="isEnabled"></a>

## isEnabled() ⇒ <code>string</code>
获取版本信息

**Kind**: global function
<a name="requestPermission"></a>

## requestPermission(options) ⇒ <code>Promise.&lt;boolean&gt;</code>
请求权限

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| options | <code>Object</code> |  |
| [options.timeout] | <code>number</code> | <code>60000</code> |

<a name="back"></a>

## back()
后退操作

**Kind**: global function
<a name="home"></a>

## home()
主屏幕操作

**Kind**: global function
<a name="recent"></a>

## recent()
最近应用操作

**Kind**: global function
<a name="powerDialog"></a>

## powerDialog()
最近应用操作

**Kind**: global function
<a name="notificationBar"></a>

## notificationBar()
通知栏操作

**Kind**: global function
<a name="quickSettings"></a>

## quickSettings()
快速设置操作

**Kind**: global function
<a name="lockScreen"></a>

## lockScreen()
锁定屏幕操作

**Kind**: global function
<a name="splitScreen"></a>

## splitScreen()
锁定屏幕操作

**Kind**: global function
<a name="setVolume"></a>

## setVolume(volumeLevel, streamType)
设置音量

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| volumeLevel | <code>number</code> |  |
| streamType | <code>number</code> | <code>1</code> |

<a name="getVolume"></a>

## getVolume(streamType) ⇒ <code>number</code>
获取音量

**Kind**: global function

| Param | Type | Default |
| --- | --- | --- |
| streamType | <code>number</code> | <code>1</code> |

<a name="startActivity"></a>

## startActivity(streamType) ⇒ <code>number</code>
获取音量

**Kind**: global function

| Param | Type |
| --- | --- |
| streamType | <code>number</code> |

<a name="openUrl"></a>

## openUrl(url)
打开网页的函数，支持 http 和 https 协议。
如果 URL 不是以 http 或 https 开头，则添加 https://。
不添加 URL scheme，比如 weixin://

**Kind**: global function

| Param | Type |
| --- | --- |
| url | <code>string</code> |

<a name="encodeURIComponent"></a>

## encodeURIComponent(str) ⇒ <code>string</code>
对字符串进行 encodeURIComponent 编码

**Kind**: global function

| Param | Type |
| --- | --- |
| str | <code>string</code> |

<a name="encodeURI"></a>

## encodeURI(uri, allowedChars) ⇒ <code>string</code>
对 URI 进行 encodeURI 编码

**Kind**: global function

| Param | Type |
| --- | --- |
| uri | <code>string</code> |
| allowedChars | <code>string</code> |

<a name="decodeURIComponent"></a>

## decodeURIComponent(str) ⇒ <code>string</code>
对字符串进行 decodeURIComponent 解码

**Kind**: global function

| Param | Type |
| --- | --- |
| str | <code>string</code> |

<a name="decodeURI"></a>

## decodeURI(uri) ⇒ <code>string</code>
对 URI 进行 decodeURI 解码

**Kind**: global function

| Param | Type |
| --- | --- |
| uri | <code>string</code> |


<dl>
<dt><a href="#toast">toast(value)</a></dt>
<dd><p>显示 toast 消息
使用给定的值显示一个 toast 消息。</p>
</dd>
<dt><a href="#alert">alert(message)</a> ⇒ <code>Promise.&lt;void&gt;</code></dt>
<dd><p>显示 alert 对话框
显示一个包含给定消息的 alert 对话框，并返回一个承诺，当用户关闭对话框时解决该承诺。</p>
</dd>
<dt><a href="#confirm">confirm(title, [content], [callback])</a> ⇒ <code>Promise.&lt;boolean&gt;</code></dt>
<dd><p>显示 confirm 对话框
显示一个具有给定标题和内容的 confirm 对话框。如果提供了回调函数，它将使用对话框的结果调用。
如果没有提供回调函数，则返回一个承诺，该承诺根据对话框的结果进行解析。</p>
</dd>
<dt><a href="#prompt">prompt(title, [defaultValue], [callback])</a> ⇒ <code>Promise.&lt;string&gt;</code></dt>
<dd><p>显示 prompt 对话框
显示一个具有给定标题和默认值的 prompt 对话框。如果提供了回调函数，它将使用对话框的结果调用。
如果没有提供回调函数，则返回一个承诺，该承诺根据对话框的结果进行解析。</p>
</dd>
<dt><a href="#copyToClipboard">copyToClipboard(text)</a></dt>
<dd><p>将文本复制到剪贴板
将给定的文本复制到设备的剪贴板。</p>
</dd>
<dt><a href="#getClipboard">getClipboard()</a> ⇒ <code>string</code></dt>
<dd><p>获取剪贴板内容
获取设备剪贴板当前的内容。</p>
</dd>
</dl>

<a name="toast"></a>

## toast(value)
显示 toast 消息
使用给定的值显示一个 toast 消息。

**Kind**: global function

| Param | Type | Description |
| --- | --- | --- |
| value | <code>string</code> | 要在 toast 中显示的消息。 |

<a name="alert"></a>

## alert(message) ⇒ <code>Promise.&lt;void&gt;</code>
显示 alert 对话框
显示一个包含给定消息的 alert 对话框，并返回一个承诺，当用户关闭对话框时解决该承诺。

**Kind**: global function
**Returns**: <code>Promise.&lt;void&gt;</code> - - 当用户关闭对话框时解决的承诺。

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | 要在 alert 对话框中显示的消息。 |

<a name="confirm"></a>

## confirm(title, [content], [callback]) ⇒ <code>Promise.&lt;boolean&gt;</code>
显示 confirm 对话框
显示一个具有给定标题和内容的 confirm 对话框。如果提供了回调函数，它将使用对话框的结果调用。
如果没有提供回调函数，则返回一个承诺，该承诺根据对话框的结果进行解析。

**Kind**: global function
**Returns**: <code>Promise.&lt;boolean&gt;</code> - - 如果未提供回调函数，则根据对话框结果解析的承诺。

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| title | <code>string</code> |  | confirm 对话框的标题。 |
| [content] | <code>string</code> | <code>&quot;&#x27;&#x27;&quot;</code> | 要在 confirm 对话框中显示的内容。 |
| [callback] | <code>function</code> |  | 可选的回调函数，将在对话框结果上被调用。 |

<a name="prompt"></a>

## prompt(title, [defaultValue], [callback]) ⇒ <code>Promise.&lt;string&gt;</code>
显示 prompt 对话框
显示一个具有给定标题和默认值的 prompt 对话框。如果提供了回调函数，它将使用对话框的结果调用。
如果没有提供回调函数，则返回一个承诺，该承诺根据对话框的结果进行解析。

**Kind**: global function
**Returns**: <code>Promise.&lt;string&gt;</code> - - 如果未提供回调函数，则根据对话框结果解析的承诺。

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| title | <code>string</code> |  | prompt 对话框的标题。 |
| [defaultValue] | <code>string</code> | <code>&quot;&#x27;&#x27;&quot;</code> | 在 prompt 对话框中显示的默认值。 |
| [callback] | <code>function</code> |  | 可选的回调函数，将在对话框结果上被调用。 |

<a name="copyToClipboard"></a>

## copyToClipboard(text)
将文本复制到剪贴板
将给定的文本复制到设备的剪贴板。

**Kind**: global function

| Param | Type | Description |
| --- | --- | --- |
| text | <code>string</code> | 要复制到剪贴板的文本。 |

<a name="getClipboard"></a>

## getClipboard() ⇒ <code>string</code>
获取剪贴板内容
获取设备剪贴板当前的内容。

**Kind**: global function
**Returns**: <code>string</code> - - 剪贴板当前的内容。