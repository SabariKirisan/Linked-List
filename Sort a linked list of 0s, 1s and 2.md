## Sort a linked list of 0s, 1s and 2 (c++)

Given a linked list where nodes can contain values 0s, 1s, and 2s only. The task is to segregate 0s, 1s, and 2s linked list such that all zeros segregate to the head side, 2s at the end of the linked list, and 1s in the middle of 0s and 2s.

## Example
Input: LinkedList: 1->2->2->1->2->0->2->2

Output: 0->1->1->2->2->2->2->2

Explanation: All the 0s are segregated to the left end of the linked list, 2s to the right end of the list, and 1s in between.

![image](https://github.com/user-attachments/assets/d818a068-a47c-4107-877d-0af18662d770)


## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* segregate(Node* head) 
    {
        Node* dumzero=new Node(-1);
        Node* dumone=new Node(-1);
        Node* dumtwo=new Node(-1);
        
        Node* zero=dumzero;
        Node* one=dumone;
        Node* two=dumtwo;
        Node* temp=head;
        
        while(temp!=NULL)
        {
            if(temp->data==0)
            {
                zero->next=temp;
                zero=temp;
            }
            else if(temp->data==1)
            {
                one->next=temp;
                one=temp;
            }
            else
            {
                two->next=temp;
                two=temp;
            }
            temp=temp->next;
        }
        zero->next=(dumone->next) ? (dumone->next):(dumtwo->next);
        one->next=dumtwo->next;
        two->next=NULL;
        
        Node* newhead=dumzero->next;
        
        delete dumzero;
        delete dumone;
        delete dumtwo;
        return newhead;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
