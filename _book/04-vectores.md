# Vectores

Los vectores son cadenas unidimensionales (es decir una sola columna o fila) de un mismo tipo de valores (numéricos, caracteres, etc.)
Para crear un vector se usa la función `combinar c()`


```r
longitud <- c(12,11,15,13,16,12,11)
```


```r
colores  <- c("Negro", "Rosa", "Amarillo", "Blanco", "Azul", "Marron", "Guinda")
```

El objeto más simple que se puede almacenar en R es un vector con 1 elemento.

```r
simple <- "Dora"
```

## Manejo de vectores
Creamos el vector *PesosPacientes* utilizando datos de pesos de diferentes pacientes:

```r
PesosPacientes <- c(55, 45, 85, 55, 63, 78, 57) 
```

Para acceder a elementos específicos de cada vector usamos los corchetes indicando el elemento al que queremos acceder. En este ejemplo accederemos al peso del paciente 5:

```r
PesosPacientes[5]
```

```
## [1] 63
```

La longitud del vector se obtiene con la función `length()`

```r
length(PesosPacientes)
```

```
## [1] 7
```

Para extraer de nuestro objeto más de un elemento se usa la función para combinar o concatenar `c()`. En este ejemplo vamos a usar los pesos de los pacientes 3 y 6:

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


## Operaciones con vectores
Para hacer una operación utilizando varios números a la vez usamos la función combinar `c()`

```r
PesosPacientes <- c(55, 45, 85, 55, 63, 78, 57)
```

Para ver los valores, tecleamos **PesosPacientes** en la consola. El *+ 1* sumará uno al peso de cada paciente

```r
PesosPacientes + 1
```

```
## [1] 56 46 86 56 64 79 58
```

## Funciones en vectores

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

La función `sort()` ordena de menor a mayor los valores.

```r
sort(PesosPacientes)
```

```
## [1] 45 55 55 57 63 78 85
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


