---
title: "CASO 22 DIAGRAMS DE DISPERSION"
author: "ANGELICA ITZEL LOPEZ DELGADO"
date: '2022-05-25'
output:  html_document
---

# Objetivo

Construir diagramas de dispersión de dos variables

# Marco teórico

La dispersión de datos significa un diagrama que identifica como el grado de distanciamiento de un conjunto de valores respecto a su valor medio.

A partir de dicho concepto se puede establecer dispersión de medidas tales como rango, varianza, desviación; ahora en estos temas se asociará la dispersión en términos de covarianza y coeficiente de correlación.

Un ejemplo de una dispersión sería asociar a través de punto que son coordenadas de valores de dos variables $x , y$.

La tabla 2 identifica valores de dos variables. La primer columna son los vendedores, la segunda columna denota el número de llamadas que hace un vendedor vía telefónica para que le adquieran un producto, y la columna tres refleja las ventas de ese vendedor.

# Desarrollo

## Cargar librerías

```{r message=FALSE, warning=FALSE}
library(ggplot2)
library(readr)
library(dplyr)
```

## Cargar funciones

Se cargan funciones que se reutilizan en el caso

```{r message=FALSE, warning=FALSE}
source("https://raw.githubusercontent.com/rpizarrog/probabilidad-y-estad-stica/master/Enero%20Junio%202022/funciones/f.diagramas.graficos.r", encoding = "UTF-8")
```

## Llamadas y ventas

### Datos

```{r}
llamadas <- c(96, 40, 104, 128, 164, 76, 72, 80 , 36, 84, 180, 132, 120, 44, 84) 
ventas <- c(41, 41, 51, 60, 61, 29, 39, 50, 28, 43, 70, 56, 45, 31, 30)
```

### Construir diagrama de dispersión

Se manda llamar función previamente programada en las para visualizar diagrama de dispersión

```{r}
f_diag.dispersion(data.frame(llamadas, ventas))
```

## Datos de Fifa


### Datos 

Se cargan datos de dirección de internet

```{r}
datos.bruto <- read.csv("https://raw.githubusercontent.com/rpizarrog/probabilidad-y-estad-stica/master/Enero%20Junio%202022/datos/players_20.csv", stringsAsFactors = TRUE, encoding = "UTF-8")
str(datos.bruto)
```

Son 18278 observaciones o registros y 104 variables.

## Seleccionar las variables de interés

Se seleccionan dos variables numéricas de interés, **height_cm** y **weight_kg**; se modifican los nombres de variables o columnas en el conjunto de **datos** y se muestran los primeros 10 y últimos 10 registros.

```{r}
datos <- datos.bruto %>%
    select(height_cm, weight_kg)
colnames(datos) <- c("altura", "peso")
head(datos, 10)
tail(datos, 10)
```

Se muestran los estadísticos descriptivos principales de datos

```{r}
summary(datos)
```

### Dispersión de los datos

```{r}
f_diag.dispersion(datos)
```

## Otros datos  de ejemplo

Se solicita al alumno identificar un archivo CSV con dos variables numéricas de interés, que se puedan importar a R y construir un diagrama de dispersión con las dos variables de interés $x, y$

### Importar datos
datos.bruto <- read.csv("http://www.disfrutalasmatematicas.com/datos/grafica-dispersion-xy.html", stringsAsFactors = TRUE, encoding = "UTF-8"))
str(datos.bruto)

temperatura <- c(14.2°	$215,16.4°,	11.9°,	15.2°,	18.5°,22.1°,	19.4°25.1°23.4°18.1°	22.6°	17.2°)
vaentas <- c($215	$325, $185,$332,$406,$522,$412,$614,$544,$421,$445,$408)
### Variables de interés
datos <- datos.bruto %>%
    select(height_cm, weight_kg)

colnames(datos) <- c("temperatura °c", "ventas")

head(datos, 100)
tail(datos, 100)
### Descripción de los datos con summary(datos)
summary(datos)
### Diagrama de dispersión
f_diag.dispersion(datos)

# Interpretación

¿Qué es un diagrama de dispersión? es una herramienta muy útil para conocer cómo se comportan dos variables entre sí. 

¿Cómo se interpreta un diagrama de dispersión?  mediante la búsqueda de las tendencias en los datos a medida que avanza de izquierda a derecha

¿Que estadísticos se pueden asociar con un diagrama de dispersión? muestra que cuando el número de empleados aumenta, el beneficio aumenta 

# Bibliografía
http://www.disfrutalasmatematicas.com/datos/grafica-dispersion-xy.html
https://unade.edu.mx/diagrama-de-dispersion/

