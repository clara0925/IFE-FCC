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

titleCase("I'm a little tea pot");
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

confirmEnding("He has to give me a new name", "name");
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

chunk([0, 1, 2, 3, 4, 5, 6, 7, 8], 4);
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

mutation(["zyxwvutsrqponmlkjihgfedcba", "qrstu"]);
```
[`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf#Example:_indexOf_and_case-sensitivity)

