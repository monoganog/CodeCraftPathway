# 1758. Minimum Changes To Make Alternating Binary String 

https://leetcode.com/problems/minimum-changes-to-make-alternating-binary-string/description/

## Solution

    public class Solution
    {
        public int MinOperations(string s)
        {
            int startsWithZeroOperations = CountOperations(0, s);
            int startsWithOneOperations = CountOperations(1, s);

            return(Math.Min(startsWithZeroOperations, startsWithOneOperations));
        }

        public int CountOperations(int startingNumber, string s)
        {
            int operationsPerformed = 0;
            int currentNumber = startingNumber;

            for(int i = 0; i < s.Length; i++)
            {
                if(currentNumber.ToString() != s[i].ToString())
                {
                    operationsPerformed++;
                }

                currentNumber = 1 - currentNumber;
            }
            return operationsPerformed;
        }
    }

## Complexity

Time O(n)
Space O(1)
