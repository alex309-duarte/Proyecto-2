### 11. En este problema vamos a investigar la estadistica t para la hipotesis nula Ho : β = 0
---
generamos un predictor X y la respuesta de Y como;
```r
set.seed(1)
x = rnorm(100)
y = 2*x + rnorm(100)
``` 
a) realizar una regresión lineal de y sobre x Informe el coeficiente estimado β, el error estándar deeste coeficiente, el estadístico t y el valor p asociado con la hipótesis nula Ho : β = 0
