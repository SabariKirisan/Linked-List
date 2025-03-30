## Intersection of Two LL (c++)

Given the heads of two singly linked-lists headA and headB, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return null.

## Example
For example, the following two linked lists begin to intersect at node c1:

![image](https://github.com/user-attachments/assets/436c967c-4cd1-4f0f-bc1e-0987fcec7f6e)

The test cases are generated such that there are no cycles anywhere in the entire linked structure.

Note that the linked lists must retain their original structure after the function returns.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) 
    {
        if (!headA || !headB) return NULL;

        ListNode* t1=headA;
        ListNode* t2=headB;

        while(t1!=t2)
        {
            t1=t1->next;
            t2=t2->next;
            if(t1==t2) return t1;
            if(t1==NULL) t1=headB;
            if(t2==NULL) t2=headA;
        }
        return t1;
    }
};
```
## Complexity
- Time complexity : O(N1 + N2)

- Space complexity : O(1)
