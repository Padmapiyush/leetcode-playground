# Solution

```
class Solution {
    public int singleNumber(int[] nums) {
        int j = 0;
        for(int num:nums){
            j = j^num;
        }
        return j;
        }
    }

```

# Explaination
- Ways to Solve : 
1. Hash Mapping and storing every element in key pairs.
   | Number | Occurrence |
   |-----------------|-----------------|
   | 4 | 1 |
   | 1 | 2 |
   | 2 | 2 |
but because we are processing every number here in the list with extra space, it will return **Time Complexity**: `O(n)` and **Space Complexity**: `O(n)`

2. Using Sorting Technique
   | 1 | 1 | 2 | 2 | 4 |
   |---|---|---|---|---|

   Here Space Complexity reduced to `O(1)` but the Time Complexity has increased to `O(nlogn)`

3. **Applying** Using XOR :
   | Number | Boolean |
   |--------|---------|
   | 4 | 100 |
   | 1 | 001 |
   | 2 | 010 |
   | 1 | 001 |
   | 2 | 010 |
   | **XOR** | `100` |
   
   When we do **XOR** of two or more same numbers, it returns `0` or **Unpaired Value** or **Unique Value**
   Thus we'll **XOR** here of all the numbers using For Each loop. 
   
