# interviewProb
# Given a non negative integer number num. For every numbers i in the range 0 ≤ i ≤ num calculate the number of 1's in their binary representation and return them as an array.
public class Solution
{
    public int[] CountBits(int num)
    {
        int[] mylist = new int[num + 1];
        if (num < 0)
        {
            return new int[] { 0 };
        }
        mylist[0] = 0;
        for (int i = 1; i <= num; i++)
        {
            if ((i & 1) == 1)
            {
                mylist[i] = mylist[(i >> 1)] + 1;
            }
            else
            {
                mylist[i] = mylist[(i >> 1)];
            }
        }
        return mylist;
    }
}
