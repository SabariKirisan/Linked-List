## Length of Loop in Linked List (c++)

Given the head of a linked list, determine whether the list contains a loop. If a loop is present, return the number of nodes in the loop, otherwise return 0.
## Example
Input: LinkedList: 25->14->19->33->10->21->39->90->58->45, c = 4

Output: 7

Explanation: The loop is from 33 to 45. So length of loop is 33->10->21->39-> 90->58->45 = 7. 

The number 33 is connected to the last node of the linkedlist to form the loop because according to the input the 4th node from the beginning(1 based indexing) 
will be connected to the last node for the loop.

![image](https://github.com/user-attachments/assets/7eb311b5-e620-45e5-b396-b69913c3a3ff)


## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int countNodesinLoop(Node *head) 
    {
        Node* slow=head;
        Node* fast=head;
        int cnt=0;
        while(fast!=NULL && fast->next!= NULL)
        {
            slow=slow->next;
            fast=fast->next->next;
            if(slow==fast)
            {
                slow=slow->next;
                cnt=1;
                while(slow!=fast)
                {
                    cnt++;
                    slow=slow->next;
                }
                return cnt;
            }
        }
        return 0;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
