---
outline: deep
---

# Interface Documentation



## Custom Script Tool
> Note: The script recording tool uses the http interface protocol to execute scripts, and the interface is as follows.
> This method can be used for custom automation testing tools or testing platforms.

```js
const baseURL = "http://192.168.28.54:60844";
let type = "app" ; // app | web
let script = ' console.log("hello world") ; ' ;
script = wrapAsync(script) ;
const res = await axios.post(`${baseURL}/SCRIPT_RUN` , {  script , type  } ).then(r => r.data);

function wrapAsync(code) {
    // Check whether the 'async' keyword has already been used in the code.
    const hasAsync = /async\s+function/.test(code);

	// If the code contains 'await' but does not contain 'async'.
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

	// If the code contains 'await' but does not contain 'async'.
	if (!hasAsync && /await/.test(code)) {
		// Wrap the code in an immediately-invoked asynchronous function expression. 
		let newColde = `
			(async function() {
				${tryCode}
			})()
		` ;
		return newColde;
	}

	// If the code is already async or doesn't need to be modified, return it as is.
	return tryCode;
}
```
