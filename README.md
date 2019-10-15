### arguments使用

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



### 字符串方法

1. charAt(): 返回指定位置的字符串（从0开始算起）

   ```javascript
   var str = 'abc';
   var str1 = str.charAt(1);
   document.write(str1);			//输出b
   ```

2. indexOf(): 返回字符在字符串中首次出现的位置（如果没有则返回-1）

   ```javascript
   var str = 'abcb';
   var str1 = str.indexOf('b');
   document.write(str1);			//输出1
   ```

3. lastIndexOf(): 返回字符在字符串中“最后一次出现的位置”

   ```javascript
   var str = 'abcb';
   var str1 = str.lastIndexOf('b');
   document.write(str1);			//输出3
   ```

4. replace(): 替换，将字符串的部分内容替换为另外的内容

   ```javascript
   var str = 'abc';
   var str1 = str.replace('a','1');
   document.write(str1);			//输出1bc
   ```

5. slice(): 截取 （如果是负数则从后向前截取）

   ```javascript
   var str = 'abcdefg';
   var str1 = str.slice(1,5);
   document.write(str1);			//输出bcde
   var str2 = str.slice(2);
   document.write(str2);			//输出cdefg
   var str3 = str.slice(-1);
   document.write(str3);			//输出g
   var str3 = str.slice(-2);
   document.write(str3);			//输出fg
   ```

6. substring(): 截取 （如果是负数则返回整个字符串）

   ```javascript
   var str = 'abcdefg';
   var str1 = str.substring(1,5);
   document.write(str1);			//输出bcde
   var str2 = str.substring(2);
   document.write(str2);			//输出cdefg
   var str3 = str.substring(-1);
   document.write(str3);			//输出abcdefg
   ```

7. trim():  去除前后空格

   ```javascript
   var str = '  abcdefg  ';
   var str1 = str.trim();
   document.write(str1);			//输出abcdefg
   ```

8. toUpperCase(): 将字符串改换成大写

   ```javascript
   var str = 'abc';
   var str1 = str.toUpperCase();
   document.write(str1);			//输出ABC
   ```
   
9. toLowerCase(): 将字符串转换成小写

   ```javascript
   var str = 'ABC';
   var str1 = str.toLowerCase();
   document.write(str1);			//输出abc
   ```
   
10. split(): 将字符串拆分为数组

    ```javascript
    var str = 'A-B-C';
    var str1 = str.split(‘-’);		//str1==>是数组
    document.write(str1);			//输出A,B,C
    ```
    
11. 例题：去除字符串中的非数字字符

    ```javascript
    var str= 'cvs1r#356g7ad';
    var str1 = str.split('');			// 先把字符串拆成数组
    for(var i=0;i<str.length;i++){
        str1[i] = parseInt(str1[i]);	// 把数组的每个元素强制转换一下，如果不是数
    }									// 字会自动转成NaN
    var str2 = str1.join('');			// 把数组拼接成字符串
    str2 = str2.replace(/NaN/g,'');		// 通过全局搜索把字符串中的所有NaN改成‘’
    document.write(str2);				// 输出字符串中的数字
    ```



### 数组中的常用方法

1. concat(): 连接两个或多个数组，并返回结果

   ```javascript
   var arr = ['hello']
   var brr = ['word']
   var crr = arr.concat(brr)
   document.write(crr);		//输出 hello，word
   ```
   
2. join(): 把数组的所有元素放入到一个字符串中，通过制定的分隔符进行分割（用分隔符分割数组，最后变成一个数组）

   ```javascript
   var arr = [1,2,3];
   var brr = arr.join('===>');
   document.write(brr);		//输出 ‘1===>2===>3’
   ```
   
3. pop(): 删除并返回数组的最后一个元素

   ```javascript
   var arr = [1,2,3];
   var brr = arr.pop();
   document.write(brr);		//输出 3
   document.write(arr);		//输出 1,2
   ```
   
4. shift(): 删除并返回数组的第一个元素

   ```javascript
   var arr = [1,2,3];
   var brr = arr.shift();
   document.write(brr);		//输出 1
   document.write(arr);		//输出 2,3
   ```
   
5. push(): 向数组末尾添加新的元素，并返回新的长度

   ```javascript
   var arr = [1,2,3];
   var brr = arr.push('000');
   document.write(brr);		//输出 4(代表4个元素)
   document.write(arr);		//输出 1,2,3,000
   ```
   
