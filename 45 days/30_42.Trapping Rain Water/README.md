---
comments: true
difficulty: Hard
edit_url: https://github.com/PraveenMohan13
tags:
    - Stack
    - Array
    - Two Pointers
    - Dynamic Programming
    - Monotonic Stack
---

<!-- problem:start -->

# [42. Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water)


## Description

<!-- description:start -->

<p>Given <code>n</code> non-negative integers representing an elevation map where the width of each bar is <code>1</code>, compute how much water it can trap after raining.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>
<img src="https://fastly.jsdelivr.net/gh/doocs/leetcode@main/solution/0000-0099/0042.Trapping%20Rain%20Water/images/rainwatertrap.png" style="width: 412px; height: 161px;" />
<pre>
<strong>Input:</strong> height = [0,1,0,2,1,0,1,3,2,1,2,1]
<strong>Output:</strong> 6
<strong>Explanation:</strong> The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> height = [4,2,0,3,2,5]
<strong>Output:</strong> 9
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == height.length</code></li>
	<li><code>1 &lt;= n &lt;= 2 * 10<sup>4</sup></code></li>
	<li><code>0 &lt;= height[i] &lt;= 10<sup>5</sup></code></li>
</ul>

<!-- description:end -->

## Solutions

<!-- solution:start -->

### Solution 1: Dynamic Programming

We define $left[i]$ as the height of the highest bar to the left of and including the position at index $i$, and $right[i]$ as the height of the highest bar to the right of and including the position at index $i$. Therefore, the amount of rainwater that can be trapped at index $i$ is $min(left[i], right[i]) - height[i]$. We traverse the array to calculate $left[i]$ and $right[i]$, and the final answer is $\sum_{i=0}^{n-1} \min(left[i], right[i]) - height[i]$.

The time complexity is $O(n)$, and the space complexity is $O(n)$. Here, $n$ is the length of the array.

<!-- tabs:start -->

#### Python3

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)
        left = [height[0]] * n
        right = [height[-1]] * n
        for i in range(1, n):
            left[i] = max(left[i - 1], height[i])
            right[n - i - 1] = max(right[n - i], height[n - i - 1])
        return sum(min(l, r) - h for l, r, h in zip(left, right, height))
```

#### Java

```java
class Solution {
    public int trap(int[] height) {
        int n = height.length;
        int[] left = new int[n];
        int[] right = new int[n];
        left[0] = height[0];
        right[n - 1] = height[n - 1];
        for (int i = 1; i < n; ++i) {
            left[i] = Math.max(left[i - 1], height[i]);
            right[n - i - 1] = Math.max(right[n - i], height[n - i - 1]);
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            ans += Math.min(left[i], right[i]) - height[i];
        }
        return ans;
    }
}
```

#### C++

```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        int n = height.size();
        int left[n], right[n];
        left[0] = height[0];
        right[n - 1] = height[n - 1];
        for (int i = 1; i < n; ++i) {
            left[i] = max(left[i - 1], height[i]);
            right[n - i - 1] = max(right[n - i], height[n - i - 1]);
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            ans += min(left[i], right[i]) - height[i];
        }
        return ans;
    }
};
```

#### Go

```go
func trap(height []int) (ans int) {
	n := len(height)
	left := make([]int, n)
	right := make([]int, n)
	left[0], right[n-1] = height[0], height[n-1]
	for i := 1; i < n; i++ {
		left[i] = max(left[i-1], height[i])
		right[n-i-1] = max(right[n-i], height[n-i-1])
	}
	for i, h := range height {
		ans += min(left[i], right[i]) - h
	}
	return
}
```

#### TypeScript

```ts
function trap(height: number[]): number {
    const n = height.length;
    const left: number[] = new Array(n).fill(height[0]);
    const right: number[] = new Array(n).fill(height[n - 1]);
    for (let i = 1; i < n; ++i) {
        left[i] = Math.max(left[i - 1], height[i]);
        right[n - i - 1] = Math.max(right[n - i], height[n - i - 1]);
    }
    let ans = 0;
    for (let i = 0; i < n; ++i) {
        ans += Math.min(left[i], right[i]) - height[i];
    }
    return ans;
}
```

#### Rust

```rust
impl Solution {
    #[allow(dead_code)]
    pub fn trap(height: Vec<i32>) -> i32 {
        let n = height.len();
        let mut left: Vec<i32> = vec![0; n];
        let mut right: Vec<i32> = vec![0; n];

        left[0] = height[0];
        right[n - 1] = height[n - 1];

        // Initialize the left & right vector
        for i in 1..n {
            left[i] = std::cmp::max(left[i - 1], height[i]);
            right[n - i - 1] = std::cmp::max(right[n - i], height[n - i - 1]);
        }

        let mut ans = 0;

        // Calculate the ans
        for i in 0..n {
            ans += std::cmp::min(left[i], right[i]) - height[i];
        }

        ans
    }
}
```

#### C#

```cs
public class Solution {
    public int Trap(int[] height) {
        int n = height.Length;
        int[] left = new int[n];
        int[] right = new int[n];
        left[0] = height[0];
        right[n - 1] = height[n - 1];
        for (int i = 1; i < n; ++i) {
            left[i] = Math.Max(left[i - 1], height[i]);
            right[n - i - 1] = Math.Max(right[n - i], height[n - i - 1]);
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            ans += Math.Min(left[i], right[i]) - height[i];
        }
        return ans;
    }
}
```

#### PHP

```php
class Solution {
    /**
     * @param integer[] $height
     * @return integer
     */

