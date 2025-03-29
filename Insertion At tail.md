## Linked List Insertion At End (c++)

Given the head of a Singly Linked List and a value x, insert that value x at the end of the LinkedList and return the modified Linked List.
## Example
Input: LinkedList: 1->2->3->4->5 , x = 6

Output: 1->2->3->4->5->6

Explanation: 

![image](https://github.com/user-attachments/assets/804fb78a-5d77-410c-a664-cc0b0d5f6a35)


We can see that 6 is inserted at the end of the linkedlist.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node *insertAtEnd(Node *head, int x) 
    {
        if(head==NULL)
        {
            Node* val=new Node(x);
            return val;
        }
        Node* temp=head;
        while(temp->next !=NULL)
        {
            temp=temp->next;
        }
        Node* val=new Node(x);
        temp->next=val;
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
