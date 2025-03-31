## Reverse Linked List in groups of Size K (c++)

Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.

k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.

You may not alter the values in the list's nodes, only nodes themselves may be changed.

## Example
![image](https://github.com/user-attachments/assets/e0dbc408-0f2a-42e2-887f-9738f551432f)

Input: head = [1,2,3,4,5], k = 2

Output: [2,1,4,3,5]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* reverse(ListNode* head)
    {
        ListNode* temp=head;
        if(temp==NULL || temp->next==NULL)
        {
            return temp;
        }
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

    ListNode* getkthnode(ListNode* temp,int k)
    {
        k=k-1;
        while(temp!=NULL && k>0)
        {
            k--;
            temp=temp->next;
        }
        return temp;
    }
    
    ListNode* reverseKGroup(ListNode* head, int k) 
    {
        ListNode* temp=head;
        ListNode* prevlast=NULL;
        while(temp!=NULL)
        {
            ListNode* kthnode=getkthnode(temp,k);
            if(kthnode==NULL)
            {
                if(prevlast!=NULL) prevlast->next=temp;
                break;
            }
            ListNode* nextnode=kthnode->next;
            kthnode->next=NULL;

            reverse(temp);

            if(temp==head)
            {
                head=kthnode;
            }
            else
            {
                prevlast->next=kthnode;
            }
            prevlast=temp;
            temp=nextnode;
        }
        return head;
        
    }
};
```
## Complexity
- Time complexity : O(2N)

- Space complexity : O(1)
