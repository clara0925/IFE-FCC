一些杂项
===
* 遍历二维数组，找出小数组中的最大值，形成新的数组。
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
