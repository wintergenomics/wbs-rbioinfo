
# Matrices
Una matriz es una estructura de datos, ordenados por filas y columnas (matriz de dos dimensiones). Está constituida por elementos del mismo tipo de datos (numéricos, caracteres, o lógicos), organizados por filas y columnas. Para crear una matriz usamos la función `matrix()`.

## Estructura de una matriz

```r
matrix(nrow=2, ncol=3)
```

```
##      [,1] [,2] [,3]
## [1,]   NA   NA   NA
## [2,]   NA   NA   NA
```

Donde:
- **nrow** es el  número de filas
- **ncol** es el número de columnas
- **NA** significa *Not Available*

```r
matrix(1:9, byrow = TRUE, nrow = 3)
```

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4    5    6
## [3,]    7    8    9
```
- El argumento `1:9`es una colección de elementos: `1:9 c(1,2,4,5,6,7,8,9)`
- `byrow` indica que la matriz será rellenada por fila. Si queremos que la matriz sea llenada por columna ajustamos a `byrow = FALSE`
- `nrow` indica que la matriz tendrá 3 filas

## Creación de una matriz

```r
MatrixEjemplo <- matrix(1:12, nrow = 4, byrow=TRUE)
MatrixEjemplo
```

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4    5    6
## [3,]    7    8    9
## [4,]   10   11   12
```

```r
dim(MatrixEjemplo)
```

```
## [1] 4 3
```
- `byrow=TRUE` llena los elementos por fila.
- Con el comando `dim()`se obtiene las dimensiones de la matriz

## Acceder a los elementos de una matriz
Para acceder al elemento que se encuentra en la fila 3 y la columna 2 de nuestra `MatrixEjemplo`, indicamos entre corchetes la fila y la columna a la que queremos acceder. **Es muy importante indicar primero la fila y después la columna.**

```r
MatrixEjemplo[3,2]
```

```
## [1] 8
```

Ahora guardemos el resultado en la variable elemento:

```r
elemento<- MatrixEjemplo[3,2]
elemento
```

```
## [1] 8
```

Si queremos acceder únicamente a los datos de la fila 3 de nuestra matriz usamos:

```r
MatrixEjemplo[3,]
```

```
## [1] 7 8 9
```

La coma después del número 3 indica que queremos ver todos los valores de las columnas que pertenezcan a la fila 3. 
Si por el contrario, queremos acceder a los valores de la columna dos, usamos:

```r
MatrixEjemplo[,2]
```

```
## [1]  2  5  8 11
```

En este caso, la coma está situada antes del número 2 indicando que queremos ver todos los valores de las filas que pertenezcan a la columna 2. 
Guardemos los resultados en diferentes variables:

```r
fila<- MatrixEjemplo[3,]
fila
```

```
## [1] 7 8 9
```

```r
columna<- MatrixEjemplo[,2]
columna
```

```
## [1]  2  5  8 11
```


## Modificar elementos de una matriz


Para modificar cualquier elemento de una matriz debemos de indicar entre corchetes el número de fila y de columna en donde se encuentra el elemento que queremos modificar: `[fila, columna]`.
Vamos a modificar el elemento que se encuentra en la fila 2 de la columna 2.

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4    5    6
## [3,]    7    8    9
## [4,]   10   11   12
```


El elemento que queremos cambiar tiene el valor de *"5"*. Vamos a sustiurlo por el valor de 10. Para esto lo reasignamos a nuestra matriz:

```r
MatrixEjemplo[2,2]<- 10
MatrixEjemplo
```

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4   10    6
## [3,]    7    8    9
## [4,]   10   11   12
```
- **MatrixEjemplo[2,2]** indica que queremos acceder al elemento que se encuentra en la fila 2 de la columna 2. 
- **<- 10** estamos asignando el valor 10 a la matriz.

## Ejercicio
Construir una matriz con los años de secuenciación de organismos de referencia (G). El primer y el segundo elemento es el año de publicación de al menos dos organismos.


```r
Gbacterias <- c(1997, 1993)
Ghongos <- c(1999, 2000)
Ganimales <- c(2000, 2001)
cronologia <- c(Gbacterias, Ghongos, Ganimales)
```

Construir matriz de 3 filas, 2 columnas con los valores de cronologia

```r
matrix(cronologia, nrow = 3)
```

```
##      [,1] [,2]
## [1,] 1997 2000
## [2,] 1993 2000
## [3,] 1999 2001
```
Para agregar columnas o filas a matrices utilizamos `cbind()` y `rbind()` respectivamente.

**NOTA:** El número de elementos en las columnas o filas debe ser el mismo.


```r
cbind(Ganimales,Gbacterias,Ghongos)
```

```
##      Ganimales Gbacterias Ghongos
## [1,]      2000       1997    1999
## [2,]      2001       1993    2000
```


```r
rbind(Ganimales,Gbacterias,Ghongos)
```

```
##            [,1] [,2]
## Ganimales  2000 2001
## Gbacterias 1997 1993
## Ghongos    1999 2000
```

**NOTA:** Estos resultados los podemos guardar en distintas variables.
