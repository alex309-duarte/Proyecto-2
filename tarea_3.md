#### Samuel Romero Santiago
#### Manuel Alejandro Cardoso Duarte

﻿# Ejercicios-Capitulo 3
### 1. Describe the null hypotheses to which the p-values given in Table 3.4 correspond. Explain what conclusions you can draw based on these p-values. Your explanation should be phrased in terms of sales, TV, radio, and newspaper, rather than in terms of the coefficients of the linear model. 
---
                     
**R**: La hipótesis             nula relacionada a la tabla 3.4 se refiere a que los predictores "TV", "radio" y "newspapers" no tienen efecto alguno en las ventas totales. Podemos observar que los  p-valores de TV y radio, sugieren que la hipótesis nula es falsa para estos predictores, sin embargo, dado que el p-valor de newspaper es alto, podemos inferir que se cumple la hipótesis nula para este predictor.

### 2. Carefully explain the differences between the KNN classifier and KNN regression methods.
---

**R:** El clasificador KNN sirve más para resolver problemas en los que existen variables cualitativas, aquellas cuyos valores son discretos. Por su parte la regresión KNN sirve para los problemas con variables cualitativas, en donde los valores son continuos, además se predice una respuesta cualitativa de la función F(x).

### 3. Suppose we have a data set with five predictors, X1 =GPA, X2 = IQ, X3 = Gender (1 for Female and 0 forMale), X4 = Interaction between GPA and IQ, and X5 = Interaction between GPA and Gender. The response is starting salary after graduation (in thousands of dollars). Suppose we use least squares to fit the model, and get β0 = 50, β1 = 20, β2 = 0.07, β3 = 35, β4 = 0.01, β5 = −10.
---

**R:** 
**a)** Tenemos la función predictora. 

y=50+20(GPA)+0.07(IQ)+35(Gender)+0.01(GPA×IQ)−10(GPA×Gender)

Sabemos que en el género Hombre=0 y Mujer=1. Por lo que lo que tenemos para mujer:

y=50+20(GPA)+0.07(IQ)+35(1)+0.01(GPA×IQ)−10(GPA×1)
 
Resultando:

y=85+10(GPA)+0.07(IQ)+0.01(GPA×IQ)

Por su parte, para hombres tenemos:

y=50+20(GPA)+0.07(IQ)+35(0)+0.01(GPA×IQ)−10(GPA×0)

Entonces:

y=50+20(GPA)+0.07(IQ)+0.01(GPA×IQ)

Por lo que podemos observar que las mujeres tienen un salario inicial mayo, pero mientras más imcrementa GPA el promedio de salario se mantiene mayor en hombres. Por lo que la respuesta correcta es la III: Para valores fijos de IQ y GPA, los hombres ganan en promedio más que las mujeres, siempre que GPA sea lo suficientemente grande.

**b)** Predict the salary of a female with IQ of 110 and a GPA of 4.0.

**R:** Sabemos que el salario de una mujer está dado está dado por: 

y=85+10(GPA)+0.07(IQ)+0.01(GPA×IQ)

Sustituimos los valores de IQ y GPA:

y=85+10(4)+0.07(110)+0.01(4×110)

y=137.1

Somo este valor está dado en miles de dolares, podemos estimar un salario de $137100

**c)** True or false: Since the coefficient for the GPA/IQ interaction term is very small, there is very little evidence of an interaction effect. Justify your answer.

**R:** Falso: Para determinar si existe una verdadera relación se utilizan herramientas como los p-valores, la estadística t y la R²

### 4. I collect a set of data (n=100 observations) containing a single predictor and a quantitative response. I then fit a linear regression model to the data, as well as a separate cubic regression, i.e. Y=β0+β1X+β2X2+β3X3+ε
---


a) Suppose that the true relationship between X and Y is linear, i.e. Y=β0+β1X+ε. Consider the training residual sum of squares (RSS) for the linear regression, and also the training RSS for the cubic regression. Would we expect one to be lower than the other, would we expect them to be the same, or is there not enough information to tell? Justify your answer.

**R:** Dado que se especifíca que Y y X tienen una relación lineal podriamos inferir que la RSS para el modelo lineal será menor que la de la regresión cúbica para los datos de entrenamiento. 

b) Answer (a) using test rather than training RSS.

**R:** Se esperaría que la regresión multivariable tuviera un menos RSS ya que el modelo lineal simple puede crear un overfitting haciendo que su evaluación en los datos test genere un mayor RSS.

(c)  Suppose that the true relationship between X and Y is not linear,
but we don’t know how far it is from linear. Consider the training
RSS for the linear regression, and also the training RSS for the
cubic regression. Would we expect one to be lower than the
other, would we expect them to be the same, or is there not
enough information to tell? Justify your answer.

