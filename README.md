# Proyecto-2
```r
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
```
