1.**找出元素 item 在给定数组 arr 中的位置**

##### **输出描述:**

```
如果数组中存在 item，则返回元素在数组中的位置，否则返回 -1
```

##### **输入例子:**

```
indexOf([ 1, 2, 3, 4 ], 3)
```

##### **输出例子:**

```
2
```

**解**

```js
function indexOf(arr,item){
  var j=-1;
  //先设默认值
  if(!Array.isArray(arr)) return -2;
  //判断arr是否为数组，更健全！
  for(var i=0;i<arr.length;i++){
  	if(item===arr[i]) return i;
  }
  //如果在循环中找到，就return，函数就终止了
  return j;
  //这个就是默认值-1
}
```



2.**计算给定数组 arr 中所有元素的总和** 

##### **输入描述:**

```
数组中的元素均为 Number 类型
```

##### **输入例子:**

```
sum([ 1, 2, 3, 4 ])
```

##### **输出例子:**

```
10
```

**解**

```js
function sum(arr) {
	var sum=0;
    for(var i=0;i<arr.length;i++){
    	sum+=arr[i];
    }
    //循环遍历+=带走
    return sum;
}
```



3.**移除数组 arr 中的所有值与 item 相等的元素。不要直接修改数组 arr，结果返回新的数组** 

##### **输入例子:**

```
remove([1, 2, 3, 4, 2], 2)
```

##### **输出例子:**

```
[1, 3, 4
```

**解**

```js
function remove(arr, item) {
	var res=[],
		j=0;
    for(var i=0;i<arr.length;i++){
    	if(item!=arr[i]){
        	res[j++]=arr[i];
        }
    }
    return(res);
}
```

建立一个空数组操作，空的数组存新数据。下面我放另外一种常犯的错误

**错解**

```js
function remove(arr, item) {
	var res=[];
    for(var i=0;i<arr.length;i++){
    	if(item!=arr[i]){
        	res[i]=arr[i];
        }
    }
    console.log(res);
}
```

这样的结果是错的，我们打开浏览器查看，就知道其中的错误了

`Array [ 1, <1 个空的存储位置>, 3, 4 ]` 

就是我们下标为1的位置为空，所以我们必须多一个`j`指针才行！！！



4.**移除数组 arr 中的所有值与 item 相等的元素，直接在给定的 arr 数组上进行操作，并将结果返回** 

**输入例子:**
`removeWithoutCopy([1, 2, 2, 3, 4, 2, 2], 2)`

**输出例子:**

`[1, 3, 4]`

**解**

```js
function removeWithoutCopy(arr, item) {
	for(var i=0;i<arr.length;i++){
    	if(item==arr[i]){
        	arr.splice(i,1);
            i--;
        }
    }
    return arr;
    //console.log(arr);
}

```

这道题主要考splice的用法，相信网上有好多array的方法介绍，这里不赘述。但是思考的一下，为什么这里的`i--`要存在，就算去掉也是一样的？









