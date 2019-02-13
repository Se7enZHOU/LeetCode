```c++
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
    int carry=0;
        ListNode *dummyNode =new ListNode(0);
        ListNode *p=dummyNode;
        
        while (l1 || l2 )
        {
            int v1=l1 ? l1->val:0;
            int v2=l2 ? l2->val:0;
            int sum=v1+v2+carry;
            carry=sum/10;
            
            ListNode *node = new ListNode(sum%10);
            
            dummyNode->next = node;
            dummyNode = dummyNode->next;
            
            if(l1)
                l1=l1->next;
            if(l2)
                l2=l2->next;
        }
        if(carry)
        {
            dummyNode->next=new ListNode(1);
        }
        
        return p->next;
        
    }
};
```

```python3
class Solution:
    def addTwoNumbers(self, l1: 'ListNode', l2: 'ListNode') -> 'ListNode':
        dummyNode=ListNode(0)
        p=dummyNode
        carry=0
        while l1 or l2:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
            total=v1+v2+carry
            carry=total//10
            node=ListNode(total%10)
            
            dummyNode.next=node
            dummyNode=dummyNode.next
            
            if l1:
                l1 = l1.next 
            if l2:
                l2 = l2.next
        
        if carry:
            dummyNode.next = ListNode(1)
        
        return p.next
```


