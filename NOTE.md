# Linked List
```c
struct ListNode dummy;     // dummy is node
dummy.next = head;         //

struct ListNode* slow = &dummy;  // p is pointer
slow->next = head;               // p->next == (*p).next
```

|                 | `dummy`           | `fast` / `slow` |
| --------------- | ----------------- | --------------- |
| what            | A node            | An address      |
| memory          | Struct (16 bytes) | 8 bytes         |
| move address    | No                | Yes             |
| Use the element | `dummy.next`      | `fast->next`    |








# Array

# Binary Search

## Bit Manipulation

## Hash Table

## Math
## Stack
## String

## Two Pointer
