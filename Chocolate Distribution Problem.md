<h2> Chocolate Distribution Problem : </h2>
Given an array A[ ] of positive integers of size N, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates. There are M students, the task is to distribute chocolate packets among M students such that : <br/>
1. Each student gets exactly one packet. <br/>
2. The difference between maximum number of chocolates given to a student and minimum number of chocolates given to a student is minimum. <br/>

**Example 1:**

Input: <br/>
N = 8, M = 5 <br/>
A = {3, 4, 1, 9, 56, 7, 9, 12} <br/>
Output: 6 <br/>
Explanation: The minimum difference between maximum chocolates and minimum chocolates is 9 - 3 = 6 by choosing following M packets : {3, 4, 9, 7, 9}. <br/>

**Example 2:**

Input: <br/>
N = 7, M = 3 <br/>
A = {7, 3, 2, 4, 9, 12, 56} <br/>
Output: 2 <br/>
Explanation: The minimum difference between maximum chocolates and minimum chocolates is 4 - 2 = 2 by choosing following M packets : {3, 2, 4}.

-----------------------------------------------------------------------------------------------------------------------------------------------------------

<h3> Solution : </h3>

Time Complexity : O(NlogN)

```java
public long findMinDiff (ArrayList<Long> a, long n, long m)
{
    Collections.sort(a);
    int i,diff;
    long min_window=0, max_window=0;
    int ans=Integer.MAX_VALUE;
    for(i=0;i<=n-m;i++)
    {
        min_window=a.get(i);
        max_window=a.get(i+(int)m-1);
        diff=(int)(max_window - min_window);
        if(diff < ans)
            ans = diff;
    }
    return (long)ans;
}
```
![image](https://user-images.githubusercontent.com/23376002/155646608-5059acbd-93b6-413c-886a-4819f8246539.png)

TRting some changes


