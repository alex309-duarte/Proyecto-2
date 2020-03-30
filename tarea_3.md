#### Samuel Romero Santiago
#### Manuel Alejandro Cardoso Duarte

# Ejercicios-Capitulo 3
#### 1. Describe the null hypotheses to which the p-values given in Table 3.4 correspond. Explain what conclusions you can draw based on these p-values. Your explanation should be phrased in terms of sales, TV, radio, and newspaper, rather than in terms of the coefficients of the linear model. 
---
                     
**R**: La hipótesis             nula relacionada a la tabla 3.4 se refiere a que los predictores "TV", "radio" y "newspapers" no tienen efecto alguno en las ventas totales. Podemos observar que los  p-valores de TV y radio, sugieren que la hipótesis nula es falsa para estos predictores, sin embargo, dado que el p-valor de newspaper es alto, podemos inferir que se cumple la hipótesis nula para este predictor.

#### 2. Carefully explain the differences between the KNN classifier and KNN regression methods.
---

**R:** El clasificador KNN sirve más para resolver problemas en los que existen variables cualitativas, aquellas cuyos valores son discretos. Por su parte la regresión KNN sirve para los problemas con variables cualitativas, en donde los valores son continuos, además se predice una respuesta cualitativa de la función F(x).

#### 3. Suppose we have a data set with five predictors, X1 =GPA, X2 = IQ, X3 = Gender (1 for Female and 0 forMale), X4 = Interaction between GPA and IQ, and X5 = Interaction between GPA and Gender. The response is starting salary after graduation (in thousands of dollars). Suppose we use least squares to fit the model, and get β0 = 50, β1 = 20, β2 = 0.07, β3 = 35, β4 = 0.01, β5 = −10.
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

#### 4. I collect a set of data (n=100 observations) containing a single predictor and a quantitative response. I then fit a linear regression model to the data, as well as a separate cubic regression, i.e. Y=β0+β1X+β2X2+β3X3+ε
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

#### 5.  Consider the fitted values that result from performing linear regression without an intercept. In this setting, the i-th fitted value takes the form yi=xiβ.
---

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/2020-03-27_21-49-32.png)

y

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_21-49-51.png)

¿Qué es ai'?
**R:**
Haciendo un poco de álgebra podemos obtener: 

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_21-49-09.png)

#### 6. Using (3.4), argue that in the case of simple linear regression, the least squares line always passes through the point (x1, y1).
---
La línea de mínimos cuadrados está dada por: 
    y=β0+β1X
Haciendo álgebra podemos decir que:
y=β0+β1(x)=y1−β1(x1)+β1(x1)=y1
Entonces podemos concluir que la linea de mínimos cuadrados si pasa por el punto (x1,y1).

#### 7.   It is claimed in the text that in the case of simple linear regression of Y onto X, the R2 statistic (3.17) is equal to the square of the correlation between X and Y (3.18). Prove that this is the case. For simplicity, you may assume that x=y=0.
---
**R:** Sabemos que:
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_22-18-16.png)
y que:
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_22-22-04.png)

Por lo que podemos reescribir R cuadrada como (sustituyendo Y gorro): 
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_22-30-06.png)
Haciendo álgebra (convirtiendo el 1 en términos similares):
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_23-02-26.png)
 Simplificando:
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_23-08-32.png)

Sabemos que la correlación al cuadrado de X y Y está dada por:
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_23-09-14.png)

Por lo que:
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/2020-03-27_23-10-00.png)

#### 8. This question involves the use of simple linear regression on the Auto data set.
---

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

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot.png)

c)
```r
par(mfrow = c(2, 2))

plot(fit1)
```
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot01.png)

En la grafica de residuales contra datos ajustados podemos observar que no hay una relación totalmente lineal. En la gráfica de residuals vs promedio, podemos observar que hay algunos puntos muy alejados, que pueden generar un mayor error en nuestra predicción.

#### 9. This question involves the use of multiple linear regression on the Auto data set.
---

a)
```R Script
pairs(auto)
```
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot02.png)

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
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot03.png)

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

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot04.png)

Observando las gráficas de residuales podemos decir que el modelo no es mucho mejor al lineal. 

#### 10. This question should be answered using the Carseats data set. 
---

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
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/Rplot05.png)

Podemos observar en las gráficas de residuales algunos outlayers (mayores a 2 o menos a -2) y también en la última gráfica podemos encontrar unos cuantos puntos leverage. 

#### 11. In this problem we will investigate the t-statistic for the null hypothesis Ho : β = 0 in simple linear regression without an intercept.
---
generamos un predictor X y la respuesta de Y como;
```r
set.seed(1)
x = rnorm(100)
y = 2*x + rnorm(100)
``` 
**a)** Perform a simple linear regression of y onto x, without an intercept. Report the coefficient estimate ˆβ, the standard error of this coefficient estimate, and the t-statistic and p-value associated with the null hypothesis H0 : β = 0.

**R:** Se estiman las características del ajuste lineal con el comando lm en los predictores x, y, luego se obtiene infromacion acerca de este ajuste con la funcion summary.

