# Ejercicios-Capitulo 6

#### Samuel Romero Santiago
#### Manuel Alejandro Cardoso Duarte

1. **We perform best subset, forward stepwise, and backward stepwise selection on a single data set. For each approach, we obtain p + 1 models, containing 0, 1, 2, . . . , p predictors. Explain your answers:**
___

a) Which of the three models with k predictors has the smallest training RSS?

 **R:** El modelo que proveé un menor RSS de entrenamiendo es el de elegir el mejor subconjunto porque selecciona un modelo entre todos los posibles generados por todas las K.

b) Which of the three models with k predictors has the smallest
test RSS?

**R:** No se puede saber, sin embargo podríamos suponer que el modelo de elegir el mejor subconjunto podría tener un mejor RSS porque elige entre más modelos que los otros dos.

c) True or false

i)  The predictors in the k-variable model identified by forward stepwise are a subset of the predictors in the (k+1)-variable model identified by forward stepwise selection.

**R** Verdadero: el modelo con (k+1) predictores se obtiene considerando los predictores en el modelo de k predictores con uno más.

ii) The predictors in the k-variable model identified by backward stepwise are a subset of the predictors in the (k + 1)- variable model identified by backward stepwise selection.

**R** Verdadero: Este modelo se obtiene quitando uno al modelo con (k+1) variables. 

iii) The predictors in the k-variable model identified by backward stepwise are a subset of the predictors in the (k + 1)- variable model identified by forward stepwise selection.

**R:** Falso: No hay relación directa entre ambos modelos.

iv) The predictors in the k-variable model identified by forward stepwise are a subset of the predictors in the (k+1)-variable model identified by backward stepwise selection.

**R** Falso: Como ya se mencionó no existe una relación directa entre ambos modelos.

v)The predictors in the k-variable model identified by best subset are a subset of the predictors in the (k + 1)-variable model identified by best subset selection.

**R** Falso: el modelo de k+1 variables se obtiene seleccionando entre todas los posibles modelos con k+1 varibales, pero puede no contener todaslas variables seleccionadas para el modelo de k-variables.

2. **For parts (a) through (c), indicate which of i. through iv. is correct. Justify your answer.** 
___

**a)	Lasso relativo a mínimos cuadrados es:**

**R:** Inciso iii).  Es menos flexible y por tanto dará una precisión de predicción cuando se aumenta el sesgo y disminuye la varianza, la ventaja de Lasso se centra en encontrar el equilibrio de sesgo varianza, este método sirve para seleccionar variables, en el caso de que la varianza por mínimos cuadrados sea muy alta, Lasso puede lograr una reducción de la varianza por medio de aumentar el sesgo, esto por la relación sesgo varianza del modelo.

**b)	Regresión de Ridge relativa a mínimos cuadrados.**

**R:** Inciso iii). Tenemos el mismo caso que anteriormente, la diferencia entre Ridge y Lasso se centra en que Ridge no sirve para la selección de variables, pero sirve para disminuir la varianza de mínimos cuadrados. Esto funciona bien cuando tenemos una alta varianza en mínimos cuadrados ya que Ridge disminuye la varianza aumentando un poco el sesgo del modelo.

**c)	Métodos no lineales relativos a mínimos cuadrados.**

**R:** Inciso ii). Los métodos no lineales son más flexibles, tienen un sesgo menor pero un incremento en la varianza, se enfocan más en hacer un ajuste de los puntos mayor a través de otro tipo de funciones, esto sacrificando el aumento de la varianza.

3. **Suppose we estimate the regression coefficients in a linear regression model by minimizing... for a particular value of s. For parts (a) through (e), indicate which of i. through v. is correct. Justify your answer.**
___

a) As we increase s from 0, the training RSS will: 

**R** el RSS irá disminuyendo: Si incrementamos s, el coeficiente βj irá aumentando cada vez más hacia su minimo cuadrado (estimado), por lo que el modelo se va haciendo más flexible (complejo) que provoca una decreción continua en el RSS. 

b)Repeat (a) for test RSS.

**R** Decrece inicialmente, después crece en forma de U: como incrementamos s de igual forma el coeficiente βj irá aumentando cada vez más hacia su minimo cuadrado (estimado), lo que provoca que se reduzca el RSS de prueba hasta que eventualmente comienza a crecer en forma de U. 

c) Repeat (a) for variance.

**R** Continuamente incrementa: omo incrementamos s de igual forma el coeficiente βj irá aumentando cada vez más hacia su minimo cuadrado (estimado), esto hace que el modelo sea más flexible disminuyendo la varianza. 

d) Repeat (a) for (squared) bias.

**R** Constantemente decrece: Como el modelo se va haciendo más flexible cada vez cuando aumentamos s, el sezgo va decreciendo constantemente.

e) Repeat (a) for the irreducible error.

**R** Se mantiene constante, ya que el error irreducible es independiente del modelo y no se puede controlar.

4. **Suppose we estimate the regression coefficients in a linear regression model by minimizing**
___

**for a particular value of λ. For parts (a) through (e), indicate which of i. through v. is correct. Justify your answer.**

a)	Cuando incrementamos el valor de **s** desde cero, el valor de entrenamiento RSS 
Inciso iii) incremento constante. Al incrementar **s** estamos restringiendo los coeficientes βj haciéndolos más pequeños con esto hacemos menos flexible el modelo y estamos aumentando el RSS del set de entrenamiento.

