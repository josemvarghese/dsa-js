# Big O Notation in JavaScript

Big O notation is used to describe the upper bound of an algorithm's runtime or space complexity in terms of the input size. Here are some common Big O notations with examples in JavaScript.

## O(1) - Constant Time

The runtime does not change with the size of the input.

```javascript
function getFirstElement(arr) {
    return arr[0];
}

let array = [10, 20, 30, 40, 50];
console.log(getFirstElement(array)); // Output: 10
```
## O(log n) - Logarithmic Time
The runtime increases logarithmically as the input size increases.

```javascript
function binarySearch(arr, target) {
    let left = 0;
    let right = arr.length - 1;
    
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        
        if (arr[mid] === target) {
            return mid;
        } else if (arr[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return -1; // Target not found
}

let sortedArray = [1, 3, 5, 7, 9, 11];
console.log(binarySearch(sortedArray, 7)); // Output: 3

```
## O(n) - Linear Time
The runtime increases linearly with the input size.


```javascript
function findMax(arr) {
    let maxVal = arr[0];
    
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] > maxVal) {
            maxVal = arr[i];
        }
    }
    
    return maxVal;
}

let array2 = [10, 20, 30, 40, 50];
console.log(findMax(array2)); // Output: 50


```

## O(n log n) - Linearithmic Time
The runtime increases proportionally to \( n \log n \).

```javascript


function merge(left, right) {
    let result = [];
    let leftIndex = 0;
    let rightIndex = 0;
    
    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }
    
    return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));
}

let unsortedArray = [34, 7, 23, 32, 5, 62];
console.log(mergeSort(unsortedArray)); // Output: [ 5, 7, 23, 32, 34, 62 ]



```

## O(n^2) - Quadratic Time
The runtime increases quadratically as the input size increases.

```javascript


function bubbleSort(arr) {
    let n = arr.length;
    
    for (let i = 0; i < n; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // Swap elements
            }
        }
    }
    
    return arr;
}

let unsortedArray2 = [64, 34, 25, 12, 22, 11, 90];
console.log(bubbleSort(unsortedArray2)); // Output: [ 11, 12, 22, 25, 34, 64, 90 ]


```

## O(2^n) - Exponential Time
The runtime doubles with each additional element in the input.

```javascript


function fibonacci(n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(10)); // Output: 55



```
## O(n!) - Factorial Time
The runtime increases factorially with the input size.

```javascript


function permute(str) {
    let results = [];
    
    if (str.length === 1) {
        return [str];
    }
    
    for (let i = 0; i < str.length; i++) {
        let char = str[i];
        let remainingChars = str.slice(0, i) + str.slice(i + 1, str.length);
        for (let subPermutation of permute(remainingChars)) {
            results.push(char + subPermutation);
        }
    }
    
    return results;
}

console.log(permute("abc")); // Output: [ 'abc', 'acb', 'bac', 'bca', 'cab', 'cba' ]




```


