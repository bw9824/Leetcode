# LeetCode 刷題進度表（嚴格版）

> 重新起算 2026/08/15 · 目標：**2026/09/27 前完成 228 題**，趕在 UW 開學＋實習面試高峰前備妥
> 頻率標記：⭐⭐⭐ 極高頻 · ⭐⭐ 高頻 · ⭐ 常見
> 狀態標記：**✔** 已完成 · **☐** 尚未開始

---

> [!danger] 時程現實
> 2027 Summer Intern 的缺 **8–9 月開**、**10–11 月是面試高峰**、**多數 12 月前關閉**。
> 第一場 OA 可能 **9 月就來**。
>
> 開學後（9/30 起）你同時要上課、面試、投履歷，刷題強度必然掉一半。
> **開學前這段時間是唯一能高強度衝刺的窗口。**

---

> [!warning] 全部重新起算（2026/08/15 更新）
> 之前的紀錄全部作廢，228 題現在全部是 ☐，今天（08/15，週六）是新的第 1 天。
>
> 09/27 這個終點是外部硬期限（開缺／開學時間），不會往後延，但重新起算後只剩 **37 個工作日**（原本 7 週的設計是 42 個工作日），少了 5 天。所以每天題量從原本的 5–6 題拉高到 **平均 6–7 題**，7 個主題區塊的題數不變，只是區塊之間的日期不再剛好對齊星期一到星期日，下面每個區塊標題旁邊都寫了新的日期範圍和實際工作天數。

---

> [!note] 新時程總覽（依工作日反推，跳過每週日）
>
> | 區塊 | 新日期範圍 | 工作日 | 題數 | 平均每天 |
> |---|---|---|---|---|
> | W1 | 08/15（六）–08/21（五） | 6 | 33 | ~5.5 |
> | W2 | 08/22（六）–08/28（五） | 6 | 33 | ~5.5 |
> | W3 | 08/29（六）–09/03（四） | 5 | 33 | ~6.6 |
> | W4 | 09/04（五）–09/09（三） | 5 | 33 | ~6.6 |
> | W5 | 09/10（四）–09/15（二） | 5 | 32 | ~6.4 |
> | W6 | 09/16（三）–09/21（一） | 5 | 32 | ~6.4 |
> | W7 | 09/22（二）–09/26（六） | 5 | 32 | ~6.4 |
> | 09/27（日） | 檢核點 4：模擬面試，不排新題 | — | — | — |

---

## 每日規則（不可協商）

| 項目 | 標準 |
|---|---|
| **週一–週六** | **每天 6–7 題**（依新時程壓縮後的平均量，各區塊實際目標見上方新時程總覽），約 5–6 小時 |
| **週日** | 休息，或補進度（**不准把週日當常態進度**） |
| **單題上限** | Medium 卡 **35 分鐘**就看解答，看完當天再默寫一次 |
| **看解答後** | 隔 1 天不看筆記重寫，寫不出來 = 沒學會 |
| **以前寫過的題** | **一律當作沒寫過**，不准先翻自己的舊解答。寫完才比對，並確認當初是不是最優解 |
| **每題必做** | 更新 [[NOTE]] 一行心法 ＋ 標記 🟢🟡🔴 |

---

## 語言：本週決定，不要拖

| 場合 | 用哪個 |
|---|---|
| 韌體／嵌入式職缺 | **C**（差異化優勢，會被問指標與記憶體細節） |
| 一般 SWE 演算法輪 | **C++**（改用 STL） |

**W1 前兩天先練熟**：`unordered_map` · `vector` · `priority_queue` · `sort` · `stack`／`queue`。之後一律 C++。

### C 語言硬底子清單（依 [Dcard 求職心得](https://www.dcard.tw/f/tech_job/p/260108034) — 韌體面試 99.9% 用 C 考）

> 面試官會直接問「這行 code 印出什麼」「這樣寫有什麼問題」，不是選擇題，要能口頭講清楚。

| 主題 | 要能做到 | ✔ |
|---|---|---|
| 指標 | 指標運算、多重指標、function pointer、指標 vs 陣列差異 | ☐ |
| 記憶體 | struct 記憶體對齊（alignment/padding）、`sizeof` 各型別大小 | ☐ |
| 關鍵字 | `volatile` / `static` / `extern` 各自用途與面試常考陷阱 | ☐ |
| 字串函式手刻 | `strlen`、`strcpy`、`strcmp`、`memcpy` 自己手寫一版 | ☐ |
| 型別轉換 | `atoi`／`itoa` 手刻 | ☐ |
| Edge case | 每題預設要主動講 NULL 指標、空字串、溢位、負數情境 | ☐ |

