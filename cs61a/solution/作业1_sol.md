### 问题2

```python
def a_plus_abs_b(a, b):
    """Return a+abs(b), but without calling abs.

    >>> a_plus_abs_b(2, 3)
    5
    >>> a_plus_abs_b(2, -3)
    5
    """
    if b < 0:
        f = sub
    else:
        f = add
    return f(a, b)
```

如果`b`是正数，我们将数字相加。如果`b`是负数，我们减去数字。因此，我们基于`b`的符号选择运算符`add`或`sub` 。

### 问题3

```python
def two_of_three(x, y, z):
    """Return a*a + b*b, where a and b are the two smallest members of the
    positive numbers x, y, and z.

    >>> two_of_three(1, 2, 3)
    5
    >>> two_of_three(5, 3, 1)
    10
    >>> two_of_three(10, 2, 8)
    68
    >>> two_of_three(5, 5, 5)
    50
    """
    return min(x*x+y*y, x*x+z*z, y*y+z*z)
    # Alternate solution
def two_of_three_alternate(x, y, z):
    return x**2 + y**2 + z**2 - max(x, y, z)**2
```

我们使用的事实是，如果`x>y`且`y>0`，则`square(x)>square(y)`。所以，我们可以用`min`取所有对的平方和的最小值。`min`函数可以接受任意数量的参数。

或者，我们可以计算所有数字的平方和。然后我们挑出最大的数字，然后减去它的平方。

### 问题4

```python
def largest_factor(n):
    """Return the largest factor of n that is smaller than n.

    >>> largest_factor(15) # factors are 1, 3, 5
    5
    >>> largest_factor(80) # factors are 1, 2, 4, 5, 8, 10, 16, 20, 40
    40
    >>> largest_factor(13) # factor is 1 since 13 is prime
    1
    """
    factor = n - 1
    while factor > 0:
        if n % factor == 0:
            return factor
        factor -= 1
```

从`n-1`到 1 进行迭代，我们返回第一个整除`n`的整数。这能保证是`n`的最大因数。

### 问题5

```python
def limited(x, z, limit):
    """Logic that is common to invert and change."""
    if x != 0:
        return min(z / x, limit)
    else:
        return limit

def invert_short(x, limit):
    """Return 1/x, but with a limit.

    >>> x = 0.2
    >>> 1/x
    5.0
    >>> invert_short(x, 100)
    5.0
    >>> invert_short(x, 2)    # 2 is smaller than 5
    2

    >>> x = 0
    >>> invert_short(x, 100)  # No error, even though 1/x divides by 0!
    100
    """
    return limited(x, 1, limit)

def change_short(x, y, limit):
    """Return abs(y - x) as a fraction of x, but with a limit.

    >>> x, y = 2, 5
    >>> abs(y - x) / x
    1.5
    >>> change_short(x, y, 100)
    1.5
    >>> change_short(x, y, 1)    # 1 is smaller than 1.5
    1

    >>> x = 0
    >>> change_short(x, y, 100)  # No error, even though abs(y - x) / x divides by 0!
    100
    """
    return limited(x, abs(y - x), limit)
```

在最初的`invert_short`和`change_short`中，我们将首先求值`limited`函数调用的参数，它在`limited`被调用之前产生了`ZeroDivisionError`错误。

因此，我们希望推迟对除法的求值，使其发生在`limited`的`if`语句中，观察除以`x`是`invert_short`和`change_short`之间的另一个共同逻辑。

我们现在可以更新`invert_short`，`change_short`使它们只传入表达式的分子，因为分母是公共表达式 `x`，现在抽象进`limited`。没有`ZeroDivisionError`了！

### 问题6

```python
def hailstone(n):
    """Print the hailstone sequence starting at n and return its
    length.

    >>> a = hailstone(10)
    10
    5
    16
    8
    4
    2
    1
    >>> a
    7
    """
    length = 1
    while n != 1:
        print(n)
        if n % 2 == 0:
            n = n // 2      # Integer division prevents "1.0" output
        else:
            n = 3 * n + 1
        length = length + 1
    print(n)                # n is now 1
    return length
```

我们保持跟踪冰雹序列的当前长度和当前值。从那里，我们循环直到到达序列的末尾，每一步更新序列的长度。

> 注意：我们需要做向下取整除法`//`来去除小数部分。

### 问题7

```python
q='q=%r;print (q%%q)';print (q%q)
```

[参考](https://stackoverflow.com/questions/55430197/python-3s-shortest-quine-i-dont-get-it)