###### arguments使用

arguments可以获取函数的**实参**：

```javascript
function add() {
 	var res = 0;
 	if (arguments) {
 		for (var i = 0; i < arguments.length; i++) {
			if (typeof arguments[i] == "number") {
 				res += arguments[i];
 			}
 		}
 	}
 	console.log(res);
 }
 add(3, 4, 5);		//输出12
```

> arguments[0]		// 3
>
> arguments[1]		// 4
>
> arguments[2]		// 5