### 11. En este problema vamos a investigar la estadistica t para la hipotesis nula ![equation](http://latex.codecogs.com/gif.latex?Concentration%3D%5Cfrac%7BTotalTemplate%7D%7BTotalVolume%7D)
---
generamos un predictor X y la respuesta de Y como;
```r
set.seed(1)
x = rnorm(100)
y = 2*x + rnorm(100)
``` 
a) realizar una regresión lineal de y sobre x Informe el coeficiente estimado $\beta$, el error estándar deeste coeficiente, el estadístico t y el valor p asociado con la hipótesis nula ![equation](http://latex.codecogs.com/gif.latex?Concentration%3D%5Cfrac%7BTotalTemplate%7D%7BTotalVolume%7D)
