
## page - puppeteerApp & chrome extension

The interface is the same as the Page class in Google's Puppeteer library.


## page.title() 
Get the name of the current app, such as WeChat.


**Returns**: <code>\*</code> - {Promise&lt;string&gt;}
`

## page.url()
Get the package name of the current app, such as WeChat.


**Returns**: <code>\*</code> - {Promise&lt;string&gt;} , 如com.tencent.mm/android.widget.FrameLayout
<a name="page.ChromePage+goto"></a>

## page.goto(activityFullName) ⇒ <code>\*</code>
Jump to the activity of the specified app


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type |
| --- | --- |
| activityFullName | <code>string</code> |

<a name="page.ChromePage+$"></a>

## page.$(selector) ⇒ <code>\*</code>
Returns the DOM element, or null if not found. It has the same function as document.querySelector.
The object is cloned, not the original one. It is mainly used to get the attributes and content of DOM elements.

**Returns**: <code>\*</code> - {Promise&lt;any&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let ele = await page.$('#bkk');
```
<a name="page.ChromePage+$$"></a>

## page.$$(selector) ⇒ <code>\*</code>
Returns the DOM element, or null if not found. It has the same function as document.querySelector.
The object is cloned, not the original one. It is mainly used to get the attributes and content of DOM elements.


**Returns**: <code>\*</code> - {Promise&lt;any[]&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let eles = await page.$$('#bkk');
```
<a name="page.ChromePage+addScriptTag"></a>

## page.addScriptTag(options) ⇒ <code>\*</code>
Add script, js will be added to the body.


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type | Description                                      |
| --- | --- |--------------------------------------------------|
| options | <code>Object</code> |                                                  |
| [options.url] | <code>string</code> | the URL of script                                |
| [options.content] | <code>string</code> | the content of script                            |
| [options.type] | <code>string</code> | the type of script , script.type = options.type; |

**Example**
```js
await page.addScriptTag({ url: 'https://code.jquery.com/jquery-3.2.1.min.js' });
await page.addScriptTag({ content: 'window.alert("Injected script")' });
await page.addScriptTag({
        content: 'window.alert("Injected script")',
        onload: 'console.log("load")'
});
```
<a name="page.ChromePage+addStyleTag"></a>

## page.addStyleTag(options) ⇒ <code>\*</code>
Add style sheet, css will be added to the head.


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type | Description               |
| --- | --- |---------------------------|
| options | <code>Object</code> |                           |
| [options.url] | <code>string</code> | URL of the style sheet    |
| [options.content] | <code>string</code> | content of the style sheet |

**Example**
```js
await page.addStyleTag({ url: 'https://fonts.googleapis.com/css?family=Roboto' });
await page.addStyleTag({ content: 'body { background-color: white; }' });
await page.addStyleTag({
        content: 'body { background-color: white; }',
        onload: 'console.log("load")'
});
```
<a name="page.ChromePage+click"></a>

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
<a name="page.ChromePage+type"></a>

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
<a name="page.ChromePage+waitForSelector"></a>

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
<a name="page.ChromePage+waitForFunction"></a>

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
<a name="page.ChromePage+evaluate"></a>

## page.evaluate(fnOrString, ...args) ⇒ <code>\*</code>
Execute the specified method in the page context and return the execution result.
Wrap both synchronous and asynchronous methods once, and handle across devices. Reduce the logic code across devices. For example, WebViewInterceptor's webView.evaluateJavascript in Android app.

**Returns**: <code>\*</code> - {Promise&lt;any&gt;} Returns a Promise that resolves with the result of executing fnOrString.

| Param | Type | Description |
| --- | --- | --- |
| fnOrString | <code>function</code> \| <code>string</code> | The method to be executed in the page instance context  |
| ...args | <code>any</code> | The parameters to be passed to fnOrString  |

**Example**
```js
await page.evaluate(() => document.title);
await page.evaluate((a, b) => a + b, 1, 2);
await page.evaluate('document.title');
await page.evaluate('function() { return document.title }');
await page.evaluate(() => Promise.resolve(8 * 7));
```


## page.home
Go back to the default page of the webview in the app; wait for 200 milliseconds by default.

**Example**
```js
await page.home();
```
