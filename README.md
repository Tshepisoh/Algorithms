# Algorithms

## 1.🧩 Two Sum (JavaScript)

## 📌 Problem Overview

The **Two Sum** problem is a classic algorithm challenge:

> Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.

### ✅ Constraints

* Exactly **one solution** exists
* You **cannot use the same element twice**
* Return **indices**, not the values

---

## 📥 Example

```javascript
Input: nums = [2, 7, 11, 15], target = 9  
Output: [0, 1]
```

**Explanation:**
`nums[0] + nums[1] = 2 + 7 = 9`

---

## 🚀 Optimal Approach (Hash Map)

### 💡 Idea

Instead of checking all pairs (O(n²)), we:

1. Store numbers we’ve already seen
2. For each number, check if its complement exists

**Complement formula:**

```javascript
complement = target - current
```

---

## 🧠 Algorithm Steps

1. Create a `Map` to store numbers and their indices
2. Loop through the array
3. For each element:

   * Calculate its complement
   * Check if complement exists in the map
   * If yes → return indices
   * If not → store current number in map

---

## 💻 Implementation

```javascript
function twoSum(nums, target) {
    const map = new Map(); // number -> index

    for (let i = 0; i < nums.length; i++) {
        const current = nums[i];
        const complement = target - current;

        if (map.has(complement)) {
            return [map.get(complement), i];
        }

        map.set(current, i);
    }
}
```

---

## 🔍 Example Walkthrough

For:

```javascript
nums = [2, 7, 11, 15]
target = 9
```

| Step | Current | Complement | Map    | Action        |
| ---- | ------- | ---------- | ------ | ------------- |
| 1    | 2       | 7          | {}     | Store 2 → 0   |
| 2    | 7       | 2          | {2: 0} | Found match ✅ |

---

## ⏱️ Complexity Analysis

| Metric           | Value |
| ---------------- | ----- |
| Time Complexity  | O(n)  |
| Space Complexity | O(n)  |

---

## ⚠️ Important Notes

* Always **check before inserting** into the map
* This prevents using the same element twice
* Works with:

  * Negative numbers ✅
  * Duplicates ✅
  * Zero values ✅

---

## 🆚 Brute Force vs Optimal

| Approach    | Time Complexity | Description          |
| ----------- | --------------- | -------------------- |
| Brute Force | O(n²)           | Check all pairs      |
| Hash Map    | O(n)            | Fast lookup strategy |

---

## 📚 Key Takeaway

> Use a **hash map** to trade space for speed and reduce time complexity.

This pattern is widely used in:

* Pair matching problems
* Subarray sum problems
* Data lookup optimizations
* 

# 2. 🔁 Palindrome Number (JavaScript)

## 📌 Problem Statement

Given an integer `x`, determine whether it is a **palindrome**.

A number is a palindrome if it reads the same forward and backward.

### ✅ Examples

```text id="k2v8q1"
121   → true
-121  → false
123   → false
```

---

# 🚀 Approach: Reverse the Number

## 💡 Idea

We reverse the number digit by digit and compare it to the original number.

If both are equal → it's a palindrome.

---

# 💻 Implementation

```javascript id="p8x2v9"
var isPalindrome = function (x) {
    let reversed = 0;
    let copy = x;

    if (x < 0) {
        return false;
    }

    while (copy > 0) {
        let remainder = copy % 10;
        reversed = reversed * 10 + remainder;
        copy = Math.floor(copy / 10);
    }

    if (reversed === x) {
        return true;
    } else {
        return false;
    }
};
```

---

# 🔍 How It Works

## Step-by-step breakdown

For `x = 121`:

| Step | copy | remainder | reversed |
| ---- | ---- | --------- | -------- |
| 1    | 121  | 1         | 1        |
| 2    | 12   | 2         | 12       |
| 3    | 1    | 1         | 121      |

---

## 🔹 Key Operations

### 1. Extract last digit

```javascript id="l9n3xq"
copy % 10
```

### 2. Remove last digit

```javascript id="m4v7qp"
copy = Math.floor(copy / 10);
```

### 3. Build reversed number

```javascript id="z8p2tn"
reversed = reversed * 10 + remainder;
```

---

# ⚠️ Edge Cases

| Input | Output | Reason                               |
| ----- | ------ | ------------------------------------ |
| -121  | false  | negative numbers are not palindromes |
| 10    | false  | reversed = 01                        |
| 0     | true   | single digit is always palindrome    |

---

# ⏱️ Time Complexity

## 🟡 O(log n)

* The loop runs once per digit
* Number of digits in `x` is proportional to `log₁₀(x)`

### Why?

Each iteration removes one digit:

```text id="v2n8q1"
121 → 12 → 1 → 0
```

---

# 📦 Space Complexity

## 🟢 O(1)

Only a few variables are used:

* `reversed`
* `copy`
* `remainder`

No extra data structures required.

---

# 🧠 Key Takeaways

* Uses **math operations instead of strings**
* Efficient digit manipulation technique
* Common pattern in coding interviews
* Helps build foundation for:

  * reverse number problems
  * digit extraction problems
  * numeric validation problems

---

# 🏁 Summary

This solution checks if a number is a palindrome by reversing it mathematically and comparing it to the original value. It runs in **O(log n)** time and uses constant space.

---