---

## 總覽

| 階段 | 期間 | 題數 | 累計 | 目標 |
|---|---|---|---|---|
| **A 衝刺** | 08/15 – 09/27（37 個工作日） | **228** | **228** | 全主題覆蓋，含 NeetCode 150 |
| **B 實戰** | 09/28 – 12/20（秋季＋面試季） | 60 | 288 | 進階題、mock、公司題庫 |
| **C 深化** | 2027/01 – 03（冬季） | 50 | 338 | Hard、系統設計、二輪限時 |
| **D 維持** | 2027/04 – 10 | — | ~350 | 手感維持、New Grad 投遞 |

---

# Phase A：7 週衝刺

## W1 · 08/15（六）–08/21（五） · Arrays & Hashing ＋ Two Pointers（33 題，6 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 217 | Contains Duplicate | E | ⭐⭐ | ☐ |
| 242 | Valid Anagram | E | ⭐⭐ | ☐ |
| 383 | Ransom Note | E | ⭐ | ☐ |
| 205 | Isomorphic Strings | E | ⭐ | ☐ |
| 290 | Word Pattern | E | ⭐ | ☐ |
| 219 | Contains Duplicate II | E | ⭐ | ☐ |
| 268 | Missing Number | E | ⭐⭐ | ☐ |
| 202 | Happy Number | E | ⭐ | ☐ |
| 13 | Roman to Integer | E | ⭐⭐ | ☐ |
| 1 | Two Sum ← **必須 hash O(n)** | E | ⭐⭐⭐ | ☐ |
| 169 | Majority Element | E | ⭐⭐ | ☐ |
| 66 | Plus One | E | ⭐ | ☐ |
| 1929 | Concatenation of Array | E | ⭐ | ☐ |
| 49 | Group Anagrams | M | ⭐⭐⭐ | ☐ |
| 347 | Top K Frequent Elements | M | ⭐⭐⭐ | ☐ |
| 238 | Product of Array Except Self | M | ⭐⭐⭐ | ☐ |
| 36 | Valid Sudoku | M | ⭐ | ☐ |
| 271 | Encode and Decode Strings | M | ⭐⭐ | ☐ |
| 128 | Longest Consecutive Sequence | M | ⭐⭐⭐ | ☐ |
| 380 | Insert Delete GetRandom O(1) | M | ⭐⭐ | ☐ |
| 41 | First Missing Positive | H | ⭐⭐ | ☐ |
| 125 | Valid Palindrome | E | ⭐⭐ | ☐ |
| 392 | Is Subsequence | E | ⭐⭐ | ☐ |
| 26 | Remove Duplicates from Sorted Array | E | ⭐⭐ | ☐ |
| 27 | Remove Element | E | ⭐ | ☐ |
| 88 | Merge Sorted Array | E | ⭐⭐ | ☐ |
| 80 | Remove Duplicates from Sorted Array II | M | ⭐⭐ | ☐ |
| 189 | Rotate Array ← **要寫出 O(1) space 三次反轉** | M | ⭐⭐ | ☐ |
| 167 | Two Sum II | M | ⭐⭐ | ☐ |
| 15 | 3Sum | M | ⭐⭐⭐ | ☐ |
| 11 | Container With Most Water | M | ⭐⭐ | ☐ |
| 151 | Reverse Words in a String | M | ⭐⭐ | ☐ |
| 42 | Trapping Rain Water | H | ⭐⭐⭐ | ☐ |

**W1 現況：0 ✔ ・ 33 ☐**（目標 33）