```r
fit = lm(y~x-1) # predictor_1~predictor_2 el -1 indica que es el ajuste lineal sin intercept
summary(fit)
```
La funcion summary nos regresa;
```r
Call:
lm(formula = y ~ x - 1)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.9154 -0.6472 -0.1771  0.5056  2.3109 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)    
x   1.9939     0.1065   18.73   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.9586 on 99 degrees of freedom
Multiple R-squared:  0.7798,	Adjusted R-squared:  0.7776 
F-statistic: 350.7 on 1 and 99 DF,  p-value: < 2.2e-16
```
El p-value nos dice si se acepta la hipotesis nula o no, solo si es menor al 5% se dice que la hipotesis nula es rechazada, por lo tanto en este ajuste entre de los predictores de y sobre x la hipotesis nula es rechada porque es p valor es muy cercano a cero.

**b)** Now perform a simple linear regression of x onto y without an intercept, and report the coefficient estimate, its standard error, and the corresponding t-statistic and p-values associated with the null hypothesis Ho : β = 0.

**R:** Se estiman las características del ajuste lineal con el comando lm en los predictores x, y, al contrario del caso anterior ahora va a ser x sobre y, luego se obtiene infromacion acerca de este ajuste con la funcion summary.

```r
fit = lm(x~y-1) 
summary(fit)
```
La funcion summary nos regresa;
```r
Call:
lm(formula = x ~ y - 1)

Residuals:
    Min      1Q  Median      3Q     Max 
-0.8699 -0.2368  0.1030  0.2858  0.8938 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)    
y  0.39111    0.02089   18.73   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.4246 on 99 degrees of freedom
Multiple R-squared:  0.7798,	Adjusted R-squared:  0.7776 
F-statistic: 350.7 on 1 and 99 DF,  p-value: < 2.2e-16
```
Vemos nuevamente que el p-value es muy cercano a cero, casi cero, por lo tanto la hipotesis nula es rechazada.

**c)** What is the relationship between the results obtained in (a) and (b)?

**R:** El ajuste lineal en ambos casos de Y sobre X y viceversa representan a la linea y=2x+error y x=(1/2)*(y-error) respectivamente, es decir, representan una misma curva pero en ejes diferentes y esto se vio reflejado desde el inciso 11.a al crear los predictores X y Y el predictor Y guarda relacion con el predictor X.

**d)** For the regression of Y onto X without an intercept, the tstatistic for H0 : β = 0 takes the form ˆβ/SE( ˆ β), where ˆ β is given by (3.38), and where

(These formulas are slightly different from those given in Sections 3.1.1 and 3.1.2, since here we are performing regression without an intercept.) Show algebraically, and confirm numerically in R, that the t-statistic can be written as


SE(β)=$\sqrt{\frac{ Σ (y_i - x_i β )^2 }{(n-1)Σ x_i^2}}$

luego t = $\frac{β}{SE(β)}$

$β = \frac{Σ x_i y_i}{Σ x_i^2}$

podemos sustituir

$t = \frac{Σ x_i y_i}{Σ x_i^2} \sqrt{\frac{(n-1)Σ x_i^2}{ Σ (y_i - x_i β )^2 }}$

reduciendo

$t = \frac{Σ x_i y_i\sqrt{(n-1)}}{\sqrt{Σ x_i^2 Σ (y_i - x_i β )^2} }$

desarrollamos el binomio

$t = \frac{Σ x_i y_i\sqrt{(n-1)}}{\sqrt{Σ x_i^2 Σ (y_i^2 - 2* y_i *x_i β +x_i^2 β^2)^2} }$

agrupamos

$t = \frac{Σ x_i y_i\sqrt{(n-1)}}{\sqrt{Σ x_i^2 Σ y_i^2 -  Σ x_i^2 β( 2* y_i *x_i  +x_i^2 β)^2} }$

reducimos hasta el final

$t = \frac{Σ x_i y_i\sqrt{(n-1)}}{\sqrt{Σ x_i^2 Σ y_i^2 - ( Σ x_i y_i)^2} }$

Para comprobarlo numericamente escribimos la formula en R

```r
(sqrt(length(x)-1) * sum(x*y)) / (sqrt(sum(x*x) * sum(y*y) - (sum(x*y))^2))

18.7259319374486 # resultado
```

**e)** Using the results from (d), argue that the t-statistic for the regression of y onto x is the same as the t-statistic for the regression of x onto y.

**R:** se puede hacer un intercambio entre las funcion f(x,y) como f(y,x)  y después provamos que f(x,y)=f(y,x)

**f)** In R, show that when regression is performed with an intercept, the t-statistic for H0 : β1 = 0 is the same for the regression of y onto x as it is for the regression of x onto y.

**R:** Generamos un ajuste lineal

```r
ajuste_1 = lm(y~x)
ajuste_2 = lm(x~y)
summary(ajuste_1)
```

```r
Call:
lm(formula = y ~ x)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.8768 -0.6138 -0.1395  0.5394  2.3462 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -0.03769    0.09699  -0.389    0.698    
x            1.99894    0.10773  18.556   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.9628 on 98 degrees of freedom
Multiple R-squared:  0.7784,	Adjusted R-squared:  0.7762 
F-statistic: 344.3 on 1 and 98 DF,  p-value: < 2.2e-16
```

```r
summary(ajuste_2)
```

```r
Call:
lm(formula = x ~ y)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.90848 -0.28101  0.06274  0.24570  0.85736 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  0.03880    0.04266    0.91    0.365    
y            0.38942    0.02099   18.56   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.4249 on 98 degrees of freedom
Multiple R-squared:  0.7784,	Adjusted R-squared:  0.7762 
F-statistic: 344.3 on 1 and 98 DF,  p-value: < 2.2e-16
```

Es visible que t-stadistic es la misma para ambos casos, con un valor de 18.56.

#### 12. This problem involves simple linear regression without an intercept.
---

