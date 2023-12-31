# 1897. Redistribute Characters to Make All Strings Equal

https://leetcode.com/problems/path-crossing/description/

## Solution

    public class Solution
    {
        public bool MakeEqual(string[] words)
        {
            Dictionary<char,int> charFrequencyDict = new Dictionary<char,int>();

            foreach(string word in words)
            {
                foreach(char character in word)
                {
                    if (charFrequencyDict.ContainsKey(character))
                    {
                        charFrequencyDict[character]++;
                    }
                    else
                    {
                        charFrequencyDict[character] = 1;
                    }
                }
            }

            foreach (var kvp in charFrequencyDict)
            {
                if((kvp.Value % words.Length) != 0)
                {
                    return false;
                }
            }
            return true;
        }
    }

## Complexity

Time O(n\*m)
Space O(n) (assuming a fixed character set like lowercase English alphabet)
