# Fibonacci

## Recurrence Relation

The Fibonacci sequence is defined by the recurrence relation:

$$F_n = F_{n-1} + F_{n-2}$$

More formally, $$F(n) = \left\{
\begin{array}{ll}
 0 & \text{$n = 0$} \\
 1 & \text{$n = 1$} \\
    F(n-1) + F(n-2) & \text{$n > 1$}
\end{array}
\right.$$

```python
def fib(n):
    if n < 2:
        return n
    else:
        return fib(n-1) + fib(n-2)
```

Time: $O(2^n)$, gross!

Space: $O(n)$

## Memoization

We can store and reuse previously computed values to reduce the running time.

```python
def fib(n, memo):
    if n < 2:
        return n
    if n in memo:
        return memo[n]
    
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
```

Our `memo` is a dictionary that maps from `n` to $F(n)$.

Time: $O(n)$ I guess maybe $O(n^2)$ because of the dictionary lookup? But, we could have also used a an array and guaranteed $O(n)$.

```python
memo = [-1] * (n+1)

def fib(n, memo):
    if n < 2:
        return n
    if memo[n] != -1:
        return memo[n]
    
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
```

Time: $O(n)$

Space: $O(n)$
