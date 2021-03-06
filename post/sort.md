## 排序

在js中，数组才是有序的，所以讲排序一般都是操作数组，以下排序方法中，测试数据均为
```js
const arr = [8, 6, 4, 9, 3, 2, 1]
```

### 冒泡排序

原理：遍历对比数组相邻元素的大小

实现：数组长度为 n，遍历 n - 1 次，每次循环 n - i - 1 次找出一个最大值或最小值

<details>
  <summary>实现一</summary>
  
  ```js
  const bubbleSort = (arr = []) => {
    const newArr = [...arr]
  
    for (let i = 0; i < arr.length - 1; i++) {
      for (let j = 0; j < newArr.length; j++) {
        if (j === newArr.length - i - 1) {
          break
        } else if (newArr[j] > newArr[j + 1]) {
          [newArr[j], newArr[j + 1]] = [newArr[j + 1], newArr[j]]
        }
      }
    }
  
    return newArr
  }
  ```
</details>

<details>
  <summary>实现二</summary>
  
  ```js
  const bubbleSort2 = (arr = []) => {
    const newArr = [...arr]
    
    for (let i = 0; i < arr.length - 1; i++) {
      let j = 0
      while (j < newArr.length - i && newArr[j + 1] !== undefined) {
        if (newArr[j] > newArr[j + 1]) {
          [newArr[j], newArr[j + 1]] = [newArr[j + 1], newArr[j]]
        }
        j++
      }
    }
    
    return newArr
  }
  ```
</details>

### 选择排序

原理：遍历选择数组中最小或最大的值

实现：数组长度为 n，从左到右假设 i 处的值最小，然后遍历 n - i - 1 次找到更小的值并替换

<details>
  <summary>实现一</summary>
  
  ```js
  const selectionSort = (arr = []) => {
    const newArr = [...arr]

    for (let i = 0; i < arr.length - 1; i++) {
      let min = newArr[i]
      let minIndex = i

      for (let j = i + 1; j < newArr.length; j++) {
        if (newArr[j] < min) {
          min = newArr[j]
          minIndex = j
        }
      }
      [newArr[i], newArr[minIndex]] = [newArr[minIndex], newArr[i]]
    }

    return newArr
  }
  ```
</details>

### 插入排序

原理：从左依次插入比它大的位置

实现：数组长度为 n，遍历 n 次，然后从左依次插入比它大的位置

<details>
  <summary>实现一</summary>
  
  ```js
  const insertionSort = (arr = []) => {
    const newArr = [...arr]

    for (let i = 0; i < newArr.length; i ++) {
      let index = i
      while (index - 1 >= 0 && newArr[index] < newArr[index - 1]) {
        [newArr[index - 1], newArr[index]] = [newArr[index], newArr[index - 1]]
        index--
      }
    }

    return newArr
  }
  ```
</details>

