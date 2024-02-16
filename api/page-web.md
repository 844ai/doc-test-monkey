
## page - puppeteerApp & chrome extension

接口和谷歌公司的puppeteer库中的Page类相同。


## page.title() 
获取当前app的名称，如微信


**Returns**: <code>\*</code> - {Promise&lt;string&gt;}
`

## page.url()
获取当前app的package name


**Returns**: <code>\*</code> - {Promise&lt;string&gt;} , 如com.tencent.mm/android.widget.FrameLayout
<a name="page.ChromePage+goto"></a>

## page.goto(activityFullName) ⇒ <code>\*</code>
跳转到指定app的activity


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type |
| --- | --- |
| activityFullName | <code>string</code> |

<a name="page.ChromePage+$"></a>

## page.$(selector) ⇒ <code>\*</code>
返回dom元素，如果没有找到则返回null。和document.querySelector 作用相同
对象是克隆的，不是原始对象。主要用于获取dom元素的属性和内容。


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
返回dom元素，如果没有找到则返回null。和document.querySelectorAll 作用相同
对象是克隆的，不是原始对象。主要用于获取dom元素的属性和内容。


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
添加脚本，js会添加到body中


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type | Description |
| --- | --- | --- |
| options | <code>Object</code> |  |
| [options.url] | <code>string</code> | 脚本的URL |
| [options.content] | <code>string</code> | 脚本的内容 |
| [options.type] | <code>string</code> | 脚本的类型, script.type = options.type; |

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
添加样式表,css会添加到head中


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type | Description |
| --- | --- | --- |
| options | <code>Object</code> |  |
| [options.url] | <code>string</code> | 样式表的URL |
| [options.content] | <code>string</code> | 样式表的内容 |

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
点击指定元素


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
在页面上指定的元素中输入文本。


**Returns**: <code>Promise.&lt;void&gt;</code> - 返回一个 Promise，表示输入操作完成。

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| selector | <code>string</code> |  | 要输入内容的元素选择器。如果有多个匹配的元素，输入到第一个匹配的元素。 |
| text | <code>string</code> |  | 要输入的文本 |
| [options] | <code>Object</code> | <code>{ delay: 0, autoCorrect: true }</code> | 可选参数 |
| [options.delay] | <code>number</code> | <code>0</code> | 输入文本之间的延迟时间（毫秒）。默认为0。 |
| [options.autoCorrect] | <code>boolean</code> | <code>true</code> | 指定是否自动纠正输入的文本。默认为 true。 |

**Example**
```js
await page.type('#bkk', 'test.844.ai');
```
<a name="page.ChromePage+waitForSelector"></a>

## page.waitForSelector(selector, options) ⇒ <code>Promise.&lt;AppElement&gt;</code>
要等待的元素选择器
等待指定的选择器匹配的元素出现在页面中，如果调用此方法时已经有匹配的元素，那么此方法立即返回。 如果指定的选择器在超时时间后扔不出现，此方法会报错。    


**Returns**: <code>Promise.&lt;AppElement&gt;</code> - 返回一个 Promise，resolve 后返回一个 AppElement 对象。

| Param | Type | Description |
| --- | --- | --- |
| selector | <code>string</code> | 要等待的元素选择器。和document.querySelector()的参数一样。css选择器语法格式；#id，.class，[attr=value]，=文本, >=文 
本 |
| options | <code>Object</code> | 可选参数： |
| options.timeout | <code>number</code> | 超时时间，单位毫秒，默认30000 |
| options.pollingInterval | <code>number</code> | 轮询间隔时间，单位毫秒，默认100 |

**Example**
```js
await page.waitForSelector('#bkk');
await page.waitForSelector('#bkk', { timeout: 10000 });
await page.waitForSelector('.android.view.View[text="爱读书"]')
await page.waitForSelector('.View[text="爱读书"]');
let element = await page.waitForSelector('.View[text="爱读书"]');
await element.click();
```
<a name="page.ChromePage+waitForFunction"></a>

## page.waitForFunction(pageFunction, [options], ...args) ⇒ <code>\*</code>
等待pageFunction中的返回值为true，如果超时则报错。
waitForFunction 可以用来监控页面的大小变化，屏幕旋转。



| Param | Type | Default | Description |
| --- | --- | --- | --- |
| pageFunction | <code>\*</code> |  | 要在页面实例上下文中执行的方法 |
| [options] | <code>Object</code> | <code>{ timeout: 30000, pollingInterval: 100 }</code> |  |
| ...args | <code>\*</code> |  |  |

**Example**
```js
await page.waitForFunction(()=> Device.rotation() !=0 );
```
<a name="page.ChromePage+evaluate"></a>

## page.evaluate(fnOrString, ...args) ⇒ <code>\*</code>
在页面上下文中执行指定的方法，并返回执行结果。
把同步或异步的方法都包装一次，按照跨设备处理。减少跨设备中的逻辑代码。如：android app中WebViewInterceptor的webView.evaluateJavascript


**Returns**: <code>\*</code> - {Promise&lt;any&gt;} 返回一个 Promise，resolve 后返回 fnOrString 的执行结果。

| Param | Type | Description |
| --- | --- | --- |
| fnOrString | <code>function</code> \| <code>string</code> | 要在页面实例上下文中执行的方法 |
| ...args | <code>any</code> | 要传递给fnOrString的参数 |

**Example**
```js
await page.evaluate(() => document.title);
await page.evaluate((a, b) => a + b, 1, 2);
await page.evaluate('document.title');
await page.evaluate('function() { return document.title }');
await page.evaluate(() => Promise.resolve(8 * 7));
```


## page.home
回到app中webview的默认页面；默认等待200毫秒

**Example**
```js
await page.home();
```