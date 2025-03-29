## Linked List Insertion At End (c++)

Given an integer array arr of size n. Construct the doubly linked list from arr and return the head of it.
## Example
Input: n = 5

arr = [1,2,3,4,5]

Output:1 2 3 4 5

Explanation: Linked list for the given array will be 1<->2<->3<->4<->5.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* constructDLL(vector<int>& arr) 
    {
        int n=arr.size();
        Node* head=new Node(arr[0]);
        Node* prev=head;
        
        for(int i=1;i<n;i++)
        {
            Node* temp=new Node(arr[i]);
            temp->next=nullptr;
            temp->prev=prev;
            
            prev->next=temp;
            prev=temp;
        }
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
