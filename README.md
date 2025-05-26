```python
def f(x):
    return x**3 - x - 2

def f1(x):
    return 3 * x**2 - 1

xo = float(input("Enter the initial approximation: "))

for i in range(1, 10):
    xn = xo - f(xo) / f1(xo)
    xo = xn

print("The approximate root using Newton-Raphson method is %.4f" % xn)
```

# 2 gauss

```python
x0 = 0
y0 = 0
z0 = 0

for i in range(1, 10):
    x = 1/4 * (1 - y0 - z0)
    x0 = x
    y = 1/3 * (2 - x0 - z0)
    y0 = y
    z = 1/5 * (3 - x0 - y0)
    z0 = z

print("The approximate solution of x = %.4f, y = %.4f, z = %.4f" % (x, y, z))
```

# 3 Lagrange
```python
x = [0, 1, 2, 4, 5, 6]
y = [1, 14, 15, 5, 6, 19]
s = float(input("Enter the value of x to be interpolated: "))

sum = 0
for i in range(0, 6):
    prod = 1
    for j in range(0, 6):
        if i != j:
            prod = prod * (s - x[j]) / (x[i] - x[j])
    sum = sum + prod * y[i]

print("The functional value is %.4f" % sum)
```