b)	Para el set de prueba.
Inciso ii) comienza a decrementar inicialmente y luego comienza a incrementar en forma de U. en el momento que **s** es cero, los coeficientes βs tiene el mínimo error cuadrado, entonces tenemos una acumulación de RSS alta, a medida que incrementamos el valor de **s** el valor RSS comienza a decrementar, pero llega un momento en que los coeficientes βs tienden a cero, entonces aumenta el valor RSS, esto porque el modelo se vuelve cada vez menos flexible.

c)	Para la varianza.
Inciso iii) incrementa continuamente. Cuando **s**=0 los coeficientes βs tienen valores iniciales estimados mínimos cuadrados, a medida que vamos incrementando el valor de **s** los coeficientes se van restringiendo menos y menos y la varianza va incrementando **s** y el modelo se vuelve más y más flexible.

d)	Para el bias (sesgo).
Inciso iv) decremente continuamente. Esto se debe que al incrementar **s** los coeficientes βs comienzan a reducirse a cero y el modelo es más flexible aumenta a medida que incrementamos **s**, cuando **s** y el sesgo del modelo disminuye.

e)	Para el error irreducible (ruido).
Inciso v) permanece constante. Esto se debe a que el error irreducible, o ruido, es independiente del modelo, por lo tanto, no cambia con este método de regularización.

5. **It is well-known that ridge regression tends to give similar coefficient values to correlated variables, whereas the lasso may give quite different coefficient values to correlated variables. We will now explore this property in a very simple setting. Suppose that n = 2, p = 2, x11 = x12, x21 = x22. Furthermore, suppose that y1+y2 = 0 and x11+x21 = 0 and x12+x22 = 0, so that the estimate for the intercept in a least squares, ridge regression, or lasso model is zero: β0 = 0.**
___

a) Write out the ridge regression optimization problem in this setting.

**R** como sabemos que x11=x12=x1 and  x21=x22=x2, entonces podemos escribir que la regresión Ridge busca regularizar el siguiente problema: 

![2020-05-15_16-04-06](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_16-04-06.png)

b) Argue that in this setting, the ridge coefficient estimates satisfy β1 =  β2.

**R** Para probar esto es necesario sacar la  derivada de la expresión anterior con respecto a  β1 y β2 e igualarla a 0. Obteniendo las siguientes dos expresiones: 

![2020-05-15_16-15-40](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_16-15-40.png)

c) Write out the lasso optimization problem in this setting.

**R** como sabemos que x11=x12=x1 and  x21=x22=x2 podemos escribir que el problema que busca resolver Lasso es el siguiente:

![2020-05-15_16-25-55](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_16-25-55.png)


d) Argue that in this setting, the lasso coefficients  β1 and β2 are not unique—in other words, there are many possible solutions to the optimization problem in (c). Describe these solutions.

**R** Partimos utilizando la otra forma de Lasso 

![2020-05-15_18-33-06](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_18-33-06.png)

sabemos que en el plano Lasso toma la siguiente forma en donde las intersecciones están a una distancia s del origen:

![2020-05-15_18-34-10](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_18-34-10.png)

Pero también sabemos por las condiciones del problema que: 

![2020-05-15_18-39-51](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_18-39-51.png)

entonces podemos reducir la expresión a:
 
![2020-05-15_18-43-07](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_18-43-07.png)

podemos entonces determinar que la solución del problema es: β1+β2=y1/x2. Esto lo podemos observar en la gráfica como una linea paralela al borde del rombo formado. Las soluciones de lasso son los contornos que se pueden ver como

![2020-05-15_18-49-39](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_18-49-39.png)

que intersecta al rombo en la esquina. 
Podemos también determinar que todo el borde β1+β2=s y el β1+β2=-s son posibles soluciones. Entonces podemos decir que en realidad existe un conjunto de soluciones (que está dado por dos segmentos de recta) para lasso y no solo una que sería:

![2020-05-15_19-05-07](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_19-05-07.png)


6. 
a) Probar que la expresión 6.14 es solución de la expresión de Ridge 6.12 con valor de p=1, y cualquier valor, lambda mayor que cero y esto graficado en función de un intervalo de beta.

**R:** primero vamos a guaradr el método de Ridge en una función, posteriormente vamos a verificar en un rango de betas, donde el valor de p = 1, y cualquier valor de yi, donde nuestro gráfico debe de confirmar que la solución de la ecuación 6.14. para que exista solución debe de haber una intersección. Vamos a graficar con respecto de β, que le dimos un intervalo de -5 a 5 con un paso de 0.1.

```r
y = 5   # establecemos un valor arbitrario de y
lambda = 5   # escogemos un valor para labda mayor a cero
beta = seq(-5, 5, 0.1)   #definimos el intervalo de β
plot(beta, (y - beta)^2 + lambda * beta^2, pch = 20,lwd = 5, xlab = "betas", ylab = "optimización de Ridge")   #dibujamos la grafica, p=1
solved_beta = y/(1 + lambda)  # agregamos la función propuesta, que es solución de la ecuacion 6.12
points(solved_beta, (y - solved_beta)^2 + lambda * solved_beta^2, col = 2, lwd = 6, cex = solved_beta)# agregamos el punto, mientras que cruce con la gráfica es solución
```

![grafica](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_a_1.png)

De la gráfica anterior el punto rojo simboliza la intersección de la solución alternativa de Beta=y/(1+lambda).

