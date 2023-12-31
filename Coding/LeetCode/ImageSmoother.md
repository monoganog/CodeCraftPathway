# 661. Image Smoother

https://leetcode.com/problems/image-smoother/description/

## Solution

    public class Solution
    {
        public int[][] ImageSmoother(int[][] img)
        {
            int[][] smoothedArray = new int[img.Length][];

            for(int x = 0; x < img.Length; x++)
            {

                smoothedArray[x] = new int[img[x].Length];

                for(int y = 0; y < img[x].Length; y++)
                {
                    int smoothSum = 0;
                    int spacesVisited = 0;

                    for(int x2 = -1; x2 <=1; x2++)
                    {
                        for(int y2 = -1; y2 <= 1; y2++)
                        {
                            if(IsIndexInBounds(img,x + x2,y + y2))
                            {
                                smoothSum += img[x+x2][y+y2];
                                spacesVisited++;
                            }
                        }

                        if(smoothSum > 0 && spacesVisited > 0)
                        {
                            smoothedArray[x][y] = smoothSum/spacesVisited;
                        }
                    }
                }
            }
                return smoothedArray;
        }

        public bool IsIndexInBounds(int[][] array, int row, int col)
        {
            if (row >= 0 && row < array.Length && col >= 0 && col < array[row].Length)
            {
                return true;
            }
            return false;
        }
    }

## Complexity

Time O(m \* n)
Space O(m \* n)
