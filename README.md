# Bitacora de uso de R para aplicaciones estadísticas

###  Héctor García de la Cruz

## Semana 1. Clase 1: 2 de Febrero del 2024

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

## Semana 2. Clase 2: 9 de Febrero del 2024

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

_ Ahora bien, para aterrizar el uso de R en el análisis cualitativo vale la pena mencionar que un factor puede representarse en R como un vector. _

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

'''sh
> class(banana)
[1] "data.frame"
'''

Para obtener el resultado del tipo de dato para cada columna debemos usar

>sapply(<varDF>, <función_a_repetir>)

## Semana 3. Clase 3: 16 de Febrero


//Aún pendiente de detalles:

total_ex1 <- rowSums(examen1)
total_ex2 <- rowSums(examen2)
> cor(total_ex1,total_ex2)

Vamos a hacer una gráfica de dispersión
>plot(total_ex1,total_ex2)
 
Vamos a hermosear la gráfica para que se vea mejor. 

Cambiar la escala de los ejes: 
> plot(total_ex1,total_ex2, xlim=c(0,20), ylim=c(0,20))

Agregar títulos en los ejes
>plot(total_ex1,total_ex2, xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2")

Agregar un título principal
>plot(total_ex1,total_ex2,main="Prueba de Validez de Criterio", xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2")

Rellenar los puntos y ponerlos de color verde obscuro (dark green)
 plot(total_ex1,total_ex2,main="Prueba de Validez de Criterio", xlim=c(0,20), ylim=c(0,20), xlab="Examen 1", ylab="Examen 2",pch=19, col="dark green")

Dibujar línea de tendencia en rojo
abline(lm( total_ex1~total_ex2),col="red")


## Semana 5. Clase 4: 26 de Febrero

//Pendiente de explicación:

>banana<-read.csv(file.choose(), header=TRUE)
>View(banana)
>clear
>clear()
>sapply(banana, class)
#sumar valores de la tabla
>sum(banana$Age)
#Dividirlos entre el número de datos (length
>length(banana$Age)
>valoresTabla <-sum(banana$Age)
>numeroDatos <- length(banana$Age)
>valoresTabla/numeroDatos
>valoresTabla <-sum(banana$Age)
>numeroDatos <- length(banana$Age)
>valoresTabla/numeroDatos
>mean(banana$Age)
>promedioManual <- valoresTabla/numeroDatos
>primedioFuncion <- mean(banana$Age)
>fPilotos <- c(4, 11, 12, 21, 30, 12, 9, 1)
>vPilotos <- c(97, 94, 92, 91, 90, 89, 78, 60)
>wighted.mean(vPilotos, fPilotos)
>weighted.mean(vPilotos, fPilotos)
#Ordenar de mayor a menor
>sort(vPilotos)
#Sacarle la longitud
>length(vPilotos)
>median(vPilotos)
>median(vPilotos)
#Respuesta para la tercera columna
>median(banana$Age)
#Prueba sólo para ver qué sale
>mode(banana$Age)
#convertimos a factor los resultados y summary los suma
>summary(as.factor(banana$Age))
>source("~/.active-rstudio-document")
>install.packages("modeest")
>library(modeest)
>moda<-mfv(banana$Age)
>moda
#usar funcion del paquete
>moda <- mfv(banana$Age)
>summary(banana)
#Histograma
>hist(banana$Age)
#Histograma
>hist(banana$Age, color="pink")
#Histograma
>hist(banana$Age")
#Histograma
>hist(banana$Age", main="Histograma", xlab="Edad", ylab="Frecuencia")
#Histograma
>hist(banana$Age, main="Histograma", xlab="Edad", ylab="Frecuencia")
#Marcar linea de tendencia
>abline(v=mean(banana$Age))
#Marcar linea de tendencia pero vertical
>abline(v=mean(banana$Age), col="pink", lwd=5)
#Marcar linea de tendencia pero vertical
>abline(v=mean(banana$Age), col="darkred", lwd=5)
#Grafica histograma
>hist(banana$Age, main="Histograma", xlab="Edad", ylab="Frecuencia", col="green"")
#Grafica histograma
>hist(banana$Age, main="Histograma", xlab="Edad", ylab="Frecuencia", col="green")
#Grafica histograma
>hist(banana$Age, main="Histograma", xlab="Edad", ylab="Frecuencia")
#Marcar linea de tendencia pero vertical. Se cambian parametros col
>abline(v=mean(banana$Age), col="darkred", lwd=5)
#Marcar linea de tendencia pero vertical. Se cambian parametros col
>abline(v=mean(banana$Age), col="darkred", lwd=5)
#Marcar linea de tendencia pero vertical. Se cambian parametros col
>abline(v=median(banana$Age), col="pink", lwd=5)
>summary(banana)
>sapply(banana, class)
>producto <- mfv(banana)
>producto <- mfv(banana$Product)
>producto
>mean(banana$Age)
>median(banana$Age)
>mvf(banana$Age)
>mfv(banana$Age)
>mfv(banana$Gender)
>mean(banana$Education)
>median(banana$Education)
>mfv(banana$Education)
>mfv(banana$MaritalStatus)
>mean(banana$Usage)
>median(banana$Usage)
>mfv(banana$Usage)
>mfv(banana$Fitness)
>mean(banana$Income)
>median(banana$Income)
>mfv(banana$Income)
>mean(banana$Miles)
>median(banana$Miles)
>mfv(banana$Miles)
>hist(banana$Miles, main="Histograma", xlab="Millas", ylab="Frecuencia")
>abline(v=mean(banana$Miles), col="darkred", lwd=5)
>abline(v=median(banana$Miles), col="pink", lwd=5)
>hist(banana$Miles, main="Histograma", xlab="Frecuencia", ylab="Millas")
>hist(banana$Miles, main="Histograma", xlab="Millas", ylab="Frecuencia")
>abline(v=mean(banana$Miles), col="darkred", lwd=5)
>abline(v=median(banana$Miles), col="pink", lwd=5)
>abline(v=mean(banana$Miles), col="lightsalmon2", lwd=5)
>abline(v=median(banana$Miles), col="cornflowerblue", lwd=5)
>as.factor(mean(banana$Age))
>as.integer(mean(banana$Age))
>as.integer(mean(banana$Usage))
>as.integer(mean(banana$Education))
>sapplu(banana, class)
>sapply(banana, class)
>print(banana$Gender)

## Semana 6. Clase 5 4 de Marzo del 2024



## Semana 7. Clase 6 11 de Marzo del 2024


## Semana 8. No hubo Clase.

Clase 7 21 de Marzo del 2024

## Semana 9. Clase 8 1 de Abril del 2024
En esta clase nos encargamos de aplicar la teoría de sesgo y curtósis:


### Primero se installa moments

> install.packages("moments")

### Se activa

> library(moments)

# Usamos este dataframe

> data(mtcars)

#Vemos el dataframe

> View(mtcars)

#Recordar:
#>3 lepto, 
#= 3 meso
#< plati

# -0.5 a 0.5 simétrica
# -1 a 1, sesgo moderado
# mayor a -1 y 1, sesgo considerable

#Aplicamos la función skewness a la columna mpg

skewness(mtcars$mpg)
kurtosis(mtcars$mpg)

hist(mtcars$mpg)
hist(mtcars$mpg, probability=TRUE)
lines(density(mtcars$mpg))

#Aplicamos la función skewness a la columna wt y disp

skewness(mtcars$wt)
kurtosis(mtcars$wt)

hist(mtcars$wt)
hist(mtcars$wt, probability=TRUE)
lines(density(mtcars$wt))

skewness(mtcars$disp)
kurtosis(mtcars$disp)

hist(mtcars$disp)
hist(mtcars$disp, probability=TRUE)
lines(density(mtcars$disp))

#usamos saply

sapply(mtcars, skewness)

#graficamos carb por ser mayor a uno

hist(mtcars$carb, probability=TRUE)

#vemos que para la grafica anterior hay uns sesgo a la derecha

# Dot plot

stripchart(mtcars$carb, method="stack", offset=1, at=0, pch=20, col="red")

#Box plot

boxplot(mtcars$disp, horizontal=TRUE)
stripchart(mtcars$disp, method="jitter", pch=19, add=TRUE, col="orange")

#TODO LO ANTERIOR FUE PARA PRACTICAR, LA ACTIVIDAD SE HACE CON LOS DATOS crime_R

crime <- read.csv(file.choose())
View(crime)

#Se cambia eje x y y 
hist(crime$StateSize10, main="StateSize10", xlab="StateSize", ylab="Frecuencia", col="red")

hist(crime$HighYouthUnemploy10, main="HighYouthUnemploy10", xlab="HighYouthUnemploy10", ylab="Frecuencia", col="blue")

hist(crime$YouthUnemployment, main="YouthUnemployment", xlab="YouthUnemployment", ylab="Frecuencia", col="green")

stripchart(crime$Males, method="stack", offset=2, at=0, pch=19, col="darkgreen")

# preparar para boxplot de Expenditure Year 0 y Expenditure Year 10
expenditureyear0 <- crime$ExpenditureYear0
expenditureyear10 <- crime$ExpenditureYear10

expenditureyear0_norm <- rnorm(200,mean=mean(expenditureyear0, na.rm=TRUE), sd=sd(expenditureyear0, na.rm=TRUE))
expenditureyear10_norm <- rnorm(200,mean=mean(expenditureyear10, na.rm=TRUE), sd=sd(expenditureyear10, na.rm=TRUE))

boxplot(expenditureyear0, expenditureyear10, main = "comparación", at = c(1,2), names = c("expenditureyear0", "expenditureyear10"), las = 2, col = c("orange","red"), border = "brown", horizontal = TRUE)

#### 15 de abril #Cargar resultados crudos de una prueba de opción múltiple
score <- read.csv("http://lang-tech.net/doc/sample.score.csv", header = TRUE, sep = ",")
View(score)

#Cargar la clave de respuestas (si te sale un warning es normal)
key <- read.csv("http://lang-tech.net/doc/sample.key.csv", header = TRUE, sep =",")

#Instala el paquete CTT
install.packages("CTT")
library(CTT)

# Calificar prueba
myScore <- score(score, key, output.scored=TRUE)

#Ve qué hay en myScore
View(myScore)

# ¿Cuántas pruebas vamos a calificar?
length(myScore$score)

#Saca el promedio y mediana usando una sola función (myScore$score)

#Puntajes alternativos

#Sacar percentiles
percentil<-score.transform(myScore$score,mu.new=9.44,sd.new=3, normalize=TRUE)
View(percentil) 

#Multiplica los p.scores por 100 para obtener el percentil en porcentaje
percentil<-percentil$p.scores*100

#¿Cuántos decimales tienen tus valores del percentil?
View(percentil)

#Redondea a 2 decimales
percentil<-round(percentil2,digits=2)

#Z-score
zscore <- scale(rowSums(myScore$scored), center = TRUE, scale = TRUE)

#T-scores: ¿Recuerdas la fórmula para sacarlo a partir del t-score? Cálculalos.

#Estaninas- (la fórmula más difícil de hoy)
stanine.scale <- vector("numeric")
i <- 1
for (i in 1:length(myScore$score)){
  stanine.scale[i] <- round(1.96*zscore[i]+5, 0)
  if (stanine.scale[i] <= 0){
    stanine.scale[i] <- 1}
  if (stanine.scale[i] >= 10){
    stanine.scale[i] <- 9
  }
  
#Crea una variable con los puntajes totales
puntaje<-rowSums(myScore$scored)
  
#Crea una tabla con los puntajes totales.
tabla<-table(puntaje)
  
#Añade a la tabla las otras formas en que se pueden reportar puntajes
tabla<-cbind(puntaje, percentil, zscore, tscore, Estaninas=stanine.scale)
  
#Ve el resultado
View(tabla)
  
#¿Te gustan los nombres de las columnas? Cámbialos. 
colnames(tabla)<-c('Puntaje', 'Percentil', 'Z-score', 'T-score','Estanina')

## Semana 10. Clase 9 1 de Abril del 2024


## Semana 12. Clase 9 22 de abril: Análisis de Reactivos



## Semana 13. Clase 10 29 de abril Análisis de Reactivos II


Escalas de Likert y retroalimentación de experiencia

Tras responder una prueba de comprensión auditiva, se les hizo una serie de preguntas a las personas:		

¿Qué tan familiares te resultaron los temas de las preguntas? 
		 	 	 								
2. ¿Qué tan interesantes te resultaron los audios?
					
3. ¿Que tan difíciles te parecieron los audios?	
					
4. ¿Qué tan bien crees que la prueba refleje tus habilidades de comprensión auditiva?

Las respuestas se respondieron usando una escala de Likert del 1 al 4 donde 1 significa “nada”  y 4 significa “extremadamente” 

#Cargar los datos
Likdat<-read.csv(file.choose())

#Revisar que se cargaron bien los datos y ver qué contiene la tabla. 
> View(Likdat)
> str(Likdat)

#Quita la primer columna (id)
Likdat_sub<-Likdat[,c(-1)]

#Análisis de respuestas
>library(CTT)
>ItanL   <- itemAnalysis(Likdat_sub)
> ItanL

#Recuerda: si quieres un análisis más completo necesitas usar str()
>str(ItanL)

#Vamos a ver sólo la parte de item report
>ItanL$itemReport

Aunque nos da información útil, sirve también ver la frecuencia de cada respuesta para cada pregunta. 

>install.packages("questionr")
>library(questionr)

#Ver la frecuencia de respuestas en una pregunta
> questionr::freq(Likdat$q1)

#Para sacar las frecuencias de las 4 preguntas al mismo tiempo usa una de las siguientes funciones:
Opción 1
> apply(Likdat_sub,2,questionr::freq)

#Opción 2 (si no creaste el subconjunto de respuestas)
> apply(Likdat[,c(2:5)],2,questionr::freq)

#Vamos a graficar la frecuencia de la pregunta 1 
> barplot(table(Likdat$q1))

#Repite con las otras 3 preguntas. 
Mejora la apariencia de las gráficas y pégalas en un documento. 


Cómo analizar reactivos politómicos
Por ejemplo, si al evaluar un ensayo hay 4 rubros o aspectos. 

>polydat<-read.csv(file.choose())
> View(polydat)

#Hacemos una variable que nos combine todos los puntajes de cada rubro
> polys   <- c("poly1", "poly2", "poly3", "poly4")

#Analizamos los rubros
> itanp   <- itemAnalysis(polydat[,polys])
>str(itanp)

#Aislamos el item report
> itanp$itemReport

#Aunque podemos ver el promedio para cada uno de los rubros, queremos ver la dificultad también. 

> PolyAnReport   <- itanp$itemReport
> PolyAnReport$item_p <- PolyAnReport$itemMean/itanp$nItem
> PolyAnReport