b) considerar la expresión 6.13 con p= 1 para algun valor de y y lambda mayor a cero, graficar como una función de beta, la gráfica debe confirmar que 6.15 es solución de 6.14.

```r
y = 5 #definimos una y con cualquier valor
lambda = 5 # definimos lambda mayor que cero, cualquier valor
beta = seq(-5, 5, 0.01)   #definimos el intervalo de las betas de -5 a 5 con paso de 0.1
plot(beta, (y - beta)^2 + lambda * abs(beta),lwd = 2, xlab = "beta", ylab = "optimización de Lasso") #graficamos la expresión de Lasso, respecto de las betas
solved_beta = y - lambda/2  #la expresión solución para lasso
points(solved_beta, (y - solved_beta)^2 + lambda * abs(solved_beta), col = 2, pch = 4, lwd = 5, cex = est.beta) #indicamos la intersección de la solución de Lasso, la cual debe de intersectar en algún lugar de la gráfica de la expresión de lasso
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_b_1.png)

7. **We will now derive the Bayesian connection to the lasso and ridge regression discussed in Section 6.2.2**
___

a) Write out the likelihood for the data.

**R** La verosimilitud la podemos expresar como:

![2020-05-15_19-39-05](2020-05-15_19-39-05.png)

b) Assume the following prior for β: β1, . . . , βp are independent and identically distributed according to a double-exponential distribution with mean 0 and common scale parameter b. Write out the posterior for β in this setting.

**R** Sabemos que:

![2020-05-15_19-49-31](2020-05-15_19-49-31.png)

c) Argue that the lasso estimate is the mode for β under this posterior distribution.

**R** Del inciso anterior podemos factorizar la parte exponencial obteniendo: 

![2020-05-15_20-21-40](2020-05-15_20-21-40.png)

![2020-05-15_20-21-53](2020-05-15_20-21-53.png)

![2020-05-15_20-22-04](2020-05-15_20-22-04.png)

d) Now assume the following prior for β: β1, . . . , βp are independent and identically distributed according to a normal distribution with mean zero and variance c. Write out the posterior for β in this setting.

**R** Podemos escribir que:

![2020-05-15_20-39-34](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_20-39-34.png)

e)Argue that the ridge regression estimate is both the mode and the mean for β under this posterior distribution. 

**R** Podemos pobrar esto como en el inciso c) fijando un λ específico:
Del inciso anterior podemos sacar logaritmo de ambos lados.

![2020-05-15_20-59-29](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_20-59-29.png)

![2020-05-15_20-59-45](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_20-59-45.png)


8. In this exercise, we will generate simulated data, and will then use this data to perform best subset selection.

**a) Usar la función rnorm() para generar un predictor X de tamaño n=100 asi como un vector de ruido de n=100.**

```r
set.seed(1) # creamos la semilla
X = rnorm(100) #generamos la función x con n=100
ruido = rnorm(100) # generamos el vector de ruido
```

**b) Generar un vector de respues Y de longitud n = 100 de acuerdo con el modelo Y = β0 + β1X + β2X^2+β3X^2+ ruido donde β0, β1, β2 y β3 son constantes que uno escoge.**

```r
beta0 = 5  # definimos a nuestras constantes betas
beta1 = -2
beta2 = 3
beta3 = 0.2
Y = beta0 + beta1 * X + beta2 * X^2 + beta3 * X^3 + ruido  # definimos la expresión para el vector Y
```

**c) Utilice la función regsubsets() para encontrar la mejor seleción de predictores, ¿Cuál es el mejor valor ajustado segun cp, BIC y R2? utilice graficas para probar su respuesta.**

Pára generar el dataframe necesitamos de la libreria leaps, poteriormente generamos el polinomio hasta llegar a grado 10, esto como lo indica el inciso, después la función regsubsets() nos va a regresar los modelos y debemos buscar el mejor modelo de acuerdo con el valor de cp (estadístico Cp de Mallows), BIC(criterio de infromación bayesiano) y R2 (coeficiente de determinación), y considerando que cada modelo generado va desde 1 hasta 10 variables, estosnces busca el mejor modelo para un numero de variables.

```r
library(leaps)   # importamos la libreria para poder trabajar con dataframes
modelo = data.frame(y = Y, x = X) #asignamos el dataframe
modelo.regresion = regsubsets(y ~ poly(x, 10, raw = TRUE), data = modelo, nvmax = 10) #buscamos los mejores 10 coefientes de x
modelo.summary = summary(modelo.regresion)  # de los modelo generamos, guardamos todos y buscamos el mejor
```

```r
#generamos la gráfica de cp
plot(modelo.summary$cp, xlab = "Número de variables", ylab = "C_p", type = "l") 
points(which.min(modelo.summary$cp), modelo.summary$cp[which.min(modelo.summary$cp)], col = 2, cex = 2, pch = 20,lwd = 5)

#generamos la gráfica de BIC
plot(modelo.summary$bic, xlab = "Número de variables", ylab = "BIC", type = "l")
points(which.min(modelo.summary$bic), modelo.summary$bic[which.min(modelo.summary$bic)], col = 2, cex = 2, pch = 20,lwd = 5)

