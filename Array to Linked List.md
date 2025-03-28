## Array to Linked List (c++)

Given an array of integer arr. Your task is to construct the linked list from arr & return the head of the linked list.
## Example
Input: arr = [1, 2, 3, 4, 5]

Output: LinkedList: 1->2->3->4->5

Explanation: Linked list for the given array will be

![image](https://github.com/user-attachments/assets/02858944-9a67-4f00-8898-116224cd2f46)

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    Node* constructLL(vector<int>& arr) 
    {
        int n=arr.size();
        Node* head= new Node(arr[0]);
        Node* mover=head;
        for(int i=1;i<n;i++)
        {
            Node* temp=new Node(arr[i]);
            mover->next=temp;
            mover=temp;
        }
        return head;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
