---
output:
  pdf_document: default
  html_document: default
---

# Objetos

Todos los elementos que maneja R se llaman objetos

En términos prácticos:

Es un nombre que almacena cualquier tipo y cantidad de datos (inputs o outputs) con atributos específicos.

## Creación de objetos

En R podemos asignar valores a objetos con el siguiente símbolo para la asignación 	`<-`
Ejemplo:


```r
x <- 1
```
Donde x es la variable y 1 es el objeto

**¿Cuál sería otra forma de mostrar el valor de x usando una función?**				

Es importante mantener la estructura de la función u operación, y en ocasiones no importa agregar más espacios, por ejemplo:


```r
y  <- 1 + 2
y
```

```
## [1] 3
```


Al incluir más espacios, sigue produciendo el mismo resultado

```r
y  <-      1       +      3
y
```

```
## [1] 4
```

### Ejercicio

Asigna el resultado de multiplicar 2 por 8 a la variable cromosomas

```r
cromosomas <- 2*8
cromosomas
```

```
## [1] 16
```

Ahora asigna el valor 3400 a la variable cromosomas.

Para R, no es lo mismo: Juan y “Juan”.

Juan (sin comillas) es el nombre de un objeto

## Tipos de datos en R




|Tipos    |Dato                |Ejemplo                 |
|:--------|:-------------------|:-----------------------|
|Caracter |Id de paciente      |"Alejandra", "IMSS_311" |
|Numérico |Cigarrillos por día |9, 4.15, 1000           |
|Lógico   |¿Fumador?           |TRUE (T), FALSE (F)     |

**NUMÉRICO**

Agrega un valor numérico a la variable mi_numero

```r
mi_numero <- 30
```

**CARACTER**

Agrega la siguiente palabra a mi_caracter: Mexico

```r
mi_caracter <- "Mexico"
```
**NOTA: Cuando usamos texto debemos escribirlo entre " " (comillas)**

**LÓGICO**

Agrega el valor lógico

```r
mi_logico <- TRUE
```

Podemos conocer la clase a la que corresponde cada uno de nuestros datos con la función `class()`


```r
class(mi_numero)
```

```
## [1] "numeric"
```


```r
class(mi_caracter)
```

```
## [1] "character"
```


```r
class(mi_logico)
```

```
## [1] "logical"
```


Es posible convertir la clase de un objeto usando las siguientes funciones:

- `as.numeric()`
- `as.logical()`
- `as.character()`
- `as.integer()`

**Ejemplo**
Convierte `mi_numero` a caracter usando la función `as.character()`


```r
mi_numero
```

```
## [1] 30
```


```r
class(mi_numero)
```

```
## [1] "numeric"
```


```r
as.character(mi_numero)
```

```
## [1] "30"
```

## Tipos de objetos en R

- **Vectores:** Son secuencias uni-dimensionales de elementos.
- **Matrices:** Son objetos de bi-dimensionales. El contenido de este objeto debe de ser de un solo tipo de datos.
- **Factores:** Son vectores de tipo categóricos, pueden contener datos numéricos, integrales o caracteres.
- **Listas:** Las listas son parecidas a los vectores, pero a diferencia de estas, no tienen que contener el mismo tipo de datos.
- **Data frames:** Es una matriz pero puede contener datos de diferentes tipos, ya sea numéricos o tipo carácter.






|Tipos      |Ejemplo                                                |Descripción                                                                                     |
|:----------|:------------------------------------------------------|:-----------------------------------------------------------------------------------------------|
|Vector     |c(“Mary”,”Juan”, … )                                   |Colección de datos en serie                                                                     |
|Matriz     |matrix(37, 20, 25, 17, … )                             |Vector ordenado por filas y columnas                                                            |
|Data.frame |data.frame(ID_Pacientes, cigarrillos por día, Fumador) |Colección de vectores ordenados por columnas; todos los vectores deben ser de la misma longitud |
|Listas     |list(mi_vector, mi_matriz, mi_dataframe, mi gráfico)   |Son contenedores generales de datos. Muy flexibles, pero sin estructura                         |

## Atributos de los objetos
Los atributos de los objetos pueden ser:

- Nombres
- Dimensiones
- Clases
- Longitud 
- Otros atributos definidos por el usuario

Se pueden acceder a estos atributos usando la función `attributes()`

## Operadores

### Operadores artiméticos




|Aritmético |Descripción         |
|:----------|:-------------------|
|+          |Adición             |
|-          |Substracción        |
|*          |Multiplicación      |
|/          |División            |
|^          |Exponente           |
|%%         |Residuo de división |
|%/%        |División entera     |

### Operadores Relacionales



|Relacionales |Descripción       |
|:------------|:-----------------|
|<            |Menor que         |
|>            |Mayor que         |
|<=           |Menor o igual que |
|>=           |Mayor o igual que |
|==           |Igual que         |
|!=           |No igual que      |

### Operadores Lógicos



|Lógico       |Descripción           |
|:------------|:---------------------|
|!            |No lógico             |
|&            |Y lógico por elemento |
|&&           |Y lógico              |
|&#124;       |O lógico por elemento |
|&#124;&#124; |O lógico              |