#generamos la gráfica de R^2
plot(modelo.summary$adjr2, xlab = "Número de variables", ylab = "Adjusted R^2", type = "l")
points(which.max(modelo.summary$adjr2), modelo.summary$adjr2[which.max(modelo.summary$adjr2)], col = 2, cex = 2, pch = 20,lwd = 5)
```

buscamos que el coefiente cp o estadístico de Mallow sea mínimo, en la siguiente gráfica se puede ver que el estadístico Mallow o cp contra el numero de variables.  El punto rojo indica donde se encuentra el valor mas pequeño.

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_c_1.png)

Buscamos que el BIC o críterio bayesiano sea el mínimo posible, en la siguiente gráfica podemos ver el valor BIC contra el numero de variables. El punto rojo indica donde se encuentra el valor mas pequeño.

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_c_2.png)

Buscamos que el valor R^2 sea muy grande, en la siguiente grafica podemos ver como una cruz en rojo que indica donde el valor de la gráfica de R^2 contra las variables es mas grande.

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_c_3.png)

en todos coincide que es en en las tres variables, luego vemos los coeficientes para ese caso en específico con la siguiente función en R.

```r
coef(modelo.regresion, which.max( modelo.summary$adjr2)) #buscamos el mejor ajuste y encontramos los coeficientes del modelo
# también se puede usar el método coef(modelo.regresion, id = 3) donde buscamos solo con un identificdor del numero de variables. ambos métodos nos dan el mismo resultado
```

**R**
(Intercept): 5.0762283505285

poly(x, 10, raw = TRUE)1:-1.78069755335632

poly(x, 10, raw = TRUE)2:2.8419935402321

poly(x, 10, raw = TRUE)7:0.00764952811755896

Los coeficientes son muy aproximados a los propuestos en el modelo Y.

**d) Hacemos lo mismo que el inciso c) pero para forward y backward selection.**

Con la misma función regsubsets() podemos seleccionar al final el tipo de selección de variables que deseamos, en este caso se eligió primero selección hacia adelante o Forward y luego la selección hacia atras o backward partiendo del hecho que nuestro que nuestro modelo se guardo en y, Y = y, en ele ejericio anterior por lo que no es necesario repetirlo.

```r
#método de seleción de variables forward y backward
modelo.forward = regsubsets(y ~ poly(x, 10, raw = T), data = data.full, nvmax = 10, method = "forward")  #calculamos el modelo con selección de variables hacia adelante
modelo.backward = regsubsets(y ~ poly(x, 10, raw = T), data = data.full, nvmax = 10, method = "backward") #calculamos el modelo con la selección de variables hacia atrás
modelo.forward.summary = summary(modelo.forward)  
modelo.backward.summary = summary(modelo.backward)
```

primero revisamos el método hacia adelante y vemos el numero de variables que selecciona cuando cp es mínimo, BIC es mínimo y R^2 es máximo, eso nos va a indicar el numero de variables preferentes que ha escogido el método de seleccion de variables hacia adelante.

```r
par(mfrow = c(2, 2))
plot(modelo.forward.summary$cp, xlab = "Número de variables", ylab = "Forward Cp, estadístico Mallow", pch = 20, type = "l") # graficamos CP
     
points(3, modelo.forward.summary$cp[3], pch = 20, col = 3, lwd = 7) 
plot(modelo.forward.summary$bic, xlab = "Número de variables", ylab = "Forward BIC", pch = 20, type = "l") #graficamos BIC
points(3, modelo.forward.summary$bic[3], pch = 20, col = 3, lwd = 7)
plot(modelo.forward.summary$adjr2, xlab = "Número de variables", ylab = "Forward R^2", pch = 20, type = "l") #graficamos R^2
points(3, modelo.forward.summary$adjr2[3], pch = 20, col = 3, lwd = 7)
mtext("Gráficas de ajuste por selección hacia adelante inidicando cp, BIC y R^2", side = 3, line = -2, outer = TRUE)
```

Indicamos con un punto de color verde en las gráficas donde se encuentra el mínimo valor de cp y BIC dependiendo del numero de variables escogidas para nuestro modelo y el máximo valor de R^2. En la siguiente imágen se ven agrupadas las gráficas.

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_8_d_1.png)

Para el método de selección de variables hacia atrás vamos a proceder a gráficar el cp, BIC y el R^2 buscando en los dos primeros el mínimo en las gráficas y en R^2 buscando el máximo. Los puntos mínimos y máximos estan indicados con un punto verde.

```r
par(mfrow = c(2, 2))
plot(modelo.backward.summary$cp, xlab = "Número de variables", ylab = "Forward Cp, estadístico Mallow", pch = 20, type = "l")
points(3, modelo.backward.summary$cp[3], pch = 20, col = 4, lwd = 7)
plot(modelo.backward.summary$bic, xlab = "Número de variables", ylab = "Forward BIC", pch = 20, 
    type = "l")
points(3, modelo.backward.summary$bic[3], pch = 20, col = 4, lwd = 7)
plot(modelo.backward.summary$adjr2, xlab = "Número de variables", ylab = "Forward R^2", 
    pch = 20, type = "l")
