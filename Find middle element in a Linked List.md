## Find middle element in a Linked List (c++)

Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.
## Example
![image](https://github.com/user-attachments/assets/4e0f1891-8776-4cbb-940a-4c335eee060c)


Input: head = [1,2,3,4,5]

Output: [3,4,5

Explanation: The middle node of the list is node 3.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* middleNode(ListNode* head) 
    {
        ListNode* slow=head;
        ListNode* fast=head;
        while(fast!= NULL && fast->next!=NULL)
        {
            slow=slow->next;
            fast=fast->next->next;
        }
        return slow;
    }
};
```
## Complexity
- Time complexity : O(N/2)

- Space complexity : O(1)
