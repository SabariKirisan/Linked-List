## Merge two sorted LL (c++)

You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.
## Example
![image](https://github.com/user-attachments/assets/deeba424-f6fa-42d9-8133-5d9aa3c985d2)

Input: list1 = [1,2,4], list2 = [1,3,4]

Output: [1,1,2,3,4,4]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) 
    {
        ListNode* t1=list1;
        ListNode* t2=list2;
        ListNode* dumynode=new ListNode(-1);
        ListNode* temp=dumynode;
        while(t1!=NULL && t2!=NULL)
        {
            if(t1->val < t2->val)
            {
                temp->next=t1;
                temp=t1;
                t1=t1->next;
            }
            else
            {
                temp->next=t2;
                temp=t2;
                t2=t2->next;
            }
        }
        if(t1) temp->next=t1;
        else temp->next=t2;
        return dumynode->next;
    }
};
```
## Complexity
- Time complexity : O(N1 + N2). 

- Space complexity : O(1)
