
# Instalación de paqueterías
Las paqueterías o librerías son herramientas que se utilizan en R y facilitan la manipulación de datos y realizar diferentes tipos de análisis y gráficos. Las paqueterías se pueden descargar desde tres repositorios principales:

+ [CRAN](https://cran.r-project.org/)
+ [Bioconductor](https://www.bioconductor.org/)
+ [GitHub](https://github.com/)

Cada paquetería contiene su manual o documentación para conocer las opciones o argumentos que se pueden usar.  También contienen datos de prueba para verificar que todo funcione. La instalación de las paqueterías se realiza una sola vez.

## Paqueterías de CRAN

[CRAN](https://cran.r-project.org/) es el repositorio oficial de R contenido en una red de servidores ftp y web mantenidos por la comunidad R. 
Para que un paquete se publique en CRAN, debe pasar pruebas que garanticen que el paquete cumple con las políticas de la comunidad.

[Aquí](https://cran.r-project.org/web/packages/available_packages_by_name.html) puedes consultar todas las paqueterías disponibles en CRAN. A continuación instalaremos la paquetería `ggplot2`, que se encuentra en el repositorio CRAN.

### Instalación de paqueteria ggplot2 

```r
install.packages("ggplot2")
```

El comando `packageDescription()` muestra una descripción general sobre la paquetería.

```r
packageDescription("ggplot2")
```

El comando `help()` muestra la ayuda sobre la paquetería.

```r
help(package = "ggplot2")
```

Si quieres eliminar una paquetería, utiliza el comando `remove.packages()` indicando entre paréntesis el nombre de la paquetería.


## Paqueterías de Bioconductor

[Bioconductor](https://www.bioconductor.org/) es un repositorio de temas específicos para software de código abierto en bioinformática. Para instalar cualquier paquetería de Bioconductor, es necesario instalar **BiocManager**, que es el gestor de paqueterías de Bioconductor. 

### Instalación de BiocManager

```r
install.packages("BiocManager")
```

Una vez instalado BiocManager, ya podemos instalar las paqueterías que se encuentran en Bioconductor. [Aquí](https://www.bioconductor.org/packages/release/BiocViews.html#___Software) puedes revisar todas las paqueterías disponibles en Bioconductor.

### Instalación de paqueterías de Bioconductor. 
En este caso instalaremos la paquetería **AnnotationDbi**

```r
BiocManager::install("AnnotationDbi")
```



## Paqueterías de GitHub

[GitHub](https://github.com/) no es específico de R pero es el repositorio más popular para proyectos de código abierto. Su popularidad se debe al espacio ilimitado, la integración con git, control de versiones y su facilidad para compartir y colaborar con otros usuarios.

La instalación de paqueterías desde GitHub dependerá de instrucciones indicadas por los autores. 






