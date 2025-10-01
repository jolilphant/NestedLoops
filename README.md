# Looping Challenges (Combinations, Permutations, Grid)

---

## Challenge 1 — List all 2-combinations from {1..n}

### What is a Combination?  
A **combination** is a selection where **order does not matter**.  
For 2-combinations (pairs), `{2,5}` is the **same** as `{5,2}` — so we list it only once.  

Mathematically:  

$$
\binom{n}{2} = \frac{n(n-1)}{2}
$$

### Task
- Ask for an integer `n` (e.g., `n ≤ 30`).  
- Use **nested for loops** to print every unique pair `(i, j)` with `1 ≤ i < j ≤ n`.  
- Keep a running **counter** of pairs printed.  
- After printing, also show the **formula result** `n*(n-1)/2` and verify the counts match.  

### Hints
- The condition `i < j` ensures each pair is listed only once.  
- Use `long long` for counters if you like.  

---

## Challenge 2 — List all 3-permutations from {1..n} (order matters, no repeats)

### What is a Permutation?  
A **permutation** is an arrangement where **order matters**.  
For 3-permutations (ordered triples), `(2,5,7)` is **different** from `(5,2,7)` and `(7,5,2)`.  

Mathematically:  

$$
P(n,3) = n \times (n-1) \times (n-2)
$$

### Task
- Ask for an integer `n` (recommend `n ≤ 8` to keep output manageable).  
- Use **three nested for loops** over the range `1..n`.  
- Inside the innermost loop, require all indices to be **distinct**: `i != j`, `i != k`, `j != k`.  
- Print each ordered triple `(i, j, k)` and keep a **counter**.  
- After printing, also print the expected count `n*(n-1)*(n-2)` and verify the counts match.  

### Hints
- Must use **three nested loops** — no libraries.  
- Format your output so lines don’t wrap messily.  

---

## Challenge 3 — Grid of Ordered Pairs vs. Unique Combinations

### Goal  
Use a **grid** to visualize the difference between **ordered pairs** (permutations with replacement) and **unique combinations**.  

### Task
- Ask for an integer `n` (e.g., `n ≤ 12`).  
- Print an **n×n grid** with row index `i` and column index `j` (both from `1..n`).  
- In each cell, print one of these markers:  
  - `"D"` if `i == j` (diagonal),  
  - `"U"` if `i < j` (upper triangle → **unique combinations** region),  
  - `"L"` if `i > j` (lower triangle).  
- After printing the grid, also print these counts:  
  - Diagonal cells (`i == j`) → should be `n`  
  - Upper triangle (`i < j`) → $\tfrac{n(n-1)}{2}$  
  - Lower triangle (`i > j`) → $\tfrac{n(n-1)}{2}$  
  - All cells (`n \times n`) → ordered pairs with replacement  

### Requirements
- Use **two nested loops** (rows then columns).  
- Add **row/column headers** for readability.  

### Example Output (n = 4, D/U/L markers)
1  2  3  4
1 | D U U U
2 | L D U U
3 | L L D U
4 | L L L D

Diagonal (i == j): 4
Upper triangle (i < j): 6
Lower triangle (i > j): 6
Total cells (n * n): 16
Unique combinations (choose 2) = n*(n-1)/2 = 6
Ordered pairs (with replacement) = n*n = 16
