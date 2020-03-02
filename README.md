# Proyecto-2
```r
#generamos 100 numeros aleatorios para x y y
x=sample(1:20,100,replace=T) 
y = sample(10:40,100,replace=T) 

datos=matrix(c(x,y),nrow=100,ncol=2)
#guardamos los datos como un documento csv
write.csv(datos, file="numeros_ale.csv")

#función para clusterizar considerando distancia euclidiana
#calculamos los puntos con la menor distancia a otros puntos y calculando los centros vemos los puntos mas cercanos

cluster<-function(x,y){
    #x es la lista (x,y) y y es el numero de cluster que deseamos
    elementos = dim(x)[1]
    m <- matrix(nrow=elementos,ncol=elementos)
    menores <- c(1:elementos)
    clust <- c(elementos)
    menos <- c(1:y)
    salida <- c(1:elementos)
    for(i in 1:elementos) {for(j in 1:elementos) m[i,j]=sqrt(((x[j,1]-x[i,1])^2)+((x[j,2]-x[i,2])^2))}
    for(i in 1:elementos) menores[i]=sum(m[i,])
    masgrand <- max(menores)
    color <- 2
    posicion <- c(0:elementos)*0+1
    for(i in 1:y) {menos[i]=which.min(menores)
        for(j in 1:elementos) {clust[j]=sqrt(((x[j,1]-x[menos[i],1])^2)+((x[j,2]-x[menos[i],2])^2))}
            for(j in 1:floor(elementos/y)){
                salida[j] <- which.min(clust)
                clust[salida[j]] = masgrand
                menores[salida[j]] = masgrand
                posicion[salida[j]] = color
                   }
         menores[menos[i]]=masgrand
         color <- color+1}
     return(posicion)
    
}
#la funcion nos regresa un vector de las posiciones y a que cluster pertenece

cold=cluster(datos,4)

#graficamos los datos
png(file="cluster_4_nucleos.png") #guadamos el gráfico generado
plot(datos,col=cold)
dev.off()


```
