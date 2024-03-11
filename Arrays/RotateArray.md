# Rotate Array: 

**Leetcode: ** https://leetcode.com/problems/rotate-array/description/?envType=study-plan-v2&envId=top-interview-150

#### First Try: 
```
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        for(int j=0; j<k;j++){
            int temp1,temp2;
            for(int i=nums.size()-1; i>=0; i--){
                if(i==nums.size()-1){
                    temp1 = nums[i];
                    temp2 = nums[i-1];
                } else if(i==0){
                    nums[nums.size()-1] = temp2;
                    nums[0] = temp1;
                } else{
                    nums[i] = nums[i-1];
                }
            }
        }
    }
};
```
**Takeaway:** Did not include testcase for when size of nums array is 1.

#### Second Try: 
```
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        if(nums.size()==1){
            
        } else {
        for(int j=0; j<k;j++){
            int temp1,temp2;
            for(int i=nums.size()-1; i>=0; i--){
                if(i==nums.size()-1){
                    temp1 = nums[i];
                    temp2 = nums[i-1];
                } else if(i==0){
                    nums[nums.size()-1] = temp2;
                    nums[0] = temp1;
                } else{
                    nums[i] = nums[i-1];
                }
            }
        }
        }
    }
};
```
**Takeaway:** My Code does not hold valid for super large arrays and a large number of rotations since it exceeds the given time limit.

#### Solution: 
```
    class Solution 
    {
    public:
        void rotate(vector<int>& nums, int k) 
        {
            int n = nums.size();
            if ((n == 0) || (k <= 0)){
                return;
            }
            
            // Make a copy of nums
            vector<int> numsCopy(n);
            for (int i = 0; i < n; i++)
            {
                numsCopy[i] = nums[i];
            }
            
            // Rotate the elements.
            for (int i = 0; i < n; i++)
            {
                nums[(i + k)%n] = numsCopy[i];
            }
        }
    };
```
**Takeaway:** Referred to solutions tab to find this solution, thought this had the easiest concept to grasp. Main takeaway was the use of modulo function for rotating the elements in the array (I didn't even think of that). 

