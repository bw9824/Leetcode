# Leetcode Quick Note — 各 Section 重點整理

> 用途：不用重看整篇解法，掃一眼就能想起這題的核心技巧。

## Array

| 題目 | 重點 |
|---|---|
| 1. Two Sum | 雙迴圈找兩數和 O(n²)；可用 hash table 優化成 O(n)（此版本未用） |
| 11. Container With Most Water | 雙指標從兩端夾向中間，永遠移動「較短」的一邊，因為面積被較短邊限制住 |
| 121. Best Time to Buy/Sell Stock | 一次交易：邊掃邊維護目前最小值 min_price，更新最大獲利 |
| 122. Best Time to Buy/Sell Stock II | 可多次交易：貪心，只要今天比昨天貴就把價差全部吃下來 |
| 169. Majority Element | Boyer-Moore 投票法：count 歸零就換 candidate，多數元素最終會留下 |
| 189. Rotate Array | 額外陣列 O(n) space；或原地環狀替換（The Big Wind Blows）達到 O(1) space |
| 1929. Concatenation of Array | 直接用 memcpy 複製記憶體區塊，效能最好 |
| 26. Remove Duplicates from Sorted Array | 快慢指標，遇到跟前一個不同的值才寫入 |
| 27. Remove Element | 用 cnt 記錄已跳過幾個 val，nums[i-cnt] = nums[i] 邊掃邊搬 |
| 42. Trapping Rain Water | 雙指標 + left_max/right_max，該側積水量只取決於較矮邊的最大值 |
| 605. Can Place Flowers | 貪心：檢查左右是否為空，可以種就種，最後比較 count 與 n |
| 66. Plus One | 從尾端往前找第一個不是 9 的位 +1，其餘歸零；若全部進位需多配一格 |
| 80. Remove Duplicates from Sorted Array II | 快慢指標，但比較 nums[slow-2]，允許每個元素最多出現兩次 |
| 88. Merge Sorted Array | 從陣列「尾端」開始比較填入，避免覆蓋還沒讀取的資料 |

## Binary Search

| 題目 | 重點 |
|---|---|
| 35. Search Insert Position | 標準二分搜尋；找不到時 begin 即為插入位置 |
| 69. Sqrt(x) | 二分搜尋在 [0, x] 找平方 ≤ x 的最大值，比逐一累加快 |
| 704. Binary Search | 標準二分搜尋模板；mid = min + (max-min)/2 避免溢位 |

## Bit Manipulation

| 題目 | 重點 |
|---|---|
| 136. Single Number | 全部 XOR，成對的數字互相抵消為 0，剩下落單的那個 |
| 137. Single Number II | 用 ones/twos 兩個變數模擬「三進位」計數每個 bit 出現次數 |
| 1720. Decode XORed Array | arr[i+1] = encoded[i] ^ arr[i]，逐步還原原陣列 |
| 190. Reverse Bits | 逐 bit 取出最低位塞進 result 高位，共 32 次 |
| 191. Number of 1 Bits | n & (n-1) 可消去最右邊的一個 1（Brian Kernighan's algorithm），比逐位檢查快 |
| 231. Power of Two | n & (n-1) == 0 代表只有一個 bit 是 1，即 2 的冪 |
| 2595. Number of Even and Odd Bits | 每次檢查最低兩位 (n&1, n&2)，再右移兩位跳一組 |
| 371. Sum of Two Integers | 不能用 +/-：XOR 做無進位加法，(a&b)<<1 表示進位，重複到沒有進位 |
| 67. Add Binary | 從字串尾端往前逐位相加，temp 記錄進位，最後位移指標跳過多配的空位 |

## Hash Table

| 題目 | 重點 |
|---|---|
| 13. Roman to Integer | 用 map[128] 陣列直接對應字元 ASCII 到數值，取代大量 if-else；後一位比前一位大就用減法 |
| 3. Longest Substring Without Repeating Characters | 滑動窗口 + 陣列記錄「每個字元上次出現位置+1」，重複時直接跳到該位置，不逐格移動 |

## Linked List

> 注意：101 其實是二元樹題目，被放在這個資料夾。

| 題目 | 重點 |
|---|---|
| 101. Symmetric Tree | 遞迴比較左右子樹是否互為鏡像：t1.left vs t2.right、t1.right vs t2.left |
| 2. Add Two Numbers | 用 dummyHead 解決「第一個節點沒有前導節點可接」的邊界問題，逐位相加處理進位 |
| 206. Reverse Linked List | pre/cur/next 三指標原地反轉；也有遞迴解法 |
| 21. Merge Two Sorted Lists | 用 dummy node 簡化合併邏輯，兩邊比大小，誰小就接誰 |
| 92. Reverse Linked List II | 先把 pre 移到 left 前一個節點，再用「頭插法」反覆把後面節點插到 pre 之後 |

## Math

| 題目 | 重點 |
|---|---|
| 172. Factorial Trailing Zeroes | 只需算 n! 中「5」的因數個數（2 一定比 5 多），累加 5, 25, 125… 的倍數 |
| 201. Bitwise AND of Numbers Range | 兩數不斷右移直到相等，取共同高位前綴，再左移補 0 |
| 258. Add Digits | 反覆加總數位；數學捷徑：1 + (num-1) % 9（九餘數定理） |
| 2600. K Items With the Maximum Sum | 貪心：先拿 1、再拿 0，最後不得已才拿 -1 |
| 292. Nim Game | n 是 4 的倍數時必輸，其餘必贏（雙方都會湊出 4 的倍數留給對方） |
| 3536. Maximum Product of Two Digits | 邊掃邊維護最大與次大的數字 |
| 50. Pow(x, n) | 快速冪：n 拆成二進位，cur_pow 每次平方、N 右移一位，位元是 1 才乘進 result |
| 509. Fibonacci Number | 兩個變數迭代滾動計算，避免遞迴的重複計算 |
| 7. Reverse Integer | 逐位重組時要先檢查是否會超過 INT_MAX/INT_MIN 再相乘，避免溢位 |
| 70. Climbing Stairs | 本質是費氏數列 DP：f(n) = f(n-1) + f(n-2) |
| 728. Self Dividing Numbers | 逐位檢查是否整除，含 0 或除不盡就跳過 |
| 9. Palindrome Number | 只反轉「一半」數字並跟前半比較，避免整個反轉時的溢位問題 |

## String

| 題目 | 重點 |
|---|---|
| 1047. Remove All Adjacent Duplicates In String | 用陣列模擬 stack：相鄰相同就 pop，否則 push |
| 125. Valid Palindrome | 雙指標從兩端夾向中間，跳過非英數字元，比較前先轉小寫 |
| 14. Longest Common Prefix | 以第一個字串為基準，逐字元跟其他字串比較，不同就截斷回傳 |
| 171. Excel Sheet Column Number | 26 進位轉換：ans = ans*26 + (char - 'A' + 1) |
| 28. Find the Index of the First Occurrence in a String | 樸素字串比對（可再優化為 KMP），比對失敗要回退指標 |
| 392. Is Subsequence | 雙指標，t 移動比對 s，count == len(s) 即為子序列 |
| 58. Length of Last Word | 從尾端往前數，先跳過空白，再數字母直到下一個空白 |
