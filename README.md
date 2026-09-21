# Leetcode_Day51
Day 51 – Remove Duplicates from Sorted List

## 🧩 Problem
Given the head of a **sorted linked list**, remove all duplicate values so that each element appears only once.

Return the linked list after removing the duplicates.

### Example
Input:
1 → 1 → 2

Output:
1 → 2

---

## 💡 Approach

Since the linked list is already sorted, duplicate values will always be next to each other.

I used a pointer `th` to traverse the list:

1. Start from the head.
2. Compare the current node's value with the next node's value.
3. If both values are equal:
   - Skip the duplicate node using:
     `th.next = th.next.next`
4. If the values are different:
   - Move to the next node.
5. Continue until the end of the list.

Because the list is sorted, there is no need for extra data structures like a HashSet.

---

## 💻 Java Solution

```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode th = head;

        while (th != null && th.next != null) {
            if (th.val == th.next.val) {
                th.next = th.next.next;
            } else {
                th = th.next;
            }
        }

        return head;
    }
}
⏱️ Complexity
Time Complexity: O(n)
Space Complexity: O(1)

We traverse the linked list only once and modify it in place without using extra space.

📚 What I Learned
How to traverse a singly linked list using pointers.
How to remove a node by changing the next reference.
How sorted data can make duplicate removal much easier.
How to solve a problem efficiently without using extra memory.
🎯 Key Takeaway

A sorted data structure often gives us useful information for free.

Here, because duplicates are always adjacent, a simple pointer comparison is enough to remove them efficiently.
