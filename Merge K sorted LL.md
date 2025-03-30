## Merge K sorted LL (c++)

You are given an array of k linked-lists lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

Return the head of the merged linked list.
## Example
Input: lists = [[1,4,5],[1,3,4],[2,6]]

Output: [1,1,2,3,4,4,5,6]

Explanation: The linked-lists are:

[

  1->4->5,
  
  1->3->4,
  
  2->6
  
]

merging them into one sorted list:

1->1->2->3->4->4->5->6

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    ListNode* mergeKLists(vector<ListNode*>& lists) 
    {
        priority_queue<pair<int,ListNode*>,vector<pair<int,ListNode*>>,greater<pair<int,ListNode*>>> pq;

        for(int i=0;i<lists.size();i++)
        {
            if(lists[i])
            {
                pq.push({lists[i]->val,lists[i]});
            }
        }
        ListNode* dumynode= new ListNode(-1);
        ListNode* temp=dumynode;
        while(!pq.empty())
        {
            auto it=pq.top();
            pq.pop();
            if(it.second->next)
            {
                pq.push({it.second->next->val,it.second->next});
            }
            temp->next=it.second;
            temp=temp->next;
        }
        return dumynode->next;
    }
};
```
## Complexity
- Time complexity : O(k log k) + O(N log k) = O(N log k)

- Space complexity : O(K)
