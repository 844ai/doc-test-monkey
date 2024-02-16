# 示例代码demo
以下内容方便查看和理解,更多请查看更新更频繁的github仓库：[844ai/testMonkey - github](https://github.com/844ai/testMonkey)。也欢迎提交您的代码。


## app: page

```javascript

openAppName("微信")
// openApp("com.tencent.mm")

await sleep(500); 

Screen.setMetrics( 390 , 844); // 当使用page.tap(x,y)时，Screen.setMetrics可以确保不同宽高的屏幕运行正常 

// await page.tap(243,801, { left: 195 , top: 775 , width:97,height:53 } );
await page.waitFor('=通讯录');
await page.click('=通讯录');
await sleep(500); 

await page.waitFor('=微信');
await page.click('=微信');

await page.tap(195,115, { left: 0 , top: 81 , width:390,height:68 } );  // 列表中第一个位置的坐标

// await page.tap(174,801, { left: 46 , top: 783 , width:257,height:37 } );
await page.waitFor('#bkk[isEditable="true"]');
await page.click('#bkk[isEditable="true"]'); 
await sleep(500); 

await page.waitFor('#bkk[isEditable="true"]'); 
await page.type('#bkk[isEditable="true"]' , "测试");
await sleep(500); 

// await page.tap(352,493, { left: 323 , top: 478 , width:58,height:30 } );
await page.waitFor('#bql');
await page.click('#bql'); // await page.click("=发送")
await sleep(500); 


```

## app: appstorage

```javascript
appStorage.setItem("age", "10" )
console.log("appStorage get 1:" , appStorage.getItem("age" ) )

appStorage.setItem("age", 20 )
console.log("appStorage get 2:" , appStorage.getItem("age" ) )

appStorage.setItem("age", null )
console.log("appStorage get 3:" , appStorage.getItem("age" ) )
```

## web:chrome & webview
接口参考谷歌chrome headless的api，如 [puppeteer Page](https://zhaoqize.github.io/puppeteer-api-zh_CN/#?product=Puppeteer&version=puppeteer-v21.6.1&show=api-class-page)

```javascript
toast("5秒钟切换回页面")
let url = await page.url()
console.log("url:", url);
await page.goto("https://www.baidu.com");
await sleep(5000);
await page.goto(url);
```


## 通用 console
```javascript
Console.open();
Console.show();
Console.showLine();
// Console.showTime();
// Console.clear();
Console.log("hello testk monkey", "auto test")
Console.log("测试App悬浮窗打印信息");
Console.warn("warn info，警告信息");
Console.error("error info，错误信息");

Console.log("测试打印")
Console.hide( 2000 ); // delay hide 
```

## 通用 爬虫 crawler

#### 协议版本
```javascript
const hds = [
    {'User-Agent':'Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.6) Gecko/20091201 Firefox/3.5.6'},
    {'User-Agent':'Mozilla/5.0 (Windows NT 6.2) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.12 Safari/535.11'},
    {'User-Agent': 'Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; Trident/6.0)'}
];
const bookTag = '计算机'
const headers = hds[Math.floor(Math.random() * hds.length)];
// let url = `http://www.douban.com/tag/${encodeURIComponent(bookTag)}/book`;        
let url = "https://book.douban.com/subject/36424128/" ;                
        
function extractInfo(infoText, key) {
    const regex = new RegExp(`${key}\\s*([^\n]+)`);
    const match = infoText.match(regex);
    return match ? match[1].trim() : '';
}

let html = await axios.get(url, { headers }).then( r=> r.data) ;
let $ = cheerio.load(html);
let infoText = $('#info').text();

const book = {
    title: $('h1 span').text(),
    author: $('#info span a').first().text(),
    subtitle: extractInfo(infoText, '副标题:'),
    publisher: $('#info .pl:contains("出版社:")').next('a').text(),
    // year: $('#info .pl:contains("出版年:")').next().text(),  //没有值
    // price: $('#info .pl:contains("定价:")').next().text(),
    series: $('#info .pl:contains("丛书:")').next('a').text(),
    // ISBN: $('#info .pl:contains("ISBN:")').next().text()
    year: extractInfo(infoText, '出版年:'),
    price: extractInfo(infoText, '定价:'),
    series: extractInfo(infoText, '丛书:'),
    ISBN: extractInfo(infoText, 'ISBN:')
};
console.log("book item:", JSON.stringify(book));
```

#### 浏览器版本crawl
```javascript
let userAgent = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/96.0.4664.45 Safari/537.36" ;
webView.setUserAgent(userAgent);
// page.evaluate(()=> AndroidApp.setUserAgent(userAgent) ) ;
// page.evaluate((value)=> AndroidApp.setUserAgent(value) , userAgent ) ;
await sleep(1000)

await page.goto('https://book.douban.com/subject/36424128/');

// Extract book information
const book = await page.evaluate(() => {
    function extractInfo(infoText, key) {
        const regex = new RegExp(`${key}\\s*([^\n]+)`);
        const match = infoText.match(regex);
        return match ? match[1].trim() : '';
    }            

    const infoText = document.querySelector('#info').textContent;
    return {
        title: document.querySelector('h1 span').innerText,
        author: document.querySelector('#info span a').innerText,
        subtitle: extractInfo(infoText, '副标题:'),
        publisher: extractInfo(infoText, '出版社:'),
        year: extractInfo(infoText, '出版年:'),
        price: extractInfo(infoText, '定价:'),
        series: extractInfo(infoText, '丛书:'),
        ISBN: extractInfo(infoText, 'ISBN:')
    };
});

// Log book information
console.log("Book Information:", JSON.stringify(book));
```

## 通用 device
```javascript
console.log("device.js start")
let width = Device.width() ;
let rotation = Device.rotation() ;
let height = Device.height() ;
let getIMEI = Device.getIMEI() ;
let isWifi = Device.isWifi();
let localIp = Device.getLocalIp();
console.log('Device:' , JSON.stringify({width, height, rotation , getIMEI , isWifi , localIp }) )
Device.vibrate(1000)
```

### event
```javascript
App.addEventListener( NotificationEvent.received , function( data ){
    console.log( "NotificationEvent.received" , JSON.stringify(data) ) ;
    toast("sms:" + JSON.stringify(data) )
}) ;
```

### http
```javascript


```

### 全局global
```javascript
openApp("com.tencent.mm")

```

### screenshot
```javascript

Screen.setMetrics(390,844); // 1080, 1920
let opened = Screen.isEnabled();
Screen.requestPermission();  
toast("开启权限状态：" + opened)
if(!opened){
    await page.waitFor("=立即开始")
    await page.click("=立即开始")
}
        
```

### selector
```javascript
let people = await page.$('#kbq[text="用户昵称"]');
console.log("ele find" , JSON.stringify(people ) ) ;

let people1 = await page.$('.android.view.View[text="爱读书"]');
console.log("ele find" , JSON.stringify(people1) ) ;

let people2 = await page.$('.View[text="爱读书"]');
console.log("ele find" , JSON.stringify(people2) ) ;
  
```

### sound
```javascript
let value = getVolume()
console.log('getVolume:', value);
setVolume( 50 ) ; // setVolume( 50 , type对应静态整形数值 ) 
```

### touch
```javascript
Screen.setMetrics(390,844);
await page.touchMove( 190 , 50, 173, 716 ,  5000 ) ;
await sleep(2000)
await page.touchMove( 173, 716 ,  190 , 50,500 ) ;   //  touch up

await page.touchDown(336, 816); // 也触发了点击效果；

await page.longTap(321, 616); // == await page.tap(321, 616, { delay: 500 })
```

### page

#### page.waitForFunction
```javascript

toast("wait start for ratation")
await page.waitForFunction(()=> Device.rotation() !=0 );
toast("wait roation end! step 1")
await page.waitFor(()=> Device.rotation() ==0 );
toast("wait roation end! step 2")
```
