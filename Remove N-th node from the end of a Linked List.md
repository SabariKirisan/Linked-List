## Remove N-th node from the end of a Linked List (c++)

Given the head of a linked list, remove the nth node from the end of the list and return its head.
## Example
![image](https://github.com/user-attachments/assets/1310b266-d17e-4a2c-b288-af42955c87c4)

Input: head = [1,2,3,4,5], n = 2

Output: [1,2,3,5]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) 
    {
        ListNode* slow=head;
        ListNode* fast=head;
        for(int i=0;i<n;i++)
        {
            fast=fast->next;
        }
        if(fast==NULL) return head->next;

        while(fast->next!=NULL)
        {
            slow=slow->next;
            fast=fast->next;
        }
        ListNode* delnode=slow->next;
        slow->next=slow->next->next;
        delete delnode;
        return head;
    }
};
```
## Complexity
- Time complexity : O(N). 

- Space complexity : O(1)
