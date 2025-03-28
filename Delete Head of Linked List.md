## Delete Head of Linked List (c++)

Given a linked list of n nodes and a key, the task is to check if the key is present in the linked list or not.

## Example
Input: LinkedList: 2->5->7->8->99->100

Output: 5 7 8 99 100

## PROGRAM:(Main.cpp)
```
class Solution {
Node * deleteHead(Node *head)
{
    if(head==NULL) return head;
    
    Node* temp=head;
    head=head->next;
    delete temp;
    return head;
}
```
## Complexity
- Time complexity : O(1)

- Space complexity : O(1)