**R:** No hay suficiente información para contestar esta pregunta, se necesitarían mínimamente los RSS. Podríamos decir que la regresión multivariable tendría tal vez  mayor RSS debido a su flexibilidad sobre los datos de entrenamiento, por lo que sería mejor el modelo lineal, sin embargo, la información no es suficiente.

d) Answer (c) using test rather than training RSS.

**R:** No hay suficiente información para saber que RSS es mejor o peor, debido a que no sabemos que tan lejos están los modelos del modelo lineal, entonces teniendo el conjunto de prueba el RSS del modelo lineal podría ser mejor o peor, pero no es claro.

### 5.  Consider the fitted values that result from performing linear regression without an intercept. In this setting, the i-th fitted value takes the form yi=xiβ.
---

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/2020-03-27_21-49-32.png)

y

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_21-49-51.png)

¿Qué es ai'?
**R:**
Haciendo un poco de álgebra podemos obtener: 
![2020-03-27_21-49-09](2020-03-27_21-49-09.png)

6. Using (3.4), argue that in the case of simple linear regression, the
least squares line always passes through the point (x1, y1).

La línea de mínimos cuadrados está dada por: 
    y=β0+β1X
Haciendo álgebra podemos decir que:
y=β0+β1(x)=y1−β1(x1)+β1(x1)=y1
Entonces podemos concluir que la linea de mínimos cuadrados si pasa por el punto (x1,y1).

7.   It is claimed in the text that in the case of simple linear regression of Y onto X, the R2 statistic (3.17) is equal to the square of the correlation between X and Y (3.18). Prove that this is the case. For simplicity, you may assume that x=y=0.

**R:** Sabemos que:
![2020-03-27_22-18-16](2020-03-27_22-18-16.png)
y que:
![2020-03-27_22-22-04](2020-03-27_22-22-04.png)

Por lo que podemos reescribir R cuadrada como (sustituyendo Y gorro): 
![2020-03-27_22-30-06](2020-03-27_22-30-06.png)
Haciendo álgebra (convirtiendo el 1 en términos similares):
![2020-03-27_23-02-26](2020-03-27_23-02-26.png)
 Simplificando:
![2020-03-27_23-08-32](2020-03-27_23-08-32.png)

Sabemos que la correlación al cuadrado de X y Y está dada por:
![2020-03-27_23-09-14](2020-03-27_23-09-14.png)

Por lo que:
![2020-03-27_23-10-00](2020-03-27_23-10-00.png)

```R Script
setwd('6to Semestre')
setwd('Temas Selectos de Matemáticas')
setwd('ISLR-master')##ENtro a ubicaición
getwd()
auto=read.csv("Auto.csv", na.strings = "?")
attach(auto)
fit1=lm(mpg~horsepower)
summary(fit1)
```
~~~
Call:
lm(formula = mpg ~ horsepower)

Residuals:
     Min       1Q   Median       3Q      Max 
-13.5710  -3.2592  -0.3435   2.7630  16.9240 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept) 39.935861   0.717499   55.66   <2e-16 ***
horsepower  -0.157845   0.006446  -24.49   <2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 4.906 on 390 degrees of freedom
  (5 observations deleted due to missingness)
Multiple R-squared:  0.6059,    Adjusted R-squared:  0.6049 
F-statistic: 599.7 on 1 and 390 DF,  p-value: < 2.2e-16
~~~
i) Basandonos en los p-valores podemos decir que sí hay relación entre la respuesta y el predictor.

ii) La R cuadrada nos indica que se pueden predecir el 60.9% de los datos de mpg usando el predictor horsepower. Es una relación fuerte.

iii) Como el coeficiente de horsepower es negativo (-0.157845) podemos decir que la relación entre la respuesta  y el predictor es negativa. 

iv) 
Intervalos de confianza
```r
predict(fit, data.frame(horsepower = 98), interval = "confidence")
```
~~~
       fit      lwr      upr
1 24.46708 23.97308 24.96108
~~~
Predicción.
```r
predict(fit, data.frame(horsepower = 98), interval = "prediction")
```
~~~
       fit     lwr      upr
1 24.46708 14.8094 34.12476
~~~

b) 
```r
plot(auto$horsepower, auto$mpg, xlab = "horsepower", ylab = "mpg", col = "blue")

abline(fit1, col = "red")
```

![Rplot](Rplot.png)

c)
```r
par(mfrow = c(2, 2))

plot(fit1)
```
![Rplot01](Rplot01.png)

