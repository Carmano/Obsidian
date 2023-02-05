
``` python
from turtle import *  
import colorsys  
  
tracer(50)  
bgcolor('black')  
pensize(4)  
h = 0.4  
for i in range(1000):  
    c = colorsys.hsv_to_rgb(h, 1, 1)  
    color(c)  
    h += 0.005  
    circle(i, -120)  
    left(330)  
    forward(i * 4)  
done()
```