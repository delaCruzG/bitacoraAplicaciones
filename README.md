# Bitacora de uso de R para aplicaciones estadísticas

###  Héctor García de la Cruz

Este documento corresponde a la bitacora del curso de aplicaciones estadísticas impartido por la profesora Dunia Rassy en el periodo escolar 2024-2.

___________________________________________________________________________________________

## Índice

La organización del contenido es como se presenta a continuación:

[Semana 1. Clase 1. 2 de Febrero: Intro a R y R studio. Swirl.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-1-clase-1-2-de-febrero-intro-a-r-y-r-studio-swirl)

[Semana 2. Clase 2. 9 de Febrero: Tipos de variables en R. Data frames.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-2-clase-2-9-de-febrero-tipos-de-variables-en-r-data-frames)

[Semana 3. Clase 3. 16 de Febrero: Correlaciones y Gráficas en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-3-clase-3-16-de-febrero-correlaciones-y-gr%C3%A1ficas-en-r)

[Semana 5. Clase 4. 26 de Febrero: Medidas de tendencia central e histogramas en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-5-clase-4-26-de-febrero-medidas-de-tendencia-central-e-histogramas-en-r)

[Semana 6. Clase 5. 4 de Marzo: Medidas de Dispersión. Medidas de dispersión en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-6-clase-5-4-de-marzo-medidas-de-dispersi%C3%B3n-medidas-de-dispersi%C3%B3n-en-r)

[Semana 7. Clase 6. 11 de Marzo: Distribución de frecuencias en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-7-clase-6-11-de-marzo-distribuci%C3%B3n-de-frecuencias-en-r)

[Semana 9. Clase 9. 1 de Abril: Histogramas, gráficos de caja y dotplots en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-9-clase-9-1-de-abril-histogramas-gr%C3%A1ficos-de-caja-y-dotplots-en-r)

[Semana 10. Clase 10. 8 de Abril: Formas alternativas de reportar puntajes en R.](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-10-clase-9-1-de-abril-del-2024-formas-alternativs-de-reportar-puntajes)

[Semana 12. Clase 12. 22 de abril: Análisis de Reactivos](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-12-clase-9-22-de-abril-an%C3%A1lisis-de-reactivos)