points(3, modelo.backward.summary$adjr2[3], pch = 20, col = 4, lwd = 7)
mtext("Gráficas de ajuste por selección hacia atrás inidicando cp, BIC y R^2", side = 3, line = -2, outer = TRUE)
```

Como podemos observar en las gráficas el mínimo, y el máximo en el caso de R^2, se encuentran en el numero de variables igual a tres. Los puntos mínimos y máximos, segun el tipo de gráfica, estan indicados de color azul.

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_8_d_2.png)

Ahora vamos a extraer los coeficientes ideales de la regresión, con tres variables, tanto para el método de backward como fordward.

```r
coefficients(modelo.forward, id = 3) # obtenemos el modelo a partir selección hacia adelante
```

(Intercept) = 5.0762283505285

poly(x, 10, raw = T)1:-1.78069755335632

poly(x, 10, raw = T)2:2.8419935402321poly

(x, 10, raw = T)7:0.00764952811755898

```r
coefficients(modelo.forward, id = 3) #obtenemos el modelo a partir de selección hacia atrás
```
(Intercept) = 5.07917829297518

poly(x, 10, raw = T)1:-1.73735728547462

poly(x, 10, raw = T)2:2.83173910146723

poly(x, 10, raw = T)9:0.00138563699722447

En el método de selección de variables hacia adelante se parte de todos los predictores y se van eliminando los que no son significativos para el modelo, al contrario de la selección hacia atrás donde la selección de las variables se hace por las que mas influyen y se agregan al modelo, en ambos resultados son parecidos al modelo original, notamos algunas diferencias significativas solo en el tercer término.

e) Ahora ajustamos el método de Lasso a los modelos generamos desde X hasta X^10. Aquí vamos a usar validación cruzada o cross validation para selecciónar el óptimo valor de lambda.

Para utilizar Lasso necesitamos ocupar la libreria "glmnet" 

```r
library(glmnet)
modelos = model.matrix(y ~ poly(x, 10, raw = T), data = data.full)[, -1] # Aplicamos todos los modelos posibles con x hasta x^10
modelos.lasso = cv.glmnet(xmat, Y, alpha = 1) #Aplicamos validación cruzada, para encontrar que variables sirven
min.lambda = mod.lasso$lambda.min  #encontreamos el valor para el cual lambda es mínima a través del método de Lasso
min.lambda
```
El valor mínimo de lambda es 0.0440506397617391 para nuestro modelo.

Ahora que sabemos el valor mínimo de lambda podemos predecir el valor óptimo de los coeficientes. 

```r
min_modelo = glmnet(modelos, Y, alpha = 1) # aplicamos el mejor modelo 
predict(min_modelo, s = min.lambda, type = "coefficients") #utilizamos la lambda mínima para encontrar los mejores coeficientes
```

(Intercept)             5.152664162

poly(x, 10, raw = T)1  -1.622329543

poly(x, 10, raw = T)2   2.630760960

poly(x, 10, raw = T)3   .          

poly(x, 10, raw = T)4   0.044064200

poly(x, 10, raw = T)5   .        

poly(x, 10, raw = T)6   .       

poly(x, 10, raw = T)7   .       

poly(x, 10, raw = T)8   .     

poly(x, 10, raw = T)9   0.000999706

poly(x, 10, raw = T)10  .          

Son valores muy aproximados al modelo original, el termino elevado a la novena potencia es despreciable debido al bajo valor que tiene y en vez de escoger el tercer término al cubo lo escogió a una potencia superior a la esperada.

Graficamos todos los valores generados por le método de Lasso con respecto de lambda con la siguiente función me R

```r
plot(modelos.lasso) #graficamos los valores de lambda optenidos por el método de lasso contra el promedio del error cuadratico
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_8_e_1.png)

f) ahora vamos a generar otro modelo para Y de la siguiente forma Y = β0 + β1*X^7 + error, aplicando los métodos anteriormente 

```r
Y = 2 + 6*X^7+ ruido # generamos el modelo con los valores de X generados anteriormente, con X^7
datos = data.frame(y=Y,x=X) # generamos el dataframe
modelos_todos = regsubsets(y ~ poly(x, 10, raw = T), data = datos, nvmax = 10) # generamos todos los posibles modelos
modelo.summary = summary(modelos_todos) # simplificamos los datos con la función summary

which.min(modelo.summary$cp) # buscamos el numero de variables por cp para buscar el número de variables
```

Resultado de 2 variables

```r
which.min(modelo.summary$bic) #buscamos el valor minimo BIC para el número de variables
```

Resultado de 1 variable

```r
which.max(modelo.summary$adjr2) #buscamos el valor mpinimo para R^2 para buscar el número de variables
```

Resultado de 4 variables

```r
coefficients(modelos_todos, id = 2) # vemos los coeficientes que corresponden para cada seleción de variables
```

(Intercept):2.07049036762632

poly(x, 10, raw = T)2:-0.141708425295775

poly(x, 10, raw = T)7:6.00155518856388

```r
coefficients(modelos_todos, id = 1) # vemos los coeficientes que corresponden para cada seleción de variables
```

(Intercept):1.958940246745

poly(x, 10, raw = T)7:6.00077047427057

```r
coefficients(modelos_todos, id = 4) # vemos los coeficientes que corresponden para cada seleción de variables
```

(Intercept):2.07625244968328

poly(x, 10, raw = T)1:0.291401607644686

poly(x, 10, raw = T)2:-0.161767130528645

poly(x, 10, raw = T)3:-0.252652678281635

poly(x, 10, raw = T)7:6.00913375439678

```r
modelos = model.matrix(y ~ poly(x, 10, raw = T), data = data.full)[, -1] # escojemos todos los modelos, con todos los coeficientes con x hasya x^10
modelo.lasso = cv.glmnet(modelos, Y, alpha = 1)  # luego buscamos el mejor modelo por validción cruzada por el método de lasso
min.lambda = modelo.lasso$lambda.min

```

```r
mejor.modelo = glmnet(modelos, Y, alpha = 1) #generamos los pomelos por el método de lasso
predict(mejor.modelo, s = best.lambda, type = "coefficients") # generamos el mejor modelo
```