**a)** Recall that the coefficient estimate β for the linear regression of Y onto X without an intercept is given by (3.38). Under what circumstance is the coefficient estimate for the regression of X onto Y the same as the coefficient estimate for the regression of Y onto X?

**R:** Para que los coeficientes estimados tanto para la regresion de X sobre Y y Y sobre X sean iguales, la suma de los cuadrados de los Y-valores observados debe ser igual a la suma de los X-valores observados.

**b)** Generate an example in R with n = 100 observations in which the coefficient estimate for the regression of X onto Y is different from the coefficient estimate for the regression of Y onto X.

**R:** podemos generar un predictor X que este distribuido normalemnte, como en el primer ejercicio, y posteriormente asginar una funcion para otro predictor en relación con el primero, que puede ser un coeficiente por el predictor X.

```r
set.seed(1)
x = rnorm(100) # n = 100
y = 5*x+rnorm(100)  # el predcitor Y tiene dependencia del predictor X
linea_1 = lm(y~x-1) 
linea_2 = lm(x~y-1)  # x sobre y sin intercept

```
Con la funcion summary podemos ver los coeficientes estimados de la regresion linear (lm) de x sobre y o viceversa. 

```r
summary(linea_1)
```
```r
Call:
lm(formula = y ~ x - 1)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.9154 -0.6472 -0.1771  0.5056  2.3109 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)    
x   4.9939     0.1065    46.9   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.9586 on 99 degrees of freedom
Multiple R-squared:  0.9569,	Adjusted R-squared:  0.9565 
F-statistic:  2200 on 1 and 99 DF,  p-value: < 2.2e-16
```
```r
summary(linea_2)
```
```r
Call:
lm(formula = x ~ y - 1)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.42234 -0.09331  0.04202  0.11837  0.35994 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)    
y 0.191621   0.004086    46.9   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.1878 on 99 degrees of freedom
Multiple R-squared:  0.9569,	Adjusted R-squared:  0.9565 
F-statistic:  2200 on 1 and 99 DF,  p-value: < 2.2e-16
```

como podemos observar los coeficientes son diferentes en cada estimación, en y sobre x es 4.993 y en x sobre y es de 0.191.

**c)** Generate an example in R with n = 100 observations in which the coefficient estimate for the regression of X onto Y is the same as the coefficient estimate for the regression of Y onto X.

**R:** Para que los coefienetes de de regresión lineal de X sobre Y sean igual a los coefientes Y sobre X es necesario que la suma de cuadrados sea igual por lo que se pueden aplicar el ejemplo donde el predictor Y tenga los mismos valores que el predictor X pero con signo contrario.

```r
set.seed(1)
x = rnorm(100)  # generamos un predictor X de n = 100 normalmente distribuido
y = -sample(x, 100)  # luego con la funcion sample tomamos cada elemento y le cambiamos el signo
fit_1 = lm(y~x-1)  #ajuste entre predcitores de Y sobre X sin intercept
fit_2 = lm(x~y-1)  #ajuste entre predcitores de X sobre Y sin intercept
```

Posteriormente se aplica la suma de cuadrados tanto del predictor X como Y y comporbamos que sean iguales.

```r
sum(x^2)
```

```r
81.0550927470378
```

```r
sum(y^2)
```

```r
81.0550927470378
```
Después con la función summary comporbamos que los coeficientes son exactamente los mismos

```r
summary(fit_1)
```

```r
Call:
lm(formula = y ~ x - 1)

Residuals:
    Min      1Q  Median      3Q     Max 
-2.2833 -0.6945 -0.1140  0.4995  2.1665 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)
x  0.07768    0.10020   0.775     0.44

Residual standard error: 0.9021 on 99 degrees of freedom
Multiple R-squared:  0.006034,	Adjusted R-squared:  -0.004006 
F-statistic: 0.601 on 1 and 99 DF,  p-value: 0.4401
```

```r
summary(fit_2)
```

```r
Call:
lm(formula = x ~ y - 1)

Residuals:
    Min      1Q  Median      3Q     Max 
-2.2182 -0.4969  0.1595  0.6782  2.4017 

Coefficients:
  Estimate Std. Error t value Pr(>|t|)
y  0.07768    0.10020   0.775     0.44

Residual standard error: 0.9021 on 99 degrees of freedom
Multiple R-squared:  0.006034,	Adjusted R-squared:  -0.004006 
F-statistic: 0.601 on 1 and 99 DF,  p-value: 0.4401
```

Vemos que ambos coefienetes de la regresión lineal son 0.07768, como vemos el valor mínimo y máximo son los mismos al igual que el error estandar, debido a que los calculos de estos valores son con los errores al cuadrado.

#### 13. In this exercise you will create some simulated data and will fit simple linear regression models to it.
---
**a)** Using the rnorm() function, create a vector, x, containing 100 observations drawn from a N(0, 1) distribution. This represents a feature, X.

**R:** 

```r
set.seed(1) #generación de la semilla
x = rnorm(100)  #distribución normalmente distribuida N(0,1) con varianza 1
```

**b)** Using the rnorm() function, create a vector, eps, containing 100 observations drawn from a N(0, 0.25) distribution i.e. a normal distribution with mean zero and variance 0.25.

**R:** con la función rnorm generamos un vectos de 100 observaciones con desviación estandar 0.25

```r
eps = rnorm(100, 0, sqrt(0.25))  # n= 100   varianza = 0.25 y media cero
```

