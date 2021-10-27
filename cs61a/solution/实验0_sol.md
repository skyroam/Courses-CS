### 解答

```python
def twenty_twenty_one():
    """Come up with the most creative expression that evaluates to 2021,
    using only numbers and the +, *, and - operators.

    >>> twenty_twenty_one()
    2021
    """
    return (1 + 10 ** (1 + 1)) * ((1 + 1) ** (1 + 1 + 1) + 1 + 1) * (1 + 1) + 1
```

