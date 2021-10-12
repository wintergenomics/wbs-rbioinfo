# Vectores

Los vectores son cadenas unidimensionales (es decir una sola columna o fila) de un mismo tipo de valores (numéricos, caracteres, etc.)

Para crear un vector se usa la función `combinar c()`. 


Creación de un vector numérico

```r
longitud <- c(12,11,15,13,16,12,11)
```

Creación de un vector de caracter. Los vectores de caracter se ocupan para guardar texto, por lo que deben de ir entre comillas.

```r
colores  <- c("Negro", "Rosa", "Amarillo", "Blanco", "Azul", "Marron", "Guinda")
```

Creación de vector lógico (Verdadero o Falso)

```r
logico <-c(TRUE, FALSE, TRUE, FALSE, FALSE, FALSE, TRUE)
```

El objeto más simple que se puede almacenar en R es un vector con 1 elemento.

```r
simple <- "Dora"
```

## Tipo de datos de los vectores
Revisar el tipo de datos que contienen los vectores usamos `class()`.


```r
class(longitud)
```

```
## [1] "numeric"
```


```r
class(colores)
```

```
## [1] "character"
```


```r
class(logico)
```

```
## [1] "logical"
```

## Construcción de vectores secuenciales

Para construir un vector numérico secuencial, podemos usar `seq`. Vamos a construir un vector del 1 al 6.

```r
myseq<-seq(1,6)
myseq
```

```
## [1] 1 2 3 4 5 6
```

Creando la secuencia utilizando decimales

```r
myseq2<-seq(1,6,by=0.5)
myseq2
```

```
##  [1] 1.0 1.5 2.0 2.5 3.0 3.5 4.0 4.5 5.0 5.5 6.0
```


## Manejo de vectores

Creamos el vector *PesosPacientes* utilizando datos de pesos de diferentes pacientes:

```r
PesosPacientes <- c(55, 45, 85, 55, 63, 78, 57) 
PesosPacientes
```

```
## [1] 55 45 85 55 63 78 57
```

Para acceder a elementos específicos de cada vector usamos los corchetes indicando el elemento al que queremos acceder. En este ejemplo accederemos al peso del paciente 5:

```r
PesosPacientes[5]
```

```
## [1] 63
```

Para acceder al peso de los pacientes del 3 al 5 usamos

```r
PesosPacientes[3:5]
```

```
## [1] 85 55 63
```

Otra opción para extraer de nuestro objeto más de un elemento es con la función de combinar o concatenar `c()`. En este ejemplo vamos a usar los pesos de los pacientes 3 y 6:

```r
PesosPacientes[c(3,6)]
```

```
## [1] 85 78
```

También podemos usar índices negativos para quitar temporalmente ciertos elementos de un vector. En este ejemplo vamos a quitar los pesos de los pacientes 3 y 6:

```r
PesosPacientes[-c(3,6)]
```

```
## [1] 55 45 55 63 57
```

La longitud del vector se obtiene con la función `length()`.

```r
length(PesosPacientes)
```

```
## [1] 7
```

## Operaciones con vectores

Para hacer una operación utilizando varios números a la vez usamos la función combinar `c()`. Empezamos generando los vectores "a" y "b". 

```r
a <- c(5,10,12,3)
b <- c(18,1,4,7)
```


```r
suma_vect   <- a + b # suma de los dos vectores
suma_vect
```

```
## [1] 23 11 16 10
```


```r
resta_vect  <- a - b # resta de los dos vectores
resta_vect
```

```
## [1] -13   9   8  -4
```

## Combinación de vectores

Generamos los vectores "pares" y "impares".

```r
pares<- c(1,3,5) #vector con datos impares
pares
```

```
## [1] 1 3 5
```


```r
impares<- c(2,4,6) #vector con catos pares
impares
```

```
## [1] 2 4 6
```

Con `c()`combinamos ambos vectores y lo guardamos en el nuevo vector "z".

```r
z<- c(pares,impares)
```

Revisamos la clase del vector.

```r
class(z)
```

```
## [1] "numeric"
```

## Funciones en vectores


```r
PesosPacientes <- c(55, 45, 85, 55, 63, 78, 57)
PesosPacientes
```

```
## [1] 55 45 85 55 63 78 57
```

Para ver los valores, tecleamos **PesosPacientes** en la consola. El *+ 1* sumará uno al peso de cada paciente.

```r
PesosPacientes + 1
```

```
## [1] 56 46 86 56 64 79 58
```

Se pueden usar diferentes funciones para aplicarse a los vectores numéricos.

La función `sum()`permite realizar la sumas de los datos.

```r
sum(PesosPacientes)
```

```
## [1] 438
```

La función `mean()` calcula el promedio.

```r
mean(PesosPacientes)
```

```
## [1] 62.57143
```

La función `max()` indica el valor más alto de nuestros datos.

```r
max(PesosPacientes)
```

```
## [1] 85
```

La función `min()` indica el valor más bajo de nuestros datos.

```r
min(PesosPacientes)
```

```
## [1] 45
```

La función `sort()` permite ordenar los valores.

```r
sort(PesosPacientes) #ordena de menor a mayor
```

```
## [1] 45 55 55 57 63 78 85
```


```r
sort(PesosPacientes, decreasing = T) #ordena de mayor a menor
```

```
## [1] 85 78 63 57 55 55 45
```

La función `unique()` muestra los datos o valores únicos o que no se repiten de nuestro set.

```r
unique(PesosPacientes)
```

```
## [1] 55 45 85 63 78 57
```

En R también podemos tener valores de texto que siempre van entre comillas. 
Así como guardamos una serie de números en el objeto **“PesosPacientes”**, podemos guardar valores de texto en un nuevo objeto de la siguiente manera:

```r
nombres <- c("Susana", "Angela", "Oscar", "Joel", "Blanca", "Karla", "Manuel")
nombres
```

```
## [1] "Susana" "Angela" "Oscar"  "Joel"   "Blanca" "Karla"  "Manuel"
```

Revisamos el tipo de vector de `nombres`.

```r
class(nombres)
```

```
## [1] "character"
```

El objeto “nombres” nos puede servir para etiquetar los valores numéricos de los pesos de los pacientes, esto con la función `names()` para asignar nombres de texto.

```r
names(PesosPacientes) <- nombres
PesosPacientes
```

```
## Susana Angela  Oscar   Joel Blanca  Karla Manuel 
##     55     45     85     55     63     78     57
```


