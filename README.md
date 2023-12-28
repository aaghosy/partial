# partial
在Python中，偏函数（Partial Function）是一种从现有函数衍生出来的新函数，它允许你固定某些参数的值，并生成一个新的函数。这是通过使用`functools`模块中的`partial`函数实现的。偏函数对于简化函数调用，或者当你需要传递给其他函数一个特定参数集的函数时非常有用。

### 基本原理

- 通过偏函数，你可以固定一个函数的一个或多个参数，从而创建一个新的函数。
- 这对于减少代码重复和提高代码的可读性非常有帮助。

### 示例代码

假设我们有一个简单的乘法函数，我们想要创建一个新的函数，它总是将第一个参数固定为2：

```python
from functools import partial

# 原始函数
def multiply(x, y):
    return x * y

# 创建一个偏函数，固定第一个参数为2
double = partial(multiply, 2)

# 使用偏函数
result = double(4)  # 相当于 multiply(2, 4)
print(result)  # 输出 8
```

在这个例子中：
- `multiply`是一个接受两个参数的普通乘法函数。
- 使用`partial(multiply, 2)`，我们创建了一个新的偏函数`double`，它固定了`multiply`函数的第一个参数为2。
- 现在，当我们调用`double(4)`时，实际上是在调用`multiply(2, 4)`。

偏函数非常适合用于那些有着共同参数的函数调用场景，它可以减少重复代码并提高代码的清晰度。
