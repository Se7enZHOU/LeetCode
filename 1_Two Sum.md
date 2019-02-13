```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        std::unordered_map<int,int> ht;
        

        
        for(int i=0;i<nums.size();i++)
        {
            int t=target-nums[i];
            if(ht.count(t))
            {
                return std::vector<int>{ht[t],i};
            }
            ht.insert({nums[i],i});
        }
        return {};
        
    }
};
```
```python3
class Solution:
    def twoSum(self, nums: 'List[int]', target: 'int') -> 'List[int]':
        d={}
        for idx,n in enumerate(nums):
            t = target - n
            if t in d:
                return [d[t],idx]
            d[n]=idx
```