## W2 · 08/22（六）–08/28（五） · Sliding Window ＋ Stack ＋ Binary Search（33 題，6 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 121 | Best Time to Buy and Sell Stock | E | ⭐⭐⭐ | ☐ |
| 122 | Best Time to Buy and Sell Stock II | M | ⭐⭐ | ☐ |
| 3 | Longest Substring Without Repeating | M | ⭐⭐⭐ | ☐ |
| 209 | Minimum Size Subarray Sum | M | ⭐⭐ | ☐ |
| 424 | Longest Repeating Character Replacement | M | ⭐⭐ | ☐ |
| 567 | Permutation in String | M | ⭐⭐ | ☐ |
| 1004 | Max Consecutive Ones III | M | ⭐⭐ | ☐ |
| 76 | Minimum Window Substring | H | ⭐⭐⭐ | ☐ |
| 239 | Sliding Window Maximum | H | ⭐⭐ | ☐ |
| 20 | Valid Parentheses | E | ⭐⭐⭐ | ☐ |
| 232 | Implement Queue using Stacks | E | ⭐⭐ | ☐ |
| 1047 | Remove All Adjacent Duplicates In String | E | ⭐ | ☐ |
| 155 | Min Stack | M | ⭐⭐⭐ | ☐ |
| 150 | Evaluate Reverse Polish Notation | M | ⭐⭐ | ☐ |
| 22 | Generate Parentheses | M | ⭐⭐ | ☐ |
| 71 | Simplify Path | M | ⭐⭐ | ☐ |
| 394 | Decode String | M | ⭐⭐ | ☐ |
| 739 | Daily Temperatures（單調堆疊） | M | ⭐⭐ | ☐ |
| 853 | Car Fleet | M | ⭐ | ☐ |
| 84 | Largest Rectangle in Histogram | H | ⭐⭐ | ☐ |
| 704 | Binary Search ← **模板要能默寫** | E | ⭐⭐ | ☐ |
| 35 | Search Insert Position | E | ⭐⭐ | ☐ |
| 278 | First Bad Version | E | ⭐⭐ | ☐ |
| 69 | Sqrt(x) | E | ⭐ | ☐ |
| 14 | Longest Common Prefix | E | ⭐ | ☐ |
| 74 | Search a 2D Matrix | M | ⭐⭐ | ☐ |
| 34 | Find First and Last Position in Sorted Array | M | ⭐⭐⭐ | ☐ |
| 162 | Find Peak Element | M | ⭐⭐ | ☐ |
| 875 | Koko Eating Bananas（二分答案空間） | M | ⭐⭐ | ☐ |
| 153 | Find Minimum in Rotated Sorted Array | M | ⭐⭐ | ☐ |
| 33 | Search in Rotated Sorted Array | M | ⭐⭐⭐ | ☐ |
| 981 | Time Based Key-Value Store | M | ⭐⭐ | ☐ |
| 4 | Median of Two Sorted Arrays | H | ⭐⭐ | ☐ |

**W2 現況：0 ✔ ・ 33 ☐**（目標 33）

> [!success] 🚩 檢核點 1（完成 W2 後）
> - Easy 題 **≤ 10 分鐘**寫完並通過
> - Medium 題 **≤ 30 分鐘**
> - 二分搜尋模板**不看筆記默寫**
> 沒達標 → W3 減量，先把 W1–W2 重寫一遍。

## W3 · 08/29（六）–09/03（四） · Linked List ＋ Trees I 🔴 最大缺口（33 題，5 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 206 | Reverse Linked List ← **遞迴版也要寫** | E | ⭐⭐⭐ | ☐ |
| 21 | Merge Two Sorted Lists | E | ⭐⭐ | ☐ |
| 141 | Linked List Cycle（快慢指標） | E | ⭐⭐ | ☐ |
| 160 | Intersection of Two Linked Lists | E | ⭐⭐ | ☐ |
| 234 | Palindrome Linked List | E | ⭐⭐ | ☐ |
| 2 | Add Two Numbers | M | ⭐⭐ | ☐ |
| 92 | Reverse Linked List II | M | ⭐⭐ | ☐ |
| 142 | Linked List Cycle II | M | ⭐⭐ | ☐ |
| 82 | Remove Duplicates from Sorted List II | M | ⭐⭐ | ☐ |
| 143 | Reorder List | M | ⭐⭐ | ☐ |
| 19 | Remove Nth Node From End of List | M | ⭐⭐ | ☐ |
| 138 | Copy List with Random Pointer | M | ⭐⭐ | ☐ |
| 287 | Find the Duplicate Number | M | ⭐⭐ | ☐ |
| 146 | **LRU Cache**（必須滾瓜爛熟） | M | ⭐⭐⭐ | ☐ |
| 23 | Merge k Sorted Lists | H | ⭐⭐⭐ | ☐ |
| 25 | Reverse Nodes in k-Group | H | ⭐⭐ | ☐ |
| 226 | Invert Binary Tree | E | ⭐⭐⭐ | ☐ |
| 104 | Maximum Depth of Binary Tree | E | ⭐⭐⭐ | ☐ |
| 111 | Minimum Depth of Binary Tree | E | ⭐⭐ | ☐ |
| 112 | Path Sum | E | ⭐⭐ | ☐ |
| 101 | Symmetric Tree ← **加寫迭代版**；移到 `Tree/` | E | ⭐⭐ | ☐ |
| 543 | Diameter of Binary Tree | E | ⭐⭐ | ☐ |
| 110 | Balanced Binary Tree | E | ⭐⭐ | ☐ |
| 100 | Same Tree | E | ⭐⭐ | ☐ |
| 572 | Subtree of Another Tree | E | ⭐⭐ | ☐ |
| 235 | Lowest Common Ancestor of a BST | M | ⭐⭐ | ☐ |
| 236 | Lowest Common Ancestor of a Binary Tree | M | ⭐⭐⭐ | ☐ |
| 102 | Binary Tree Level Order Traversal（BFS 模板） | M | ⭐⭐⭐ | ☐ |
| 103 | Binary Tree Zigzag Level Order Traversal | M | ⭐⭐ | ☐ |
| 199 | Binary Tree Right Side View | M | ⭐⭐ | ☐ |
| 1448 | Count Good Nodes in Binary Tree | M | ⭐ | ☐ |
| 114 | Flatten Binary Tree to Linked List | M | ⭐⭐ | ☐ |
| 98 | Validate Binary Search Tree | M | ⭐⭐⭐ | ☐ |