**c)** Using x and eps, generate a vector y according to the model Y = −1 + 0.5X + ε. What is the length of the vector y? What are the values of βo and β1 in this linear model?

**R:** El modelo anterior se puede representar en R como:
```r
y = -1 + 0.5*x + eps
```

Donde el tamaño de Y es 100, esto se puede saber con la función length() pero el tamaño de los vectores x y eps es de 100, por lo tanto no es necesario calcularlo. Donde βo = -1 y β1 = 0.5. 

```r
length(y)  # calculando el tamaño del nuevo vector generado Y
```

**d)** Create a scatterplot displaying the relationship between x and y. Comment on what you observe.

**R:** Vemos una relacion con una pensiente positiva y una varianza, esto es debido a que se generaron datos con una distribucion normal, además de que el predictor Y guarda relacipon con el vector X con un coefiente de 0.5.

```r
plot(x,y)
```
![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_d.png)

**e)** Fit a least squares linear model to predict y using x. Comment on the model obtained. How do ˆ βo and ˆ β1 compare to βo and β1?

**R:** Hacemos regresión lineal de y sobre x 

```r
fit_1 = lm(y~x)
summary(fit_1)
```

```r
Call:
lm(formula = y ~ x)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.93842 -0.30688 -0.06975  0.26970  1.17309 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -1.01885    0.04849 -21.010  < 2e-16 ***
x            0.49947    0.05386   9.273 4.58e-15 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.4814 on 98 degrees of freedom
Multiple R-squared:  0.4674,	Adjusted R-squared:  0.4619 
F-statistic: 85.99 on 1 and 98 DF,  p-value: 4.583e-15
```
La regrecion se hacerca al valor de los coeficientes como x fue de 0.5 y en este caso tenemos 0.49947 y la intercepción en la función fue de -1, el valor en el ajuste es de -1.018, los valores de βo y β1 no cambian mucho. Como vemos la estadistica F el valor es lejano a 1 y tenemos un p-value muy cercano a cero por lo que la hipotesis nula es rechazada.

**f)** Display the least squares line on the scatterplot obtained in (d). Draw the population regression line on the plot, in a different color. Use the legend() command to create an appropriate legend.

**R** Vamos a comparar le recta obtenida de la regresión lineal en el inciso d) y la generada por la funcion lm(). Para sobreponer las rectas generadas se utiliza la función abline().

```r
plot(x, y)
abline(fit_1, lwd=3, col=1)  # curva de ajuste 
abline(-1, 0.5, lwd=3, col=2)  #curva del inciso d) original
legend(-1, legend = c("Ajuste del modelo", "y=-1+0.5*x+eps"), col=1:2, lwd=4)
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_f.png)

**g)** Now fit a polynomial regression model that predicts y using x and x2. Is there evidence that the quadratic term improves the model fit? Explain your answer.

**R:** Generamos un nuevo modelo de regresion polinomial, esto se hizo untilizando la funcion I() para elevar x al cuadrado

```r
ajuste_x2 = lm(y~x+I(x^2)) #ajuste cde y sobre x y x^2
summary(ajuste_x2)
```

```r
Call:
lm(formula = y ~ x + I(x^2))

Residuals:
     Min       1Q   Median       3Q      Max 
-0.98252 -0.31270 -0.06441  0.29014  1.13500 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -0.97164    0.05883 -16.517  < 2e-16 ***
x            0.50858    0.05399   9.420  2.4e-15 ***
I(x^2)      -0.05946    0.04238  -1.403    0.164    
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.479 on 97 degrees of freedom
Multiple R-squared:  0.4779,	Adjusted R-squared:  0.4672 
F-statistic:  44.4 on 2 and 97 DF,  p-value: 2.038e-14
```
Vemos que el término cuadratico no ayuda al ajuste lineal de una forma muy nototia, existe un cambio en lo coeficientes.


**h)** Repeat (a)–(f) after modifying the data generation process in such a way that there is less noise in the data. The model (3.39) should remain the same. You can do this by decreasing the variance of the normal distribution used to generate the error term ε in (b). Describe your results.
```r
set.seed(1) #generamos la semilla
eps_1 = rnorm(100, 0, 0.125)  #generamos el error n = 100, con varianza de 0.125
x_1 = rnorm(100)  #generamos un predictor x_1 con n=100 con distribucion normal media cero y varianza 1
y_1 = -1 + (1/2)*x_1 + eps_1   #generamos a nuestro predictor Y_1 con Bo = -1 y B1 = 0.5
plot(x_1, y_1)      #graficamos ambos predictores uno contra el otro, ambos guardan relacion

