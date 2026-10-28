# 50 Most Frequently Asked Queue Interview Questions

A curated list of 50 frequently asked queue problems covering basic queues, deques, monotonic deques, circular queues, simulations, BFS (grid/graph/tree/topological) and cache design.

## Problem List

| # | Problem Name | Queue Concept Tested | Platform / Source | Frequently Asked By (Companies) | Solved? | Notes | Link |
|---|--------------|----------------------|-------------------|---------------------------------|:-------:|-------|------|
| 1 | Implement Queue using Array | Basic Queue | GFG | Amazon, Microsoft, TCS | ⬜ | Foundational FIFO behavior - enqueue/dequeue mechanics | [Link](https://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/) |
| 2 | Implement Queue using Linked List | Basic Queue | GFG | Amazon, Microsoft, OYO | ⬜ | Foundational FIFO behavior - enqueue/dequeue mechanics | [Link](https://www.geeksforgeeks.org/queue-set-2-linked-list-implementation/) |
| 3 | Implement Deque using Array | Basic Deque | GFG | Visa, Walmart | ⬜ | Insert/remove from both ends | [Link](https://www.geeksforgeeks.org/implementation-deque-using-circular-array/) |
| 4 | Implement Stack using Queues | Queue -> Stack | LeetCode 225 | Amazon, Cisco, Bloomberg, Google | ⬜ | Emulating LIFO using FIFO structures | [Link](https://leetcode.com/problems/implement-stack-using-queues/) |
| 5 | Implement Queue using Stacks | Stack -> Queue | LeetCode 232 / GFG | Amazon, Microsoft, Goldman Sachs | ⬜ | Emulating FIFO using LIFO structures | [Link](https://leetcode.com/problems/implement-queue-using-stacks/) |
| 6 | Design Circular Queue | Circular Queue | LeetCode 622 | Amazon, Microsoft, Meta, Apple | ⬜ | Wraparound indexing, fixed-size buffer management | [Link](https://leetcode.com/problems/design-circular-queue/) |
| 7 | Design Circular Queue using Linked List | Circular Queue | GFG | Amazon | ⬜ | Wraparound indexing, fixed-size buffer management | [Link](https://www.geeksforgeeks.org/circular-queue-set-2-circular-linked-list-implementation/) |
| 8 | Design Circular Deque | Deque | LeetCode 641 | Amazon, Google, Salesforce | ⬜ | Double-ended queue for flexible insert/remove | [Link](https://leetcode.com/problems/design-circular-deque/) |
| 9 | Design Front Middle Back Queue | Deque | LeetCode 1670 | Meta, Amazon, Google | ⬜ | Double-ended queue for flexible insert/remove | [Link](https://leetcode.com/problems/design-front-middle-back-queue/) |
| 10 | Design Bounded Blocking Queue | Producer-Consumer Queue | LeetCode 1188 | Meta, Google | ⬜ | Concurrency-style blocking queue design | [Link](https://leetcode.com/problems/design-bounded-blocking-queue/) |
| 11 | Reverse a Queue | Queue Manipulation | GFG | Amazon, Flipkart, Samsung, Paytm | ⬜ | Direct queue restructuring using core operations | [Link](https://www.geeksforgeeks.org/reversing-a-queue/) |
| 12 | Reverse First K Elements of a Queue | Queue + Stack | GFG | Amazon, Goldman Sachs, Microsoft | ⬜ | Combining both structures to solve ordering problems | [Link](https://www.geeksforgeeks.org/reversing-first-k-elements-queue/) |
| 13 | Interleave First Half of Queue with Second Half | Queue Manipulation | GFG | Amazon, Microsoft, Flipkart | ⬜ | Direct queue restructuring using core operations | [Link](https://www.geeksforgeeks.org/interleave-first-half-queue-second-half/) |
| 14 | Check if a Queue Can Be Sorted into Another Queue using a Stack | Queue + Stack | GFG | Amazon | ⬜ | Combining both structures to solve ordering problems | [Link](https://www.geeksforgeeks.org/check-queue-can-sorted-another-queue-using-stack/) |
| 15 | Generate Binary Numbers from 1 to N | Queue Generation / BFS-style | GFG | Amazon, Microsoft | ⬜ | Using queue to generate sequences level by level | [Link](https://www.geeksforgeeks.org/interesting-method-generate-binary-numbers-1-n/) |
| 16 | First Non-Repeating Character in a Stream | Queue + HashMap | GFG | Amazon, Microsoft, Flipkart, Yahoo | ⬜ | Queue paired with auxiliary lookup structure | [Link](https://www.geeksforgeeks.org/queue-based-approach-for-first-non-repeating-character-in-a-stream/) |
| 17 | First Negative Integer in Every Window of Size K | Deque | GFG | Amazon, Microsoft, Flipkart | ⬜ | Double-ended queue for flexible insert/remove | [Link](https://www.geeksforgeeks.org/first-negative-integer-every-window-size-k/) |
| 18 | Maximum of All Subarrays of Size K | Monotonic Deque | GFG | Amazon, Microsoft, OYO | ⬜ | Deque maintained in increasing/decreasing order for O(1) min/max | [Link](https://www.geeksforgeeks.org/sliding-window-maximum-maximum-of-all-subarrays-of-size-k/) |
| 19 | Sliding Window Maximum | Monotonic Deque | LeetCode 239 | Amazon, Google, Microsoft, Uber, Facebook | ⬜ | Deque maintained in increasing/decreasing order for O(1) min/max | [Link](https://leetcode.com/problems/sliding-window-maximum/) |
| 20 | Sliding Window Minimum | Monotonic Deque | GFG | Amazon, Microsoft | ⬜ | Deque maintained in increasing/decreasing order for O(1) min/max | [Link](https://www.geeksforgeeks.org/sliding-window-minimum-minimum-of-all-subarrays-of-size-k/) |
| 21 | Sliding Window Median | Deque + Multiset | LeetCode 480 | Google | ⬜ | Deque combined with balanced structure for median tracking | [Link](https://leetcode.com/problems/sliding-window-median/) |
| 22 | Shortest Subarray with Sum at Least K | Monotonic Deque | LeetCode 862 | Google, Amazon, Microsoft | ⬜ | Deque maintained in increasing/decreasing order for O(1) min/max | [Link](https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/) |
| 23 | Jump Game VI | Monotonic Deque + DP | LeetCode 1696 | Google, Amazon, TikTok | ⬜ | Deque-optimized dynamic programming | [Link](https://leetcode.com/problems/jump-game-vi/) |
| 24 | Number of Recent Calls | Time-Window Queue | LeetCode 933 | Google, Amazon | ⬜ | Queue storing timestamps within a sliding time window | [Link](https://leetcode.com/problems/number-of-recent-calls/) |
| 25 | Moving Average from Data Stream | Time-Window Queue | LeetCode 346 | Google, Facebook | ⬜ | Queue storing timestamps within a sliding time window | [Link](https://leetcode.com/problems/moving-average-from-data-stream/) |
| 26 | Design Hit Counter | Time-Window Queue | LeetCode 362 | Google, Amazon, Dropbox, Uber | ⬜ | Queue storing timestamps within a sliding time window | [Link](https://leetcode.com/problems/design-hit-counter/) |
| 27 | Time Needed to Buy Tickets | Simulation Queue | LeetCode 2073 | Amazon, Goldman Sachs, Google | ⬜ | Queue used to simulate a real-world process step by step | [Link](https://leetcode.com/problems/time-needed-to-buy-tickets/) |
| 28 | Number of Students Unable to Eat Lunch | Simulation Queue | LeetCode 1700 | Amazon, Microsoft | ⬜ | Queue used to simulate a real-world process step by step | [Link](https://leetcode.com/problems/number-of-students-unable-to-eat-lunch/) |
| 29 | Dota2 Senate | Two-Queue Simulation | LeetCode 649 | Amazon, Google | ⬜ | Two queues modeling turn-based state | [Link](https://leetcode.com/problems/dota2-senate/) |
| 30 | Reveal Cards In Increasing Order | Deque Simulation | LeetCode 950 | Amazon, Google | ⬜ | Deque used to simulate ordered dealing/removal process | [Link](https://leetcode.com/problems/reveal-cards-in-increasing-order/) |
| 31 | Circular Tour / Gas Station | Circular Queue Logic | LeetCode 134 / GFG | Amazon, Microsoft, Flipkart | ⬜ | Circular traversal / wraparound reasoning | [Link](https://leetcode.com/problems/gas-station/) |
| 32 | Find the Winner of the Circular Game (Josephus) | Circular Queue | LeetCode 1823 | Amazon | ⬜ | Wraparound indexing, fixed-size buffer management | [Link](https://leetcode.com/problems/find-the-winner-of-the-circular-game/) |
| 33 | Rotting Oranges | Multi-Source BFS (Grid) | LeetCode 994 | Amazon, Microsoft, Flipkart, Oracle | ⬜ | BFS starting from multiple sources simultaneously on a grid | [Link](https://leetcode.com/problems/rotting-oranges/) |
| 34 | 01 Matrix | Multi-Source BFS (Grid) | LeetCode 542 | Amazon, Google, Microsoft | ⬜ | BFS starting from multiple sources simultaneously on a grid | [Link](https://leetcode.com/problems/01-matrix/) |
| 35 | Walls and Gates | Multi-Source BFS (Grid) | LeetCode 286 | Google, Amazon, Meta | ⬜ | BFS starting from multiple sources simultaneously on a grid | [Link](https://leetcode.com/problems/walls-and-gates/) |
| 36 | As Far from Land as Possible | Multi-Source BFS (Grid) | LeetCode 1162 | Amazon, Google | ⬜ | BFS starting from multiple sources simultaneously on a grid | [Link](https://leetcode.com/problems/as-far-from-land-as-possible/) |
| 37 | Shortest Path in Binary Matrix | Grid BFS | LeetCode 1091 | Amazon, Google, Meta | ⬜ | Standard shortest-path BFS on a 2D grid | [Link](https://leetcode.com/problems/shortest-path-in-binary-matrix/) |
| 38 | Number of Islands (BFS) | Grid BFS | LeetCode 200 | Amazon, Google, Microsoft, Facebook | ⬜ | Standard shortest-path BFS on a 2D grid | [Link](https://leetcode.com/problems/number-of-islands/) |
| 39 | Snake and Ladder Problem | Graph BFS | LeetCode 909 | Amazon, Microsoft, Flipkart | ⬜ | BFS on a general graph structure | [Link](https://leetcode.com/problems/snakes-and-ladders/) |
| 40 | Open the Lock | State-Space BFS | LeetCode 752 | Google, Amazon, Meta | ⬜ | BFS over an abstract state space, not a physical grid | [Link](https://leetcode.com/problems/open-the-lock/) |
| 41 | Word Ladder | BFS + HashSet | LeetCode 127 | Amazon, Google, Microsoft, Snap, LinkedIn | ⬜ | BFS with set-based visited/candidate tracking | [Link](https://leetcode.com/problems/word-ladder/) |
| 42 | Course Schedule (Kahn's Algorithm) | Topological BFS | LeetCode 207 | Google, Amazon, Microsoft, Facebook | ⬜ | Kahn's algorithm - BFS using in-degree counts | [Link](https://leetcode.com/problems/course-schedule/) |
| 43 | Course Schedule II | Topological BFS | LeetCode 210 | Google, Amazon, Microsoft | ⬜ | Kahn's algorithm - BFS using in-degree counts | [Link](https://leetcode.com/problems/course-schedule-ii/) |
| 44 | Clone Graph | Graph BFS + HashMap | LeetCode 133 | Amazon, Microsoft, Google | ⬜ | BFS with node-to-clone/node-to-value mapping | [Link](https://leetcode.com/problems/clone-graph/) |
| 45 | Binary Tree Level Order Traversal | Tree BFS | LeetCode 102 | Amazon, Microsoft, Facebook, LinkedIn | ⬜ | Level-order traversal of a tree using a queue | [Link](https://leetcode.com/problems/binary-tree-level-order-traversal/) |
| 46 | Binary Tree Zigzag Level Order Traversal | Tree BFS + Deque | LeetCode 103 | Amazon, Microsoft | ⬜ | Level-order traversal needing direction alternation | [Link](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/) |
| 47 | Binary Tree Right Side View | Tree BFS | LeetCode 199 | Amazon, Google, Facebook | ⬜ | Level-order traversal of a tree using a queue | [Link](https://leetcode.com/problems/binary-tree-right-side-view/) |
| 48 | Populating Next Right Pointers in Each Node | Tree BFS | LeetCode 116 | Microsoft, Amazon, Facebook | ⬜ | Level-order traversal of a tree using a queue | [Link](https://leetcode.com/problems/populating-next-right-pointers-in-each-node/) |
| 49 | LRU Cache | Queue-Ordered Cache Design | LeetCode 146 | Amazon, Google, Microsoft, Meta, Bloomberg, Uber | ⬜ | Queue-like recency ordering combined with a hashmap | [Link](https://leetcode.com/problems/lru-cache/) |
| 50 | LFU Cache | Frequency Queue + Linked Structures | LeetCode 460 | Amazon, Google, Microsoft | ⬜ | Multiple ordered structures bucketed by frequency | [Link](https://leetcode.com/problems/lfu-cache/) |

> Tip: replace ⬜ with ✅ as you solve each problem.
