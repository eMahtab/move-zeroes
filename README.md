# Move Zeroes
## https://leetcode.com/problems/move-zeroes

Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.
```
Example:

Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```
**Note:**
1. You must do this in-place without making a copy of the array.
2. Minimize the total number of operations.

# Implementation 1 : Wrong Approach (Incorrect Result)

```java
class Solution {
    public void moveZeroes(int[] nums) {
        int zeroIndex = -1;
        for(int i = 0; i < nums.length; i++){
            if(nums[i] == 0){
                zeroIndex = i;
            } else{
                if(zeroIndex != -1){
                    int tmp = nums[i];
                    nums[i] = nums[zeroIndex];
                    nums[zeroIndex] = tmp;
                    zeroIndex = i;
                }
            }
        }
    }
}
```
# Implementation 2 : Right Approach (Correct Result)

```java
class Solution {
    public void moveZeroes(int[] nums) {
        int index = 0;
        for(int i = 0; i < nums.length; i++){
            if(nums[i] != 0){
                nums[index++] = nums[i];
            }
        }
        for(int i = index; i < nums.length; i++){
            nums[i] = 0;
        }
    }
}
```

# References :
https://www.youtube.com/watch?v=1PEncepEIoE

