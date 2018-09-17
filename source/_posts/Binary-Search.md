---
title: Binary Search
date: 2018-09-13 15:17:34
tags: [JavaScript, Algorithm]
---



# Binary Search

Binary Search 的前提条件是 1. 有序 2. 数组    
满足以后，即可取中间值判断与目标值是否相等， 如不相等，再取中间值对比，此时中间值为 prev中间值和最低值、最高值 中间的值

mid = (mid + high)/2      
mid = (low + mid)/2     

Time: O(logN)

```
function binarySearch(target,arr,start,end) {
    var start   = start || 0;
    var end     = end || arr.length-1;

    var mid = parseInt(start+(end-start)/2);
    if(target==arr[mid]){
        return mid;
    }else if(target>arr[mid]){
        return binarySearch(target,arr,mid+1,end);
    }else{
        return binarySearch(target,arr,start,mid-1);
    }
    return -1;
}
```

```
function binarySearch(target,arr) {
    var start   = 0;
    var end     = arr.length-1;

    while (start<=end){
        var mid = parseInt(start+(end-start)/2);
        if(target==arr[mid]){
            return mid;
        }else if(target>arr[mid]){
            start   = mid+1;
        }else{
            end     = mid-1;
        }
    }
    return -1;
}
```