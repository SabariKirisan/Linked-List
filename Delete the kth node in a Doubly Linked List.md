## Delete the kth node in a Doubly Linked List (c++)

Given a Doubly Linked list and a position. The task is to delete a node from a given position (position starts from 1) in a doubly linked list and return the head of the doubly Linked list.
## Example
Input: LinkedList = 1 <--> 3 <--> 4, x = 3

Output: 1 <--> 3

Explanation: After deleting the node at position 3 (position starts from 1),the linked list will be now as 1 <--> 3.

![image](https://github.com/user-attachments/assets/1134a108-d979-41be-9aef-3010630bd2ba)


## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    // Function to delete a node at given position.
    Node* deleteNode(Node* head, int x)
    {
        if(head==NULL)
        {
            return NULL;
        }
        int cnt=0;
        Node* temp=head;
        while(temp!=NULL)
        {
            cnt++;
            if(cnt==x)
            {
                break;
            }
            temp=temp->next;
        }
        Node* front=temp->next;
        Node* back=temp->prev;
        
        if(front==NULL && back==NULL)
        {
            delete temp;
            return NULL;
        }
        else if(front==NULL)
        {
            Node*newtail=temp->prev;
            newtail->next=nullptr;
            temp->prev=nullptr;
            delete temp;
            return head;
        }
        else if(back==NULL)
        {
            Node* newhead=head->next;
            head->next=nullptr;
            newhead->prev=nullptr;
            delete head;
            return newhead;
        }
        back->next=front;
        front->prev=back;
        temp->next=nullptr;
        temp->prev=nullptr;
        delete temp;
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