6. unshift(): 向数组开头添加新的元素，并返回新的长度

   ```javascript
   var arr = [1,2,3];
   var brr = arr.unshift('000');
   document.write(brr);		//输出 4(代表4个元素)
   document.write(arr);		//输出 000,1,2,3
   ```
   
7. reverse(): 颠倒数组中元素的顺序

   ```javascript
   var arr = [1,2,3];
   var brr = arr.reverse();
   document.write(brr);		//输出 3,2,1,
   ```
   
8. slice(): 从某个已有的数组返回选定的值（截取功能）

   ```javascript
   var arr = ['a','b','c','d','e'];
   var brr = arr.slice(2,5)		
   	//第一个参数==>2:代表下标（从0开始数）
       //第二个参数==>5:代表实际位置（从1开始数）
   document.write(brr);		//输出 c,d,e
   ```
   
9. sort(): 对数组进行排序（按照数字的类型排列）

   ```javascript
   var arr = [1,3,7,5,11,2,9];
   var brr = arr.sort();
   document.write(brr);		//输出 1,11,2,3,5,7,9
   ```
   
10. splice(): 删除元素，向数组添加新元素（用指定元素替换截取的元素）

    ```javascript
    var arr = ['a','b','c','d','e'];
    var brr = arr.splice(1,3,'*****')		
    	//第一个参数==>1:代表下标（从0开始数）
        //第二个参数==>3:截取3个元素
    	//第三个参数==>*****:用该字符替换截取的元素
    document.write(arr);		//输出 a*****e
    document.write(brr);		//输出 b,c,d
    ```
    
11. toString(): 把数组转换成字符串，并返回结果

    ```javascript
    var arr = [1,3,7];
    var brr = arr.toString();
    document.write(typeof brr);		//输出 string
    ```



### 数学对象：Math

​	方法：

1. Math.min(参数一，参数二，参数三)：求出参数中最小值

   ```javascript
   document.write(Math.min(10,3,7,8));			// 输出3
   ```
   
2. Math.max(参数一，参数二，参数三)：求出参数中最大值

   ```javascript
   document.write(Math.max(10,3,7,8));			// 输出10
   ```
   
3. Math.floor()：舍掉小数，得到整数

   ```javascript
   document.write(Math.floor(4.984));			// 输出4
   ```
   
4. Math.ceil()：有小数就进一取整

   ```javascript
   document.write(Math.ceil(4.184));			// 输出5
   ```
   
5. Math.abs()：取绝对值

   ```javascript
   document.write(Math.abs(-5));				// 输出5
   ```
   
6. Math.sqrt()：开平方

   ```javascript
   document.write(Math.sqrt(64));				// 输出8
   ```

7. Math.random()：随机数

   ```javascript
   document.write(Math.random());				// 输出0~1之间的随机数
   ```

8. Math.round()：四舍五入取整

   ```javascript
   document.write(Math.round(6.3));				// 输出3
   ```



### js中的日期对象

​			new Date()

### 日期对象的方法

**假设今天日期是：	2019/10/14 	19:21:32	星期一**

*语法：日期对象.方法*

```javascript
var date = new Date();
```

1. getTime()	===>	时间戳

   从1970年1月1日0点0分开始，到现在的毫秒数

   ```javascript
   date.getTime();				// 输出 1571052551929
   ```

2. getFullYear()   ===>   年

   ```javascript
   date.getFullYear();			// 输出 2019
   ```

3. getMonth()  ===>  月

   1. 中国月份：1-12

   2. 国外月份：0-11

      ```javascript
      date.getMonth();			// 输出 9 （以国外月份为准）
      date.getMonth()+1;			// 输出 10 （中国实际月份）
      ```

4. getDate()  ===>   日

   ```JavaScript
   date.getDate();				// 输出 14
   ```

5. getDay()  ===>  星期

   ```javascript
   date.getDay();				// 输出 1
   ```

6. getHours()  ===>  小时

   ```JavaScript
   date.getHours();			// 输出 19
   ```

7. getMinutes()  ===>  分钟

   ```JavaScript
   date.getMinutess();			// 输出 21
   ```

8. getSecounds()  ===>  秒

   ```JavaScript
   date.getSecounds();			// 输出 32
   ```