```
Ajuste de cruva entre predictores

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_i_1.png)

**figura generada**
```r
ajuste_1= lm(y_1~x_1)   #hacemos un ajuste de curva entre los predictores y_1 y x_1
summary(ajuste_1)    #vemos las caractersiticas de es ajuste
```
```r
Call:
lm(formula = y_1 ~ x_1)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.29052 -0.07545  0.00067  0.07288  0.28664 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -0.98639    0.01129  -87.34   <2e-16 ***
x_1          0.49988    0.01184   42.22   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.1128 on 98 degrees of freedom
Multiple R-squared:  0.9479,	Adjusted R-squared:  0.9474 
F-statistic:  1782 on 1 and 98 DF,  p-value: < 2.2e-16
```
vemos que los coeficientes son muy cercanos, a los establecidos en la relación y_1 = -1 + (1/2)*x_1 + eps_1. 

```r
plot(x_1, y_1)
abline(ajuste_1, lwd=3, col=1)
abline(-1, 0.5, lwd=3, col=2)
legend(-1,0, legend = c("ajuste_1", "y_1=-1+(1/2)*x+eps_1"), col=1:2, lwd=6)
```

**Gráfica generada**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_i_2.png)

Vemos que el error disminuye, esto debido a que reducimos la varianza en el error, en la variable eps_1, por lo tanto los datos no son tan variables y se reduce el error.

**i)** Repeat (a)–(f) after modifying the data generation process in such a way that there is more noise in the data. The model (3.39) should remain the same. You can do this by increasing the variance of the normal distribution used to generate the error term ε in (b). Describe your results.

**R:** Repetimos el procedimiento anterior,
```r
set.seed(1)
eps_2 = rnorm(100, 0, 0.5)
x_2 = rnorm(100)
y_2 = -1 + 0.5*x_2 + eps_2
plot(x_2, y_2)
```
**Gráfica entre los nuevos predictores x_2 y y_2**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_j_1.png)


```r
ajuste_2 = lm(y_2~x_2)
summary(ajuste_2)
```

```r
Call:
lm(formula = y_2 ~ x_2)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.16208 -0.30181  0.00268  0.29152  1.14658 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -0.94557    0.04517  -20.93   <2e-16 ***
x_2          0.49953    0.04736   10.55   <2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.4514 on 98 degrees of freedom
Multiple R-squared:  0.5317,	Adjusted R-squared:  0.5269 
F-statistic: 111.2 on 1 and 98 DF,  p-value: < 2.2e-16
```
Vemos que a comparación del ejecicio del inciso anterior la estadistica F sigue teniendo un valor alto pero menor y el error cuadratico a aumentado considerablemente. Luego procedemos a comprar las gráficas entre el predictor Y_2 generado y el generado por el ajuste lineal.

```r
plot(y_2~x_2)
abline(ajuste_2, lwd=3, col=1)
abline(-1, 0.5, lwd=3, col=2)
legend(-2.4,0, legend = c("ajuste_2", "y_2 = -1 + 0.5*x_2 + eps_2"), col=1:2, lwd=3)
```

**gráfica generada comparando el ajuste lineal entre curvas**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/13_j_2.png)

Podemos observar que las rectas están mas alejadas, casi paralelas entre si, y vemos que el error ha aumentado. esto porque incremento la varianza de la distribución normal del error asociado la a generación del predictor.

**j)** What are the confidence intervals for β0 and β1 based on the original data set, the noisier data set, and the less noisy data set? Comment on your results.

**R:** Para generar el intervalo de confianza exite una función en R que lo hace llamada confint(). Recordando el nombre que asignamos a cada modelo tenemos:

```r
confint(fit_1) #modelo original
```


obs | 2.5 % |	97.5 % |
--- | --- | --- |
(Intercept)	| -1.1150804 |	-0.9226122
x | 0.3925794 |	0.6063602



```r
confint(ajuste_1) #modelo con menor ruido, varianza en el error baja
```

Obs |	2.5 % |	97.5 % |
--- | --- | --- |
(Intercept) |	-1.008805 |	-0.9639819 |
x_1 |	0.476387 |	0.5233799 |


```r
confint(ajuste_2) #modelos con mayor cantidad de ruido, varianza en el error alta
```

Obs | 2.5 %	| 97.5 % |
--- | --- | --- |
(Intercept)	| -1.0352203 |	-0.8559276 |
x_2	| 0.4055479	| 0.5935197 |

los intervalos de confianza fueron generados con un 5% de ajuste, y vemos que el intervalo del segundo ajuste es mas pequeño que el primero y del tercer ajuste o ajuste_2 es mas grande que el primero, y esto porque crece el intervalo de confianza ante una mayor dispersión de nuestros datos.

#### 14. This problem focuses on the collinearity problem.
---

**a)** (a) Perform the following commands in R: 

```r
set.seed (1)
x1=runif (100)
x2 =0.5* x1+rnorm (100) /10
y=2+2* x1 +0.3* x2+rnorm (100)
```
The last line corresponds to creating a linear model in which y is a function of x1 and x2. Write out the form of the linear model. What are the regression coefficients?

**R:** de acuerdo con la función los coeficientes son βo = 2, β1 = 2, β2 = 0.3 y el error es rnorm(100).

**b)** What is the correlation between x1 and x2? Create a scatterplot displaying the relationship between the variables.

**R:** La correlación entre x1 y x2 se calcula en R con la función cor().

```r
cor(x1, x2) #calculando la corerelacion entre predictores

0.835121242463113  #la correlacion va de -1 a 1 donde cercano a 1 es correlacion fuerte
```
```r
plot(x1, x2) #generamos un grafico entre los predictores x1 y x2
```

**Gráfica de relación entre x1 y x2**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/14_b.png)

**c)** Using this data, fit a least squares regression to predict y using x1 and x2. Describe the results obtained. What are ˆ β0, ˆ β1, and ˆ β2? How do these relate to the true β0, β1, and β2? Can you reject the null hypothesis H0 : β1 = 0? How about the null hypothesis H0 : β2 = 0?

```r
fit_14 = lm(y~x1+x2)
summary(fit_14)
```

```r
Call:
lm(formula = y ~ x1 + x2)

Residuals:
    Min      1Q  Median      3Q     Max 