(Intercept)            2.697189 .

poly(x, 10, raw = T)1  .    

poly(x, 10, raw = T)2  .    

poly(x, 10, raw = T)3  .    

poly(x, 10, raw = T)4  .   

poly(x, 10, raw = T)5  .  

poly(x, 10, raw = T)6  .      

poly(x, 10, raw = T)7  5.825845 .

poly(x, 10, raw = T)8  .  

poly(x, 10, raw = T)9  .    

poly(x, 10, raw = T)10 .   

La mejor selección fue hecha por la selelción de Lasso 

9. **In this exercise, we will predict the number of applications received using the other variables in the College data set.**
a) Split the data set into a training set and a test set.
___

**R**
```r
library(ISLR)
data(College)
set.seed(11)
train = sample(1:dim(College)[1], dim(College)[1] / 2)
test <- -train
Train <- College[train, ]
Test <- College[test, ]
summary(Test)
summary(Train)
```
```> dim(Test)
[1] 389  18
> dim(Train)
[1] 388  18
```
 b) Fit a linear model using least squares on the training set, and
report the test error obtained.

**R**
```r
fit <- lm(Apps ~ ., data = Train)
pred<- predict(fit, Test)
mean((pred - Test$Apps)^2)
```
```
[1] 1538442
```
el error medio residual del set de prueba con la regresión lineal es de 1026096

c) Fit a ridge regression model on the training set, with λ chosen by cross-validation. Report the test error obtained.

**R** 
```r
library(glmnet)
train_ridge <- model.matrix(Apps ~ ., data = Train)
test_ridge <- model.matrix(Apps ~ ., data =Test)
lam<- 10 ^ seq(4, -2, length = 100)
Ridge <- glmnet(train_ridge, Train$Apps, alpha = 0, lambda = lam, thresh = 1e-12)
Ridge_cv <- cv.glmnet(train_ridge,Train$Apps, alpha = 0, lambda = lam, thresh = 1e-12)
mejor_cv <- Ridge_cv$lambda.min
mejor_cv
```
La menor lambda es
```
1] 18.73817
```
```r
ridge_test <- predict(Ridge, s = mejor_cv, newx = test_ridge)
print("media")
mean((ridge_test - Test$Apps)^2)
```

```
1608859
```
La media es mayor a la obtenida por mínimos cuadrados.

d) Fit a lasso model on the training set, with λ chosen by crossvalidation. Report the test error obtained, along with the number of non-zero coefficient estimates.

Primero realizamos cross validation.
```r
Lasso <- glmnet(train_ridge, Train$Apps, alpha = 1, lambda = lam, thresh = 1e-12)
lasso_cv <- cv.glmnet(train_ridge, Train$Apps, alpha = 1, lambda =lam, thresh = 1e-12)
mejor_lam <- lasso_cv$lambda.min
mejor_lam
```
```
## [1] 21.54435
```
```r
lasso_pred <- predict(Lasso, s = mejor_lam, newx = ridge_test)
mean((lasso_pred - Test$Apps)^2)
```
```
## [1] 1635280
```
La media también es mayor a los dos métodos anteriores.

```r
predict(Lasso, s = mejor_lam, type = "coefficients")
```
Los coeficientes son
```
## 19 x 1 sparse Matrix of class "dgCMatrix"
##                         1
## (Intercept) -836.50402310
## (Intercept)    .         
## PrivateYes  -385.73749394
## Accept         1.17935134
## Enroll         .         
## Top10perc     22.70211938
## Top25perc      .         
## F.Undergrad    0.07062149
## P.Undergrad    0.01366763
## Outstate      -0.03424677
## Room.Board     0.01281659
## Books         -0.02167770
## Personal       .         
## PhD           -1.46396964
## Terminal      -5.17281004
## S.F.Ratio      5.70969524
## perc.alumni   -9.95007567
## Expend         0.14852541

```
e) Fit a PCR model on the training set, with M chosen by crossvalidation. Report the test error obtained, along with the value of M selected by cross-validation.

**R**
```r
library(pls)
pcr<- pcr(Apps ~ ., data = Train, scale = TRUE, validation = "CV")
validationplot(pcr, val.type = "MSEP")

```
![2020-05-15_21-56-24](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_21-56-24.png)


```r
pcr_pred<- predict(pcr, Test, ncomp = 10)
mean((pcr_pred - Test$Apps)^2)
```
entonces el MSE es 
```
## [1] 3014496
```
que también es más alto que mínimos cuadrados

f)Fit a PLS model on the training set, with M chosen by crossvalidation. Report the test error obtained, along with the value of M selected by cross-validation.

**R**
```r
pls <- plsr(Apps ~ ., data = Train, scale = TRUE, validation = "CV")
validationplot(pls, val.type = "MSEP")
```
![2020-05-15_23-06-52](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_23-06-52.png)

```r
pls_pred <- predict(pls, Test, ncomp = 10)
mean((pls_pred - Test$Apps)^2)
```
```      
1508987
```
Podemos observar que finalmente el MSE para pls es mejor que el de mínimos cuadrados y los demás métodos.

g) Comment on the results obtained. How accurately can we predict the number of college applications received? Is there much difference among the test errors resulting from these five approaches?

