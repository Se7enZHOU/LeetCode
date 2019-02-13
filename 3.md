```c++
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        
        std::vector<int> m(256,-1);
        int left=-1;
        int maxLen=0;
        
        for(int right=0;right<s.length();right++)
        {
            if(m[s[right]]>left)
               left=m[s[right]]; 
            m[s[right]]=right;
            maxLen=max(maxLen,right-left);
        }
        return maxLen;

        
    }
};
```
```python3
class Solution:
    def lengthOfLongestSubstring(self, s: 'str') -> 'int':
        d={}
        maxLen=0
        left=-1
        for right in range(len(s)):
            if s[right] in d and d[s[right]]>left:
                left=d[s[right]]
            d[s[right]]=right 
            maxLen=max(maxLen,right-left)
        return maxLen
```
