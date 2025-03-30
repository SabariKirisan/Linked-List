## Sort a Linked List(Merge sort) (c++)

Given the head of a linked list, return the list after sorting it in ascending order.

## Example
![image](https://github.com/user-attachments/assets/cf53cff4-8de4-4261-9f3f-afe7585a6d69)

Input: head = [4,2,1,3]

Output: [1,2,3,4]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* findmid(ListNode* head)
    {
        if(head==NULL|| head->next==NULL)
        {
            return head;
        }
        ListNode* slow=head;
        ListNode* fast=head->next;
        while(fast!=NULL && fast->next!=NULL)
        {
            slow=slow->next;
            fast=fast->next->next;
        }
        return slow;
    }
    ListNode* mergetwosortedLL(ListNode* left,ListNode* right)
    {
        ListNode* l1=left;
        ListNode* l2=right;
        ListNode* dummy=new ListNode(-1);
        ListNode* temp=dummy;

        while(l1 != NULL && l2 !=NULL)
        {
            if(l1->val < l2->val)
            {
                temp->next=l1;
                l1=l1->next;
                temp=temp->next;
            }
            else
            {
                temp->next=l2;
                l2=l2->next;
                temp=temp->next;
            }
        }
        if(l1) temp->next=l1;
        else temp->next=l2;
        return dummy->next;
    }
    ListNode* sortList(ListNode* head) 
    {
        if(head == NULL || head->next==NULL)
        {
            return head;
        }
        ListNode* middle=findmid(head);
        ListNode* lefthead=head;
        ListNode* righthead=middle->next;
        middle->next=nullptr;

        lefthead=sortList(lefthead);
        righthead=sortList(righthead);
        
        return mergetwosortedLL(lefthead,righthead);
    }
};
```
## Complexity
- Time complexity : O(N log N)

- Space complexity : O(log N)
