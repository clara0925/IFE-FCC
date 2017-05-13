FCC
===
* 遍历二维数组，找出小数组中的最大值，形成新的数组
```javascript
function largestOfFour(arr) {
  var myArr = [];
  
    for(var i = 0; i < arr.length; i++){
     for(j = 0; j < arr[i].length; j++){
        arr[i].sort(function(a,b){return b - a; });
     }
      myArr.push(arr[i][0]);
    }
  return myArr;
  }
  
largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

* 将字符串的每个首字母大写
```javascript
function titleCase(str) {
    var arr = str.toLowerCase().split(" ");
    
    for(var i = 0; i < arr.length; i++){
     arr[i] = arr[i][0].toUpperCase() + arr[i].substr(1,arr[i].length); 
                
  }
  return arr.join(" ");
}

titleCase("I'm a little tea pot"); // "I'm A Little Tea Pot"
```
[`substr()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substr)

* 检查字符串是否以指定的结尾（target）结束
```javascript
function confirmEnding(str, target) {
  var string = str.substring(str.length - target.length, str.length);
  
  if (string == target){
    return true;
  }
  else {
    return false;
  }
}

confirmEnding("He has to give me a new name", "name"); //true
```

* 把一个数组arr按照指定的数组大小size分割成若干个数组块
```javascript
function chunk(arr, size) {
  var newArr = [];
  for(var i = 0; i < arr.length; i += size){
   var a = arr.slice(i,i + size);
    newArr.push(a); 
  }
    return newArr;  
}

chunk([0, 1, 2, 3, 4, 5, 6, 7, 8], 4); // [[0, 1, 2, 3], [4, 5, 6, 7], [8]]
```
[`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
 
 
* 如果数组第一个字符串元素包含了第二个字符串元素的所有字符，函数返回true

```javascript
function mutation(arr) {
  var result;
  var j = 0;
  
      arr[0] = arr[0].toLowerCase();
      arr[1] = arr[1].toLowerCase().split("");
  
  while(j < arr[1].length) {
    result = arr[0].indexOf(arr[1][j]);
    if(result === -1) break;
    j++;
  }
  if(result === -1){ return false;}
    else { return true;}
}

mutation(["zyxwvutsrqponmlkjihgfedcba", "qrstu"]); //true
```
[`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf#Example:_indexOf_and_case-sensitivity)
 
* 实现一个摧毁函数，第一个参数是待摧毁的数组，其余的参数是待摧毁的值
```javascript
function destroyer(arr) {
  var args = arr.slice.call(arguments); //将argument对象转换成真正的数组
  var i = 1;
  var filtered = function(x){ return x != args[i];};
  
  while(i < args.length){
    args[0] = args[0].filter(filtered);
    i++; 
  }
  return args[0];
}

destroyer(["tree", "hamburger", 53], "tree", 53); //["hamburger"]
```
[`arguments`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/arguments) 
 
* 查看字符串是否是回文
```javascript
function palindrome(str) {
  var a = str.replace(/[^a-zA-Z0-9]/gi,"");
  var oldStr = str.replace(/[^a-zA-Z0-9]/gi,"");
  var arr = a.split("");
  var newStr = arr.reverse().join("");
 
 if (newStr.toLowerCase() == oldStr.toLowerCase()){
  return true;
 }
  else {
    return false;
  }
}

palindrome("race car");// true
```

* 写一个ROT13函数，实现输入加密字符串，输出解密字符串。移位密码也就是密码中的字母会按照指定的数量来做移位。
一个常见的案例就是ROT13密码，字母会移位13个位置。由'A' ↔ 'N', 'B' ↔ 'O'，以此类推。
```javascript
function rot13(str) { 
  var newNum, a;
  var newStr = "";
  var n = 0;
   
    while(n < str.length){
      newNum = str.charCodeAt(n) + 13;
      if(newNum > 90){
        newNum = newNum - 26;
      }
      a = String.fromCharCode(newNum);
      
            if(str.charCodeAt(n) < 65 || str.charCodeAt(n) > 90){
              a = str[n];
            }
      newStr += a;
      n++;
    }
  
  return newStr;
}

// Change the inputs below to test
rot13("GUR DHVPX OEBJA QBT WHZCRQ BIRE GUR YNML SBK."); //"THE QUICK BROWN DOG JUMPED OVER THE LAZY FOX."
```
[`charCodeAt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt) [`String.fromCharCode()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)fromCharCode()是String()构造函数的一个属性，不能当作对象使用。
 
 * 计算整数的阶乘
```javascript
function factorialize(num) {
  var i = 1;
  var total = 1;
  while (i <= num){
    total *= i;
    i++;
  }
  return total;
}

factorialize(7); // 5040
```
