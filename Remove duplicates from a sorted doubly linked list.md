## Remove duplicates from a sorted doubly linked list (c++)

Given a doubly linked list of n nodes sorted by values, the task is to remove duplicate nodes present in the linked list.

## Example
n = 6

Input: 1<->1<->1<->2<->3<->4

Output: 1<->2<->3<->4

Explanation:Only the first occurance of node with value 1 is retained, rest nodes with value = 1 are deleted.

## PROGRAM:(Main.cpp)
```
class Solution
{
public:

    Node * removeDuplicates(struct Node *head)
    {
        Node *temp=head;
        while(temp!=NULL && temp->next!=NULL)
        {
            Node *nextnode=temp->next;
            while(nextnode!=NULL && nextnode->data==temp->data)
            {
                Node *duplicate=nextnode;
                nextnode=nextnode->next;
                delete duplicate;
            }
            temp->next=nextnode;
            if(nextnode!=NULL) nextnode->prev=temp;
            
            temp=temp->next;
        }
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