-2.8311 -0.7273 -0.0537  0.6338  2.3359 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.1305     0.2319   9.188 7.61e-15 ***
x1            1.4396     0.7212   1.996   0.0487 *  
x2            1.0097     1.1337   0.891   0.3754    
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.056 on 97 degrees of freedom
Multiple R-squared:  0.2088,	Adjusted R-squared:  0.1925 
F-statistic:  12.8 on 2 and 97 DF,  p-value: 1.164e-05
```
El valor de los coeficientes es alterado considerablemente. Podemos ver que de los predictores β1 y β2 donde el p-value de β1 es menor al 5% por lo tanto se rechaza la hipotesis nula, mientras que en β2 el p-value es mayor al 5% por lo tanto se acepta la hipotesis nula, por lo que el unico predictor que sirve es β1 y entonces Ho: β2 = 0.


**d)** Now fit a least squares regression to predict y using only x1. Comment on your results. Can you reject the null hypothesis H0 : β1 = 0?

**R:** 

```r
lm.fit = lm(y~x1)
summary(lm.fit)
```

```r
Call:
lm(formula = y ~ x1)

Residuals:
     Min       1Q   Median       3Q      Max 
-2.89495 -0.66874 -0.07785  0.59221  2.45560 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.1124     0.2307   9.155 8.27e-15 ***
x1            1.9759     0.3963   4.986 2.66e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.055 on 98 degrees of freedom
Multiple R-squared:  0.2024,	Adjusted R-squared:  0.1942 
F-statistic: 24.86 on 1 and 98 DF,  p-value: 2.661e-06
```

De acuerdo con lo anterior, podemos rechazar la hipotesis nula del coeficiente, predictor β1, por lo que se puede rechazar la hipotesis nula debido a que en el estadistico t tiene un p-value muy cercano a cero.

**e)** Now fit a least squares regression to predict y using only x2. Comment on your results. Can you reject the null hypothesis H0 : β1 = 0?

**R:** 

```r
ajuste_mult_2 = lm(y~x2)
summary(ajuste_mult_2)
```

```r
Call:
lm(formula = y ~ x2)

Residuals:
     Min       1Q   Median       3Q      Max 
-2.62687 -0.75156 -0.03598  0.72383  2.44890 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.3899     0.1949   12.26  < 2e-16 ***
x2            2.8996     0.6330    4.58 1.37e-05 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.072 on 98 degrees of freedom
Multiple R-squared:  0.1763,	Adjusted R-squared:  0.1679 
F-statistic: 20.98 on 1 and 98 DF,  p-value: 1.366e-05
```

Vemos que el p-value es muy cercano a cero por lo cual se puede rechazar la hipotesis nula.

**f)** Do the results obtained in (c)–(e) contradict each other? Explain your answer.

**R:** No se contradicen, cuando se hace la regresion lineal juntos los predictores x1 y x2 existe una clara correlacion entre estos dos predictores, es decir hay una relación que no es visible cuando la regresión lineal es conjunta se ve la relación entre estos predictores. Lo que nos indica esque hay una relacion entre los predictores.

**g)** Now suppose we obtain one additional observation, which was unfortunately mismeasured.

```r
x1=c(x1 , 0.1)
x2=c(x2 , 0.8)
y=c(y,6)
```

Re-fit the linear models from (c) to (e) using this new data. What effect does this new observation have on the each of the models? In each model, is this observation an outlier? A high-leverage point? Both? Explain your answers.

**R:** Generamos el ajuste de acuerdo con los parámetros anteriores.

```r
ajuste_14g = lm(y~x1+x2)
summary(ajuste_14g)
```

```r
Call:
lm(formula = y ~ x1 + x2)

Residuals:
     Min       1Q   Median       3Q      Max 
-2.73348 -0.69318 -0.05263  0.66385  2.30619 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.2267     0.2314   9.624 7.91e-16 ***
x1            0.5394     0.5922   0.911  0.36458    
x2            2.5146     0.8977   2.801  0.00614 ** 
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.075 on 98 degrees of freedom
Multiple R-squared:  0.2188,	Adjusted R-squared:  0.2029 
F-statistic: 13.72 on 2 and 98 DF,  p-value: 5.564e-06
```

Como vemos en la regresión lineal multiple anterior podemos ver que el predictor x1 tiene un p-value de 0.36 por lo que es mayor al 5% por lo que la hipotesis nula es aceptada. y en el caso del predictor x2 el p-value es menor al 5% por lo que la hipotesis nula para este predictor es rechazada. De lo anterior, el unico predictor importante es x2.

```r
ajuste_14g_x1 = lm(y~x1)
summary(ajuste_14g_x1)
```

```r
Call:
lm(formula = y ~ x1)

Residuals:
    Min      1Q  Median      3Q     Max 
-2.8897 -0.6556 -0.0909  0.5682  3.5665 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.2569     0.2390   9.445 1.78e-15 ***
x1            1.7657     0.4124   4.282 4.29e-05 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.111 on 99 degrees of freedom
Multiple R-squared:  0.1562,	Adjusted R-squared:  0.1477 
F-statistic: 18.33 on 1 and 99 DF,  p-value: 4.295e-05
```

```r
ajuste_14g_x2= lm(y~x2)
summary(ajuste_14g_x2)
```

```r
Call:
lm(formula = y ~ x2)

Residuals:
     Min       1Q   Median       3Q      Max 
