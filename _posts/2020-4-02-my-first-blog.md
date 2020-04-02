---
layout: post
title: 任意数组中随机取出不同元素
tags: js
stickie: true
---

任意数组中随机取出不同元素 <br>
应用场景-抽奖

---

假如数组为:  
`var let = ['1','2','4','5','6','7','8','9','10'];`  
首先考虑怎样在数组中随机取出一个元素，我们可以使用 `Math.random()` 来实现随机数的选取: <br>  
`let index = Math.floor( Math.random()*arr.length ) //在上一层数组中随机随机一个元素的索引`  
`<code>let item = arr[index] //取得索引对应元素`  
现在拿到了item,即数组中随机的一个元素。  
从前面的一篇随机数组中随机取几个元素:  
```
    function getRandomArrayElements(arr, count) {
        var shuffled = arr.slice(0), i = arr.length, min = i - count, temp, index;
        while (i-- > min) {
            index = Math.floor((i + 1) * Math.random());
            temp = shuffled[index];
            shuffled[index] = shuffled[i];
            shuffled[i] = temp;
        }
        return shuffled.slice(min);
    }
    var items = ['1','2','4','5','6','7','8','9','10'];
    console.log( getRandomArrayElements(items, 4) );
```