**R**
Podemos observar que tantos datos puede predecir cada método calculando su R^2:
```r
prom_test<- mean(Test$Apps)
r2_lineal <- 1 - mean((pred - Test$Apps)^2) / mean((prom_test - Test$Apps)^2)
r2_ridge <- 1 - mean((ridge_test - Test$Apps)^2) / mean((prom_test - Test$Apps)^2)
r2_lasso <- 1 - mean((lasso_pred - Test$Apps)^2) / mean((prom_test - Test$Apps)^2)
r2_pcr <- 1 - mean((pcr_pred - Test$Apps)^2) / mean((prom_test - Test$Apps)^2)
r2_pls<- 1 - mean((pls_pred - Test$Apps)^2) / mean((prom_test - Test$Apps)^2)
r2_lineal
r2_ridge
r2_lasso 
r2_pcr
r2_pls
```
```
0.9044281
0.9000536
0.8984123
0.8127319
0.9062579
```
Podemos entonces observar que todos los modelos predicen casi con la misma veracidad con excepción de pcr que lo hace un poco peor.


10. We have seen that as the number of features used in a model increases, the training error will necessarily decrease, but the test error may not. We will now explore this in a simulated data set.
**a) Genere un set de datos con p = 20 carcterísticas, y 1000 observaciones y es generado por el vector Y de la siguiente forma. Y = βX + ruido** donde beta tiene algunos valores iguales a cero

```r
set.seed(1) # creamos la semilla
p = 20
n = 1000
x = matrix(rnorm(n*p),n,p) # genreamos una matriz con valores normales de tamaño n por p
beta = rnorm(p) #generamos la función x con n=1000
h = sample(1:20,5,replace = FALSE) #generamos numeros aleatorios
for (i in 1:5)
    beta[h[i]]=0  #hacemos algunas betas iguales a cero
ruido = rnorm(p) # generamos el vector de ruido
y = x %*% beta + ruido # generamos el modelo
```

**b) vamos a dividir nuestro data set en 100 observaciones y otras 900 van a ser en el set de entrenamiento.**

```r
train = sample(1:1000,100,replace = FALSE) #generamos los 900 datos de entrenamiento y 100 de test
train_y = y[train, ]  #generamos el set de entrenamiento
test_y = y[-train, ]  #generamos el set de test
train_x = x[train, ]
test_x = x[-train, ]
```

**c) Realizar la mejor selelción del conjunto de entrenamiento, y graficar el mejor conjunto MSE para el mejor modelo de cada tamaño.**

```r
modelo = data.frame(y = train_y, x = train_x) #generamos el dataframe
modelo_comp = regsubsets(y ~ ., data = modelo, nvmax = 20)
modelos_matrix = model.matrix(y ~ ., data = modelo, nvmax = 20)
valores = rep(0, 20) #replicamos los elementos de una lista, esto es generar una lista de tamaño 20 con todos los elemntos iguales a cero.
for (i in 1:20) {
    coeficientes = coef(modelo_comp, id = i) #evaluamos cada modelo generado a través del identificador i, como en el problema 8
    pred = modelos_matrix[, names(coeficientes)] %*% coeficientes 
    valores[i] = mean((pred - train_y)^2)
}
plot(valores, xlab = "Número de predictores", ylab = "set de entrenamiento MSE", pch = 20,type="b") #graficamos cada numero de variables, que van de cero a veinte contra en promedio del error cuadrado del set de entrenamiento
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_10_c_1.png)

**d) hacemos lo mismo del inciso c) para los valores de test.

```r
modelo_test = data.frame(y = test_y, x = test_x) # generamos el dataframe
modelo_test_matrix = model.matrix(y ~ ., data = modelo_test, nvmax = 20) #
valores = rep(0, 20)  # generamos una lista de 0 a 20 llena de ceros
for (i in 1:20) {
    coefi = coef(modelo_comp, id = i)
    pred = modelo_test_matrix[, names(coefi)] %*% coefi
    valores[i] = mean((pred - test_y)^2) #en la lista de valores guaradamos el promedio con cierto número de variables
}
plot(valores, xlab = "Número de predictores", ylab = "set de prueba MSE", pch = 19, type = "b") # generamos la gráfica de todos los posibles modelos, de 0 a 20 pero con los datos del set de entrenamiento
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_10_d_1.png)

**e) para que tamaño del modelo del conjunto de pruebas MSE toma el valor mínimo **

Esto se hace obteniendo el mpinimo valor para el conjunto de valores donde guardamos el error promedio cuadratico MSE.

```r
which.min(valores) # buscamos el valor mínimo de MSE del set de test
```

Es de 15 el valor minimo, por lo tanto con 16 variables tenemos el menor MSE.

**f) buscar el modelo**

```r
coef(modelo_comp, id = 15) # buscamos el modelos, los valores de los coeficientes, con el identificador 
```

(Intercept):0.0256087383675092
x.3:-0.53582873825561
x.5:1.1269288270941
x.6:-0.25244655631405
x.7:-1.34435865450564
x.8:0.796874849061235
x.9:1.95206949671049
x.10:0.851635786060172
x.11:0.878751185630349
x.12:0.611389941030793
x.13:-0.33796868154489
x.15:-0.729064926766218
x.17:0.311682540214127
x.18:1.68638798437704
x.19:0.933290118604291
x.20:-1.03163757315562

**g) crear un gráfico en el que se muestre la expresión mostrada anteriormente.