En la grafica de residuales contra datos ajustados podemos observar que no hay una relación totalmente lineal. En la gráfica de residuals vs promedio, podemos observar que hay algunos puntos muy alejados, que pueden generar un mayor error en nuestra predicción.

9. This question involves the use of multiple linear regression on the Auto data set.
a)
```R Script
pairs(auto)
```
![Rplot02](Rplot02.png)

b) 
```R Script
cor(auto[1:8])
```
~~~
                    mpg  cylinders displacement horsepower     weight acceleration       year
mpg           1.0000000 -0.7762599   -0.8044430         NA -0.8317389    0.4222974  0.5814695
cylinders    -0.7762599  1.0000000    0.9509199         NA  0.8970169   -0.5040606 -0.3467172
displacement -0.8044430  0.9509199    1.0000000         NA  0.9331044   -0.5441618 -0.3698041
horsepower           NA         NA           NA          1         NA           NA         NA
weight       -0.8317389  0.8970169    0.9331044         NA  1.0000000   -0.4195023 -0.3079004
acceleration  0.4222974 -0.5040606   -0.5441618         NA -0.4195023    1.0000000  0.2829009
year          0.5814695 -0.3467172   -0.3698041         NA -0.3079004    0.2829009  1.0000000
origin        0.5636979 -0.5649716   -0.6106643         NA -0.5812652    0.2100836  0.1843141
                 origin
mpg           0.5636979
cylinders    -0.5649716
displacement -0.6106643
horsepower           NA
weight       -0.5812652
acceleration  0.2100836
year          0.1843141
origin        1.0000000
~~~

c) 
```R Script
fit.multi = lm(mpg ~ . - name, data = auto)
summary(fit.multi)
```
~~~


Call:
lm(formula = mpg ~ . - name, data = auto)

Residuals:
    Min      1Q  Median      3Q     Max 
-9.5903 -2.1565 -0.1169  1.8690 13.0604 

Coefficients:
               Estimate Std. Error t value Pr(>|t|)    
(Intercept)  -17.218435   4.644294  -3.707  0.00024 ***
cylinders     -0.493376   0.323282  -1.526  0.12780    
displacement   0.019896   0.007515   2.647  0.00844 ** 
horsepower    -0.016951   0.013787  -1.230  0.21963    
weight        -0.006474   0.000652  -9.929  < 2e-16 ***
acceleration   0.080576   0.098845   0.815  0.41548    
year           0.750773   0.050973  14.729  < 2e-16 ***
origin         1.426141   0.278136   5.127 4.67e-07 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 3.328 on 384 degrees of freedom
  (5 observations deleted due to missingness)
Multiple R-squared:  0.8215,    Adjusted R-squared:  0.8182 
F-statistic: 252.4 on 7 and 384 DF,  p-value: < 2.2e-16
~~~

i) Si existe una relación de mpg con los demás predictores, según el valor de R cuadrada podemos predecir el 82% de los datos de mpg con los demás predictores, sin embargo hay unos más significativos que otros.

ii)
displacement, weight, year y origin. 

iii) nos indica que entre más reciente sea el año, más millas podrá recorrer el vehículo, en específico, con una realación de 0.750773.

d) 
```R Script
plot(fit.multi
```
![Rplot03](Rplot03.png)

Si tenemos algunos outlayers y podemos observar que de igual forma no existe una relación totalmente lineal. 

e) 
Para realizar el ajuste se utilizan los predictores con más correlación. 

```R Script
fit.multi2 = lm(mpg~cylinders*displacement+displacement*weight)
summary(fit.multi2)
```

~~~
Call:
lm(formula = mpg ~ cylinders * displacement + displacement * 
    weight)

Residuals:
     Min       1Q   Median       3Q      Max 
-13.3564  -2.4882  -0.3635   1.8469  17.8176 

Coefficients:
                         Estimate Std. Error t value Pr(>|t|)    
(Intercept)             5.285e+01  2.233e+00  23.673  < 2e-16 ***
cylinders               7.580e-01  7.645e-01   0.992    0.322    
displacement           -7.514e-02  1.669e-02  -4.502 8.90e-06 ***
weight                 -9.931e-03  1.323e-03  -7.505 4.19e-13 ***
cylinders:displacement -2.893e-03  3.424e-03  -0.845    0.399    
displacement:weight     2.147e-05  4.996e-06   4.298 2.18e-05 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 4.115 on 391 degrees of freedom
Multiple R-squared:  0.7269,    Adjusted R-squared:  0.7234 
F-statistic: 208.2 on 5 and 391 DF,  p-value: < 2.2e-16
~~~

Los significativos son la relación entre displacement, weight.

f) Se probó con el siguiente modelo.

