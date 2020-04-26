## Ejercicios

###### Samuel Romero Santiago
###### Manuel Alejandro Cardoso Duarte

#### 1) Which plane (check the tail number) flew out of each New York airport the most?
---
**R**. Consideramos a tail number como el vuelo, de ahi filtramos estos valores ya que contienen valores nulos, posteriormente debemos agrupar a tialnum con el origin que es el origen, todos parten de Nueva York. Para resolver el ejercicio debemos buscar cuantas veces se repite el numero de vuelo (tailnum) en cada aeropuerto de origen.

```r
library(dplyr)
library(nycflights13)    #dataset de todos los vuelos de los aeropuertos de Nueva York en el año 2013

flights %>%
filter(tailnum != "NA") %>%    #filtramos los valores nulos, tambien se puede hacer con la función filter(!is.na(tailnum))
group_by(origin,tailnum) %>%   # agrupamos por origen, los tres aeropuertos de Nueva York, que es el origen
summarize(num_obs = n()) %>%    #agrupamos los datos por el numero de observaciones, reducimos las variables a numero de observaciones
arrange(origin,desc(num_obs)) %>%   #ordenamos de mayor a menor el numero de observaciones
slice(1)                     #tomamos la primera fila de cada agrupamiento origin.

 ```

Como resultado tenemos la siguiente tabla, donde viene el aeropuerto de origen, el numero de vuelo y el numero de vuelos realizados.

origin |	tailnum	| num_obs |
--- | --- | --- |
<chr> | <chr> | <int> |
EWR	| N15980 | 314 |
JFK	| N328AA | 393 |
LGA	| N725MQ | 567 |
    

#### 2) What was the shortest flight out of each airport in terms of distance? In terms of duration?
    
En términos de distancia, el vuelo más corto desde el aeropuerto EWR fue el 1632 con una distancia de 17 millas, para el aeropuerto JFK con una distancia de 94 millas los vuelos fueron más cortos fueron todos los vuelos que van hacia Filadelfia, y para el aeropuerto LGA los vuelos más cortos son de 96 millas, que son todos los vuelos que también van hacia Filadelfia.
Para el aeropuerto EWR los vuelos más cortos en término de tiempo (de 20 horas) fueron el 4368 y el 4631, para el aeropuerto JFK (con 21 horas)fue el vuelo 3650 y para el aeropuerto LGA (con 21 horas) fue el vuelo 2132

```R Script
suppressMessages(library(dplyr))
library(nycflights13)
flights=flights%>%tbl_df()
str(flights)
    
###### Por tiempo
flights%>%group_by(origin)%>%
  select(flight,air_time)%>%
  summarize( min(na.omit(air_time)))
```
~~~
Adding missing grouping variables: `origin`
# A tibble: 3 x 2
  origin `min(na.omit(air_time))`
  <chr>                     <dbl>
1 EWR                          20
2 JFK                          21
3 LGA                          21
~~~
```R
flights%>%filter(air_time==20,origin=="EWR")%>%select(origin,flight,air_time)
flights%>%filter(air_time==21,origin=="JFK")%>%select(origin,flight,air_time)
flights%>%filter(air_time==21,origin=="LGA")%>%select(origin,flight,air_time)
```
~~~
  origin flight air_time
  <chr>   <int>    <dbl>
1 EWR      4368       20
2 EWR      4631       20

###
  origin flight air_time
  <chr>   <int>    <dbl>
1 JFK      3650       21

###
  origin flight air_time
  <chr>   <int>    <dbl>
1 LGA      2132       21

~~~

```R
####### Por distancia
flights%>%group_by(origin)%>%
    summarize(min(distance))
```
~~~
 origin `min(distance)`
  <chr>            <dbl>
