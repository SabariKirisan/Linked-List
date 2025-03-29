## Reverse the Doubly LL (c++)

Given a doubly linked list. Your task is to reverse the doubly linked list and return its head.
## Example
Input: LinkedList: 3 <-> 4 <-> 5

Output: 5 <-> 4 <-> 3

![image](https://github.com/user-attachments/assets/cfd4921c-16f4-4bef-8725-f92def58d5e8)


## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    DLLNode* reverseDLL(DLLNode* head) 
    {
        if(head==NULL || head->next==NULL)
        {
            return head;
        }
        DLLNode* back=NULL;
        DLLNode* current=head;
        while(current!=NULL)
        {
            back=current->prev;
            current->prev=current->next;
            current->next=back;
            current=current->prev;
        }
        return back->prev;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
