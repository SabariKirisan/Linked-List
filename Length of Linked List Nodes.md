## Count Linked List Nodes (c++)

Given a singly linked list. The task is to find the length of the linked list, where length is defined as the number of nodes in the linked list.
## Example
Input: LinkedList : 1->2->3->4->5

![image](https://github.com/user-attachments/assets/ac176e93-b4f1-4b49-882d-2b8783ba33f3)

Output: 5

Explanation: Count of nodes in the linked list is 5, which is its length.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int getCount(struct Node* head) 
    {
        int cnt=0;
        Node*temp=head;
        while(temp!=NULL)
        {
            temp=temp->next;
            cnt++;
        }
        return cnt;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