-2.64729 -0.71021 -0.06899  0.72699  2.38074 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.3451     0.1912  12.264  < 2e-16 ***
x2            3.1190     0.6040   5.164 1.25e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.074 on 99 degrees of freedom
Multiple R-squared:  0.2122,	Adjusted R-squared:  0.2042 
F-statistic: 26.66 on 1 and 99 DF,  p-value: 1.253e-06
```

En la regresión simple con los predcitores x1 y x2 aplicando la estadistica t  el valor p en ambos casos es muy pequeño, cercano a cero, por lo que concluimos que los predictores estan relacionados entre si.

podemos visualizar las relaciones con las curvas generadas de la regresión multiple dada por la función plot. La función pair nos ayuda a acomodar las gráficas generadas en una sola imagen.

```r
par(mfrow=c(2,2))
plot(ajuste_14g)

par(mfrow=c(2,2))
plot(ajuste_14g_x1)

par(mfrow=c(2,2))
plot(ajuste_14g_x2)
```
Generando las gráficas siguientes:

**Grafica de ajuste_14g**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/14_g_1.png)

**Grafica de ajuste_14g_x1**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/14_g_2.png)

**Grafica de ajuste_14g_x2**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/14_g_3.png)

Ahora analizamos las coincidencias entre cada regresion utilizando la funcion predict() en R para las predicciones y un diagnostico sobre la regresión con la función rstudent().

```r
par(mfrow=c(2,2))  # agrupamos los gráficas generados en una sola imagen
plot(predict(ajuste_14g), rstudent(ajuste_14g))  #calculando diagnostico sobre las regresiones y las predicciones.
plot(predict(ajuste_14g_x1), rstudent(ajuste_14g_x1))
plot(predict(ajuste_14g_x2), rstudent(ajuste_14g_x2))
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/14_g_4.png)

De la gráfica anterior, solo en la segunda regresión linear se observan puntos lejos del valor esperado.

#### 15. This problem involves the Boston data set, which we saw in the lab for this chapter. We will now try to predict per capita crime rate using the other variables in this data set. In other words, per capita crime rate is the response, and the other variables are the predictors.
---

**a)** For each predictor, fit a simple linear regression model to predict the response. Describe your results. In which of the models is there a statistically significant association between the predictor and the response? Create some plots to back up your assertions.
 
**R:** Este data set se utilizó en el capítulo anterior, y para utilizarlo necesitamos de la libreria MASS, luego con la función summary podemos todo lo que contiene el data set de boston.
 
```r
library(MASS)
summary(Boston)
```

```r
 crim                zn             indus            chas        
 Min.   : 0.00632   Min.   :  0.00   Min.   : 0.46   Min.   :0.00000  
 1st Qu.: 0.08204   1st Qu.:  0.00   1st Qu.: 5.19   1st Qu.:0.00000  
 Median : 0.25651   Median :  0.00   Median : 9.69   Median :0.00000  
 Mean   : 3.61352   Mean   : 11.36   Mean   :11.14   Mean   :0.06917  
 3rd Qu.: 3.67708   3rd Qu.: 12.50   3rd Qu.:18.10   3rd Qu.:0.00000  
 Max.   :88.97620   Max.   :100.00   Max.   :27.74   Max.   :1.00000  
      nox               rm             age              dis        
 Min.   :0.3850   Min.   :3.561   Min.   :  2.90   Min.   : 1.130  
 1st Qu.:0.4490   1st Qu.:5.886   1st Qu.: 45.02   1st Qu.: 2.100  
 Median :0.5380   Median :6.208   Median : 77.50   Median : 3.207  
 Mean   :0.5547   Mean   :6.285   Mean   : 68.57   Mean   : 3.795  
 3rd Qu.:0.6240   3rd Qu.:6.623   3rd Qu.: 94.08   3rd Qu.: 5.188  
 Max.   :0.8710   Max.   :8.780   Max.   :100.00   Max.   :12.127  
      rad              tax           ptratio          black       
 Min.   : 1.000   Min.   :187.0   Min.   :12.60   Min.   :  0.32  
 1st Qu.: 4.000   1st Qu.:279.0   1st Qu.:17.40   1st Qu.:375.38  
 Median : 5.000   Median :330.0   Median :19.05   Median :391.44  
 Mean   : 9.549   Mean   :408.2   Mean   :18.46   Mean   :356.67  
 3rd Qu.:24.000   3rd Qu.:666.0   3rd Qu.:20.20   3rd Qu.:396.23  
 Max.   :24.000   Max.   :711.0   Max.   :22.00   Max.   :396.90  
     lstat            medv      
 Min.   : 1.73   Min.   : 5.00  
 1st Qu.: 6.95   1st Qu.:17.02  
 Median :11.36   Median :21.20  
 Mean   :12.65   Mean   :22.53  
 3rd Qu.:16.95   3rd Qu.:25.00  
 Max.   :37.97   Max.   :50.00  
```



```r
attach(Boston)  #de esta manera enviamos a los nombres de los predictores como los predictores sin necesidad de llamarlos a través de Boston$name
names(Boston)
```

nombre de los predictores 'crim''zn''indus''chas''nox''rm''age''dis''rad''tax''ptratio''black''lstat''medv'.

```r
fit_zn = lm(crim~zn)
summary(fit_zn)
fit_indus = lm(crim~indus)
summary(fit_indus)
fit_chas = lm(crim~chas)
summary(fit_chas)
fit_nox = lm(crim~nox)
summary(fit_nox)
fit_rm = lm(crim~rm)
summary(fit_rm)
fit_age = lm(crim~age)
summary(fit_age)
fit_dis = lm(crim~dis)
summary(fit_dis)
fit_rad = lm(crim~rad)
summary(fit_rad)
fit_tax = lm(crim~tax)
summary(fit_tax)
fit_ptratio = lm(crim~ptratio)
summary(fit_ptratio)
fit_black = lm(crim~black)
summary(fit_black)
fit_lstat = lm(crim~lstat)
summary(fit_lstat)
fit_medv = lm(crim~medv)
summary(fit_medv)
```