**W3 現況：0 ✔ ・ 33 ☐**（目標 33）

## W4 · 09/04（五）–09/09（三） · Trees II ＋ Trie ＋ Heap ＋ Backtracking（33 題，5 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 108 | Convert Sorted Array to BST | E | ⭐⭐ | ☐ |
| 230 | Kth Smallest Element in a BST | M | ⭐⭐ | ☐ |
| 173 | Binary Search Tree Iterator | M | ⭐⭐ | ☐ |
| 105 | Construct Binary Tree from Preorder and Inorder | M | ⭐⭐⭐ | ☐ |
| 106 | Construct Binary Tree from Inorder and Postorder | M | ⭐⭐ | ☐ |
| 124 | Binary Tree Maximum Path Sum | H | ⭐⭐⭐ | ☐ |
| 297 | Serialize and Deserialize Binary Tree | H | ⭐⭐⭐ | ☐ |
| 208 | Implement Trie | M | ⭐⭐⭐ | ☐ |
| 211 | Design Add and Search Words | M | ⭐⭐ | ☐ |
| 212 | Word Search II | H | ⭐⭐ | ☐ |
| 703 | Kth Largest Element in a Stream | E | ⭐ | ☐ |
| 1046 | Last Stone Weight | E | ⭐ | ☐ |
| 973 | K Closest Points to Origin | M | ⭐⭐ | ☐ |
| 215 | Kth Largest Element in an Array（含 quickselect） | M | ⭐⭐⭐ | ☐ |
| 621 | Task Scheduler | M | ⭐⭐ | ☐ |
| 355 | Design Twitter | M | ⭐ | ☐ |
| 295 | Find Median from Data Stream | H | ⭐⭐⭐ | ☐ |
| 78 | Subsets | M | ⭐⭐⭐ | ☐ |
| 90 | Subsets II | M | ⭐⭐ | ☐ |
| 39 | Combination Sum | M | ⭐⭐⭐ | ☐ |
| 40 | Combination Sum II | M | ⭐⭐ | ☐ |
| 77 | Combinations | M | ⭐⭐ | ☐ |
| 46 | Permutations | M | ⭐⭐⭐ | ☐ |
| 47 | Permutations II | M | ⭐⭐ | ☐ |
| 79 | Word Search | M | ⭐⭐⭐ | ☐ |
| 131 | Palindrome Partitioning | M | ⭐⭐ | ☐ |
| 17 | Letter Combinations of a Phone Number | M | ⭐⭐ | ☐ |
| 51 | N-Queens | H | ⭐ | ☐ |
| 136 | Single Number | E | ⭐⭐ | ☐ |
| 191 | Number of 1 Bits | E | ⭐⭐ | ☐ |
| 190 | Reverse Bits | E | ⭐ | ☐ |
| 231 | Power of Two | E | ⭐ | ☐ |
| 67 | Add Binary | E | ⭐ | ☐ |

