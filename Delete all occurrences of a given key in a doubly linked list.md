## Delete all occurrences of a given key in a doubly linked list (c++)

You are given the head_ref of a doubly Linked List and a Key. Your task is to delete all occurrences of the given key if it is present and return the new DLL.

## Example
Input: 2<->2<->10<->8<->4<->2<->5<->2

x=2

Output: 10<->8<->4<->5

Explanation: All Occurences of 2 have been deleted.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    void deleteAllOccurOfX(struct Node** head_ref, int x) 
    {
        Node* temp=*head_ref;
        while(temp != NULL)
        {
            if(temp->data==x)
            {
                if(temp==*head_ref)
                {
                    *head_ref=temp->next;
                }
                Node* temp_next=temp->next;
                Node* temp_prev=temp->prev;
                
                if(temp_next!=NULL) temp_next->prev=temp_prev;
                if(temp_prev!=NULL) temp_prev->next=temp_next;
                
                delete temp;
                temp=temp_next;
            }
            else
            {
                temp=temp->next;
            }
        }
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
