2. **For parts (a) through (c), indicate which of i. through iv. is correct. Justify your answer.** 
___

**a)	Lasso relativo a mínimos cuadrados es:**

**R:** Inciso iii).  Es menos flexible y por tanto dará una precisión de predicción cuando se aumenta el sesgo y disminuye la varianza, la ventaja de Lasso se centra en encontrar el equilibrio de sesgo varianza, este método sirve para seleccionar variables, en el caso de que la varianza por mínimos cuadrados sea muy alta, Lasso puede lograr una reducción de la varianza por medio de aumentar el sesgo, esto por la relación sesgo varianza del modelo.

**b)	Regresión de Ridge relativa a mínimos cuadrados.**

**R:** Inciso iii). Tenemos el mismo caso que anteriormente, la diferencia entre Ridge y Lasso se centra en que Ridge no sirve para la selección de variables, pero sirve para disminuir la varianza de mínimos cuadrados. Esto funciona bien cuando tenemos una alta varianza en mínimos cuadrados ya que Ridge disminuye la varianza aumentando un poco el sesgo del modelo.

**c)	Métodos no lineales relativos a mínimos cuadrados.**

**R:** Inciso ii). Los métodos no lineales son más flexibles, tienen un sesgo menor pero un incremento en la varianza, se enfocan más en hacer un ajuste de los puntos mayor a través de otro tipo de funciones, esto sacrificando el aumento de la varianza.

4. **Suppose we estimate the regression coefficients in a linear regression model by minimizing**

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

6. 
a) probar que la expresión 6.14 es solución de la expresión de Ridge 6.12 con valor de p=1, y cualquier valor, lambda mayor que cero y esto graficado en función de un intervalo de beta.

**R:** primero vamos a guaradr el método de Ridge en una función, posteriormente vamos a berificar en un rango de betas, donde el valor de p = 1, y cualquier valor de yi, donde nuestro grafica debe de confirmar que la solución de la ecuación 6.14. para que exista solución debe de haber una intersección. Vamos a graficar con respecto de β, que le dimos un intervalo de -5 a 5 con un paso de 0.1.

```r
y = 5   # establecemos un valor arbitrario de y
lambda = 5   # escogemos un valor para labda mayor a cero
beta = seq(-5, 5, 0.1)   #definimos el intervalo de β
plot(beta, (y - beta)^2 + lambda * beta^2, pch = 20,lwd = 5, xlab = "betas", ylab = "optimización de Ridge")   #dibujamos la grafica, p=1
solved_beta = y/(1 + lambda)  # agregamos la función propuesta, que es solución de la ecuacion 6.12
points(solved_beta, (y - solved_beta)^2 + lambda * solved_beta^2, col = 2, lwd = 6, cex = solved_beta)# agregamos el punto, mientras que cruce con la gráfica es solución
```

![](6_a_1.png)

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

![](6_b_1.png)

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

![](6_c_1.png)

Buscamos que el BIC o críterio bayesiano sea el mínimo posible, en la siguiente gráfica podemos ver el valor BIC contra el numero de variables. El punto rojo indica donde se encuentra el valor mas pequeño.

![](6_c_2.png)

Buscamos que el valor R^2 sea muy grande, en la siguiente grafica podemos ver como una cruz en rojo que indica donde el valor de la gráfica de R^2 contra las variables es mas grande.

![](6_c_3.png)

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

![](6_8_d_1.png)