[Semana 13. Clase 13. 29 de abril: Análisis de Reactivos II](https://github.com/delaCruzG/bitacoraAplicaciones?tab=readme-ov-file#semana-13-clase-10-29-de-abril-an%C3%A1lisis-de-reactivos-ii)

___________________________________________________________________________________________

## Semana 1. Clase 1. 2 de Febrero: Intro a R y R studio. Swirl.

En esta clase instalamos R y R estudio. 

Para poder completar la actividad usamos los siguientes comandos:

Para instalar el paquete swirl usamos el siguiente comando y swirl como argumento :

```
install.packages("nombre_paquete")
```

Para activar el paquete debemos usar. En este caso con swirl como argumento.

```
library()
```

Finalmente, para empezar la guía ofrecida para este caso en particular debemos de usar

```
swirl()
```

En este curso vemos sintaxis básica para trabajar con R.

Consideré como las más relevantes rescatar la asignación de variables

```
nombreVariable <- función o dato a asignar
```

Y la concatenación:

```
c(x,y, ..., z)
```

## Semana 2. Clase 2. 9 de Febrero: Tipos de variables en R. Data frames.

En esta clase se estudiaron varios conceptos relevantes para trabajar con datos y dataframes.

Para consultar el tipo de dato al que pertenece nuestra variable a nivel programación usamos la función:

```
class()
```

Ejemplo de uso:

```
class(nombreVariableAquí)
```

En relación a los números enteros, podemos usar la función as.integer para redondearlos:

```
as.integer(2.2)
```

Si queremos leer un csv, R nos brinda la función read.csv()

Como argumento para esta función a la vez usaremos la funcióñ file.choose() y marcaremos el parametro header=TRUE.

```
read.csv(file.choose(), header=TRUE)
```

Cuando leemos un csv de esta manera, podemos usarlo dentro del lenguaje R como un dataframe.

Para consultar una columna de nuestro dataframe podemos asignar la lectura de un csv a una variable y posteriormente especificar la columna que nos interesa consultar usando el signo de"$":

Primer paso:
```
dataframe <- read.csv(file.choose(), header=TRUE)
```

Segundo paso (usar $ para delimitar argumento):

```
print(dataframe$columna)
```

En el caso de class:

```
class(dataframe$columna)
```

_Ahora bien, para aterrizar el uso de R en el análisis cualitativo vale la pena mencionar que un factor puede representarse en R como un vector_

Recordar que los factores son variables categóricas estrictamente no númericas.

Recordatorio, un vector se declara de la siguiente forma:

```
factor(c(v1, v2, ..., v3))
```

Algunas funciones útiles para analizar una variable a la que se asignaron factores son:

Los diferentes factores con los que contamos
```
levels()
```

El numero de factores 

```
nlevels()
```

Esta función también se puede usar para analizar nuestros factores
```
class()
```

Finalmente, podemos usar levels dentro de class para saber el tipo de datos que tienen las diferentes categoríás de un factor.
```
class(levels())
```

Si creamos vectores podemos consultar cuántos elementos tiene mediante:

```
length()
```

Ahora bien, si queremos ver nuestro dataframe tenemos que usar la función View

```
View()
```

Poner atención a la mayuscula.

Entre los comandos útiles para trabajar con dataframes tenemos:
(nuestro argumento siempre es la variable de nuestro df)

1. Para trabajar con filas
Número de filas

```
nrow()
```

Nombre de las filas
```
rownames()
```

2. Para trabajar con columnas
Número de columnas

```
ncol()
```

Nombre de las columnas

```
colnames()
```

o bien

```
names()
```

Ejemplo de la sintáxis si queremos deliminar una fila o columna específica:

1. Consultar nombre columna x
```
colnames()[x]
```

2. Consultar nombre fila x
```
rownames()[x]
```

Nota:
La variable que guarda nuestro dataframe no puede usarse como argumento de class para saber los tipos de datos de sus columnas. Class nos da como output "data.frame"

```{r}
> class(banana)
[1] "data.frame"
```

Para obtener el resultado del tipo de dato para cada columna debemos usar

```{r}
sapply(<varDF>, <función_a_repetir>)
```

## Semana 3. Clase 3. 16 de Febrero: Correlaciones y Gráficas en R.


Exploramos la asignación de una suma de filas a una variable.

```
total_ex1 <- rowSums(examen1)
```

```
total_ex2 <- rowSums(examen2)
```

```
cor(total_ex1,total_ex2)
```

Se hizo grafica de dispersion.

```
plot(total_ex1,total_ex2)
```
 
Ahora jugamos con los parametros de la funcion plot.

Cambiar la escala de los ejes: 
```
plot(total_ex1,total_ex2, xlim=c(0,20), ylim=c(0,20))
```

Agregar títulos en los ejes
```
plot(total_ex1,total_ex2, xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2")
```

Agregar un título principal
```
plot(total_ex1,total_ex2,main="Prueba de Validez de Criterio", xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2")
```

Rellenar los puntos y ponerlos de color verde obscuro (dark green)
```
plot(total_ex1,total_ex2,main="Prueba de Validez de Criterio", xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2",pch=19, col="dark green")
```

Dibujar línea de tendencia en rojo
```
abline(lm( total_ex1~total_ex2),col="red")
```

## Semana 5. Clase 4. 26 de Febrero: Medidas de tendencia central e histogramas en R.

En esta clase se calcularon distintas medidas de tendencia central y se exploraron funciones para hacer gráficas . 

Empezamos asignando a una variable el dataframe que corresponde a un documento csv.

```
banana<-read.csv(file.choose(), header=TRUE)
```
Corroboramos su contenido.

```
View(banana)
```

```
clear()
```

Usamos sapply para aplicar la función class a las diferentes columnas.

```
sapply(banana, class)
```

Sumamos valores de una columna en especifico de la tabla

```
sum(banana$Age)
```

Dividirlos entre el número de datos usando la función length

```
length(banana$Age)
```
Asignamos a variables

```
valoresTabla <-sum(banana$Age)
```
```
numeroDatos <- length(banana$Age)
```
Una operacion aritmetica para obtener la media aritmética.

```
valoresTabla/numeroDatos
```
```
valoresTabla <-sum(banana$Age)
```
```
numeroDatos <- length(banana$Age)
```

```
valoresTabla/numeroDatos
```
Tambien podemos usar directamente una función.

```
mean(banana$Age)
```
Asignación a variable de la media calculada manualmente

```
promedioManual <- valoresTabla/numeroDatos
```
Asignación a variable de la media calculada con una función de r

```
primedioFuncion <- mean(banana$Age)
```
Asignación a varible de concatenación de valores.

```
fPilotos <- c(4, 11, 12, 21, 30, 12, 9, 1)
```
```
vPilotos <- c(97, 94, 92, 91, 90, 89, 78, 60)
```
Lbtenemos la media ponderada con las siguientes funciones.

```
wighted.mean(vPilotos, fPilotos)
```
```
weighted.mean(vPilotos, fPilotos)
```
Ordenar de mayor a menor

```
sort(vPilotos)
```

Sacarle la longitud y mediana 
```
length(vPilotos)
```
```
median(vPilotos)
```

Respuesta para la tercera columna

```
median(banana$Age)
```

Prueba sólo para ver qué sale

```
mode(banana$Age)
```

El output correpsonde a el tipo de dato en R.

convertimos a factor los resultados y summary los suma
```
summary(as.factor(banana$Age))
```

```
source("~/.active-rstudio-document")
```
Instalanos el paquete modeest y lo activamos.

```
install.packages("modeest")
library(modeest)
```
Así podemos usar la funcion mfv para calcular moda.

```
moda<-mfv(banana$Age)
```
```
moda
```

usar funcion del paquete
```
moda <- mfv(banana$Age)
```

```
summary(banana)
```

Ahora graficamos histogramas para las edades registradas.

```
hist(banana$Age)
```

Histograma

Modificamos el parametro color.

```
hist(banana$Age, color="pink")
```

Modificamos los parametros main, xlab y ylab.
```
hist(banana$Age", main="Histograma", xlab="Edad", ylab="Frecuencia")
```

Marcamos una  linea de tendencia usando abline 
```
abline(v=mean(banana$Age))
```

Marcar linea de tendencia pero vertical

Modificamos el parámetro lwd.

```
abline(v=mean(banana$Age), col="pink", lwd=5)
```

Grafica histograma con modificación en todos los parámetros vistos hasta este momento.

```
hist(banana$Age, main="Histograma", xlab="Edad", ylab="Frecuencia", col="green"")
```

Marcar linea de tendencia pero vertical. Se cambian parametros col

```
abline(v=median(banana$Age), col="pink", lwd=5)
```

Ejemplos varios de funciones vistos hasta ahora.

```
mean(banana$Education)
```
```
median(banana$Education)
```
```
mfv(banana$Education)
```
```
mfv(banana$MaritalStatus)
```
```
mean(banana$Usage)
```
```
median(banana$Usage)
````
```
mfv(banana$Usage)
```
```
mfv(banana$Fitness)
```
```
mean(banana$Income)
```
```
median(banana$Income)
```
```
mfv(banana$Income)
```
```
mean(banana$Miles)
```
```
median(banana$Miles)
```
```
mfv(banana$Miles)
```
```
hist(banana$Miles, main="Histograma", xlab="Millas", ylab="Frecuencia")
```
```
abline(v=mean(banana$Miles), col="darkred", lwd=5)
```
```
abline(v=median(banana$Miles), col="pink", lwd=5)
```
```
hist(banana$Miles, main="Histograma", xlab="Frecuencia", ylab="Millas")
```
```
hist(banana$Miles, main="Histograma", xlab="Millas", ylab="Frecuencia")
```
```
abline(v=mean(banana$Miles), col="darkred", lwd=5)
```
```
abline(v=median(banana$Miles), col="pink", lwd=5)
```
```
abline(v=mean(banana$Miles), col="lightsalmon2", lwd=5)
```
```
abline(v=median(banana$Miles), col="cornflowerblue", lwd=5)
```
```
as.factor(mean(banana$Age))
```
```
as.integer(mean(banana$Age))
```
```
as.integer(mean(banana$Usage))
```
```
as.integer(mean(banana$Education))
```
```
sapplu(banana, class)
```
```
sapply(banana, class)
```
```
print(banana$Gender)
````

## Semana 6. Clase 5. 4 de Marzo: Medidas de Dispersión. Medidas de dispersión en R.

Instalamos el paquete MASS.

```
library(MASS)
```

Cargamos los datos pima.te.

```
data("Pima.te")
```
```

Vemos el número de datos
```
Filas
```
nrow(Pima.te)
```
Vista global

```
View(Pima.te)
```
Usamos summary para la columna glu.
```
summary(Pima.te$glu)
```
Asignamos el rango calculado manualmente.

```
var <- 197-65
```
Lo obtenemos con una función.

```
range(Pima.te$glu)
```
Calculamos el rango intercuartil usando una función.

```
IQR(Pima.te$glu)
```
Obtenemos la varianza  de glu.

```
 var(Pima.te$glu)
```
Obtenemos el cuadrado de la varianza previa.
```
sqrt(var(Pima.te$glu))
```
```
sqrt(var(Pima.te$glu))
```
```
sqrt(var(Pima.te$glu))
```
Calculamos la desviación estándar 

```
sd(Pima.te$glu)
```
Usamos sapply para calcularla para todas las columnas.
```
sapply(Pima.te, sd)
```
Esto nos regresa un error 
Verificamos la clase de nuestros datos
```
sapply(Pima.te, class)
```
Encontramos valores tipos de datos que no son conoatibles con sd.
Por lo que restringimos el argumento a una concatenación valida.
```
sapply(Pima.te[c('npreg', 'glu', 'age')], sd)
```

Obtenemos promedios con la misma restricción de argumento .
```
sapply(Pima.te[c('npreg', 'glu', 'age')], mean)
```

Graficamos un histograma y su linea de tendencia,

```
hist(Pima.te$glu)
abline(v=mean(Pima.te$glue), col="salmon", lwd=5)
```

Ahora trabajamos con leuk.
```
data(leuk)
```
```
force(leuk)
```
```
View(leuk)
```
```
nrows(leuk)
```
```
nrow(leuk)
```
```
summary(leuk$time)
```
```
mvf(leuk$time)
```
```
summary(leuk$time)
```

Activamos el paquete modeeest.

```
library(modeest)
```

Usamos la funcion para calcular moda.

```
mfv(leuk$time)
```
```
var(Pima.te$glu)
```
```
range(leuk$time)
```
```
var1 <- 197-65
```
```
IQR(leuk$time)
```
```
range(leuk$wbc)
```

```
var1 <- 100000-750
```

```
IQR(leuk$wbc)
```

```
var1
```

```
var(leuk$wbc)
```

```
sqrt(var(leuk$wbc))
```

```
table(leuk$ag)
```


## Semana 7. Clase 6. 11 de Marzo: Distribución de frecuencias en R.

Notas obtenidas de presentación.

Activamos MASS y visualizamos painters.

```
library(MASS)   
painters 
```

Calculamos frecuencia con

```
table(painters$School)
```
La frecuencia acumulada la obtenemos con cumsum.

```
cumsum(table(painters$School))
```


Para convertirlo en una “Tabla”

```
cbind(cumsum(table(painters$School)))
table(painters$School) /nrow(painters)
table(painters$School) /length(painters$School)
```

Asignamos resultados a una variable.

freqr<- table(painters$School) / length(painters$School)

Corroboramos resultado.

```
sum(freqr)
```

Para transformar en porcentaje:
```
freqpct<-table(painters$School)/nrow(painters) *100
freqpct
```
Redondeamos con 

```
round(freqpct,2)
```

Verificamos que sumen 100%
```
sum(freqpct)
```

Crear una tabla con frecuencia absoluta, relativa y acumulada

```
xout <- as.data.frame(table(painters$School))
xout <- transform(xout, cumFreq = cumsum(Freq), relative = prop.table(Freq))
xout
```

Ejemplo de  creación manualmente de intervalos

```
breaks=seq(0,50, by=10)
breaks
```
Usamos la defincion anterior en la función cut.

```
clasif=cut(ch6ds1$Reading,breaks,right=FALSE)
freq.int<-table(clasif)
freq.int
clasif
cbind(freq.int)
        freq.int
```

Ahora graficamos con hist()
```
hist(ch6ds1$Reading,xlab="Scores",main="Reading",col="deeppink",breaks=7)
hist(ch6ds1$Reading, probability = TRUE)
lines(density(ch6ds1$Reading))
```
 
## Semana 9. Clase 9. 1 de Abril: Histogramas, gráficos de caja y dotplots en R.

En esta clase nos encargamos de aplicar la teoría de sesgo y curtósis:

Primero se installa moments

```
install.packages("moments")
```

Se activa

```
library(moments)
```

Usamos este dataframe

```
data(mtcars)
```

Vemos el dataframe

```
View(mtcars)
```

NOTA:
Recordar:
> >3 lepto""" 
> = 3 meso"""
> < plati

> -0.5 a 0.5 simétrica
> -1 a 1, sesgo moderado
> mayor a -1 y 1, sesgo considerable

Aplicamos la función skewness a la columna mpg

```
skewness(mtcars$mpg)
```
Aplicamos la función kurtosis a la columna mpg

```
kurtosis(mtcars$mpg)
```
Hacemos un histograma de mpg 

```
hist(mtcars$mpg)
```
Con el parametro probability = TRUE podemos obtener una visualización útil para aplicar nua línea 
```
hist(mtcars$mpg, probability=TRUE)
```
Marcamos una línea de densidad (es necesario tener prob = TRUE)
```
lines(density(mtcars$mpg))
```

Aplicamos la función skewness y kurtosis a la columna wt y disp

Para wt

```
skewness(mtcars$wt)
kurtosis(mtcars$wt)
```
Hacemos histograma

```
hist(mtcars$wt)
hist(mtcars$wt, probability=TRUE)
```

Marcamos sus líneas de dénsidad

```
lines(density(mtcars$wt))
```
Para disp

```
skewness(mtcars$disp)
kurtosis(mtcars$disp)
```
Hacemos histograma

Simple

```
hist(mtcars$disp)
```
Activamos el parametro prob.

```
hist(mtcars$disp, probability=TRUE)
```

Añadimos poligono

```
lines(density(mtcars$disp))
```

Como en otros ejercicios, usamos saply

```
sapply(mtcars, skewness)
```

graficamos carb por ser mayor a uno

```
hist(mtcars$carb, probability=TRUE)
```

Para este caso particular vemos que para la grafica anterior hay uns sesgo a la derecha.


### Dot plot

Usamos la función stripchart.

Ejemplos de uso
```
stripchart(mtcars$carb, method="stack", offset=1, at=0, pch=20, col="red")
```

#### Box plot

Usamos la función boxplot

Ejemplos de uso 
```
boxplot(mtcars$disp, horizontal=TRUE)
```

```
stripchart(mtcars$disp, method="jitter", pch=19, add=TRUE, col="orange")
```

TODO LO ANTERIOR FUE PARA PRACTICAR, LA ACTIVIDAD SE HIZO CON LOS DATOS crime_R

```
crime <- read.csv(file.choose())
```

```
View(crime)

```
Se cambia eje x y y 

A continuación se muestra ina serie de manipulación de los parametros de hist.
```
hist(crime$StateSize10, main="StateSize10", xlab="StateSize", ylab="Frecuencia", col="red")
```
```
hist(crime$HighYouthUnemploy10, main="HighYouthUnemploy10", xlab="HighYouthUnemploy10", ylab="Frecuencia", col="blue")
```
Al final se utilizaron estos parametros:

```
hist(crime$YouthUnemployment, main="YouthUnemployment", xlab="YouthUnemployment", ylab="Frecuencia", col="green")
```
Se hizo un dotplot

```
stripchart(crime$Males, method="stack", offset=2, at=0, pch=19, col="darkgreen")
```

Preparación de datos para boxplot de Expenditure Year 0 y Expenditure Year 10

```
expenditureyear0 <- crime$ExpenditureYear0
```
```
expenditureyear10 <- crime$ExpenditureYear10
```

```
expenditureyear0_norm <- rnorm(200,mean=mean(expenditureyear0, na.rm=TRUE), sd=sd(expenditureyear0, na.rm=TRUE))
```
```
expenditureyear10_norm <- rnorm(200,mean=mean(expenditureyear10, na.rm=TRUE), sd=sd(expenditureyear10, na.rm=TRUE))
```

Graficamos nuestros datos con:

```
boxplot(expenditureyear0, expenditureyear10, main = "comparación", at = c(1,2), names = c("expenditureyear0", "expenditureyear10"), las = 2, col = c("orange","red"), border = "brown", horizontal = TRUE)
```

## Semana 10. Clase 9. 1 de Abril del 2024: Formas alternativs de reportar puntajes.

15 de abril #Cargar resultados crudos de una prueba de opción múltiple

```
score <- read.csv("http://lang-tech.net/doc/sample.score.csv", header = TRUE, sep = ",")
```
```
View(score)
```

Cargar la clave de respuestas (si te sale un warning es normal)
```
key <- read.csv("http://lang-tech.net/doc/sample.key.csv", header = TRUE, sep =",")
```

```
Instala el paquete CTT
```
```
install.packages("CTT")
```
```
library(CTT)
```

Calificar prueba
```
myScore <- score(score, key, output.scored=TRUE)
```

Ve qué hay en myScore
```
View(myScore)
```

¿Cuántas pruebas vamos a calificar?
```
length(myScore$score)
```

Saca el promedio y mediana usando una sola función (myScore$score)

Puntajes alternativos

Sacar percentiles
```
percentil<-score.transform(myScore$score,mu.new=9.44,sd.new=3, normalize=TRUE)
```

```
View(percentil)
```

Multiplica los p.scores por 100 para obtener el percentil en porcentaje

```
percentil<-percentil$p.scores*100
```

¿Cuántos decimales tienen tus valores del percentil?
```
View(percentil)
```

Redondea a 2 decimales
```
percentil<-round(percentil2,digits=2)
```

Z-score
```
zscore <- scale(rowSums(myScore$scored), center = TRUE, scale = TRUE)
```

T-scores: ¿Recuerdas la fórmula para sacarlo a partir del t-score? Cálculalos.

Estaninas- (la fórmula más difícil de hoy)

```
stanine.scale <- vector("numeric")
i <- 1
for (i in 1:length(myScore$score)){
  stanine.scale[i] <- round(1.96*zscore[i]+5, 0)
  if (stanine.scale[i] <= 0){
    stanine.scale[i] <- 1}
  if (stanine.scale[i] >= 10){
    stanine.scale[i] <- 9
  }
 ``` 
Crea una variable con los puntajes totales
```
puntaje<-rowSums(myScore$scored)
```
  
Crea una tabla con los puntajes totales.
```
tabla<-table(puntaje)
```
  
Añade a la tabla las otras formas en que se pueden reportar puntajes
```
tabla<-cbind(puntaje, percentil, zscore, tscore, Estaninas=stanine.scale)
```
  
Ve el resultado
```
View(tabla)
```
  
¿Te gustan los nombres de las columnas? Cámbialos. 
```
colnames(tabla)<-c('Puntaje', 'Percentil', 'Z-score', 'T-score','Estanina')
```



## Semana 12. Clase 9. 22 de abril: Análisis de Reactivos

Análisis de reactivos en R

1. Primero cargamos un documento con las respuestas.

```
data <- read.csv(file.choose())
```
Comprobamos que su contenido

```
View(dat)
```
 
2. Definir ítems y respuestas

Aquí asignamos la la concatenación de los items a la variable items.
 
 ```
items  <- c("i1", "i2", "i3", "i4", "i5", "i6", "i7", "i8", "i9", "i10","i11","i12", "i13","i14")
```
 
Otra forma de hacer esto mismo sin escribir variable por variable es con la función paste0():

```
items<- paste0("i", 1:14)
```

Con la función rm() podemos remover la variable ítems de ser necesario.

```
rm(ítems)
```

Se definieron las respuestas asignando a la variable key una concatenación de letras.

```
key	<- c("A", "J", "M", "Q", "C", "F", "N", "I", "E", "H", "L", "O", "G", "K") 
```
 
Se instala al paquete CTT
 
```
install.packages("CTT")
```
Se activa
```
library("CTT")
```
 
3.Calificar las respuestas
 
Para poder consultar el resultado después, vamos a guardarlo en una variable

Primero asignamos a la variable puntajes el resultado de la función con los siguientes parametros:


```
puntajes<-score(dat[,items], key, output.scored = TRUE, ID = dat$candno)
```

También aplicamos esta función
 
```
options(max.print = 10000)
```

Imprimimos nuestros puntajes
```{r}
puntajes
```
Podemos usar $ para aislar resultados.

```{r}
puntajes$score
```

```{r}
puntajes$scored
```

Se convirtieron los puntajes a un data frame

```
tabpuntajes <- as.data.frame(puntajes$scored)
```

Para añadir los totales corremos:


```
tabpuntajes$tot <-puntajes$score
```
Corroboramos con

```
tabpuntajes
```


Ahora para exportarlo como csv, corremos:

```
write.csv(tabpuntajes,"PuntajesSB.csv")
```

4. Análisis de ítems

Con la función itemAnalysis podemos automatizar esto

```
analisis<-itemAnalysis(tabpuntajes[,items])
```

Corroboramos

```
analisis
```

O con más detalle
 
```
str(analisis)
```
  
 
5. Análisis de distractores
   
CTT tiene una función para esto. Por default, necesita dividir los datos en 3 grupos por lo menos.

 
```
distractorAnalysis(dat[, items], key, nGroups=3, digits=2)
``` 
 
Anteriormente, habíamos visto que para obtener el índice de discriminación en grupos pequeños necesitábamos dividir por la mitad a un grupo pequeño o tomar en cuenta el 25% inferior y el 25% superior. Si quisiéramos obtener la proporción de respuestas correctas en estos últimos:

```
AnDist <-distractorAnalysis(dat[, items], key, defineGroups=c(.25, 0.50, .25), digits=2)
``` 
```
AnDist
```
  
Ejemplo de análisis de reacrivos concretos:

```
DistAn3 <- distractorAnalysis(dat[, items], key, defineGroups=c(.27, .46, .27), digits=2)[1:4]
```

Uno de los parametros de esta función nos permite guardar el output como csv.
 
```
AnDist <-distractorAnalysis(dat[, items], key, defineGroups=c(.25, 0.50, .25), digits=2,        	csvReport="reporte_distractores.csv")
```

## Semana 13. Clase 10. 29 de abril: Análisis de Reactivos II


En este ejercicio analizamos escalas de likert.

Las funciones relevantes para esto fueronn:


Cargar los datos

```{r}
Likdat<-read.csv(file.choose())
```

Corroborar datos:

Usando View

```
View(Likdat)
```

o str

```
str(Likdat)
```

Para este ejercicio quitamos la primer columna (id)

```{r}
Likdat_sub<-Likdat[,c(-1)]
```

#### Análisis de respuestas

Usamos el paquete CTT

```{r}
library(CTT)
```
Con este paquete es posible usar la función itemAnalysis, se usará como a continuación:

```{r}
ItanL   <- itemAnalysis(Likdat_sub)
```

Vemos el resultado

```{r}
ItanL
```

Para un análisis más completo usamos usar str()

```
str(ItanL)
```

Visualizamos itemReport

```
ItanL$itemReport
```

Ahora instalamos el paquete questionr para usar sus funciones

```
install.packages("questionr")
```

Activamos 

```{r}
library(questionr)
```

Ver la frecuencia de respuestas en una pregunta con esta función:

```
questionr::freq(Likdat$q1)
```

Para sacar las frecuencias de las 4 preguntas al mismo tiempo usa una de las siguientes funciones:

Opción 1

```
apply(Likdat_sub,2,questionr::freq)
```

Opción 2 (si no creaste el subconjunto de respuestas)
```
apply(Likdat[,c(2:5)],2,questionr::freq)
```

Vamos a graficar la frecuencia de la pregunta 1 
```
barplot(table(Likdat$q1))
```

#### Cómo analizar reactivos politómicos

Por ejemplo, si al evaluar un ensayo hay 4 rubros o aspectos. 

```
polydat<-read.csv(file.choose())
```

```
View(polydat)
```

Se asignan a una variable la concatenación de los resultados.

```
polys   <- c("poly1", "poly2", "poly3", "poly4")
```

Analizamos los rubros

```
itanp   <- itemAnalysis(polydat[,polys])
```

```
str(itanp)
```

Aislamos el item report
```
itanp$itemReport
```

Aunque podemos ver el promedio para cada uno de los rubros, queremos ver la dificultad también. 

Para eso usamos:

```{r}
PolyAnReport   <- itanp$itemReport
PolyAnReport$item_p <- PolyAnReport$itemMean/itanp$nItem
PolyAnReport
```