**W4 現況：0 ✔ ・ 33 ☐**（目標 33）

> [!success] 🚩 檢核點 2（完成 W4 後）
> 空白編輯器，**不看任何筆記**默寫：
> - 樹的前／中／後序 DFS（**遞迴＋迭代兩版**）
> - 樹的 BFS 層序模板
> - Backtracking 通用模板（選擇 → 遞迴 → 撤銷）
> 三個都寫得出來才能進 W5。

## W5 · 09/10（四）–09/15（二） · Graphs 🔴 第二大缺口（32 題，5 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 733 | Flood Fill | E | ⭐⭐ | ☐ |
| 200 | Number of Islands | M | ⭐⭐⭐ | ☐ |
| 695 | Max Area of Island | M | ⭐⭐ | ☐ |
| 547 | Number of Provinces | M | ⭐⭐ | ☐ |
| 133 | Clone Graph | M | ⭐⭐ | ☐ |
| 994 | Rotting Oranges（多源 BFS） | M | ⭐⭐⭐ | ☐ |
| 286 | Walls and Gates | M | ⭐ | ☐ |
| 1926 | Nearest Exit from Entrance in Maze | M | ⭐⭐ | ☐ |
| 417 | Pacific Atlantic Water Flow | M | ⭐⭐ | ☐ |
| 130 | Surrounded Regions | M | ⭐ | ☐ |
| 1091 | Shortest Path in Binary Matrix | M | ⭐⭐ | ☐ |
| 433 | Minimum Genetic Mutation | M | ⭐ | ☐ |
| 207 | Course Schedule（拓撲排序） | M | ⭐⭐⭐ | ☐ |
| 210 | Course Schedule II | M | ⭐⭐⭐ | ☐ |
| 802 | Find Eventual Safe States | M | ⭐ | ☐ |
| 684 | Redundant Connection（Union Find） | M | ⭐⭐ | ☐ |
| 323 | Number of Connected Components | M | ⭐⭐ | ☐ |
| 261 | Graph Valid Tree | M | ⭐⭐ | ☐ |
| 743 | Network Delay Time（Dijkstra） | M | ⭐⭐ | ☐ |
| 787 | Cheapest Flights Within K Stops | M | ⭐⭐ | ☐ |
| 1584 | Min Cost to Connect All Points（MST） | M | ⭐ | ☐ |
| 127 | Word Ladder | H | ⭐⭐ | ☐ |
| 269 | Alien Dictionary | H | ⭐⭐ | ☐ |
| 332 | Reconstruct Itinerary | H | ⭐ | ☐ |
| 778 | Swim in Rising Water | H | ⭐ | ☐ |
| 137 | Single Number II | M | ⭐ | ☐ |
| 371 | Sum of Two Integers | M | ⭐ | ☐ |
| 2595 | Number of Even and Odd Bits | E | ⭐ | ☐ |
| 1720 | Decode XORed Array | E | ⭐ | ☐ |
| 201 | Bitwise AND of Numbers Range | M | ⭐ | ☐ |
| 7 | Reverse Integer ← **溢位判斷是評分點** | M | ⭐⭐ | ☐ |
| 9 | Palindrome Number | E | ⭐ | ☐ |

**W5 現況：0 ✔ ・ 32 ☐**（目標 32）

