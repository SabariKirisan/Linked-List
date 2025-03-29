## Reverse a Singly Linked List(Recusive) (c++)

Given the head of a singly linked list, reverse the list, and return the reversed list.

## Example
![image](https://github.com/user-attachments/assets/382a9664-dcff-46b7-b986-bbc33deb9765)

Input: head = [1,2,3,4,5]

Output: [5,4,3,2,1]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* reverseList(ListNode* head) 
    {
        if(head==NULL || head->next==NULL)
        {
            return head;
        }
        ListNode* newhead=reverseList(head->next);
        ListNode* front=head->next;
        front->next=head;
        head->next=NULL;
        return newhead;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
