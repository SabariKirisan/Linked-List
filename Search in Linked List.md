## Search in Linked List (c++)

Given a linked list of n nodes and a key, the task is to check if the key is present in the linked list or not.

## Example
Input: LinkedList : 1->2->3->4->5

Input: n = 4, key = 3

1->2->3->4

Output: true

Explanation: 3 is present in Linked List, so the function returns true.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    bool searchKey(int n, Node* head, int key) 
    {
        Node* temp=head;
        while(temp!=NULL)
        {
            if(temp->data==key)
            {
                return true;
            }
            temp=temp->next;
        }
        return false;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