## W6 · 09/16（三）–09/21（一） · 1-D DP ＋ Greedy（32 題，5 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 1137 | N-th Tribonacci Number | E | ⭐ | ☐ |
| 509 | Fibonacci Number | E | ⭐ | ☐ |
| 70 | Climbing Stairs ← **用 DP 狀態轉移重講一次** | E | ⭐⭐ | ☐ |
| 118 | Pascal's Triangle | E | ⭐⭐ | ☐ |
| 746 | Min Cost Climbing Stairs | E | ⭐⭐ | ☐ |
| 198 | House Robber | M | ⭐⭐⭐ | ☐ |
| 213 | House Robber II | M | ⭐⭐ | ☐ |
| 740 | Delete and Earn | M | ⭐ | ☐ |
| 5 | Longest Palindromic Substring | M | ⭐⭐⭐ | ☐ |
| 647 | Palindromic Substrings | M | ⭐⭐ | ☐ |
| 91 | Decode Ways | M | ⭐⭐ | ☐ |
| 322 | Coin Change | M | ⭐⭐⭐ | ☐ |
| 377 | Combination Sum IV | M | ⭐⭐ | ☐ |
| 279 | Perfect Squares | M | ⭐⭐ | ☐ |
| 152 | Maximum Product Subarray | M | ⭐⭐ | ☐ |
| 139 | Word Break | M | ⭐⭐⭐ | ☐ |
| 300 | Longest Increasing Subsequence | M | ⭐⭐⭐ | ☐ |
| 416 | Partition Equal Subset Sum | M | ⭐⭐ | ☐ |
| 53 | Maximum Subarray（Kadane） | M | ⭐⭐⭐ | ☐ |
| 55 | Jump Game | M | ⭐⭐⭐ | ☐ |
| 45 | Jump Game II | M | ⭐⭐ | ☐ |
| 134 | Gas Station | M | ⭐⭐ | ☐ |
| 846 | Hand of Straights | M | ⭐ | ☐ |
| 763 | Partition Labels | M | ⭐⭐ | ☐ |
| 678 | Valid Parenthesis String | M | ⭐ | ☐ |
| 452 | Minimum Number of Arrows to Burst Balloons | M | ⭐⭐ | ☐ |
| 1899 | Merge Triplets to Form Target | M | ⭐ | ☐ |
| 605 | Can Place Flowers | E | ⭐ | ☐ |
| 2600 | K Items With the Maximum Sum | M | ⭐ | ☐ |
| 628 | Maximum Product of Three Numbers ← **負數情境** | M | ⭐ | ☐ |
| 3536 | Maximum Product of Two Digits | E | ⭐ | ☐ |
| 292 | Nim Game | E | ⭐ | ☐ |

**W6 現況：0 ✔ ・ 32 ☐**（目標 32）

> [!success] 🚩 檢核點 3（完成 W6 後）
> **45 分鐘內完成 2 題沒做過的 Medium**（隨機抽）。
> 這是實際面試節奏。做不到代表還不能上場。

## W7 · 09/22（二）–09/26（六） · 2-D DP ＋ Intervals ＋ Matrix（32 題，5 個工作日）

| # | 題目 | 難度 | 頻率 | 狀態 |
|---|---|---|---|---|
| 62 | Unique Paths | M | ⭐⭐ | ☐ |
| 63 | Unique Paths II | M | ⭐⭐ | ☐ |
| 64 | Minimum Path Sum | M | ⭐⭐ | ☐ |
| 120 | Triangle | M | ⭐⭐ | ☐ |
| 221 | Maximal Square | M | ⭐⭐ | ☐ |
| 1143 | Longest Common Subsequence | M | ⭐⭐⭐ | ☐ |
| 309 | Best Time to Buy/Sell Stock with Cooldown | M | ⭐⭐ | ☐ |
| 518 | Coin Change II | M | ⭐⭐ | ☐ |
| 494 | Target Sum | M | ⭐⭐ | ☐ |
| 97 | Interleaving String | M | ⭐ | ☐ |
| 72 | Edit Distance | H | ⭐⭐⭐ | ☐ |
| 329 | Longest Increasing Path in a Matrix | H | ⭐⭐ | ☐ |
| 312 | Burst Balloons | H | ⭐ | ☐ |
| 10 | Regular Expression Matching | H | ⭐⭐ | ☐ |
| 252 | Meeting Rooms | E | ⭐⭐ | ☐ |
| 57 | Insert Interval | M | ⭐⭐ | ☐ |
| 56 | Merge Intervals | M | ⭐⭐⭐ | ☐ |
| 435 | Non-overlapping Intervals | M | ⭐⭐ | ☐ |
| 253 | Meeting Rooms II | M | ⭐⭐⭐ | ☐ |
| 1851 | Minimum Interval to Include Each Query | H | ⭐ | ☐ |
| 48 | Rotate Image | M | ⭐⭐ | ☐ |
| 54 | Spiral Matrix | M | ⭐⭐ | ☐ |
| 73 | Set Matrix Zeroes | M | ⭐⭐ | ☐ |
| 240 | Search a 2D Matrix II | M | ⭐⭐ | ☐ |
| 289 | Game of Life | M | ⭐⭐ | ☐ |
| 50 | Pow(x, n) | M | ⭐⭐ | ☐ |
| 172 | Factorial Trailing Zeroes | M | ⭐ | ☐ |
| 258 | Add Digits | E | ⭐ | ☐ |
| 728 | Self Dividing Numbers | E | ⭐ | ☐ |
| 171 | Excel Sheet Column Number | E | ⭐ | ☐ |
| 28 | Find the Index of First Occurrence ← **能講 KMP 概念** | E | ⭐⭐ | ☐ |
| 58 | Length of Last Word | E | ⭐ | ☐ |

