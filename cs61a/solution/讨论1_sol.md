### 问题1

```python
def wears_jacket_with_if(temp, raining):
    """
    >>> wears_jacket_with_if(90, False)
    False
    >>> wears_jacket_with_if(40, False)
    True
    >>> wears_jacket_with_if(100, True)
    True
    """
    "*** YOUR CODE HERE ***"
    if raining or temp < 60:
        return True
    else:
        return False
```

```python
def wears_jacket(temp, raining):
    "*** YOUR CODE HERE ***"
    return raining or temp < 60
```

### 问题2

对`special_case`和`case_in_point`的调用都返回 12，而对`just_in_case`的调用返回 19。由于数字 10 满足每个函数中的全部三个条件，因此在`just_in_case`调用时`x`变量的值增加了 3 次。如果每个`if`子句都以一个`return`语句结尾， 则一系列`if`语句与使用`if`和`elif`组合具有相同的效果。

### 问题3

```python
def with_if_statement():
    """
    >>> result = with_if_statement()
    61A
    >>> print(result)
    None
    """
    if cond():
        return true_func()
    else:
        return false_func()

def with_if_function():
    """
    >>> result = with_if_function()
    Welcome to
    61A
    >>> print(result)
    None
    """
    return if_function(cond(), true_func(), false_func())

def cond():
    "*** YOUR CODE HERE ***"
	return False
def true_func():
    "*** YOUR CODE HERE ***"
	print("Welcome to")
def false_func():
    "*** YOUR CODE HERE ***"
	print("61A")
```

函数`with_if_function`使用了一个调用表达式，它保证先将其所有操作数子表达式求值，然后再将结果作为参数应用于`if_function`。

因此，即使`cond`返回`False`，函数`true_func`也会被调用。当我们调用时`true_func`，我们打印出`Welcome to`。然后，当我们调用`false_func`时，我们也会打印`61A`。

相比之下，如果 `cond`返回`False`，`with_if_statement`永远不会调用`true_func`。因此，我们只会调用`false_func`打印`61A`。

### 问题4

这个程序会导致无限循环，因为`x`总是大于 0，而`x / 0`永远不会被执行。我们也知道`here!`永远不会打印，因为在调用`function square(x)`之前必须求值操作数`so_slow(5)`。

[视频](https://www.youtube.com/watch?v=Fiw0f5yuQgo&vq=hd1080&t=39m34s)

### 问题5

```python
def is_prime(n):
    """
    >>> is_prime(10)
    False
    >>> is_prime(7)
    True
    """
    "*** YOUR CODE HERE ***"
    if n == 1:
        return True
    else:
        for i in range(2, n):
            if n % i == 0:
                return False
        return True
```

### 问题6

```python
def fizzbuzz(n):
    """
    >>> result = fizzbuzz(16)
    1
    2
    fizz
    4
    buzz
    fizz
    7
    8
    fizz
    buzz
    11
    fizz
    13
    14
    fizzbuzz
    16
    >>> result == None
    True
    """
    "*** YOUR CODE HERE ***"
    for i in range(1, n+1):
        if i % 3 == 0 and i % 5 == 0:
            print('fizzbuzz')
        elif i % 3 == 0:
            print('fizz')
        elif i % 5 == 0:
            print('buzz')
        else:
            print(i)
```

要为从 1 到`n`的每个数字打印一些内容，我们可以使用循环遍历每个数字，然后使用`if-elif-else`检查哪些情况适用以确定要打印的内容。

学生应该注意他们`if-elif`语句的顺序：我们要首先检查是否`i`可以被 3 和 5 整除，否则如果学生首先检查了 3 的可除性就会输出“fizz”（如果学生首先检查了 5 的可除性则是“buzz”），而不是“fizzbuzz”。

### 问题7

<iframe width="800" height="320" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=x+%3D+11+%25+4%0Ay+%3D+x%0Ax+%2A%2A%3D+2%0A&amp;codeDivHeight=320&amp;codeDivWidth=350&amp;cumulative=true&amp;curInstr=1&amp;heapPrimitives=nevernest&amp;origin=composingprograms.js&amp;py=3&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false" style="box-sizing: border-box;"></iframe>

<iframe width="800" height="320" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=x+%3D+11+%25+4%0Ay+%3D+x%0Ax+%2A%2A%3D+2%0A&amp;codeDivHeight=320&amp;codeDivWidth=350&amp;cumulative=true&amp;curInstr=1&amp;heapPrimitives=nevernest&amp;origin=composingprograms.js&amp;py=3&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false" style="box-sizing: border-box;"></iframe>

我们首先把`11 % 4`求值的结果赋值给`x`。然后我们绑定`y`到`x`的当前值（我们可以通过在当前环境图中查找它来确定）。最后，我们想更新`x`为当前`x`的值的平方。

[视频](https://www.youtube.com/watch?v=m-m8Yp1uwlg)

### 问题8

<iframe width="800" height="400" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=def+double%28x%29%3A%0A++++return+x+%2A+2%0A%0Adef+triple%28x%29%3A%0A++++return+x+%2A+3%0A%0Ahat+%3D+double%0Adouble+%3D+triple%0A&amp;codeDivHeight=379&amp;codeDivWidth=350&amp;cumulative=true&amp;curInstr=1&amp;heapPrimitives=nevernest&amp;origin=composingprograms.js&amp;py=3&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false" style="box-sizing: border-box;"></iframe>

我们首先定义两个函数`double`和`triple`，每个函数都绑定到它们对应的名称。在下一行中，我们将名称`hat`赋给`double`引用的函数对象。最后，我们将`double`名称赋给`triple`引用的函数对象。

[视频](https://youtu.be/EuygSqH8nTk)

### 问题9

<iframe width="800" height="578" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=def+double%28x%29%3A%0A++++return+x+%2A+2%0A%0Ahmmm+%3D+double%0Awow+%3D+double%283%29%0Ahmmm%28wow%29%0A&amp;codeDivHeight=578&amp;codeDivWidth=350&amp;cumulative=true&amp;curInstr=1&amp;heapPrimitives=nevernest&amp;origin=composingprograms.js&amp;py=3&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false" style="box-sizing: border-box;"></iframe>

[视频](https://youtu.be/kmspUmcd6RI)

### 问题10

<iframe width="800" height="802" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=def+f%28x%29%3A%0A++++return+x%0A%0Adef+g%28x%2C+y%29%3A%0A++++if+x%28y%29%3A%0A++++++++return+not+y%0A++++return+y%0A%0Ax+%3D+3%0Ax+%3D+g%28f%2C+x%29%0Af+%3D+g%28f%2C+0%29%0A&amp;codeDivHeight=802&amp;codeDivWidth=350&amp;cumulative=true&amp;curInstr=1&amp;heapPrimitives=nevernest&amp;origin=composingprograms.js&amp;py=3&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false" style="box-sizing: border-box;"></iframe>

[视频](https://youtu.be/zVThisRzK7A)