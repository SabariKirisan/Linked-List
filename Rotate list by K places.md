## Rotate list by K places (c++)

Given the head of a linked list, rotate the list to the right by k places.

## Example
![image](https://github.com/user-attachments/assets/b644ab9e-5613-4404-beae-8394ec7d26b0)

Input: head = [1,2,3,4,5], k = 2

Output: [4,5,1,2,3]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* findkthnode(ListNode* temp, int k)
    {
        int cnt=1;
        while(temp!=NULL)
        {
            if(cnt==k) return temp;
            cnt++;
            temp=temp->next;
        }
        return temp;
    }
    ListNode* rotateRight(ListNode* head, int k) 
    {
        if(head==NULL || k==0) return head;
        
        ListNode* tail=head;
        int len=1;
        while(tail->next != NULL)
        {
            len++;
            tail=tail->next;
        }
        if(k%len==0) return head;
        k=k%len;

        tail->next=head;

        ListNode* kthnode=findkthnode(head,len-k);

        head=kthnode->next;

        kthnode->next=NULL;

        return head;
    }
};
```
## Complexity
- Time complexity : O(2N)

- Space complexity : O(1)
