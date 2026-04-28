#Algorithms

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