    function trap($height) {
        $n = count($height);

        if ($n == 0) {
            return 0;
        }

        $left = 0;
        $right = $n - 1;
        $leftMax = 0;
        $rightMax = 0;
        $ans = 0;

        while ($left < $right) {
            if ($height[$left] < $height[$right]) {
                if ($height[$left] > $leftMax) {
                    $leftMax = $height[$left];
                } else {
                    $ans += $leftMax - $height[$left];
                }
                $left++;
            } else {
                if ($height[$right] > $rightMax) {
                    $rightMax = $height[$right];
                } else {
                    $ans += $rightMax - $height[$right];
                }
                $right--;
            }
        }
        return $ans;
    }
}
```

<!-- tabs:end -->
### Solution 2: Two Pointer

Intuition
Water at any position depends on the maximum bar to the left and the maximum bar to the right.
Instead of precomputing with extra arrays, we can use two pointers with running max values.
Approach
Maintain two pointers left and right.
Track leftMax and rightMax.
If height[left] < height[right], then water trapped at left depends only on leftMax.
If height[left] >= leftMax, update leftMax.
Else, add leftMax - height[left].
Move left++.

Else do the same for right using rightMax.

<!-- tabs:start -->
```Java
class Solution {
    public int trap(int[] a) {
        int n = a.length;
        int left = 0, right = n-1;
        int leftMax = 0, rightMax = 0;
        int res = 0;
        while (left <= right) {
            if (a[left] <= a[right]) {
                if (a[left] >= leftMax) {
                    leftMax = a[left];
                } else {
                    res += leftMax - a[left];
                }
                left++;
            } else {
                if (a[right] >= rightMax) {
                    rightMax = a[right];
                } else {
                    res += rightMax - a[right];
                }
                right--;
            }
        }
        return res;
    }
}
```
<!-- tabs:end -->

### Solution 3: Two Pointer

Problem in Simple Words
You are given an array height.

Each element represents the height of a vertical bar
Bars are next to each other
After raining, water can get trapped between bars
Your task is to calculate how much total water can be trapped.

First Thing to Understand (Very Important)
Water does not depend on just one bar.

At any index i, the water trapped depends on:

The tallest bar to the left
The tallest bar to the right
Water level at index i is:

min(maxLeft, maxRight) - height[i]
If this value is negative, water is 0.

Why This Formula Makes Sense
Imagine standing at position i.

Water can only stay if there is a wall on both sides
The shorter wall decides how much water can stay
Anything taller than that wall will overflow
That’s why we take:

min(leftMax, rightMax)
Naive Way (Why We Don’t Do It)
For every index:

Scan left to find max
Scan right to find max
That takes O(n²) time.

We need something better.

Optimized Idea: Two Pointers
Instead of calculating left and right max for every index separately, we:

Start from both ends

Move inward

Keep track of:

maximum height seen so far from the left
maximum height seen so far from the right
This allows us to compute trapped water in one pass.

Variables Explained
int left = 0;
int right = n - 1;

int left_max = 0;
int right_max = 0;

int ans = 0;
What each one means:

left → pointer moving from start
right → pointer moving from end
left_max → tallest bar seen from the left so far
right_max → tallest bar seen from the right so far
ans → total trapped water
Core Logic (The Most Important Part)
We keep looping while left <= right.

At every step, we decide which side to process.

if (left_max <= right_max)
Why this condition?
If left_max is smaller or equal:

The water level on the left is decided only by left_max
The right side is guaranteed to be tall enough
So it is safe to calculate water at left.

Processing the Left Side
left_max = Math.max(left_max, height[left]);
ans += left_max - height[left];
left++;
What’s happening:

Update the tallest bar seen so far on the left
Calculate water at current index
Move left pointer forward
Processing the Right Side
If right_max is smaller:

right_max = Math.max(right_max, height[right]);
ans += right_max - height[right];
right--;
Same idea, just mirrored:

Update tallest bar on the right
Calculate water at current index
Move right pointer backward

<!-- tabs:start -->
```Java
class Solution {
    public int trap(int[] height) {
        int n = height.length;

        int left = 0;
        int right = n - 1;

        int left_max = 0;
        int right_max = 0;

        int ans = 0;

        while (left <= right) {
            if (left_max <= right_max) {
                left_max = Math.max(left_max, height[left]);
                ans += left_max - height[left];
                left++;
            } else {
                right_max = Math.max(right_max, height[right]);
                ans += right_max - height[right];
                right--;
            }
        }

        return ans;
    }
}
```
Why This Always Works
Water is always limited by the shorter boundary
We only process a side when we know its boundary is fixed
Each index is processed exactly once
No guessing, no revisiting
Time and Space Complexity
Time: O(n)
Space: O(1)
Final Takeaway
This problem is not about counting water directly.

It’s about understanding one rule:

Water height is decided by the shorter side.

Once you accept that and process from both ends intelligently, the solution becomes clean and efficient.



### Solution 3: Monotonic Stack - Last In first out
<!-- tabs:start -->
```Java
class Solution {
    public int trap(List<Integer> height) {
        int n = height.size(); // Number of elements in the height array
        int water = 0;         // Initialize the total trapped water volume
        Stack<Integer> stack = new Stack<>(); // Stack to store indices of height elements
        // Iterate through the heights
        for (int right = 0; right < n; right++) {
            // Process each height to trap water
            while (!stack.isEmpty() && height.get(stack.peek()) < height.get(right)) {
                // If the current height is greater than the height at the top of the stack
                int mid = stack.pop(); // Get the index of the height at the top of the stack
                // If the stack becomes empty, no more water can be trapped
                if (stack.isEmpty())
                    break;
                int left = stack.peek();                     // Get the index of the next height from the top of the stack
                int minHeight = Math.min(height.get(right) - height.get(mid), height.get(left) - height.get(mid));
											// Calculate the minimum height of the two borders
                int width = right - left - 1;         // Calculate the width between the left and right borders
                water += minHeight * width;         // Calculate the trapped water volume and add it to the total
            }
            stack.push(right); // Push the current index onto the stack
        }
        return water; // Return the total trapped water volume
    }
}
<!-- tabs:end -->
<!-- solution:end -->
<!-- problem:end -->
