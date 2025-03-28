## Remove k'th node (c++)

Given a singly linked list, your task is to remove kth node from the linked list. 

## Example
Input: Linked list: 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8, k = 2

Output: 1 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8

Explanation: After removing 2nd node of the linked list, the resultant linked list will be: 1 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8
## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* deleteK(Node* head, int k) 
    {
        if(head==NULL) return NULL;

        if(k==1)
        {
            Node* temp=head;
            head=head->next;
            delete temp;
            return head;
        }
        int cnt=0;
        Node*temp=head;
        Node*prev=NULL;
        while(temp!=NULL)
        {
            cnt++;
            if(cnt==k)
            {
                prev->next=prev->next->next;
                delete temp;
                break;
            }
            prev=temp;
            temp=temp->next;
        }
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
