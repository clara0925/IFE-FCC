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
  var string = str.substr(str.length - target.length, str.length);
  
  if (string == target){
    return true;
  }
  else {
    return false;
  }
}

confirmEnding("He has to give me a new name", "name");
```
