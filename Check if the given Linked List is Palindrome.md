## Check if the given Linked List is Palindrome (c++)

Given the head of a singly linked list, return true if it is a palindrome or false otherwise.
## Example
![image](https://github.com/user-attachments/assets/5a09a529-6210-41f5-825c-e3c376996037)

Input: head = [1,2,2,1]

Output: true

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* reverse(ListNode* head)
    {
        if(head==NULL || head->next==NULL)
        {
            return head;
        }
        ListNode* temp=head;
        ListNode* prev=NULL;
        while(temp!=NULL)
        {
            ListNode* front=temp->next;
            temp->next=prev;
            prev=temp;
            temp=front;
        }
        return prev;
    }
    bool isPalindrome(ListNode* head) 
    {
        if(head==NULL || head->next==NULL)
        {
            return true;
        }
        ListNode* slow=head;
        ListNode* fast=head;
        while(fast->next!=NULL && fast->next->next!=NULL)
        {
            slow=slow->next;
            fast=fast->next->next;
        }
        ListNode* newhead=reverse(slow->next);
        ListNode* first=head;
        ListNode* second=newhead;
        while(second!=NULL)
        {
            if(first->val != second->val)
            {
                reverse(newhead);
                return false;
            }
            first=first->next;
            second=second->next;
        }
        reverse(newhead);
        return true;
    }
};
```
## Complexity
- Time complexity : O (2*N) The algorithm traverses the linked list twice, dividing it into halves. During the first traversal, it reverses one-half of the list, and during the second traversal, it compares the elements of both halves. As each traversal covers N/2 elements, the time complexity is calculated as O(N/2 + N/2 + N/2 + N/2), which simplifies to O(2N), ultimately representing O(N). 

- Space complexity : O(1)
