
``` python
def _reduce_fraction(num, den):  
    return num // math.gcd(num, den), den // math.gcd(num, den)
```