## Flattening a Linked List (c++)

Given a linked list containing n head nodes where every node in the linked list contains two pointers:

(i) next points to the next node in the list.

(ii) bottom pointer to a sub-linked list where the current node is the head.
Each of the sub-linked lists nodes and the head nodes are sorted in ascending order based on their data.
Your task is to flatten the linked list such that all the nodes appear in a single level while maintaining the sorted order.

Note:

1. ↓ represents the bottom pointer and -> represents the next pointer.
2. The flattened list will be printed using the bottom pointer instead of the next pointer.

## Example
![image](https://github.com/user-attachments/assets/14f3551b-7fa3-4b95-8598-3627384f7e0e)

Output: 5-> 7-> 8-> 10 -> 19-> 20-> 22-> 28-> 30-> 35-> 40-> 45-> 50.

Explanation: 

Bottom pointer of 5 is pointing to 7.

Bottom pointer of 7 is pointing to 8.

Bottom pointer of 8 is pointing to 10 and so on.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* merge(Node* head1,Node* head2)
    {
        Node* dummy= new Node(-1);
        Node* res=dummy;
        while(head1!=NULL && head2!=NULL)
        {
            if(head1->data < head2->data)
            {
                res->bottom=head1;
                res=head1;
                head1=head1->bottom;
            }
            else
            {
                res->bottom=head2;
                res=head2;
                head2=head2->bottom;
            }
            res->next=nullptr;
        }
        if(head1) res->bottom=head1;
        else res->bottom=head2;
        
        if(dummy->bottom) dummy->bottom->next=nullptr;
        return dummy->bottom;
    }
    Node *flatten(Node *root) 
    {
        if(root == NULL || root->next==NULL) return root;
        
        Node* newroot=flatten(root->next);
        
        root=merge(root,newroot);
        
        return root;
        
    }
};
```
## Complexity
- Time complexity : O( N*(2M) ) ~ O(2 N*M)where N is the length of the linked list along the next pointer and M is the length of the linked list along the child pointers.

- Space complexity : O(1)
