[[NumPy Arrays#What is NumPy?|What is NumPy?]]
# Math Operators and Functions

- ***arithmetic operator*** such as + - * / %
	- may have array operands
	- is applied to element pairs and returns an array
	- on list operands + implements concatenation, not addition
		- Ex: `[5, 5, 5] + [1, 2, 3]` returns `[5, 5, 5, 1, 2, 3]` rather than `[6, 7, 8]`
- ***simple function*** such as `sqrt()` and `log()`
	- may have an array argument
	- is applied to each element and returns an array
- ***aggregate function*** such as `min()`, `max()`, `median()`, and `var()`
	- returns one value for an entire array or array slice
	- many aggregate functions are statistical
		- Ex: `std(array)` returns the standard deviation of `array` elements
		- `var(array)` returns the variance of `array` elements
- ***matrix function*** interprets arrays as mathematical matrices and implements matrix algebra
	- Ex: `dot(array1, array2)` returns the dot product of `array1` and `array2`
	- `cross(array1, array2)` returns the cross product

![[Pasted image 20260904132143.png]]

# NumPy: Comparison Operators

## Core Behavior

- `==`, `!=`, `<`, `>`, `<=`, `>=` all work **element-wise** on ndarrays (they are ufuncs under the hood).
- Result is always a new **boolean array** (`dtype: bool`) — same shape as the input.
- Operands can be: array vs scalar, or array vs array.
- Array vs array compares element-by-element; shapes must match **or be broadcastable**.

```python
a = np.array([[1, 7], [3, 5]])
a > 3
# array([[False,  True],
#        [False,  True]])

x = np.array([1, 5, 3, 7])
y = np.array([2, 4, 3, 8])
x > y
# array([False,  True, False, False])
```

> [!warning] Shape mismatch
 Incompatible shapes raise `ValueError: operands could not be broadcast together` (e.g. `(4,)` vs `(3,)`).

## Operator ↔ Ufunc Equivalents

|Operator|Ufunc|
|---|---|
|`==`|`np.equal`|
|`!=`|`np.not_equal`|
|`<`|`np.less`|
|`<=`|`np.less_equal`|
|`>`|`np.greater`|
|`>=`|`np.greater_equal`|

## Boolean Indexing

- Passing a boolean array back into `[]` returns only the elements where the mask is `True`. Result comes back **1-D (flattened)**.

```python
a[a > 3]        # array([7, 5])
```

## Combining Conditions

- Use **bitwise** operators: `&` (AND), `|` (OR), `~` (NOT) — never `and` / `or` / `not`.
- Wrap **each condition in parentheses** (`&` binds tighter than `>`).

```python
b = np.array([1, 7, 3, 5])
b[(b > 2) & (b < 6)]    # array([3, 5])
```

> [!failure] Why `and` fails
Python keywords expect one True/False, but an array holds many → `ValueError: The truth value of an array with more than one element is ambiguous. Use a.any() or a.all()`.

## Whole-Array Tests

- `np.array_equal(a, b)` — one `True`/`False` for exact equality of two arrays
- `mask.any()` — at least one `True`
- `mask.all()` — every element `True`
- `np.count_nonzero(mask)` or `mask.sum()` — count matches (`True` = 1)