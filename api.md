---
outline: deep
---

# 接口文档



## 自定义脚本工具
> 注意：脚本录制工具使用http接口协议执行脚本，接口如下.
> 此方法可用于自定义自动化测试工具，或者测试平台。

```js
const baseURL = "http://192.168.28.54:60844";
let type = "app" ; // app | web
let script = ' console.log("hello world") ; ' ;
script = wrapAsync(script) ;
const res = await axios.post(`${baseURL}/SCRIPT_RUN` , {  script , type  } ).then(r => r.data);

function wrapAsync(code) {
    // 检查代码中是否已经有 'async' 关键字
    const hasAsync = /async\s+function/.test(code);

	// 如果代码包含 'await' 但不包含 'async'
	let tryCode = `
		try{
			${code}
		}catch(e){
			console.log('script run error:' ,e)

			Console.open()
			Console.show()
			Console.error("错误:", e )
			Console.hide( 10000 );
		}` ;

	// 如果代码包含 'await' 但不包含 'async'
	if (!hasAsync && /await/.test(code)) {
		// 将代码包装在一个立即执行的异步函数表达式中
		let newColde = `
			(async function() {
				${tryCode}
			})()
		` ;
		return newColde;
	}

	// 如果代码已经是 async 或者不需要修改，则原样返回
	return tryCode;
}
```