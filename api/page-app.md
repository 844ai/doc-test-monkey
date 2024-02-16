## page - puppeteerApp

在android app中运行，调用kotlin代码.
[Page](https://zhaoqize.github.io/puppeteer-api-zh_CN/s-page#?product=Puppeteer&version=puppeteer-v21.6.1&show=api-class-page)
默认已经实例化了一个page对象，可以直接使用。如 await page.click('#id');



## page.title() ⇒ <code>\*</code>
获取当前app的名称，如微信


**Returns**: <code>\*</code> - {Promise&lt;string&gt;}


## page.url() ⇒ <code>\*</code>
获取当前app的package name


**Returns**: <code>\*</code> - {Promise&lt;string&gt;} , 如com.tencent.mm/android.widget.FrameLayout


## page.goto(activityFullName) ⇒ <code>\*</code>
跳转到指定app的activity


**Returns**: <code>\*</code> - {Promise&lt;void&gt;}

| Param | Type |
| --- | --- |
| activityFullName | <code>string</code> |



## page.$(selector) ⇒ <code>\*</code>
获取指定元素，如果元素不存在，返回null。如果存在多个，则返回第一个。


**Returns**: <code>\*</code> - {Promise&lt;any&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let ele = await page.$('#bkk');
```


## page.$$(selector) ⇒ <code>\*</code>
获取所有指定元素，返回数组。


**Returns**: <code>\*</code> - {Promise&lt;any[]&gt;}

| Param | Type |
| --- | --- |
| selector | <code>string</code> |

**Example**
```js
let eles = await page.$$('#bkk');
```


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


## page.evaluate(pageFunction, ...args) ⇒ <code>Promise.&lt;Serializable&gt;</code>
在页面上执行指定的方法。类似eval()方法。


**Returns**: <code>Promise.&lt;Serializable&gt;</code> - pageFunction执行的结果

| Param | Type | Description |
| --- | --- | --- |
| pageFunction | <code>function</code> \| <code>string</code> | 要在页面实例上下文中执行的方法 |
| ...args | <code>\*</code> | 要传给 pageFunction 的参数 |



## page.waitForSelector(selector, options) ⇒ <code>Promise.&lt;AppElement&gt;</code>
要等待的元素选择器
等待指定的选择器匹配的元素出现在页面中，如果调用此方法时已经有匹配的元素，那么此方法立即返回。 如果指定的选择器在超时时间后扔不出现，此方法会报错。     


**Returns**: <code>Promise.&lt;AppElement&gt;</code> - 返回一个 Promise，resolve 后返回一个 AppElement 对象。

| Param | Type | Description |
| --- | --- | --- |
| selector | <code>string</code> | 要等待的元素选择器。和document.querySelector()的参数一样。css选择器语法格式；#id，.class，[attr=value]，=文本, >=文本
 |
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


## page.screenshot([options]) ⇒ <code>Promise.&lt;string&gt;</code>
对当前页面进行截图。


**Returns**: <code>Promise.&lt;string&gt;</code> - - Promise 对象，resolve 后返回截图的 base64 字符串。

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | <code>Object</code> | <code>{}</code> | 可选配置参数 |
| [options.path] | <code>string</code> |  | 截图保存路径。文件扩展名决定图片类型。相对路径从当前路径解析。若未指定路径，则不保存到硬盘。 |
| [options.type] | <code>string</code> | <code>&quot;&#x27;png&#x27;&quot;</code> | 指定截图类型，可为 'jpeg' 或 'png'。默认 'png'。 |
| [options.quality] | <code>number</code> |  | 图片质量（0-100），仅适用于 jpeg 类型。 |
| [options.clip] | <code>Object</code> |  | 指定裁剪区域 |
| [options.clip.x] | <code>number</code> |  | 裁剪区域左上角 x 坐标 |
| [options.clip.y] | <code>number</code> |  | 裁剪区域左上角 y 坐标 |
| [options.clip.width] | <code>number</code> |  | 裁剪宽度 |
| [options.clip.height] | <code>number</code> |  | 裁剪高度 |
| [options.omitBackground] | <code>boolean</code> | <code>false</code> | 是否隐藏默认白色背景，使背景透明。默认不透明。 |
| [options.encoding] | <code>string</code> | <code>&quot;&#x27;binary&#x27;&quot;</code> | 图像编码类型，可为 'base64' 或 'binary'。默认 'binary'。 |   



## page.clicks(selectors, options)
方便点击多个元素。如输入金额、密码.



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
在指定的坐标位置进行轻触（tap）操作。


**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [options] | <code>Object</code> | <code>{}</code> | 可选配置参数 |
| [options.clickCount] | <code>number</code> | <code>1</code> | 点击次数，默认为1 |
| [options.delay] | <code>number</code> | <code>50</code> | 点击之间的延迟时间（毫秒），默认为50 |
| [options.interval] | <code>number</code> | <code>100</code> | 每次点击之间的间隔时间（毫秒），默认为100 |
| [options.left] | <code>number</code> \| <code>null</code> | <code></code> | 区域左上角的 X 轴坐标。如果设置了 left，top，width，height，则会在该区域内
随机生成坐标。 |
| [options.top] | <code>number</code> \| <code>null</code> | <code></code> | 区域左上角的 Y 轴坐标 |
| [options.width] | <code>number</code> \| <code>null</code> | <code></code> | 区域宽度 |
| [options.height] | <code>number</code> \| <code>null</code> | <code></code> | 区域高度 |


## page.tapText(text, [options]) ⇒ <code>Promise.&lt;void&gt;</code>
点击指定文本的元素，当匹配多个元素时，点击第一个元素。
解决 page.click时失效，找不到元素的问题；提高健全性；
和下面代码相同，把它包装成了一个方法。方便使用
```js
let elements = await page.elements()
let item = flatElements(elements).find(item => item.text === '查看排行榜');
if(item){
    let { left , top , right , bottom  } = item.boundsInScreen ;
    let x = ( left + right ) / 2 ;
    let y = ( top + bottom ) / 2 ;
    await page.tap(  x , y );
}
```

**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | text 文本，默认是>=选择器。text支持选择器字符。如：爱读书，=爱读书，或 >=爱读书。 |
| [options] | <code>Object</code> | <code>{}</code> | 可选配置参数 |
| [options.clickCount] | <code>number</code> | <code>1</code> | 点击次数，默认为1 |
| [options.delay] | <code>number</code> | <code>50</code> | 点击之间的延迟时间（毫秒），默认为50 |
| [options.interval] | <code>number</code> | <code>100</code> | 每次点击之间的间隔时间（毫秒），默认为100 |



## page.elements
获取当前页面的所有元素，
数据内容是nodeInfo转换为json对象。

**Kind**: static property of [<code>page</code>](#page)


## page.longTap ⇒ <code>Promise.&lt;void&gt;</code>
在指定的坐标位置进行长按（long tap）操作。触发长按，如手机系统桌面长按app图标。接口参数类似 如page.tap

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [options] | <code>Object</code> | <code>{}</code> | 可选配置参数 |
| [options.delay] | <code>number</code> | <code>500</code> | 长按延迟时间（毫秒），默认为500 |
| [options.left] | <code>number</code> \| <code>null</code> | <code></code> | 区域左上角的 X 轴坐标 |
| [options.top] | <code>number</code> \| <code>null</code> | <code></code> | 区域左上角的 Y 轴坐标 |
| [options.width] | <code>number</code> \| <code>null</code> | <code></code> | 区域宽度 |
| [options.height] | <code>number</code> \| <code>null</code> | <code></code> | 区域高度 |


## page.touchDown ⇒ <code>Promise.&lt;void&gt;</code>
模拟按下指定坐标位置的触摸操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | X 轴坐标位置 |
| y | <code>number</code> | Y 轴坐标位置 |



## page.touchUp ⇒ <code>Promise.&lt;void&gt;</code>
模拟释放指定坐标位置的触摸操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Description |
| --- | --- | --- |
| x | <code>number</code> | X 轴坐标位置 |
| y | <code>number</code> | Y 轴坐标位置 |



## page.touchMove ⇒ <code>Promise.&lt;void&gt;</code>
模拟从一个坐标位置移动到另一个坐标位置的触摸滑动操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| xFrom | <code>number</code> |  | 起始 X 轴坐标位置 |
| yFrom | <code>number</code> |  | 起始 Y 轴坐标位置 |
| xTo | <code>number</code> |  | 目标 X 轴坐标位置 |
| yTo | <code>number</code> |  | 目标 Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |



## page.swipe ⇒ <code>Promise.&lt;void&gt;</code>
模拟从一个坐标位置滑动到另一个坐标位置的滑动操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| xFrom | <code>number</code> |  | 起始 X 轴坐标位置 |
| yFrom | <code>number</code> |  | 起始 Y 轴坐标位置 |
| xTo | <code>number</code> |  | 目标 X 轴坐标位置 |
| yTo | <code>number</code> |  | 目标 Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |



## page.swipeDown ⇒ <code>Promise.&lt;void&gt;</code>
模拟从指定坐标位置向下滑动的操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |



## page.swipeUp ⇒ <code>Promise.&lt;void&gt;</code>
模拟从指定坐标位置向上滑动的操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |



## page.swipeLeft ⇒ <code>Promise.&lt;void&gt;</code>
模拟从指定坐标位置向左滑动的操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |



## page.swipeRight ⇒ <code>Promise.&lt;void&gt;</code>
模拟从指定坐标位置向右滑动的操作。

**Kind**: static property of [<code>page</code>](#page)
**Returns**: <code>Promise.&lt;void&gt;</code> - 一个表示操作完成的 Promise

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| x | <code>number</code> |  | X 轴坐标位置 |
| y | <code>number</code> |  | Y 轴坐标位置 |
| [duration] | <code>number</code> | <code>200</code> | 滑动持续时间（毫秒），默认为200 |


## page.home
回到这个App；默认等待200毫秒

**Example**
```js
await page.home();
```