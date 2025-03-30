## Add 1 to a Linked List Number (c++)

You are given a linked list where each element in the list is a node and have an integer data. You need to add 1 to the number formed by concatinating all the list node numbers together and return the head of the modified linked list. 

Note: The head represents the first element of the given array.

## Example
Input: LinkedList: 4->5->6

Output: 457

![image](https://github.com/user-attachments/assets/43f0b14b-e0b8-464f-bbb9-4d0438641b98)

Explanation: 4->5->6 represents 456 and when 1 is added it becomes 457. 

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int helper(Node* temp)
    {
        if(temp==NULL) return 1;
        int carry=helper(temp->next);
        temp->data+=carry;
        if(temp->data <10) return 0;
        temp->data=0;
        return 1;
    }
    
    Node* addOne(Node* head) 
    {
        int carry=helper(head);
        if(carry==1)
        {
            Node* newhead= new Node(1);
            newhead->next= head;
            head=newhead;
        }
        return head;
        
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(N)
