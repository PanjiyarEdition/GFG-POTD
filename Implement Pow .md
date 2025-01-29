# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Implement the function power(b, e), which calculates b raised to the power of e (i.e. be)


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public double power(double b, int e) {
        if (e == 0) return 1.0;
        double half = power(b, e / 2);
        return e % 2 == 0 ? half * half : (e > 0 ? b * half * half : (1.0 / b) * half * half);
    }
}

```

# C++
``` cpp []
class Solution {
public:
    double power(double b, int e) {
        if (e == 0) return 1.0;
        double half = power(b, e / 2);
        return e % 2 == 0 ? half * half : (e > 0 ? b * half * half : (1.0 / b) * half * half);
    }
};
```

# Python
``` python []
class Solution:
    def power(self, b: float, e: int) -> float:
        result = 1.0
        exp = abs(e)
        while exp > 0:
            if exp % 2 == 1:
                result *= b
            b *= b
            exp //= 2
        return result if e >= 0 else 1.0 / result   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