```R Script 
fit.multi3 = lm(mpg~sqrt(weight)+log(horsepower)+acceleration*acceleration+origin+cylinders*cylinders)
```
~~~
Call:
lm(formula = mpg ~ sqrt(weight) + log(horsepower) + acceleration * 
    acceleration + origin + cylinders * cylinders)

Residuals:
     Min       1Q   Median       3Q      Max 
-11.8957  -2.6875  -0.0547   2.0362  14.3751 

Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)     103.05354    7.42772  13.874  < 2e-16 ***
sqrt(weight)     -0.29964    0.08564  -3.499 0.000522 ***
log(horsepower) -12.73109    1.91469  -6.649 1.01e-10 ***
acceleration     -0.38157    0.12738  -2.996 0.002916 ** 
origin            1.21065    0.31294   3.869 0.000128 ***
cylinders        -0.18054    0.27805  -0.649 0.516528    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 3.933 on 386 degrees of freedom
  (5 observations deleted due to missingness)
Multiple R-squared:  0.7493,    Adjusted R-squared:  0.746 
F-statistic: 230.7 on 5 and 386 DF,  p-value: < 2.2e-16
~~~

Se observa un incremento en la significancia de las variables (ahora todas son significativas con excepción de cylinders) sin embargo la R cuadrado bajó. Lo que indica que podemos predecir menos datos. 

![Rplot04](Rplot04.png)

Observando las gráficas de residuales podemos decir que el modelo no es mucho mejor al lineal. 

10. This question should be answered using the Carseats data set. 
a) 
```R Script
library(ISLR)
fix(Carseats)
cars<-Carseats
cars
fix(cars)
attach(cars)
fit.cars = lm(Sales~Price+Urban+US)
summary(fit.cars)
```
~~~
Call:
lm(formula = Sales ~ Price + Urban + US)

Residuals:
    Min      1Q  Median      3Q     Max 
-6.9206 -1.6220 -0.0564  1.5786  7.0581 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept) 13.043469   0.651012  20.036  < 2e-16 ***
Price       -0.054459   0.005242 -10.389  < 2e-16 ***
UrbanYes    -0.021916   0.271650  -0.081    0.936    
USYes        1.200573   0.259042   4.635 4.86e-06 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 2.472 on 396 degrees of freedom
Multiple R-squared:  0.2393,    Adjusted R-squared:  0.2335 
F-statistic: 41.52 on 3 and 396 DF,  p-value: < 2.2e-16
~~~

b) 
Price: Nos indica (gracias a su p-valor) que existe una relación entre este predictor y las ventas. 
Urban: El p-valor nos indica que no hay relación entre si esta en zona urbana o no, y las ventas totales.
USYes: Nos indica que si existe una relación entre si la tienda está en los Estados Unidos o no, si lo está, las ventas se incrementan en un factor de 1.200573.

c)
El modelo sería (recordando que los valores de Urban y US son 0 o 1):
Sales=13.0434689−0.0544588(Price)-0.0219162(Urban)+1.2005727(US)+ε

d) 
Por sus p-values podemos rechazar la hipótesis nula para US y Price. 

e) 
```R Script
fit.cars2 <- lm(Sales ~ Price + US)
summary(fit.cars2)
```
~~~
Call:
lm(formula = Sales ~ Price + US)

Residuals:
    Min      1Q  Median      3Q     Max 
-6.9269 -1.6286 -0.0574  1.5766  7.0515 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 13.03079    0.63098  20.652  < 2e-16 ***
Price       -0.05448    0.00523 -10.416  < 2e-16 ***
USYes        1.19964    0.25846   4.641 4.71e-06 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 2.469 on 397 degrees of freedom
Multiple R-squared:  0.2393,    Adjusted R-squared:  0.2354 
F-statistic: 62.43 on 2 and 397 DF,  p-value: < 2.2e-16
~~~

f) Basandonos el la estadística F y en la R cuadrada podemos decir que el modelo e) es mejor pero solo un poco, ya que su R cuadrada es de 0.2354 y la del modelo a) es de 0.2335, sin emargo, el modelo es mejor y con una variable menos que podría generar menos ruido. 

g) 
```R Script
confint(fit.cars2)
```
~~~
                  2.5 %      97.5 %
(Intercept) 11.79032020 14.27126531
Price       -0.06475984 -0.04419543
USYes        0.69151957  1.70776632
~~~

h) 
```R Script
plot(fit.cars2)
```
![Rplot05](Rplot05.png)

Podemos observar en las gráficas de residuales algunos outlayers (mayores a 2 o menos a -2) y también en la última gráfica podemos encontrar unos cuantos puntos leverage. 
