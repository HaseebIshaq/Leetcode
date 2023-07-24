# Remove Duplicates from Sorted Linked List

## Problem Description

Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.

### Example:

Input:
```py
1 -> 1 -> 2 -> 3 -> 3
```

Output:
```py
1 -> 2 -> 3
```

## Python Solution

```py
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution(object):
    def deleteDuplicates(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        temp = head
        while temp and temp.next:
            if temp.val == temp.next.val:
                temp.next = temp.next.next
            else:
                temp = temp.next
        return head
```

The given Python solution provides a class `Solution` with a method `deleteDuplicates` that takes the head of a sorted linked list as input. The method deletes all duplicates such that each element appears only once and returns the linked list sorted as well.

### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*.
- The method uses a temporary node `temp` initialized to the head of the linked list.
- It iterates through the linked list while `temp` and `temp.next` are not None.
- If the current node's value `temp.val` is equal to the value of the next node `temp.next.val`, it means there is a duplicate node. In this case, it modifies the pointers to skip the next node, effectively removing the duplicate node from the list.
- If the values of consecutive nodes are different, it means that there are no duplicates, and it advances the `temp` pointer to the next node.
- Finally, the method returns the head of the modified linked list after removing all duplicates.

## Results
This solution efficiently removes duplicates from the sorted linked list in-place and returns the head of the sorted linked list with all duplicates removed.This code beats **82.14%** of the runtime.