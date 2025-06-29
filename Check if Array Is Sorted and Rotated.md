# 1752. Check if Array Is Sorted and Rotated

## Approach :
so we are given an array which can be rotated by one point x
and x = 0,1,2,3,....

and we have to check the array given is sorted or not
the optimal approach to solve is we initailize a integer c =0;

and traverse the loop if (arr[i]>arr[i+1]) them we do c++

so after traversing the array we have 3 cases
1. c=0 and arr[0] < arr[len-1] => array is sorted
2. c=1 and arr[0] > arr[len-1] => array is sorted
3. otherwise array is not sorted

## Solution :
```cpp
bool check(vector<int>& nums) {
    int n = nums.size(), c = 0;
    if (n <= 1) return true;

    for (int i = 0; i < n - 1; i++) {
        if (nums[i] > nums[i + 1]) c++;
    }

    if (c == 0 && nums[0] <= nums[n - 1]) return true;
    else if (c == 1 && nums[0] >= nums[n - 1]) return true;
    else return false;
}
```

