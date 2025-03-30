## Segregate even and odd nodes in LinkedList (c++)

Given the head of a singly linked list, group all the nodes with odd indices together followed by the nodes with even indices, and return the reordered list.

The first node is considered odd, and the second node is even, and so on.

Note that the relative order inside both the even and odd groups should remain as it was in the input.

You must solve the problem in O(1) extra space complexity and O(n) time complexity.
## Example
![image](https://github.com/user-attachments/assets/66111b81-b589-400c-9f71-668b46bee4a3)

Input: head = [1,2,3,4,5]

Output: [1,3,5,2,4]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) 
    {
        if(head == NULL || head->next==NULL)
        {
            return head;
        }
        ListNode* odd=head;
        ListNode* even=head->next;
        ListNode* evenhead=head->next;
        while(even!=NULL && even->next!=NULL)
        {
            odd->next=odd->next->next;
            even->next=even->next->next;

            odd=odd->next;
            even=even->next;
        }
        odd->next=evenhead;
        return head;
    }
};
```
## Complexity
- Time complexity : O(N/2 + N/2), which simplifies to O(N). 

- Space complexity : O(1)
