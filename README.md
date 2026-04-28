# ⏱️ Time Complexity: O(n) vs O(n²)

## 📌 Overview

Time complexity describes how an algorithm’s runtime grows as the input size (`n`) increases.

This document focuses on two of the most important and commonly encountered complexities:

* **O(n)** — Linear Time
* **O(n²)** — Quadratic Time

---

# 🟢 O(n) — Linear Time

## 💡 Definition

An algorithm runs in **O(n)** time if its runtime grows **linearly** with the size of the input.

> If the input doubles, the runtime roughly doubles.

---

## 💻 Example

```javascript
function printNumbers(arr) {
    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }
}
```

---

## 🔍 Explanation

* The loop runs once for each element in the array
* If `n = 5` → 5 operations
* If `n = 100` → 100 operations

---

## 📈 Growth Pattern

| Input Size (n) | Operations |
| -------------- | ---------- |
| 10             | 10         |
| 100            | 100        |
| 1000           | 1000       |

---

## ✅ Characteristics

* Efficient and scalable
* Common in real-world applications
* Often achieved with a **single loop**

---

## 📌 Common Use Cases

* Iterating through arrays
* Searching (linear search)
* Basic data processing

---

# 🔴 O(n²) — Quadratic Time

## 💡 Definition

An algorithm runs in **O(n²)** time if its runtime grows **proportional to the square** of the input size.

> If the input doubles, runtime becomes ~4× larger.

---

## 💻 Example

```javascript
function printPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = 0; j < arr.length; j++) {
            console.log(arr[i], arr[j]);
        }
    }
}
```

---

## 🔍 Explanation

* For each element, the algorithm loops through the entire array again
* If `n = 5` → 25 operations
* If `n = 100` → 10,000 operations

---

## 📈 Growth Pattern

| Input Size (n) | Operations |
| -------------- | ---------- |
| 10             | 100        |
| 100            | 10,000     |
| 1000           | 1,000,000  |

---

## ⚠️ Characteristics

* Becomes slow quickly as input grows
* Often caused by **nested loops**
* Should be optimized when possible

---

## 📌 Common Use Cases

* Comparing all pairs
* Brute-force solutions
* Some sorting algorithms (e.g., Bubble Sort)

---

# 🆚 O(n) vs O(n²)

| Feature         | O(n)     | O(n²)              |
| --------------- | -------- | ------------------ |
| Growth Rate     | Linear   | Quadratic          |
| Performance     | Fast     | Slow (large input) |
| Typical Pattern | One loop | Nested loops       |
| Scalability     | Good     | Poor               |

---

# 🧠 Key Takeaways

* Prefer **O(n)** solutions whenever possible
* Avoid **O(n²)** for large datasets
* Look for opportunities to:

  * Use **hash maps**
  * Reduce nested loops
  * Trade space for time

---

# 🚀 Real-World Insight

Optimizing from **O(n²) → O(n)** can turn:

* Minutes → milliseconds
* Unusable → production-ready

