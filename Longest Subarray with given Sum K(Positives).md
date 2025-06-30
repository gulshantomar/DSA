# Longest Subarray with given Sum K(Positives)

# [Problem](https://takeuforward.org/data-structure/longest-subarray-with-given-sum-k/)

## Approach :
### Brute Force :
first we generate all the subarray and find sum of that sub array and compare that if sum == k if yes then store the length of max array in result var

```cpp
for(int i=0;i<n;i++){
    for(int j=i;j<n;j++){
        sum +=arr[j];
        if(sum==k) len = max(len,i-j-1)
    }
}

print(len)
```

### Better :
we will do some reverse mathematics in this

```cpp
int getLongestSubarray(vector<int>& a, long long k) {
    int n = a.size(); // size of the array.

    int left = 0, right = 0; // 2 pointers
    long long sum = a[0];
    int maxLen = 0;
    while (right < n) {
        // if sum > k, reduce the subarray from left
        // until sum becomes less or equal to k:
        while (left <= right && sum > k) {
            sum -= a[left];
            left++;
        }

        // if sum = k, update the maxLen i.e. answer:
        if (sum == k) {
            maxLen = max(maxLen, right - left + 1);
        }

        // Move forward thw right pointer:
        right++;
        if (right < n) sum += a[right];
    }

    return maxLen;
}
```

### Optimal :
this approach uses two pointer technique in this we have two pointer left and right

right pointer is used to add values of array in sum and if sum increases than k we decrease it by subracting arr[left++] till sum>k and if sum = k we give the max length to sub array to len

```cpp
while(right<n){
    while(left <= right && sum > k){
        sum-=arr[left++]

    }
    if(sum==k) maxLen = max(maxLen,right-left+1);
    right++;
    if(right<n) sum+=arr[right];
}
```


