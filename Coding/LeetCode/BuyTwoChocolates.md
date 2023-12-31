# 2706. Buy Two Chocolates

https://leetcode.com/problems/buy-two-chocolates/description/

## Solution

    public class Solution
    {
        public int BuyChoco(int[] prices, int money)
        {
            int cheapestChocolate = 100;
            int secondCheapestChocolate = 100;

            for(int i = 0; i < prices.Length; i++)
            {
                if(prices[i] < cheapestChocolate)
                {
                    secondCheapestChocolate = cheapestChocolate;
                    cheapestChocolate = prices[i];
                }
                else if(prices[i] < secondCheapestChocolate)
                {
                    secondCheapestChocolate = prices[i];
                }
            }

            if((cheapestChocolate + secondCheapestChocolate) <= money)
            {
                return money - (cheapestChocolate + secondCheapestChocolate);
            }

            return money;
        }
    }

## Complexity

Time O(n)
Space O(1)
