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

---
# Bit Manipulation

| Operator | Name        | Rule                                   | Example                         |
| -------- | ----------- | -------------------------------------- | ------------------------------- |
| &        | AND         | 1 only if **both** are 1               | 1100 & 1010 = 1000              |
| \|       | OR          | 1 if **either** is 1                   | 1100 \| 1010 = 1110             |
| ^        | XOR         | 1 if they **differ**                   | 1100 ^ 1010 = 0110              |
| ~        | NOT         | flips every bit                        | ~1100 = 0011 (within its width) |
| <<       | left shift  | push left, fill 0 on the right         | 0011 << 2 = 1100                |
| >>       | right shift | push right; fill depends on signedness | 1100 >> 2 = 0011                |

### Common Tricks

| Goal                       | Code                    | Notes                                                                       |
| -------------------------- | ----------------------- | --------------------------------------------------------------------------- |
| Reverse Bits               |                         | swap first 16-bit halves, then 8-bit, 4-bit, 2-bit, and finally single bits |
| Remove the last bit 1      | n&(n-1)                 |                                                                             |
| found the missing          | 0^1^2^0^1 = 2           |                                                                             |
| add                        | a^b                     |                                                                             |
| carry                      | (a&b)<<1                |                                                                             |
|                            |                         |                                                                             |
| Swap without temp          | a ^= b; b ^= a; a ^= b; | fails if `a` and `b` are the same variable                                  |
| Check if bit `i` is set    | (x >> i) & 1            | returns 0 or 1                                                              |
| Set bit `i`                | x \|= (1<< i)           |                                                                             |
| Clear bit `i`              | x &= ~(1<< i)           |                                                                             |
| Toggle bit `i`             | x ^= (1<< i)            |                                                                             |
| **Clear lowest set bit**   | x & (x - 1)             | `n-1` flips the lowest 1 and everything right of it                         |
| **Isolate lowest set bit** | x & (-x)                | two's complement leaves only that bit matching                              |
| Check power of two         | x && !(x & (x - 1))     | a power of 2 has exactly one set bit                                        |
| Check odd / even           | x & 1                   | 1 = odd, 0 = even                                                           |




# Array

# Binary Search

## Hash Table

## Math
## Stack
## String

## Two Pointer
