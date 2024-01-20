# 1. Two Sum

https://leetcode.com/problems/two-sum/

## Brute Force Solution

    public class Solution
    {
        public int[] TwoSum(int[] nums, int target)
        {
            int[] indexesOfAnswers = new int[2];

            for(int i = 0; i < nums.Length; i++)
            {
                for(int j = 0; j < nums.Length;j++)
                {
                    if(j != i)
                    {
                        if((nums[j] + nums[i]) == target)
                        {
                            indexesOfAnswers[0] = i;
                            indexesOfAnswers[1] = j;
                            return indexesOfAnswers;
                        }
                    }
                }
            }

            return indexesOfAnswers;
        }
    }

## Complexity

Time O(n^2)
Space O(1)

## Better Solution

    public class Solution
    {
        public int[] TwoSum(int[] nums, int target)
        {
            Dictionary<int, int> map = new Dictionary<int, int>();

            for (int i = 0; i < nums.Length; i++)
            {
                int complement = target - nums[i];

                if (map.ContainsKey(complement))
                {
                    return new int[] { map[complement], i };
                }
                else
                {
                    map[nums[i]] = i;
                }
            }

            return new int[] { -1, -1 };
        }
    }

## Complexity

Time O(n)
Space O(n)