```r
valores = rep(0, 20) #generamos la lista de los 20 valores
x_cols = colnames(x, do.NULL = FALSE, prefix = "x.")
for (i in 1:20) {
    coeficientes <- coef(modelo_comp, id = i) #escogemos los coefientes del modelo_comp
    valores[i] <- sqrt(sum((beta[x_cols %in% names(coeficientes)] - coeficientes[names(coeficientes) %in% x_cols])^2) + sum(beta[!(x_cols %in% names(coeficientes))])^2)
} #aplicamos la expresión del inciso del ejericcio
plot(valores, xlab = "Número de coeficientes", ylab = "Error entre coeficientes estimados y los coeficientes", pch = 19, type = "b")
```

![](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/6_10_e_1.png)

el mínimo valor es 15.

**11. We will now try to predict per capita crime rate in the Boston data set.** 
___

a) Try out some of the regression methods explored in this chapter, such as best subset selection, the lasso, ridge regression, and PCR. Present and discuss results for the approaches that you consider.

**R** Primero tenemos que elegir el mejor subconjunto a utilizar en el modelo, para esto, utilizamos cross validation, utilizando 20 folds como k:


```r
library(MASS)
library(leaps)
data(Boston)
set.seed(1)
###del laboratorio del libro
predict.regsubsets <- function(object, newdata, id, ...) {
  form <- as.formula(object$call[[2]])
  mat <- model.matrix(form, newdata)
  coefi <- coef(object, id = id)
  xvars <- names(coefi)
  mat[, xvars] %*% coefi
}


k = 20 ###se hacen los folds 
folds <- sample(1:k, nrow(Boston), replace = TRUE)
cv.errors <- matrix(NA, k, 13, dimnames = list(NULL, paste(1:13)))
for (j in 1:k) {
  best.fit <- regsubsets(crim ~ ., data = Boston[folds != j, ], nvmax = 13)
  for (i in 1:13) {
    pred <- predict(best.fit, Boston[folds == j, ], id = i)
    cv.errors[j, i] <- mean((Boston$crim[folds == j] - pred)^2)
  }
}
mean.cv.errors <- apply(cv.errors, 2, mean)
mean.cv.errors
plot(mean.cv.errors, type = "b", xlab = "Number of variables", ylab = "CV error") 
```
```
   1        2        3        4        5        6        7        8        9 
45.85516 43.99675 44.97814 45.52512 44.84868 44.89512 44.21741 43.64725 43.11899 
      10       11       12       13 
43.18569 43.19659 43.03855 43.15379 
```
![2020-05-15_23-46-35](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_23-46-35.png)

Podemos observar que el menor error es con 12 variables, por lo que el modelo se hará así. 

LASSO
 ```r  
x1 <- model.matrix(crim ~ ., Boston)[, -1]
y2 <- Boston$crim
Lasso <- cv.glmnet(x, y, alpha = 1, type.measure = "mse")
plot(Lasso)
Lasso$lambda.min
```
![2020-05-15_23-52-29](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_23-52-29.png)

```
0.0513069
```
Podemos observar una lambda de 0.0513069

RIDGE 
```r 
Ridge <- cv.glmnet(x1, y1, alpha = 0, type.measure = "mse")
plot(Ridge)
Ridge$lambda.min
 ``` 
![2020-05-15_23-59-54](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-15_23-59-54.png)

```
0.5374992
```
con ridge tenemos una lambda de 0.5374992

PCR
```r
library(pls)
pcr <- pcr(crim ~ ., data = Boston, scale = TRUE, validation = "CV")
summary(pcr)
validationplot(pcr, val.type = "MSEP")
```
```
Data:     X dimension: 506 13 
    Y dimension: 506 1
Fit method: svdpc
Number of components considered: 13

VALIDATION: RMSEP
Cross-validated using 10 random segments.
       (Intercept)  1 comps  2 comps  3 comps  4 comps  5 comps  6 comps  7 comps
CV            8.61    7.194    7.194    6.751    6.747    6.752    6.781    6.774
adjCV         8.61    7.192    7.191    6.747    6.740    6.748    6.775    6.767
       8 comps  9 comps  10 comps  11 comps  12 comps  13 comps
CV       6.652    6.664     6.656     6.662     6.631     6.561
adjCV    6.644    6.657     6.648     6.652     6.620     6.550

TRAINING: % variance explained
      1 comps  2 comps  3 comps  4 comps  5 comps  6 comps  7 comps  8 comps
X       47.70    60.36    69.67    76.45    82.99    88.00    91.14    93.45
crim    30.69    30.87    39.27    39.61    39.61    39.86    40.14    42.47
      9 comps  10 comps  11 comps  12 comps  13 comps
X       95.40     97.04     98.46     99.52     100.0
crim    42.55     42.78     43.04     44.13      45.4
```
![2020-05-16_00-09-38](https://github.com/alex309-duarte/Proyecto-2/blob/master/tarea_capitulo_6/imagenes/2020-05-16_00-09-38.png)

Observamos que en pcr, la validación cruzada toma todos las variables disponibles, por lo que no hay reducción de dimensión.

b) Propose a model (or set of models) that seem to perform well on this data set, and justify your answer. Make sure that you are evaluating model performance using validation set error, crossvalidation, or some other reasonable alternative, as opposed to using training error.
**R**
Podemos observar de los modelos elegidos anteriormente que el que presenta un menor error de validación cruzada es en este caso el primero, Lasso, ya que en promedio tiene menor error (observando las gráficas)

c) Does your chosen model involve all of the features in the data set? Why or why not?

**R**
No, elegiríamos el modelo de Lasso con 12 variables ya que es el que tiene menor error de validación cruzada.

