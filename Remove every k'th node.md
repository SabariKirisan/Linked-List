## Remove every k'th node (c++)

Given a singly linked list, your task is to remove every kth node from the linked list. 

## Example
Input: Linked list: 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8, k = 2

Output: 1 -> 3 -> 5 -> 7

![image](https://github.com/user-attachments/assets/eb556c52-d04f-4f76-84bb-06f72b12bb4a)


Explanation: After removing every 2nd node of the linked list, the resultant linked list will be: 1 -> 3 -> 5 -> 7.
## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* deleteK(Node* head, int k) 
    {
        if(head==NULL) return NULL;

        if(k==1)
        {
            Node* temp=head;
            head=head->next;
            delete temp;
            return head;
        }
        int cnt=0;
        Node*temp=head;
        Node*prev=NULL;
        int n=k;
        while(temp!=NULL)
        {
            cnt++;
            if(cnt==n)
            {
                prev->next=prev->next->next;
                delete temp;
                n=n+k;
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