1 EWR                 17
2 JFK                 94
3 LGA                 96
~~~
```R
flights%>%filter(distance==17,origin=="EWR")%>%select(origin,flight,distance,dest)
flights%>%filter(distance==94,origin=="JFK")%>%select(origin,flight,distance,dest)
flights%>%filter(distance==96,origin=="LGA")%>%select(origin,flight,distance,dest)
```
~~~
 origin flight distance dest 
  <chr>   <int>    <dbl> <chr>
1 EWR      1632       17 LGA  
####
origin flight distance dest 
   <chr>   <int>    <dbl> <chr>
 1 JFK      4088       94 PHL  
 2 JFK      3664       94 PHL  
 3 JFK      3373       94 PHL  
 4 JFK      4088       94 PHL  
 5 JFK      3664       94 PHL  
 6 JFK      3667       94 PHL  
 7 JFK      3638       94 PHL  
 8 JFK      3689       94 PHL  
 9 JFK      3609       94 PHL  
10 JFK      3667       94 PHL  
# ... with 966 more rows
#####
   origin flight distance dest 
   <chr>   <int>    <dbl> <chr>
 1 LGA      1467       96 PHL  
 2 LGA      1833       96 PHL  
 3 LGA      1833       96 PHL  
 4 LGA      1833       96 PHL  
 5 LGA      1935       96 PHL  
 6 LGA      1569       96 PHL  
 7 LGA      1825       96 PHL  
 8 LGA      1153       96 PHL  
 9 LGA      1860       96 PHL  
10 LGA      1860       96 PHL  
# ... with 597 more rows
~~~
    
#### 3) Which date should you fly on if you want to have the lowest possible average departure delay? What about arrival delay?
---
**R:** Para resolver este ejercicio primero necesitamos agrupar los datos por año, mes y dia, una vez agrupados sacar un promedio por dia del tiempo de espera de los vuelos, porteriormente ordenar los tiempos de espera, los tiempos negativos indican que el vuelo salio antes, y seleccionamos el primer renglon que contiene el año, mes y dia en que el tiempo de espera fue menor. Aplicamos esta misma metodología para el tiempo de el tiempo de llegada.
    
```r
flights %>% 
group_by(year,month,day) %>%      #hacemos grupos por dia,mes y año que son las fechas, para poder obtener el promedio de cada dia posteriormente
summarize(dep_per_day = mean(dep_delay,na.rm = TRUE)) %>% #hacemos un promedio del tiempo de espera de cada dia, conjuntandolos con summarize
arrange(dep_per_day)     %>% #ordenamos las fechas de manera ascendente dependiendo del tiempo de espera dep_delay
group_by(year) %>%     # si no volvemos a agrupar por año, slice(1) da el tiempo mas bajo de dep_delay por cada mes
slice(1)               #escogemos la fecha con el departure delay mas bajo
```
    
Tenemos como resultado la siguiente información, correspondiente a la fecha con menos departure delay

year |	month | day |	dep_per_day |
--- | --- | --- | --- |
<int> | <int> | <int> | <dbl> |
2013 | 9 | 24 | -1.329832 |
    
```r
flights %>% 
group_by(year,month,day) %>%      #hacemos grupos por dia,mes y año que son las fechas, para poder obtener el promedio de cada dia posteriormente
summarize(arr_per_day = mean(arr_delay,na.rm = TRUE)) %>% #hacemos un promedio de arriavl delay de cada dia, y con los datos de agrupamiento
arrange(arr_per_day)     %>% #ordenamos las fechas de manera ascendente dependiendo del tiempo de arrival delay
group_by(year) %>%     # si no volvemos a agrupar por año, slice(1) da el tiempo mas bajo de arr_delay por cada mes
slice(1)               #escogemos la fecha con el arrival delay mas bajo
```
Tenemos como resultado la siguiente información, correpondiente a la fecha con menos arrival delay
    
year | month | day | arr_per_day |
--- | --- | --- | --- |
<int> | <int> | <int> | <dbl> |
2013 | 9 | 7 | -20.34985 |
    
 
    