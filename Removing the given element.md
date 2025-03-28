## Removing the given element (c++)

Given a singly linked list, your task is to remove kth node from the linked list. 

## Example
Input: Linked list: 1 -> 2 -> 4 -> 3 -> 8 -> 6 -> 7 -> 5, ele = 8

Output: 1 -> 2 -> 4 -> 3 -> 6 -> 7 -> 5

Explanation: After removing given element in linked list, the resultant linked list will be: 1 -> 2 -> 4 -> 3 -> 6 -> 7 -> 5
## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* deleteK(Node* head, int ele) 
    {
        if(head==NULL) return NULL;

        if(head->data==ele)
        {
            Node* temp=head;
            head=head->next;
            delete temp;
            return head;
        }
        Node*temp=head;
        Node*prev=NULL;
        while(temp!=NULL)
        {
            if(temp->data==ele)
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
