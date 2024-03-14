# Best Time to Buy and Sell Stock II 
**Leetcode:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/?envType=study-plan-v2&envId=top-interview-150

#### Solution:
```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        for(int i=0;i<prices.size()-1;i++){
            if(prices[i] < prices[i+1]){
                profit += (prices[i+1] - prices[i]);
            }
        }
        return profit;
    }
};
```
**Takeaway:** I was able to think of it in myn own way, though a few Dynamic Programming ways to approach this can be really helpful too.
