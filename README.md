# Move Zeroes
## https://leetcode.com/problems/move-zeroes


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

