## page - puppeteerApp

In the Android app, you can run and call Kotlin code.
[Page](https://zhaoqize.github.io/puppeteer-api-zh_CN/s-page#?product=Puppeteer&version=puppeteer-v21.6.1&show=api-class-page)
By default, a page object has been instantiated, and you can use it directly. For example,  await page.click('#id');



## page.title() ⇒ <code>\*</code>
Get the name of the current app, such as WeChat.


**Returns**: <code>\*</code> - {Promise&lt;string&gt;}


## page.url() ⇒ <code>\*</code>
Get the package name of the current app, such as WeChat.


**Returns**: <code>\*</code> - {Promise&lt;string&gt;} , for example,com.tencent.mm/android.widget.FrameLayout


## page.goto(activityFullName) ⇒ <code>\*</code>
Jump to the activity of the specified app


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type |
| --- | --- |
| activityFullName | <code>string</code> |



## page.$(selector) ⇒ <code>\*</code>
Get the specified element. If the element does not exist, return null. If there are multiple, return the first one.


**Returns**: <code>\*</code> - {Promise&lt;any&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let ele = await page.$('#bkk');
```


## page.$$(selector) ⇒ <code>\*</code>
Get all specified elements, return an array.


**Returns**: <code>\*</code> - {Promise&lt;any[]&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let eles = await page.$$('#bkk');
```


## page.click(selector, [options]) ⇒ <code>\*</code>
Click on the specified element.


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type | Default |
| --- | --- | --- |
| selector | <code>string</code> |  |
| [options] | <code>ClickOptions</code> | <code>{ clickCount: 1, delay: 100 }</code> |

**Example**
```js
await page.click('#bkk');
```


## page.evaluate(pageFunction, ...args) ⇒ <code>Promise.&lt;Serializable&gt;</code>
Execute the specified method on the page. Similar to the eval() method.


**Returns**: <code>Promise.&lt;Serializable&gt;</code> - The result of pageFunction execution.

| Param | Type | Description |
| --- | --- | --- |
| pageFunction | <code>function</code> \| <code>string</code> | The method to be executed in the context of the page instance. |
| ...args | <code>\*</code> | The parameters to be passed to pageFunction. |



## page.waitForSelector(selector, options) ⇒ <code>Promise.&lt;AppElement&gt;</code>
The selector of the element to wait for.
Waiting for the element matching the specified selector to appear on the page. If the matching element already exists when this method is called, it immediately returns.
If the specified selector still does not appear after the timeout period, this method will throw an error.

**Returns**: <code>Promise.&lt;AppElement&gt;</code> - Returns a Promise that resolves to an AppElement object.

| Param | Type | Description                                                                                                                                                      |
| --- | --- |------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| selector | <code>string</code> | The selector of the element to wait for. It is the same as the parameter of document.querySelector(). css selector syntax. #id，.class，[attr=value]，=text, >=text 

| options | <code>Object</code> | Optional parameter:                                                                                                                                              |
| options.timeout | <code>number</code> | Timeout, unit milliseconds, default is 30000.                                                                                                                    |
| options.pollingInterval | <code>number</code> | pollingInterval, unit milliseconds, default is 100.                                                                                                                      |

**Example**
```js
await page.waitForSelector('#bkk');
await page.waitForSelector('#bkk', { timeout: 10000 });
await page.waitForSelector('.android.view.View[text="love reading"]')
await page.waitForSelector('.View[text="love reading"]');
let element = await page.waitForSelector('.View[text="love reading"]');
await element.click();
```


## page.waitForFunction(pageFunction, [options], ...args) ⇒ <code>\*</code>
Wait for the return value of pageFunction to be true. If it times out, an error will be thrown.
waitForFunction can be used to monitor changes in the size of the page and screen rotation.



| Param | Type | Default | Description |
| --- | --- | --- | --- |
| pageFunction | <code>\*</code> |  | The method to be executed in the context of the page instance. |
| [options] | <code>Object</code> | <code>{ timeout: 30000, pollingInterval: 100 }</code> |  |
| ...args | <code>\*</code> |  |  |

**Example**
```js
await page.waitForFunction(()=> Device.rotation() !=0 );
```


## page.type(selector, text, [options]) ⇒ <code>Promise.&lt;void&gt;</code>
Input text in the specified element on the page.


**Returns**: <code>Promise.&lt;void&gt;</code> - Returns a Promise that resolves when the input operation is complete.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| selector | <code>string</code> |  | The element selector for the content to be input. If there are multiple matching elements, the input will be entered into the first matching element. |
| text | <code>string</code> |  | The text to be input. |
| [options] | <code>Object</code> | <code>{ delay: 0, autoCorrect: true }</code> | Optional parameters. |
| [options.delay] | <code>number</code> | <code>0</code> | The delay time between inputting texts (in milliseconds). Default is 0. |
| [options.autoCorrect] | <code>boolean</code> | <code>true</code> | Specifies whether to automatically correct the input text. Default is true. |

**Example**
```js
await page.type('#bkk', 'test.844.ai');
```


## page.screenshot([options]) ⇒ <code>Promise.&lt;string&gt;</code>
Take a screenshot of the current page.


**Returns**: <code>Promise.&lt;string&gt;</code> - - A Promise object that resolves to the base64 string of the screenshot.

| Param | Type | Default | Description                                                                                                                                                                        |
| --- | --- | --- |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [options] | <code>Object</code> | <code>{}</code> | Optional configuration parameters:                                                                                                                                                 |
| [options.path] | <code>string</code> |  | Screenshot save path. The file extension determines the image type. Relative paths are resolved from the current path. If no path is specified, it is not saved to the hard drive. |
| [options.type] | <code>string</code> | <code>&quot;&#x27;png&#x27;&quot;</code> | Specify the screenshot type, which can be 'jpeg' or 'png'. Default is 'png'.                                                                                                       |
| [options.quality] | <code>number</code> |  | Image quality (0-100), only applicable to jpeg type.                                                                                                                               |
| [options.clip] | <code>Object</code> |  | Specify a cropping area,                                                                                                                                                           |
| [options.clip.x] | <code>number</code> |  | Top left corner x coordinate of the cropping area.                                                                                                                                 |
| [options.clip.y] | <code>number</code> |  | Top left corner y coordinate of the cropping area.                                                                                                                                 |
| [options.clip.width] | <code>number</code> |  | Width of the cropping area.                                                                                                                                                        |
| [options.clip.height] | <code>number</code> |  | Height of the cropping area.                                                                                                                                                       |
| [options.omitBackground] | <code>boolean</code> | <code>false</code> | Whether to hide the default white background and make it transparent. Default is opaque.                                                                                           |
| [options.encoding] | <code>string</code> | <code>&quot;&#x27;binary&#x27;&quot;</code> | Image encoding type, can be 'base64' or 'binary'. default 'binary'。                                                                                                                |   



## page.clicks(selectors, options)
Easy to click multiple elements. Such as inputting the amount, password.



| Param | Type |
| --- | --- |
| selectors | <code>\*</code> |
| options | <code>\*</code> |

**Example**
```js
await page.clicks(['=1', '=.', '=8', '=8']);
```
**Example**
```js
await page.clicks(['=1', '=.', '=8', '=8'], { delay: 200 });
```
**Example**
```js
await page.clicks('1.88');
```


## page.tap(x, y, [options]) ⇒ <code>Promise.&lt;void&gt;</code>
Perform a tap operation at the specified coordinate position.


**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param                | Type | Default | Description |
|----------------------| --- | --- | --- |
| x                    | <code>number</code> |  | X-axis coordinate position |
| y                    | <code>number</code> |  | Y-axis coordinate position |
| [options]            | <code>Object</code> | <code>{}</code> | Optional configuration parameters |
| [options.clickCount] | <code>number</code> | <code>1</code> | Number of taps, default is 1 |
| [options.delay]      | <code>number</code> | <code>50</code> | Delay time between taps (milliseconds), default is 50 |
| [options.interval]   | <code>number</code> | <code>100</code> | Interval time between each tap (milliseconds), default is 100 |
| [options.left]       | <code>number</code> \| <code>null</code> | <code></code> | Top left corner x coordinate of the cropping area.If left, top, width, and height are set, then coordinates will be randomly generated within that area.
              |
| [options.top]        | <code>number</code> \| <code>null</code> | <code></code> | Top left corner y coordinate of the area. |
| [options.width]      | <code>number</code> \| <code>null</code> | <code></code> | Width of the area. |
| [options.height]     | <code>number</code> \| <code>null</code> | <code></code> | Height of the area. |


## page.tapText(text, [options]) ⇒ <code>Promise.&lt;void&gt;</code>
Click on the specified text element. If multiple elements match, click on the first one.
Address the issue of page.Click not working and element not found. Improve robustness.
Wrap the following code into a method for easy use.
```js
let elements = await page.elements()
let item = flatElements(elements).find(item => item.text === 'View leaderboard');
if(item){
    let { left , top , right , bottom  } = item.boundsInScreen ;
    let x = ( left + right ) / 2 ;
    let y = ( top + bottom ) / 2 ;
    await page.tap(  x , y );
}
```

**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description                                                                                                        |
| --- | --- | --- |--------------------------------------------------------------------------------------------------------------------|
| x | <code>number</code> |  | text,default>=selector。The text supports selector characters. For example:loving reading，=loving reading，or >=loving reading。 |
| [options] | <code>Object</code> | <code>{}</code> | Optional configuration parameters                                                                                  |
| [options.clickCount] | <code>number</code> | <code>1</code> | Number of taps, default is 1                                                                                       |
| [options.delay] | <code>number</code> | <code>50</code> | Delay time between taps (milliseconds), default is 50                                                              |
| [options.interval] | <code>number</code> | <code>100</code> | Interval time between each tap (milliseconds), default is 100                                                      |



## page.elements
Get all elements on the current page,
The data content is the nodeInfo converted to a JSON object.

**Kind**: static property of [<code>page</code>](#page)


## page.longTap ⇒ <code>Promise.&lt;void&gt;</code>
Perform a long tap operation at the specified coordinate position. Trigger long press, such as long pressing on an app icon on the phone system's home screen. The interface parameters are similar to page.tap.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> -A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X-axis coordinate position |
| y | <code>number</code> |  | Y-axis coordinate position |
| [options] | <code>Object</code> | <code>{}</code> | Optional configuration parameters: |
| [options.delay] | <code>number</code> | <code>500</code> | Long press delay time (milliseconds), default is 500|
| [options.left] | <code>number</code> \| <code>null</code> | <code></code> | Top left corner x coordinate of the area. |
| [options.top] | <code>number</code> \| <code>null</code> | <code></code> | Top left corner y coordinate of the area. |
| [options.width] | <code>number</code> \| <code>null</code> | <code></code> | Width of the area. |
| [options.height] | <code>number</code> \| <code>null</code> | <code></code> | Height of the area. |


## page.touchDown ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the touch operation of pressing down at the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> -A Promise that resolves to indicate completion of the operation.

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | X-axis coordinate position |
| y | <code>number</code> | Y-axis coordinate position |



## page.touchUp ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the touch operation of releasing the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | X-axis coordinate position |
| y | <code>number</code> | Y-axis coordinate position |



## page.touchMove ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the touch operation of sliding from one coordinate position to another.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| xFrom | <code>number</code> |  | start X-axis coordinate position |
| yFrom | <code>number</code> |  | start Y-axis coordinate position |
| xTo | <code>number</code> |  | target X-axis coordinate position |
| yTo | <code>number</code> |  | target Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |



## page.swipe ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the slide operation of sliding from one coordinate position to another.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| xFrom | <code>number</code> |  | start X-axis coordinate position |
| yFrom | <code>number</code> |  | start Y-axis coordinate position |
| xTo | <code>number</code> |  | target X-axis coordinate position |
| yTo | <code>number</code> |  | target Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |



## page.swipeDown ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the operation of sliding down from the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X-axis coordinate position |
| y | <code>number</code> |  | Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |



## page.swipeUp ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the operation of sliding up from the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X-axis coordinate position |
| y | <code>number</code> |  | Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |



## page.swipeLeft ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the operation of sliding left from the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X-axis coordinate position |
| y | <code>number</code> |  | Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |



## page.swipeRight ⇒ <code>Promise.&lt;void&gt;</code>
Simulate the operation of sliding right from the specified coordinate position.

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - A Promise that resolves to indicate completion of the operation.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X-axis coordinate position |
| y | <code>number</code> |  | Y-axis coordinate position |
| [duration] | <code>number</code> | <code>200</code> | Slide duration (milliseconds), default is 200 |


## page.home
Back to the App; default wait 200 milliseconds

**Example**
```js
await page.home();
```