**W7 現況：0 ✔ ・ 32 ☐**（目標 32）

> [!success] 🚩 檢核點 4（09/27，週日）= **能不能上場的最終判定**
> 三場完整模擬面試（pramp / interviewing.io，**全英文口述**），至少 **2 場拿到 Hire**。
> 四項缺一不可：① 先講思路再寫 code ② 主動提 edge case ③ 講出時間／空間複雜度 ④ 45 分鐘內完成
> 沒過 → 10 月重點從新題改成模擬面試補強。

---

# 韌體／嵌入式加強週表（與 Phase A 平行進行，每天額外 30–45 分鐘）

> 依 [Dcard 求職心得文](https://www.dcard.tw/f/tech_job/p/260108034)（USC 畢業、Qualcomm offer）整理。
> 作者強調：韌體面試考的不只是 LeetCode，**OS、多執行緒、電腦結構、周邊協議**都是常態考點，而且幾乎全程用 C。
> 光看筆記沒用，**每個主題都要練「動口講一次」**，不是只求寫得出來。

| 週 | 主題 | 具體內容 | ✔ |
|---|---|---|---|
| W1 | C 硬底子 | 指標／記憶體對齊／`volatile`／`static`／`extern`／型別大小；手刻 `strlen`／`strcpy`／`strcmp`／`memcpy` | ☐ |
| W2 | Bit Manipulation＋Endian | 手刻 reverse bits、count bits、2's complement；byte order（endianness）偵測與交換 | ☐ |
| W3 | 連結串列延伸＋OS 基礎 | （對應本週 DSA 主題）process vs thread 差異、context switch（含硬體層面）、嵌入式系統開機流程 | ☐ |
| W4 | 多執行緒 coding | 手寫 pthread：`create`／`join`／`mutex lock`／`unlock`；練習「兩執行緒交錯印出奇偶數」這類經典題 | ☐ |
| W5 | 中斷與同步 | ISR 流程、降低中斷延遲、mutex／semaphore／spinlock 使用時機、critical section、deadlock、priority inversion、starvation | ☐ |
| W6 | 電腦結構 | 5-stage pipeline、data hazard、CISC vs RISC、cache mapping、virtual memory／MMU／TLB | ☐ |
| W7 | 周邊協議＋總複習 | I2C／SPI／UART 原理、傳輸速度比較、I2C 仲裁與 clock stretching；把 W1–W6 全部口述複習一次 | ☐ |

> [!tip] 面試技巧（文章重點）
> - 每場面試後**立刻記錄**卡住的題目與觀念，不要重複犯錯
> - 說出思路比寫出正確答案更重要——**先講 approach 再寫 code**
> - Panel 超過 4 輪可以主動要求分兩天進行，前一天不要熬夜衝刺
> - 找同儕一起練習口說，孤軍奮戰效果較差

> [!note] 參考資源（文章提及）
> - *0x10 Best Questions for Would-be Embedded Programmers*
> - PTT 北美版 firmware 心得、相關 Medium 文章
> - [1point3acres](https://www.1point3acres.com) 面試題庫（需每日簽到累積大米解鎖）

---

# Phase B：秋季實戰 09/28–12/20

開學後降到 **每週 8–10 題**，重心轉到「面試會過」。

| 項目 | 頻率 | ✔ |
|---|---|---|
| **每週 2 場計時模擬面試**（全英文） | 每週 | ☐ |
| **OA 專項**：HackerRank / CodeSignal 題型，限時完成 | 每週 1 次 | ☐ |
| 第二輪：Phase A 標記 🟡🔴 的全部再寫一次 | 持續 | ☐ |
| 公司題庫：Google / Meta / Amazon / NVIDIA / Apple 近半年 | 持續 | ☐ |
| 嵌入式專屬題：ring buffer、memory pool、`memcpy` 實作、中斷安全佇列 → [[Firmware 面試準備]] | 一輪 | ☐ |
| BQ 五個故事練到 60 秒版＋3 分鐘版 → [[Behavioral Questions (BQ)]] | 持續 | ☐ |

### 嵌入式專屬題細項（Phase B 補強用，依文章整理）

| 項目 | ✔ |
|---|---|
| Ring buffer 手刻（含 full/empty 判斷） | ☐ |
| Memory pool 手刻 | ☐ |
| `memcpy`／`memmove` 手刻（含 overlap 情境） | ☐ |
| 中斷安全佇列（interrupt-safe queue） | ☐ |
| pthread 多執行緒 coding 題（奇偶數交錯印出、producer-consumer） | ☐ |
| I2C／SPI／UART 口頭問答自我測驗 | ☐ |
| OS／電腦結構 flashcard 全部複習一輪 | ☐ |

## ⏰ 投遞時間軸（**與刷題並行，不要等刷完才投**）

> [!tip] 履歷與投遞策略（依文章：作者新鮮人投約 600 份 LinkedIn Easy Apply，拿到 18 場面試）
> - **越早投越好，不要等履歷改到完美**——履歷可以邊投邊修
> - 履歷開頭加 2 句總結，明確寫出「Embedded Software Engineer」定位
> - 經歷用 **STAR** 原則寫，盡量帶數字結果
> - 履歷寫完找**至少 2–3 人**幫忙看，確認別人能秒懂你的專案在做什麼
> - 內推不一定比海投有效，**海投＋內推雙軌並行**，不要只押一邊

| 時間 | 動作 |
|---|---|
| **08 月（現在）** | 履歷定稿、LinkedIn 更新、Simplify 設定自動填表 |
| **08–09 月** | 大廠 2027 summer intern 陸續開缺，**開一個投一個** |
| **09–11 月** | OA ＋ 面試高峰 |
| **10–12 月** | 多數缺陸續關閉 |
| **2027/01–02** | 補投晚開的缺、小公司、新創 |

---

# Phase C：冬季深化 2027/01–03

| 項目 | ✔ |
|---|---|
| Hard 題專攻（DP、圖論、設計題各 15 題） | ☐ |
| 第二輪：全部限時 25 分鐘 | ☐ |
| 系統設計入門（intern 通常輕量，Google 偶爾考） | ☐ |
| 若已拿到 offer → 轉向該公司技術棧預習 | ☐ |

---

## 週進度追蹤

| 週次 | 期間 | 工作日 | 主題 | 週目標 | 累計目標 | ✔ 已完成 | 累計 ✔ | 檢核點 |
|---|---|---|---|---|---|---|---|---|
| W1 | 08/15（六）–08/21（五） | 6 | Arrays & Hashing、Two Pointers | 33 | 33 |  |  | |
| W2 | 08/22（六）–08/28（五） | 6 | Sliding Window、Stack、Binary Search | 33 | 66 |  |  | 🚩1 速度 |
| W3 | 08/29（六）–09/03（四） | 5 | Linked List、Trees I | 33 | 99 |  |  | |
| W4 | 09/04（五）–09/09（三） | 5 | Trees II、Trie、Heap、Backtracking | 33 | 132 |  |  | 🚩2 模板默寫 |
| W5 | 09/10（四）–09/15（二） | 5 | Graphs | 32 | 164 |  |  | |
| W6 | 09/16（三）–09/21（一） | 5 | 1-D DP、Greedy | 32 | 196 |  |  | 🚩3 45 分鐘 2 題 |
| W7 | 09/22（二）–09/26（六） | 5 | 2-D DP、Intervals、Matrix | 32 | **228** |  |  | 🚩4 **模擬面試（09/27）** |

> [!note] 怎麼讀這張表
> 「✔ 已完成」只填當週實際新完成的題數，每天寫完當場更新，不要等週末回填。截至 08/15 全部重新起算，兩欄都還是空的。區塊之間不再對齊星期一到星期日，每週日一律休息，工作日欄是扣掉週日之後的實際天數。

## 錯題本（🔴 隔 1 天重寫、🟡 隔 3 天、🟢 隔 2 週；三次全 🟢 才算會）

| 日期 | 題號 | 卡在哪 | 重寫日 | 結果 |
|---|---|---|---|---|
|  |  |  |  |  |

---

> [!note] 三個最容易失敗的地方
> 1. **只追數量不追品質**——檢核點沒過就不要往前推。
> 2. **不練口說**——大廠評的是「思考過程」不是「程式碼」。從 W1 就**出聲講**。
> 3. **等刷完才投履歷**——缺會關。8 月就開始投，邊面邊補。
