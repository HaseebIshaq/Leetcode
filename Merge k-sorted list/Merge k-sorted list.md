# Merge k Sorted Lists
## Problem Description
You are given an array of k linked-lists lists, each linked-list is sorted in ascending order. Merge all the linked-lists into one sorted linked-list and return it.

## Python Solution
```py
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution(object):
    def mergeKLists(self, lists):
        """
        :type lists: List[ListNode]
        :rtype: ListNode
        """
        li = []  

        for i in lists:
            node = i
            while node:
                li.append(node.val)
                node = node.next

        li.sort() 

        dm = ListNode(0)  
        tem = dm

        for val in li:
            n_node = ListNode(val)
            tem.next = n_node
            tem = tem.next

        return dm.next
```
The given Python solution provides a class Solution with a method mergeKLists that takes in a list of linked lists lists. The method merges all the linked-lists into one sorted linked-list and returns it.

### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*.
- The method first initializes an empty list li.
- It iterates through each linked list in lists, extracting the values of each node and adding them to the li list.
- The li list is then sorted in ascending order using li.sort().
- A dummy node dm is created to simplify the merging process.
- A temporary node tem is initialized to the dummy node dm.
- For each value in the sorted li list, a new node n_node is created, and tem.next is set to n_node, effectively merging the nodes into a single sorted linked-list.
- Finally, the method returns the next node after the dummy node dm, which represents the head of the merged sorted linked-list.

## Results
This solution efficiently merges the sorted linked-lists into one sorted linked-list and returns the head of the merged list. This code beats **99.72%** of the runtime.