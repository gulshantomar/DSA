# Leaders in an Array
[Problem](https://takeuforward.org/data-structure/leaders-in-an-array/)

## Approach
Problem Statement: Given an array, print all the elements which are leaders. A Leader is an element that is greater than all of the elements on its right side in the array.

initially the leader is INT_MIN
so to find tha leader we traverse the array from right and if find a number greater than the previous leader then print that number and update the new leader

```cpp []
leader= INT_MIN
for(int i=0;i<n;i++){
    if(nums[i]>leader){
        leader = nums[i];
        cout << leader
    }
}
```
