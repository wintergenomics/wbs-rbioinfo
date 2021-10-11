
# Data.frames

Es una estructura de tipo tabular, que permite el uso de diferentes tipos de datos. Combina listas de vectores de la misma longitud. 
Ejemplo, en una encuesta se tienen preguntas como las siguientes con sus respectivas respuestas:

- ¿Está vacunado para Influenza? : **sí/no (lógicos)**
- ¿Año de nacimiento? : **1990, 1981, 2000, 1952 (numérico)**
- ¿Nacionalidad?: **Chi, Rus, Mex, USA (caracteres)**

## Características de los data.frames

- Los nombres de columna no deben estar vacíos
- Los nombres de las filas deben ser **únicos**
- Los datos almacenados en un dataframe pueden ser de tipo numérico, factor o carácter.
- Cada columna debe contener el mismo número de elementos de datos

## Creación de un data.frame

Crear data.frame *"TipoDatos"* a partir de los siguientes vectores:

```r
origen <- c("Chi", "Rus", "Mex", "USA")
vacunado <- c(FALSE, TRUE, TRUE, TRUE)
fecha <- c("1990", "1981", "2000", "1952")
TipoDatos <- data.frame(origen, vacunado, fecha)
TipoDatos
```

```
##   origen vacunado fecha
## 1    Chi    FALSE  1990
## 2    Rus     TRUE  1981
## 3    Mex     TRUE  2000
## 4    USA     TRUE  1952
```

`str()` Brinda información sobre la estructura del data.frame.


```r
str(TipoDatos)
```

```
## 'data.frame':	4 obs. of  3 variables:
##  $ origen  : chr  "Chi" "Rus" "Mex" "USA"
##  $ vacunado: logi  FALSE TRUE TRUE TRUE
##  $ fecha   : chr  "1990" "1981" "2000" "1952"
```

Para acceder a una columna de un data.frame, utilizamos el símbolo de pesos:

```r
TipoDatos$fecha
```

```
## [1] "1990" "1981" "2000" "1952"
```

Otra forma de acceder a los elementos de un data.frames es mediante corchetes. Recordemos que esta nomenclatura la estudiamos en el capítulo anterior de Matrices. 

```r
TipoDatos[,3]
```

```
## [1] "1990" "1981" "2000" "1952"
```


De manera similar, para acceder a una fila de un data.frame utilizamos los corchetes, donde `[fila, columna]`. 

```r
TipoDatos[2,]
```

```
##   origen vacunado fecha
## 2    Rus     TRUE  1981
```


## Extracción de datos de un data.frame
### Extracción de datos por columna

Crear un nuevo data.frame llamado "result" que contenga todos los datos de las columnas origen y fecha. 

```r
result <- data.frame(TipoDatos$origen,TipoDatos$fecha)
result
```

```
##   TipoDatos.origen TipoDatos.fecha
## 1              Chi            1990
## 2              Rus            1981
## 3              Mex            2000
## 4              USA            1952
```


### Extracción de datos por filas

Extraer todos los datos de las filas 1 y 2. 

```r
subsets <- TipoDatos[1:2,]
subsets
```

```
##   origen vacunado fecha
## 1    Chi    FALSE  1990
## 2    Rus     TRUE  1981
```


## Combinar data.frames

Creamos un segundo data.frame llamado *"TipoDatos2"*.

```r
cobertura <- c("NA", "Pandemica", "Estacional", "NA")
edad <- factor(c("60", "50", "80", "20"), ordered = TRUE)
TipoDatos2 <- data.frame(cobertura, edad)
TipoDatos2
```

```
##    cobertura edad
## 1         NA   60
## 2  Pandemica   50
## 3 Estacional   80
## 4         NA   20
```

Con `cbind()` unimos dos data.frames del mismo tamaño mediante columnas. En este caso uniremos los data.frames `TipoDatos` y `TipoDatos2`.

```r
datosfinales <- cbind(TipoDatos,TipoDatos2)
datosfinales
```

```
##   origen vacunado fecha  cobertura edad
## 1    Chi    FALSE  1990         NA   60
## 2    Rus     TRUE  1981  Pandemica   50
## 3    Mex     TRUE  2000 Estacional   80
## 4    USA     TRUE  1952         NA   20
```


## Subset de datos

`subset()` permite filtrar o extraer los datos que cumplen con un parámetro particular.

Si queremos obtener los datos de los pacientes menores a 60 años usamos:

```r
subset(datosfinales, subset=edad <60)
```

```
##   origen vacunado fecha cobertura edad
## 2    Rus     TRUE  1981 Pandemica   50
## 4    USA     TRUE  1952        NA   20
```

Si queremos obtener los datos de los pacientes vacunados usamos:

```r
subset(datosfinales, subset=vacunado)
```

```
##   origen vacunado fecha  cobertura edad
## 2    Rus     TRUE  1981  Pandemica   50
## 3    Mex     TRUE  2000 Estacional   80
## 4    USA     TRUE  1952         NA   20
```


Estos resultados los podemos guardar en distantas variables


```r
pacientes_edad<- subset(datosfinales, subset=edad <60)
pacientes_edad
```

```
##   origen vacunado fecha cobertura edad
## 2    Rus     TRUE  1981 Pandemica   50
## 4    USA     TRUE  1952        NA   20
```


```r
pacientes_vacunados<- subset(datosfinales, subset=vacunado)
pacientes_vacunados
```

```
##   origen vacunado fecha  cobertura edad
## 2    Rus     TRUE  1981  Pandemica   50
## 3    Mex     TRUE  2000 Estacional   80
## 4    USA     TRUE  1952         NA   20
```

