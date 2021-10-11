
# Heatmaps

Los heatmaps son una técnica de visualización de datos que mide la magnitud de un fenómeno en colores en dos dimensiones. La variación del color puede ser por tono o intensidad, haciendo obvia la lectura del fenómeno sobre el espacio que se trata.

Son el resultado obtenido al representar una matriz de valores en la que, en lugar de números, se muestra un gradiente de color proporcional al valor de cada variable en cada posición. 

Los heatmaps son ampliamente utilizados para visualizar e interpretar datos de expresión génica, principalmente para experimentos con microarrays y RNA-seq. También se puede combinar con métodos de agrupación, que agrupan genes y/o muestras en función de la similitud de su patrón de expresión génica. Esto puede ser útil para identificar genes que están comúnmente regulados o firmas biológicas asociadas con una condición particular (por ejemplo, una enfermedad o una condición ambiental).


Para crear los heatmps usaremos `pheatmap()`. Instalamos la paquetería y después la cargamos.

```r
install.packages("pheatmap")
```

```r
library(pheatmap)
```

El set de datos que vamos a usar los puedes descargar de [aquí](https://drive.google.com/u/0/uc?id=1aS5-Zf03OeMRtZsCCLYFXAUQpesGy4IK&export=download). Recuerda guardarlos en tu carpeta de trabajo actual, como lo vimos en la sección 7.


```r
data <- read.csv(file = "Datos.csv")
```



Vamos a restructurar los datos

```r
rownames(data) <- data[,1]
samp2 <- data[,-1]
```

Transformaremos nuestros datos a una matriz para poder crear nuestro heatmap.

```r
mat_data <- data.matrix(samp2[,1:ncol(samp2)])
mat_data
```

```
##   edad Peso
## L    6   20
## M   40   80
## P   10   30
## H   50  100
## Y    1    8
```

Construyendo un heatmap básico

```r
pheatmap(mat_data)
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-7-1.png" width="672" />



Con los comandos `fontsize_col`(columnas) y `fontsize_row` (filas), puedes cambiar el tamaño de letra y hacerlo más grande o más pequeño.

```r
pheatmap(mat_data,
         fontsize_col=6,
         fontsize_row=6)
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-8-1.png" width="672" />



`main` te permite agregar el título al Heatmap. Recuerda que el título que eligas debe estar entre comillas

```r
pheatmap(mat_data,
         fontsize_col=10,
         fontsize_row=10,
         main = "Mi primer heatmap")
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-9-1.png" width="672" />



La escala de colores fríos generalmente se usa en los heatmaps. `color` te permite cambiar los colores de la gráfica.

[Aquí](http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf) y [aquí](https://htmlcolorcodes.com/) puedes revisar los colores disponibles en R que puedes usar en tus gráficas.


```r
pheatmap(mat_data,
         fontsize_col=10,
         fontsize_row=10,
         main = "Mi primer Heatmap",
         color = c("blue", "yellow","red"))
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-10-1.png" width="672" />

Agregar o cambiar las líneas de los clusters con `cluster_cols` y `cluster_rows`

```r
pheatmap(mat_data,
         fontsize_col=10,
         fontsize_row=10,
         main = "Mi primer heatmap",
         color = c("blue", "yellow","red"),
         cluster_cols=F,
         cluster_rows=T)
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-11-1.png" width="672" />



```r
pheatmap(mat_data,
         fontsize_col=10,
         fontsize_row=10,
         main = "Mi primer heatmap",
         color = c("blue", "yellow","red"),
         cluster_cols=F,
         cluster_rows=F)
```

<img src="10-heatmaps_files/figure-html/unnamed-chunk-12-1.png" width="672" />





