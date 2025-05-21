# 📐 Trapezoidal Rule – Numerical Integration

## 🧮 What is the Trapezoidal Rule?

The **Trapezoidal Rule** is a numerical method to estimate the **definite integral** of a function `f(x)` over an interval `[a, b]`.  
It approximates the area under the curve using **trapezoids** instead of rectangles.

---

## 🔢 Formula (Single Interval)

<pre> ∫ᵃᵇ f(x) dx ≈ (b - a)/2 × [f(a) + f(b)] </pre>
---

## 🧠 Composite Trapezoidal Rule (Multiple Intervals)

Divide `[a, b]` into `n` equal subintervals of width:

\[
h = \frac{b - a}{n}
\]

Then the approximation becomes:

$$
\int_a^b f(x) \, dx \approx \frac{h}{2} \left[ f(x_0) + 2 \sum_{i=1}^{n-1} f(x_i) + f(x_n) \right]
$$


Where:
- \( x_0 = a \), \( x_n = b \)  
- \( x_i = a + i \cdot h \) for \( i = 1, 2, \ldots, n-1 \)


---

## 📊 Example: ∫₀¹ x² dx using n = 4

Let \( f(x) = x^2 \), \( a = 0 \), \( b = 1 \), and \( n = 4 \)

### Step-by-step:

- \( h = (1 - 0)/4 = 0.25 \)
- \( x_i = 0, 0.25, 0.5, 0.75, 1 \)
- \( f(x_i) = 0, 0.0625, 0.25, 0.5625, 1 \)

$$
\int_0^1 x^2 \, dx \approx \frac{0.25}{2} \left[ 0 + 2(0.0625 + 0.25 + 0.5625) + 1 \right] = 0.34375
$$


### ✅ Exact value:

<pre> ∫₀¹ x² dx = 1/3 ≈ 0.3333 </pre>
---

## 📈 Visualization (Python Code)

```python
import numpy as np
import matplotlib.pyplot as plt

def f(x):
    return x**2

a, b = 0, 1
n = 4
x = np.linspace(a, b, 100)
y = f(x)

x_points = np.linspace(a, b, n+1)
y_points = f(x_points)

plt.figure(figsize=(10, 6))
plt.plot(x, y, 'b', label='$f(x) = x^2$', linewidth=2)
plt.plot(x_points, y_points, 'ro', label='Sample points')

for i in range(n):
    xs = [x_points[i], x_points[i], x_points[i+1], x_points[i+1]]
    ys = [0, y_points[i], y_points[i+1], 0]
    plt.fill(xs, ys, 'skyblue', edgecolor='black', alpha=0.5)

plt.title("Trapezoidal Rule Approximation of $\\int_0^1 x^2 dx$")
plt.xlabel("x")
plt.ylabel("f(x)")
plt.legend()
plt.grid(True)
plt.show()
