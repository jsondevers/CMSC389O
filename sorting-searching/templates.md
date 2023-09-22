# Template Code for sorting & searching

## Searching

### Binary Search

#### Midpoint Calculation

Note there are many ways to calculate the middle index. Here are a few ways:

```cpp
mid = (left + right) // 2 # take the floor
mid = left + (right - left) // 2 # this handles integer overflow (some languages)
mid = (left + right) >> 1 # bit shift / chad way
```

#### Templates

#### General Binary Search

- `T` is a target value
- `arr` is a sorted array

```cpp
func binarySearch(arr):
    left = 0, right = size(arr) - 1

    while (left <= right):
        mid = left + (right - left) / 2
        if (check(arr[mid]) == true):
            return mid
        else if (check(arr[mid]) == false):
            left = mid + 1
        else:
            right = mid - 1



#### Binary Search left-most

```cpp
func binarySearch(arr, T):
    left = 0, right = size(arr) - 1

    while (left < right):
        mid = left + (right - left) / 2
        if (arr[mid] < T):
            left = mid + 1
        else:
            right = mid

    return left # left is the leftmost index if T is not found but where T should be
```

#### Binary Search right-most

```cpp
func binarySearch(arr, T):
    left = 0, right = size(arr) - 1

    while (left < right):
        mid = left + (right - left + 1) / 2
        if (arr[mid] > T):
            right = mid - 1
        else:
            left = mid

    return left # left is the rightmost index if T is not found but where T should be
```

Example:

| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| ----- | - | - | - | - | - | - | - |
| Value | 1 | 2 | 2 | 2 | 3 | 3 | 4 |

- For a **left-most** binary search, the algorithm will return `1`
- For a **right-most** binary search, the algorithm will return `3`

Note that we're not always searching for an element `T`, so an even more general template would be:

```cpp
func binarySearch(arr):
    left = 0, right = size(arr) - 1

    while (left < right):
        mid = left + (right - left) / 2
        if (check(arr[mid]) == true):
            right = mid
        else:
            left = mid + 1

    return left

bool check(int x):
    return condition 
```
