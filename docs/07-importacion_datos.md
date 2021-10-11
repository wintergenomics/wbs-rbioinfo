
# Importación y exportación de datos

## Estableciendo nuestro directorio de trabajo

Establecer nuestro directorio de trabajo nos permite tener una mejor organización mientras trabajamos en R. 
Para conocer nuestro directorio de trabajo actual, usamos `getwd()`

```r
getwd() 
```

Asigna a un objeto la ruta de la carpeta de trabajo. Recuerda cambiar */docs/mydir* por los nombres de tus carpetas de trabajo

```r
directory <- "C:/docs/mydir" #Windows
directory <- "/home/users/mydir"  #Mac OS o linux
```

`setwd()` permite ajustar el directorio de trabajo. Vamos a ajustarlo a la ruta de trabajo que guardamos en `directory`

```r
setwd(directory)
```

## Importación de datos
### Archivos CSV

Importa archivos de texto plano con formato CSV (*coma-separated values*). Los datos los puedes descargar de [aquí](https://drive.google.com/u/0/uc?id=1TlR9xgKl7Laf8-SNwoq3W2MXkD19AQ9d&export=download). Recuerda guardarlos en la carpeta de trabajo que asignaste en el paso anterior.

```r
datosRCSV <- read.csv("iris.csv")
```



```r
head(datosRCSV)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```


### Archivos TXT

Importa archivos de texto plano con formato de tabla (data.frame). Los datos los puedes descargar de [aquí](https://drive.google.com/u/0/uc?id=18Cgt4ret3utAuk4w2_jl8RIbKxteulIO&export=download). Recuerda guardarlos en la carpeta de trabajo.

```r
datosRT <- read.table("iris.txt")
```



```r
head(datosRT)
```

```
##             V1          V2           V3          V4      V5
## 1 Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 2          5.1         3.5          1.4         0.2  setosa
## 3          4.9           3          1.4         0.2  setosa
## 4          4.7         3.2          1.3         0.2  setosa
## 5          4.6         3.1          1.5         0.2  setosa
## 6            5         3.6          1.4         0.2  setosa
```

Notamos que los encabezados no forman parte de la tabla y que R genera sus propios encabezados. Para evitar esto, si el archivo que queremos importar contiene encabezados, el argumento `header` permite incorporar el encabezado del archivo que queremos importar.

```r
datosRT <- read.table("iris.txt", header=TRUE)
```



```r
head(datosRT)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```


Importemos este [nuevo set de datos](https://drive.google.com/u/0/uc?id=1D88k0cC5TeALDWbvRmLh07g2d65ImLHh&export=download). 



```r
datosRT <- read.table("iris2.txt", header=TRUE)
```



```r
head(datosRT)
```

```
##   Sepal.Length.Sepal.Width.Petal.Length.Petal.Width.Species
## 1                                    5.1|3.5|1.4|0.2|setosa
## 2                                4.9|3.4|1.4|0.2|versicolor
## 3                                 4.7|3.2|1.3|0.2|virginica
```
Los datos no se importaron correctamente y están separados por el símbolo **"|"** o *pipe*.

Los archivos *csv* están separados por comas y generalmente, los archivos *txt* están separados por tabulaciones. Para indicarle a R el tipo de separación que tiene nuestro archivo, usamos el argumento `sep`.

En el siguiente comando, el argumento `sep="|"` le indica a R que nuestros datos están separados por el símbolo **"|"** o *pipe*.


```r
datosRT <- read.table("iris2.txt", header=TRUE, sep = "|")
```



```r
head(datosRT)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
## 1          5.1         3.5          1.4         0.2     setosa
## 2          4.9         3.4          1.4         0.2 versicolor
## 3          4.7         3.2          1.3         0.2  virginica
```

## Exportación de datos

Vamos a crear un data.frame para practicar cómo exportar los datos.

```r
DosisX <- c(46, 20, 80, 100, 63)
DosisY <- c(6, 50, 70, 70, 63)
Lcelular <- c("MCF7", "Hela", "IPC-366", "T47D", "ZR75-1")
tablaDE <- data.frame(DosisX, DosisY, Lcelular)
tablaDE
```

```
##   DosisX DosisY Lcelular
## 1     46      6     MCF7
## 2     20     50     Hela
## 3     80     70  IPC-366
## 4    100     70     T47D
## 5     63     63   ZR75-1
```

### Exportar como TXT

Vamos a guardar el data.frame `tablaDE` como un archivo de texto llamado **"datos.txt"** utilizando el comando `write.table()`. La tabla se guardará en nuestro directorio de trabajo  actual.

```r
write.table(tablaDE, "datos.txt")
```


### Exportar como CSV

Vamos a guardar el data.frame `tablaDE` como un archivo csv llamado **"datos.csv"** utilizando el comando `write.csv()`. La tabla se guardará en nuestro directorio de trabajo  actual.

```r
write.csv(tablaDE, "datos.csv")
```

### Argumentos al exportar

Así como al importar archivos existen diversos argumentos que podemos utilizar para darles ciertas indicaciones a R, también lo podemos hacer al momento de exportar los datos. Los siguientes argumentos se pueden usar con `write.csv()` y `write.table()`.

`row.names=FALSE` nos permite suprimir los nombres de las filas

```r
write.csv(tablaDE, "datos1.csv", row.names=FALSE)
```

Para indicar la separación del archivo utilizamos `sep`. Vamos a usar la tabulación como separador poniendo `sep="\t"`.

```r
write.csv(tablaDE, "datos2.csv", row.names=FALSE, sep="\t")
```


Para suprimir los nombres de las columnas, usamos `col.names=FALSE`

```r
write.csv(tablaDE, "datos3.csv", row.names=FALSE, sep="\t", col.names=FALSE)
```



## Archivos xlsx o de Excel

Para importar o exportar archivos de Excel, es necesario utilizar la paquetería `"openxlsx"` que nos permite trabajar con documentos de Excel en R. La instalación de paqueterías se realiza sólo una vez. Una vez que la librería o paquetería esté instalada, puedes omitir este paso.


```r
install.packages("openxlsx", dependencies = TRUE)
```

Ahora cargaremos la paquetería. El llamado de librerías deberá hacerse cada que inicies una nueva sesión en R.

```r
library(openxlsx)
```

El siguiente comando te permite leer y conocer más sobre las funciones que ofrece esta paquetería.

```r
?openxlsx
```


### Importación de datos xlsx o de Excel

Importaremos un nuevo set de datos de Excel que puedes descargar de [aquí](https://drive.google.com/u/0/uc?id=1DmLiZZGq_MVkLYCMZ7rdeHydUZAoP-YW&export=download). Recuerda guardarlos en tu carpeta de trabajo.


```r
datosXLSX <- read.xlsx("iris.xlsx")
```



```r
head(datosRT)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
## 1          5.1         3.5          1.4         0.2     setosa
## 2          4.9         3.4          1.4         0.2 versicolor
## 3          4.7         3.2          1.3         0.2  virginica
```


### Exportación de datos en Excel

Vamos a exportar el data.frame `tablaDE` que creamos anteriormente como un archivo de Excel llamado **"datos.xlsx"** utilizando el comando `write.xlsx()`. El archivo se guardará en nuestro directorio de trabajo  actual.


```r
write.xlsx(tablaDE, "datos.xlsx")
```


