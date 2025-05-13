# Types of Errors: Round-off and Truncation Errors

In numerical analysis and computing, errors can occur during calculations due to the limitations of representing numbers and performing arithmetic operations. These errors can be categorized into two primary types: **round-off errors** and **truncation errors**.

## 1. **Round-off Errors**

### **Definition**:
Round-off errors arise when a number is approximated to a limited number of digits, as most computers cannot represent numbers with infinite precision.

### **Cause**:
This error occurs because floating-point numbers (the way computers represent real numbers) have limited precision. For example, when a number is too large or too small to be exactly represented, it is rounded to the nearest representable number.

### **Example**:
For instance, the number \( \frac{1}{3} \) in decimal is a repeating decimal:
