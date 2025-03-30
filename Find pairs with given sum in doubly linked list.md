## Find pairs with given sum in doubly linked list (c++)

Given a sorted doubly linked list of positive distinct elements, the task is to find pairs in a doubly-linked list whose sum is equal to given value target.

## Example
Input:  1 <-> 2 <-> 4 <-> 5 <-> 6 <-> 8 <-> 9

target = 7

Output: (1, 6), (2,5)

Explanation: We can see that there are two pairs (1, 6) and (2,5) with sum 7.

## PROGRAM:(Main.cpp)
```
class Solution
{
public:
    Node *findtail(Node *tail)
    {
        while(tail->next !=NULL) tail=tail->next;
        return tail;
    }
    vector<pair<int, int>> findPairsWithGivenSum(Node *head, int target)
    {
     vector<pair<int, int>> ans;
     Node *left=head;
     Node *right=findtail(head);
     
     while(left->data < right->data)
     {
         if(left->data + right->data == target)
         {
            ans.push_back({left->data,right->data});
            left=left->next;
            right=right->prev;
         }
         else if(left->data + right->data < target)
         {
             left=left->next;
         }
         else right=right->prev;
     }
     return ans;
    }
};
```
## Complexity
- Time complexity : O(2N)

- Space complexity : O(1)
