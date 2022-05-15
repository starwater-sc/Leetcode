1. set search range, from left to right
2. while loop, runs wehn left <= right, ends when left > right (which means full search complete)
3. each loop, calculate the mid point and comapre
4. if mid equals target, return mid
5. if mid > target, target is within left to mid, therefore set right to mid-1
6. if mid < target, target is within mid to right, therefore set left to mid+1



```
let search = function (nums, target) {
    
    let pivot, 
        left = 0, 
        right = nums.length-1; //note this will be using array for indexing, therefore from 0 to n-1
    
    while (left <= right){
        pivot = left + Math.floor((right - left)/2);
        if(nums[pivot]===target) return pivot;
        if(target < nums[pivot]) right = pivot - 1;
        else left = pivot + 1;
    }
    return -1;
};
```
