# Best Time to Buy and Sell Stock
**Leetcode:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/?envType=study-plan-v2&envId=top-interview-150

#### Try 1:
```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int first = prices[0];
        int temp = first;
        int bp=0; 
        int sp=0;
        if (prices.size()==2){
            bp = prices[0];
            sp = prices[1];
            int ans = sp - bp;
            if(ans<0){
                return 0;
            } else {
                return ans;
            }
        }
        for(int i=1; i<prices.size();i++){
            if((temp>prices[i]) && prices[i]<prices[i+1]){
                if(bp==0){
                    bp = prices[i];
                } else if(bp<prices[i]){
                    bp = bp;
                } else{
                    bp = prices[i];
                }
                sp = prices[i+1];
            } else if(first<prices[i]){
                bp = first;
                sp = prices[i];
            }
            temp = prices[i];
        }
        return sp-bp;
    }
};
```
**Takeaway:** I didn't take into account the multiple different types of testcases that can be given and how my code isn't viable for a lot of testcases.

#### Solution:
```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int maxPro = 0;
        int minPrice = INT_MAX;
        for(int i=0; i< prices.size(); i++){
            minPrice = min(minPrice, prices[i]);
            maxPro = max(maxPro, prices[i]-minPrice);
        }
        return maxPro;
    }
};
```
**Takeaway:** This solution is very easy and I had to look at solutions tab to understand it. This is a greedy approach and so easy to understand idk why I wasn't able to come up with it.