Los siguientes comandos fueron ejecutado en R, y el único predictor que tiene un p-value mayor al 5% es el predictor chas. Todos los demás predictores tienen un valor p muy cercano a cero.

**b)** Fit a multiple regression model to predict the response using all of the predictors. Describe your results. For which predictors can we reject the null hypothesis H0 : βj = 0?

**R:** Para tener la respuésta de todos los predcitores y no sumar cada nombre, al colocar ., indicamos que tome todos los predictores
```r
fit_all = lm(crim~., data=Boston)
summary(fit_all)
```

```r
Call:
lm(formula = crim ~ ., Boston)

Residuals:
   Min     1Q Median     3Q    Max 
-9.924 -2.120 -0.353  1.019 75.051 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  17.033228   7.234903   2.354 0.018949 *  
zn            0.044855   0.018734   2.394 0.017025 *  
indus        -0.063855   0.083407  -0.766 0.444294    
chas         -0.749134   1.180147  -0.635 0.525867    
nox         -10.313535   5.275536  -1.955 0.051152 .  
rm            0.430131   0.612830   0.702 0.483089    
age           0.001452   0.017925   0.081 0.935488    
dis          -0.987176   0.281817  -3.503 0.000502 ***
rad           0.588209   0.088049   6.680 6.46e-11 ***
tax          -0.003780   0.005156  -0.733 0.463793    
ptratio      -0.271081   0.186450  -1.454 0.146611    
black        -0.007538   0.003673  -2.052 0.040702 *  
lstat         0.126211   0.075725   1.667 0.096208 .  
medv         -0.198887   0.060516  -3.287 0.001087 ** 
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 6.439 on 492 degrees of freedom
Multiple R-squared:  0.454,	Adjusted R-squared:  0.4396 
F-statistic: 31.47 on 13 and 492 DF,  p-value: < 2.2e-16
```

De los resultados anteriores podemos ver que los predictores que tienen un p-value muy grande son indus, nox,chas,rm,age,tax,ptratio y lstat por lo que para estos predictores la hipotesis nula es aceptada. Para los predictores zn, dis, rad, black y medv la hipotesis nula es rechasa, por lo tanto, son los unicos predictores que funcionan.

**c)** How do your results from (a) compare to your results from (b)? Create a plot displaying the univariate regression coefficients from (a) on the x-axis, and the multiple regression coefficients from (b) on the y-axis. That is, each predictor is displayed as a single point in the plot. Its coefficient in a simple linear regression model is shown on the x-axis, and its coefficient estimate in the multiple linear regression model is shown on the y-axis.

**R:** De acuerdo con la pregunta debemos de hacer una grafica con cada predcitor, el ajuste lineal que hicimos y guardamos en las variables fit_name debemos tomar el coefiente 2, esto se representa como una lista, entonces el coeficiente dos esta en la posición coefficients(fit_name)[2], esto para los valores de x. vara los valores de y es el modelo de regresión lineal completo.

```r
x = c(coefficients(fit_zn)[2],
      coefficients(fit_indus)[2],
      coefficients(fit_chas)[2],
      coefficients(fit_nox)[2],
      coefficients(fit_rm)[2],
      coefficients(fit_age)[2],
      coefficients(fit_dis)[2],
      coefficients(fit_rad)[2],
      coefficients(fit_tax)[2],
      coefficients(fit_ptratio)[2],
      coefficients(fit_black)[2],
      coefficients(fit_lstat)[2],
      coefficients(fit_medv)[2])
y = coefficients(fit_all)[2:14]
plot(x, y)
```

**Gráfica generada**

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/imagenes_tarea03/15_c.png)

**d)** Is there evidence of non-linear association between any of the predictors and the response? To answer this question, for each predictor X, fit a model of the form Y = β0 + β1X + β2X^2 + β3X^3 + ε.

**R:** Para que quede de la forma Y = β0 + β1X + β2X^2 + β3X^3 + ε necesitamos generar el polinomio con la función poly() la cual nos regresa los polinomios desde grado 1 al grado asignado de una lista de puntos x.

```r
fit_zn = lm(crim~poly(zn,3))
summary(fit_zn)
fit_indus = lm(crim~poly(indus,3))
summary(fit_indus)

fit_nox = lm(crim~poly(nox,3))
summary(fit_nox)
fit_rm = lm(crim~poly(rm,3))
summary(fit_rm)
fit_age = lm(crim~poly(age,3))
summary(fit_age)
fit_dis = lm(crim~poly(dis,3))
summary(fit_dis)
fit_rad = lm(crim~poly(rad,3))
summary(fit_rad)
fit_tax = lm(crim~poly(tax,3))
summary(fit_tax)
fit_ptratio = lm(crim~poly(ptratio,3))
summary(fit_ptratio)
fit_black = lm(crim~poly(black,3))
summary(fit_black)
fit_lstat = lm(crim~poly(lstat,3))
summary(fit_lstat)
fit_medv = lm(crim~poly(medv,3))
summary(fit_medv)
```

en los casos anteriores se detecto solamente que los predictores chas y black presentan una linealidad, los demas presentan una no linealidad de los datos.
