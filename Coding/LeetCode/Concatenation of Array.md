# 1929. Concatenation of Array

https://leetcode.com/problems/concatenation-of-array/

## Solution

    public class Solution
    {
        public int[] GetConcatenation(int[] nums)
        {
            int[] numsConc = new int[nums.Length *2];

            for(int i = 0; i < nums.Length; i++)
            {
                numsConc[i] = nums[i];
                numsConc[i+nums.Length] = nums[i];
            }

            return numsConc;
        }
    }

## Complexity

Time O(n)
Space O(2n)
