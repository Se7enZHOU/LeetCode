```c++
class Solution {
public:
    bool isValid(string s) {
        std::stack<char> st;
        
        for (char c:s)
        {
            switch(c)
            {
                case '(':
                case '{':
                case '[':st.push(c);break;
                case ')':if(st.empty() || st.top()!='(') return false;else st.pop();break;
                case '}':if(st.empty() || st.top()!='{') return false;else st.pop();break;
                case ']':if(st.empty() || st.top()!='[') return false;else st.pop();break;
                default:;
                    
                    
                    
            }
        }
        return st.empty();
        
    }
};
```


```python3
class Solution:
    def isValid(self, s: 'str') -> 'bool':
        st=[]
        ht={')':'(','}':'{',']':'['}
        
        for c in s:
            if c in ht:
                if not(st and st.pop()==ht[c]):
                    return False
            else:
                st.append(c)
        return not st
```
