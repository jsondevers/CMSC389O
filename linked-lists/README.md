# Linked-Lists

A way that I like to think about a linked-list versus a normal array is how its stored in memory. Where an array in memory is stored in a contiguous block of memory, a linked-list is stored in a non-contiguous block of memory. Meaning that each node in the linked-list can point to a node in memory at an addresses that is not next to the previous node. These data structures are "linked" by each other and what makes their overall structure, without the link, they would just be a bunch of nodes in memory that are not connected to each other.

## Terminology

- **Node**: A single element of a linked-list. Contains a value and a pointer to the next node.
- **Head**: The first node in a linked-list.
- **Tail**: The last node in a linked-list.
- **Pointer**: A reference to another node in memory.
- **Singly Linked-List**: A linked-list where each node has a pointer to the next node.
- **Doubly Linked-List**: A linked-list where each node has a pointer to the next node and the previous node.
- **Circular Linked-List**: A linked-list where the tail node points to the head node.
- **Sentinel Node/Dummy Node**: A node that is used to mark the beginning or end of a linked-list. Typically, a sentinel node is used to mark the end of a linked-list.

## Important things to keep in mind

1. Linked-Lists are not indexed, meaning that you cannot access a node in a linked-list by its index. You must traverse the linked-list to find the node you are looking for.
2. Linked-Lists have the benefit of using $$O(1)$$ memory typically, so using recursion may create a new stack frame for each recursive call, which may make your solution $$O(n)$$ space complexity.
3. It's all about manipulating the pointers. Get comfortable with drawing out the linked-list and manipulating the pointers in a way that you want to reach your solution.

## Algorithms related to Linked-Lists

1. Merge two sorted linked-lists
    - Using merge sort with pointers (avoid recursion)
    - This problem translate nicely to sort $$k$$ sorted linked-lists
2. Reverse a linked-list
    - One of the most important algorithms to understand pointer manipulation
3. Detect a cycle in a linked-list
    - Floyd's Cycle Detection Algorithm
4. Find the middle of a linked-list
    - Floyd's Cycle Detection Algorithm
5. Remove the Nth node from the end of a linked-list
    - Floyd's Cycle Detection Algorithm
6. Add two numbers represented by linked-lists (Add two numbers II)
    - Reverse the linked-lists and add the numbers
    - Use recursion to add the numbers
