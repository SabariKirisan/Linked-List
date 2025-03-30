## Add Two Numbers (c++)

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

## Example
![image](https://github.com/user-attachments/assets/311b846e-5adf-4161-a5d7-a9f6712908d4)

Input: l1 = [2,4,3], l2 = [5,6,4]

Output: [7,0,8]

Explanation: 342 + 465 = 807.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) 
    {
        ListNode* dummy=new ListNode(-1);
        ListNode* cur=dummy;
        ListNode* temp1=l1;
        ListNode* temp2=l2;
        int carry=0;

        while(temp1 != NULL || temp2 != NULL)
        {
            int sum=carry;
            if(temp1) sum+=temp1->val;
            if(temp2) sum+=temp2->val;

            ListNode* newnode=new ListNode(sum%10);
            carry=sum/10;

            cur->next=newnode;
            cur=cur->next;

            if(temp1) temp1=temp1->next;
            if(temp2) temp2=temp2->next;
        }
        if(carry)
        {
            ListNode* newnode=new ListNode(carry);
            cur->next=newnode;
        }
        return dummy->next;
    }
};
```
## Complexity
- Time complexity : O(max(m,n))

- Space complexity : O(max(m,n))
