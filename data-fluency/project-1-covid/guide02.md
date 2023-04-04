# Introducción

## Contexto

Tal como describe el brief de este proyecto, eres una analista de datos junior en un prestigioso medio de comunicación internacional. Tu reto es analizar y calcular el exceso de muertes por  COVID-19 por cada 100 mil habitantes en 4 países de Latinoamérica: Perú, Chile, Colombia y México.  

Esta guía será tu hoja de ruta para el desarrollo exitoso de este proyecto.

# Desarrollo

## Paso 1: Pregunta

Como vimos en la sección anterior, este paso es fundamental. Aquí tenemos que definir el objetivo de nuestro estudio. Para este proyecto, convenientemente, el brief nos brinda el contexto del “ida y vuelta” que se tuvo sobre el problema en cuestión.  

En resumen, sabemos que el objetivo es entender **cuáles países han sido más afectados por la pandemia** y que, luego de evaluar diversos indicadores (muertes totales reportadas por COVID por país y muertes reportadas por COVID por cada 100,000 habitantes), se definió que la métrica pertinente para el análisis es calcular **el exceso de muertes por cada 100,000 habitantes**. Si aún tienes dudas sobre cómo se calcula este indicador o las razones por las que es el indicador más pertinente, te recomendamos regresar al brief y aclarar esto antes de continuar.  

Este proceso de idas y venidas es un claro ejemplo de lo que sucede en la práctica. Como te diste cuenta, es clave cuestionar los indicadores, complementar con la experiencia de diversos stakeholders y traer información externa que pueda aportar al análisis.  

## Paso 2: Prepara

Para este proyecto, convenientemente de nuevo, contamos con los datos que necesitamos en un archivo CSV esperando por ser analizado. Esta no es la realidad de todos los proyectos. En este caso en particular, probablemente hubiéramos tenido que ir a las bases de los distintos gobiernos y de las organizaciones centrales como la OMS para buscar los datos de cada país y luego unirlos. Como es tu primer proyecto, los recolectamos por ti 🙂.

Si bien tenemos el archivo, todavía no hemos visto los datos. ¿Son confiables? ¿Están actualizados? ¿Se seguirán actualizando (en caso de que se requieran más adelante)? ¿Desde cuándo tenemos datos? También tendrás que determinar si la calidad es suficiente para responder las preguntas del negocio.  

### 2.1 Carga los datos

Los archivos que usarás se encuentran en la siguiente ruta (archivos) en formato “.csv”. Un archivo .csv (del inglés *comma separated values*) es un archivo separado por comas que tiene un formato específico que permite guardar los datos en un formato de tabla estructurada. La ventaja de este tipo de archivos con respecto a una hoja de cálculo es que ocupan poco espacio y las exigencias del cómputo que requieren son mínimas (aunque siempre dependerá de la cantidad de datos que manejes). La desventaja de estos archivos es que solo admiten datos “en crudo”, es decir, no podremos darle colores ni formatos a los datos.  

Los archivos que utilizaremos son los siguientes:

- **Proyecto 1 Covid - Poblacion.csv**: Este archivo contiene el número de habitantes por cada país. Este dato te será útil para calcular el número de fallecidos por cada 100 mil habitantes.
- **Proyecto 1 Covid - Dataset.csv**: Este archivo contiene el número de fallecidos por semana reportados por cada país.  

El desarrollo de este análisis lo realizarás utilizando las hojas de cálculo de Google. Si nunca has trabajado con esta herramienta puedes revisar [aquí](https://support.google.com/a/users/answer/9300022) la documentación oficial de Google. En caso que ya tengas experiencia en este tema, te invitamos a iniciar con la carga de los archivos a la hoja de cálculo.  

Si tienes dudas sobre cómo cargar los dos archivos ".csv" en una misma hoja de cálculo, hemos preparado este [video](https://www.loom.com/share/4a1119fb815946a080e0e02a085b1cac)(📹) que te muestra cómo hacerlo.  

> 👀 Como buena práctica al momento de cargar tu archivo en una hoja de cálculo, colócale un nombre que represente los datos que contiene, esto les ayudará a otras personas que consulten tu archivo a identificar el contenido de cada hoja de cálculo.  

### 2.2  Revisa el dataset y la estructura de los datos

Ya tienes los datos cargados en tu Google Sheets. Exploremos el dataset.

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img03.png" alt="dataset" width="600"/>  

> 👀 En algunos casos es posible que el formato de la fecha pueda cambiar de acuerdo al país donde te encuentres debido a que está siguiendo la configuración de Estados Unidos, ya que este país sigue una estructura de fechas diferente (MM/DD/AAAA). Para solucionar esta variación, podemos cambiar el país a alguno de América Latina en la configuración de Google (archivo > configuración > general > configuración regional) y volver a importar los datos.  

El archivo “Proyecto 1 Covid - Dataset.csv” cuenta con 1,252 filas, donde cada fila representa el total de muertes por semana y el total de las muertes causadas por COVID-19. A continuación te compartimos el diccionario de datos:  

- **país**: Nombre del país (Puede ser: México, Perú, Chile o Colombia).
- **fecha inicio**: Fecha inicio de la semana.
- **fecha fin**: Fecha fin de la semana.
- **días**: Cantidad de días que forman parte del conteo de fallecidos. En el caso de Chile, Perú, Colombia y México es una semana (7 días).
- **semana**: Indica el número de la semana del año. Por ejemplo, la primera semana del 2020 tendrá un valor de 1, mientras que la segunda semana del 2020 tendrá un valor de 2.
- **total muertes reportadas**: Es el total de muertes reportadas por cualquier causa (incluidas las muertes por COVID-19) en el rango de fechas establecido.
- **total muertes reportadas por covid**: Es el total de muertes reportadas causadas por COVID-19 en el rango de fechas establecido.  

Como puedes ver hay distintos tipos de variables. Números, texto, fechas y otras. Comencemos por identificar los tipos de variable que te toca enfrentar. Las variables, según la estadística, podrían ser cualitativas (ordinales o nominales) o cuantitativas (discretas o continuas). Es importante reconocer el tipo de variable porque esto te ayudará a tomar mejores decisiones en cuanto a las operaciones, transformaciones o gráficas (formatos) que puedas aplicar. Si te interesa saber más sobre los tipos de datos mira [este video](https://www.loom.com/share/afa56686810e46309761bc889364b2d9) (📹).

### 2.3 Comprende el dataset

![dataset-detalle](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img04.png)

Aquí podemos ver un ejemplo de cómo se ven los registros del archivo “Proyecto 1 Covid - Dataset.csv”, los cuales se leen de la siguiente manera:  

- El primer registro muestra la cantidad de muertes en México del 2016-10-17 al 2016-10-23 (7 días en total). Ese rango de fechas representa la semana 42 del año 2016 (recuerda que un año tiene 52 o 53 semanas), y en la semana 42 se reportaron 12,365 muertes totales y cero muertes causadas por COVID-19. Esto tiene sentido, puesto que el COVID-19 inició en 2020.
- El segundo registro muestra la cantidad de muertes en Perú durante el periodo del 2021-11-01 al 2021-11-07 (7 días), semana 44 del año, donde hubo un total de 2,834 muertes y 184 muertes causadas por COVID-19.  

## Paso 3: Procesa  

Recuerda que en este paso debemos validar que los datos que tenemos están correctos y limpios. Como es tu primer proyecto, te entregamos un dataset que ya viene limpio y listo para ser usado. No te preocupes, en tus siguientes proyectos deberás enfocar más tiempo en la limpieza de datos.  

De todas formas, cuando uno importa un archivo CSV, Google Sheet tiende a realizar transformaciones que pueden traer errores. Asegúrate de revisar todas las columnas y que su tipo de dato tenga sentido:  

- En la hoja de cálculo tienes columnas que son fechas, asegúrate que la hoja de cálculo la está reconociendo como un dato de tipo fecha, esto te será útil para que puedas aprovechar las funciones implementadas que trabajan específicamente sobre el tipo de dato fecha.
- Cuando trabajes con decimales, Google Sheets reconoce que se trata de un decimal a partir del símbolo punto (.). Si nuestro archivo contiene decimales utilizando la coma (,) como separador decimal, es posible que no puedas realizar operaciones numéricas dado que será reconocido como texto, por lo que necesitarás realizar un paso previo que será reemplazar la coma (,) por un punto (.) y luego convertir el texto a un tipo de dato numérico. Te hemos preparado un video para que puedas conocer un poquito más sobre los formatos de datos en spreadsheet, revísalo [aquí](https://www.loom.com/share/efde04f4c92c4d7699b36b2096327b09) (📹).  

## Paso 4: Analiza  

Ya tenemos nuestros datos cargados y listos para ser analizados. Recuerda que lo que queremos es calcular el exceso de muertes para cada uno de los países del dataset, pero eso suena un poco lejano. Todavía ni siquiera entendemos muy bien con qué datos contamos. Es por esto que es una buena idea comenzar explorando los datos, o dicho de otra manera, con un análisis exploratorio de los datos.

### 4.1 Realiza un análisis exploratorio

Si bien ya cargamos el dataset y entendemos cómo están ordenados los datos, todavía no hemos extraído nada de información. ¿Cuántas muertes totales por COVID tuvo Colombia en el periodo del dataset? ¿Cuántas muertes en promedio reportó Chile en los años anteriores al COVID? Todas estas son preguntas que probablemente se pueden responder con el dataset que tenemos, pero no podemos extraer información solo mirando las filas, tenemos que empezar a realizar cálculos.  

Una forma fácil de efectuar un análisis exploratorio de los datos es a través de tablas dinámicas, o pivot tables. Esta herramienta te permite resumir y hacer cálculos rápidamente tomando la variable (columna) que desees. Si no sabes cómo ocupar tablas dinámicas, apóyate en [este video](https://www.loom.com/share/5937ac5fb32c424285e952bc07097580) (📹).  

### 4.2 Realiza un análisis descriptivo  

Con este tipo de análisis seguimos intentando entender los datos con los que contamos. Es útil emplear estadística descriptiva en estos datos históricos para ver cómo se comportan.  

Las medidas descriptivas, como su nombre lo indica, se utilizan para describir un conjunto de datos y se dividen en dos categorías: medidas de tendencia central y medidas de dispersión.  

Las medidas de tendencia central (ejemplo: media, moda y mediana) se usan para saber dónde los valores tienden a estar *centrados*.  

Por otro lado, las medidas de dispersión tratan, a través del cálculo de diferentes fórmulas, de arrojar un valor numérico que ofrezca información sobre el grado de variabilidad de una variable. Entre las principales medidas tenemos:

- **El rango** es un valor numérico que indica la diferencia entre el valor máximo y el mínimo de una población.
- **Desviación típica o estándar** es una medida de dispersión que representa qué tan dispersos están los datos respecto a su media.  

Para entender de mejor manera cómo aplicar esto a nuestro proyecto hemos preparado [este video](https://www.loom.com/share/2fd9ad30fcf549949737afebba4d26e2) (📹).

### 4.3 Calcula las muertes reportadas por COVID-19 por cada 100.000 habitantes <a name="4.3"></a>  

Ahora que entendemos mejor los datos, comencemos a calcular el exceso de muertes para los países del dataset. Una forma sensata de comenzar es hacer el análisis para un solo país, por ejemplo Perú, y luego replicar lo realizado al resto de los países. Para enfocarlos solo en Perú vamos a necesitar filtrar los datos. Si no sabes cómo filtrar y ordenar datos, mira [este video](https://www.loom.com/share/9e001f9081414ec6a1f135c35d8badea) (📹).  

¿Por qué te pide el total de muertes por cada 100,000 habitantes y no solo el total?  

La cantidad de muertes normalmente se expresa como “el número de muertes por cada 1.000, 10.000, 100.000 o un millón de habitantes” esto con el propósito de efectuar comparaciones objetivas entre ciudades o países que tienen diferentes cantidades de habitantes. En nuestro caso usaremos esta métrica multiplicando el número de fallecidos por 100.000 y dividiremos el resultado entre la población total del país.  

La fórmula a usar es la siguiente:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_formula01.png" alt="grafico-exceso-muertes" width="600"/>  

Veamos un ejemplo:  

Supongamos que en el 2020 hubo 300,000 muertes en México y sabemos que la población total de ese país es 130,262,220, entonces reemplazamos los valores en la fórmula:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_formula02.png" alt="grafico-exceso-muertes" width="600"/>

El resultado del cálculo es 230.30 y se interpreta como: hubo 230 muertes por cada 100,000 habitantes en México durante el 2020.  

Ahora que ya conoces el concepto, enfoquémonos en los datos de Perú. Hay muchas formas distintas de filtrar o copiar los datos que necesitamos. En este proyecto queremos mostrarte una fórmula muy poderosa: la función QUERY. Esta es una función fundamental para las analistas de datos, ya que tiene características del mundo del SQL, un lenguaje que aprenderás en el proyecto electivo de este programa o en futuros programas de datos de Laboratoria+.  

Con la función QUERY puedes copiar y filtrar una fuente de datos utilizando sentencias SQL. No te preocupes si no las comprendes del todo. Cuando llegues al proyecto electivo tendrás todo el conocimiento que necesitas para trabajar con SQL. Por ahora te dejamos [este video](https://www.loom.com/share/d362904bf9b54abda460c89f5d192baa) (📹) que te explica como usar esta fórmula para copiar y filtrar los datos de Perú en una nueva pestaña.  

En esta nueva pestaña vamos a ir creando nuevas columnas con los datos que necesitamos. Primero calculemos las muertes reportadas por COVID-19 por cada 100.000 habitantes. Como vimos más arriba esto se calcula de la siguiente forma:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_formula03.png" alt="grafico-exceso-muertes" width="600"/>

En Google Sheets es muy fácil generar fórmulas matemáticas empleando los operadores de multiplicación (*) y división (/). En nuestros datos contamos con la cantidad de muertes, pero el número de habitantes (la población) del país se encuentra en otra pestaña. Para traer ese dato a la pestaña actual vamos a ocupar otra fórmula crucial en el análisis de datos: [BUSCARV](https://www.loom.com/share/509194c4629c42babfe34a9951fee888) (📹). Esta función nos permite traer datos de otras fuentes utilizando una celda de referencia (en nuestro caso el país que se encuentra en ambas pestañas).  

![buscarv](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img05.png)  

Finalmente, puedes revisar la tendencia de las muertes por COVID-19 a lo largo del tiempo usando una visualización de datos. Los gráficos son aliados del análisis de datos porque nos permiten comprender mejor ciertos patrones y/o comportamientos, para utilizarlos como hallazgos. En este caso, como estamos mirando un dato a través del tiempo, es útil crear un [gráfico de líneas](https://www.loom.com/share/d36d7285796c4314b1ab118c4a54033c) (📹).  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img06.png" alt="grafico-01" width="600"/>  

Esta visualización muestra la tendencia de las muertes causadas por COVID-19 por cada 100,000 habitantes en Perú. Cada número o valor del gráfico representa el número de muertes por semana por cada 100,000 habitantes. Por ejemplo, se puede ver que en la semana que inicia el 2021-02-01 se reportaron 12.15 muertes por cada 100,000 habitantes.  

### 4.4 Calcula la cantidad de muertes acumuladas por COVID-19 por cada 100 mil habitantes <a name="4.4"></a>  

El siguiente paso es conocer la cantidad acumulativa de muertes por COVID-19, muy parecido a los resultados anteriores, con la diferencia de que iremos sumando la cantidad de muertes del periodo anterior con la semana actual en una nueva columna. De esa forma nuestro número de muertes por cada 100.000 habitantes va a ir creciendo hasta llegar al total de muertes en la última fila. [Este video](https://www.loom.com/share/215d29275e16400693d70e3370b661b4) (📹) te puede ayudar si tienes dudas de cómo hacer el cálculo.  

Para este caso la gráfica va a ir creciendo semana a semana. Muy parecida a esta visualización, en donde podemos ver que a la semana del 15 de marzo de 2021 hubo aproximadamente 408 muertes acumuladas por cada 100.000 habitantes.  
  
<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img07.png" alt="grafico-07" width="600"/>  

> 🎯 Si has llegado hasta aquí, significa que ya vas por la mitad de este proyecto. ¡Felicitaciones! De seguro ya has aprendido muchísimo y también has enfrentado algunos retos en el desarrollo de tu proyecto. Tranquila, esta guía seguirá siendo tu principal aliada en lo que viene. Sin embargo, este es un buen momento para que te detengas, hagas una pequeña reflexión sobre tu avance, y revises tu planificación. Pregúntate cómo te ha servido tu organización hasta ahora, ajusta tus prioridades de ser necesario y vuelve a ordenarte para continuar avanzando. Recuerda que puedes recurrir a tus compañeras y al equipo de Laboratoria+ ante cualquier dificultad. ¡Ánimo, vas por buen camino!  

### 4.5 Calcular el pronóstico de las muertes usando promedios simples  

¿Recuerdas lo que era el exceso de muertes según la explicación que hizo Angélica en tu reunión? Según ella, el exceso de muertes es todo aquello que queda “por sobre” la estimación que hagamos de las muertes que corresponderían a ese año según los datos históricos. En otras palabras, el exceso de muertes puede ser calculado como **la diferencia del total de muertes reportadas menos el pronóstico de muertes** para cada semana.  

Te preguntarás, ¿cómo podemos pronosticar las muertes? Una forma de hacer esto simplemente promediar las muertes de años anteriores y suponer que el año actual las muertes se mantendrán en un número similar.  

Para calcular el pronóstico para un cierto periodo de tiempo, utilizaremos el cálculo de promedios simples. Por ejemplo, supongamos que para una semana particular tuvimos las siguientes cantidades de muertes antes de que llegara el COVID-19:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img08.png" alt="tabla-numero-muertes" width="600"/>  

Si te fijas, no tenemos el dato para el 2020, que es justo lo que queremos calcular. Suponiendo que el 2020, sin el COVID-19, se debería comportar de manera similar que los años anteriores es que calcularemos el promedio de los años anteriores (sumarlos y dividirlos por la cantidad de años de la data histórica).

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_formula04.png" alt="tabla-numero-muertes" width="600"/>

Entonces, el pronóstico de muertes para el 2020 usando un promedio simple será de 332 muertes aproximadamente.  

> ⚠️ Es muy importante notar que esto es una sobre simplificación. Hay formas más precisas (pero más complejas) de hacer predicciones. Si sigues en el mundo de la ciencia de datos encontrarás algoritmos fascinantes para hacer este tipo de cálculos. Por lo pronto, y para los efectos de nuestra investigación, ese cálculo es suficiente.

Bien, vamos a nuestra hoja de cálculo. Si creamos una nueva columna para calcular el promedio nos encontraremos así:  

![promedio](http://drive.google.com/uc?export=view&id=19GgV7x5aJpXeMExylORd036dsd2FaQGF)  

La primera fila en donde tenemos muertes reportadas por COVID-19 para Perú es en la semana 10 de 2020. Según lo que ya vimos, deberíamos ir a buscar todos los datos que tengamos de la semana 10 en años anteriores. Estos datos están en la base de datos original con todos los países, por lo que una forma manual de hacer el cálculo sería:  

1. Ir a la pestaña de la base de datos original
2. Buscar fila por fila la cantidad de muertes de la semana 10 de años anteriores para Perú
3. Sumar esos datos y dividirlos por la cantidad de datos que encontremos.  

Este proceso manual puede ser extremadamente lento. Afortunadamente, Google Sheet nos facilita ese tipo de cálculos repetitivos con la fórmula PROMEDIO.SI.CONJUNTO (o AVERAGEIFS en inglés). Esta fórmula recibe un rango de datos que queremos promediar, y solo promedia aquellos que cumplan con una o varias de las condiciones que le pongamos en la fórmula. ¡Justamente lo que queremos! Queremos que promedie los datos que cumplan con ser de una semana específica y de un país específico.  

Te desafío a que lo intentes hacer por tu cuenta y, en caso de que tengas dificultades para hacerlo, veas [este video](https://www.loom.com/share/c5d8f3b090a34f609b81b1790196b73e) (📹) donde te guiamos paso a paso.  

> 👀 Algunas veces al realizar cálculos nos encontramos con distintos tipos de errores, para controlarlos puedes usar la función [SI.ERROR](https://www.loom.com/share/067a204209f445f0a02effa0852871ab)(📹) que acepta como argumento una fórmula y, en caso de que esta lance error, entonces hace lo que tú le digas que haga.  
> 👩‍💻¿Qué otra medida de tendencia central podrías usar para realizar este cálculo? ¿Qué ventajas o desventajas crees que tendrías si utilizas la mediana en lugar de la media simple?  

### 4.6 Calcular el exceso de muertes desde que inició COVID-19  

Con el pronóstico realizado, ahora podemos calcular el **exceso de muertes**. Para encontrar este valor simplemente restamos **la cantidad total de muertes reportadas menos el pronóstico de muertes calculado**.  

Siguiendo el ejemplo anterior:  

Con el cálculo del pronóstico obtuvimos un promedio histórico de 332 muertes aprox. para el 2020, pero además conocemos la cifra real de muertes que es 650. Para conocer el exceso de muertes restamos 650 (cifra real) - 332 (pronóstico) = 318, entonces decimos que **tenemos un exceso de 318 muertes**.  

Si tienes dudas para calcular el exceso de muertes en Google Sheets, puedes apoyarte con el siguiente [video](https://www.loom.com/share/56efe70149144f86880b2211c94f9569)(📹).  

### 4.7 Calcular el exceso de muertes desde que inició COVID-19 por cada 100,000 habitantes

Como ya hemos visto, los números absolutos sobre representan a algunos países. Cada métrica que calculemos debemos llevar a la medida relativa “por cada 100.000 habitantes”. Este cálculo se hace de la misma manera que lo que hicimos en la [sección 4.3](#4.3). Crea una columna “Exceso de Muertes por COVID-19 por 100,000 hab” y aplica la fórmula aprendida en esa sección. Deberías llegar a números similares a estos.  

![exceso-muertes](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img09.png)  

Llevemos estos datos a una gráfica.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img010.png" alt="grafico-exceso-muertes" width="600"/>  

> 👩‍💻¿Te llama la atención este gráfico? ¿Se parece a alguna otra visualización que ya hicimos? ¿Por qué crees que es así?  

### 4.8 Calcular el exceso de muertes por COVID-19 por cada 100,000 habitantes acumulado

En la [sección 4.4](#4.4), calculamos la cantidad de muertes acumuladas por cada 100,000 habitantes en Perú. Ahora vamos a aplicar los mismos pasos, pero sobre la columna exceso de muertes para obtener el acumulado del exceso de muertes, con el objetivo de realizar la comparación con las cifras de muertes oficiales acumuladas. Crea una columna “Exceso de Muertes por COVID-19 acumuladas por 100,000 habitantes” y aplica el mismo procedimiento que hemos venido trabajando en los pasos anteriores. La siguiente imagen muestra los resultados de la nueva columna.  

![exceso-muertes-acum-100000](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img011.png)  

Y, al igual que en las secciones anteriores, graficamos el acumulado.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img012.png" alt="grafico-exceso-muertes-acum-100000" width="600"/>  

Notarás que las formas de los dos gráficos anteriores son muy parecidos a los generados en las secciones [4.3](#4.3) y [4.4](#4.4), así que para poder realizar una mejor comparación, vas a unir estos dos gráficos dado que visualmente podemos sacar conclusiones mucho más rápido. Puedes revisar este [vídeo](https://www.loom.com/share/6b85d94c1d964f009d4f903a0483c7f8)(📹) para conocer cómo mostrar más de dos variables en un solo gráfico. El resultado se muestra en la siguiente figura, donde se compara el número de muertes reportadas de forma oficial versus el exceso de muertes por cada 100.000 habitantes.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img013.png" alt="total-muertes-versus-exceso" width="600"/>  

> 👩‍💻¿Qué puedes apreciar al comparar el exceso de muertes (línea roja) con las cifras oficiales reportadas por COVID-19 (línea azul)? ¿Existen diferencias muy marcadas? ¿Existen similitudes?.  

Por último, genera el mismo gráfico, pero ahora juntando las visualizaciones de las muertes acumuladas comparando cifras oficiales y exceso de muertes.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img013.png" alt="total-muertes-reportadas-versus-exceso-acumulado" width="600"/>  

### 4.9 Calcula la cantidad de semanas de duración de los picos  

Hasta ahora has completado con todos los gráficos y métricas que te pide el brief para cada país, pero sabemos muy bien que una buena analista de datos no se queda únicamente con lo básico, sino que complementa su análisis con métricas que puedan enriquecer las recomendaciones a los stakeholders.  

Otra métrica que puede ayudar a mostrar el impacto de la pandemia en cada país es el tiempo que pasó cada uno en un “pico” de la pandemia. Un pico es un aumento fuera de lo normal de los casos de muertes.  

¿A partir de cuántos fallecidos se considera un pico? Esto no es tan fácil de determinar. Una opción es revisar la literatura y tratar de encontrar algún número de fallecidos para tomarlo como referencia. Otra opción común es mirar las visualizaciones con las que ya cuentas y definir un valor que te hace sentido que sea considerado un pico. Para el ejemplo, podemos considerar que un "pico" es cuando las muertes por COVID-19 por cada 100 mil habitantes es mayor a 6. Podría haber sido otro número, no te preocupes, siempre y cuando tenga sentido con tu visualización y seas consistente con el resto de los países.  

Entonces, ahora calculemos cuántas semanas desde que inició la pandemia estuvieron por encima de las 6 muertes por COVID-19 por cada 100 mil habitantes. Para realizar este cálculo tendrás que usar la función **COUNTIF** (CONTAR.SI). En el siguiente [video](https://www.loom.com/share/46c82f8134334d71b3bec49acc1e7325) te mostramos cómo puedes hacerlo para el caso de Perú. Replica la fórmula para el resto de países. No olvides agregar los resultados en tu reporte, pues sin duda te ayudará a que puedas argumentar mejor tus conclusiones.  

¡Felicidades! Has completado el análisis para el caso de Perú, ahora solo queda replicar el mismo análisis para los 3 países restantes.  

Si necesitas una guía para armar la tabla comparativa por país, te recomendamos revisar este [video](https://www.loom.com/share/419c8482e6b2463c863c9d17afe1d679)(📹).  

## Paso 5: Comparte

Es momento de organizar toda la información que has acumulado. El análisis desarrollado generará impacto siempre y cuando se efectúe una adecuada presentación. Si los datos no son presentados correctamente, es posible que pasen desapercibidos o sean malinterpretados.  

Una forma útil de asegurarte de que no te falte nada, es volver a revisar el brief. En el se te pide que compartas una hoja de cálculo con tu reporte que incluya los indicadores solicitados.  

Te dejamos un ejemplo de cómo se deberían ver cada uno de los puntos solicitados en el reporte:  

- Una tabla comparativa con el total de muertes reportadas por COVID-19 por cada 100 mil habitantes, el total de “exceso de muertes” por cada 100 mil habitantes y la diferencia entre ambas cifras, por país.

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img016.png" alt="tabla-comparativa" width="600"/>

- Un gráfico que muestre los datos de la tabla anterior en forma de gráfico de barras.

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img017.png" alt="grafica-comparativa" width="600"/>

- Un gráfico por cada país que muestre el comparativo de la evolución en el tiempo de las muertes reportadas COVID-19 vs. el cálculo de “exceso de muertes” semana a semana, ambos datos por cada 100 mil habitantes.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img018.png" alt="tabla-comparativa-evolucion" width="600"/>  

- Un gráfico por cada país que muestre las mismas variables que el punto anterior, pero acumuladas en el tiempo:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img019.png" alt="grafico-por-pais-acumulado" width="600"/>  

- Con toda la información anterior busca estructurar un reporte que resuma los gráficos y tablas de forma ordenada en una pestaña de tu reporte de tal forma que te permita darle sentido a la información y soporte tu presentación. La figura muestra un ejemplo de una estructura que puedes utilizar.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img020.png" alt="ejemplo-estructura-reporte" width="600"/>

## Paso 6: Actúa  

El reporte por sí solo no genera acción. Es aquí donde se vuelve esencial el video que debes grabar simulando la reunión con tu jefe para explicarle tus hallazgos y entregar tus recomendaciones. Te recomiendo volver a leer el brief y volver a la pregunta inicial del análisis. Enfoca tu recomendación y conclusiones en ese contexto.  

Para hacer el video te recomendamos utilizar [Loom](http://loom.com/signup). Para poder conocer cómo funciona esta plataforma Loom, revisa el siguiente [video](https://www.youtube.com/watch?v=-8mwLqvNOPY).  

Cuando estés lista sube el link de tu reporte y de tu video en la plataforma de aprendizaje.  

Asegúrate que tu reporte sea visible públicamente. Aquí te explicamos cómo:  

- En la parte superior derecha encontrarás un botón verde que dice “Share”/”Compartir”.  

![screenshot-share-01](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img021.png)  

- Una vez dentro modifica el tipo de acceso que quieres brindar, en este caso usa el que dice “Cualquiera con el enlace”/”Anyone with the link”.  

![screenshot-share-02](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img022.png)

- Finalmente da clic en el botón “Copiar enlace”/”Copy link” y pégalo donde te lo soliciten.  

![screenshot-share-03](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img023.png)  

¡Ya estás lista! Felicitaciones por entregar tu proyecto. Sigue atenta a la comunidad online en Slack para ver si puedes apoyar a alguna de tus compañeras. Si todavía te queda algo de tiempo te recomendamos hacer la versión hacker de este proyecto, en donde podrás profundizar algunos objetivos de aprendizaje y llevarte algunas herramientas útiles para tu carrera.  

# Hacker Edition

Cómo ya hemos hablado, nuestra predicción de la cantidad de muertes basada en el promedio de muertes según la data histórica es solo una aproximación. Como buena analista de datos vale la pena preguntarse, ¿cómo podría mejorar esa predicción?  

Hay muchas formas de hacerlo, pero una técnica muy útil es la regresión lineal. En simple, lo que intenta hacer una regresión lineal es tomar los puntos de datos históricos y ver si estos marcan una tendencia, para luego trazar una línea que se ajuste lo mejor posible a la tendencia de esos datos y luego ocuparla para hacer predicciones. Para entender mejor este concepto veamos un ejemplo.  

Estos son los datos de fallecidos en Colombia en la semana 15 de distintos años:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition01.png" alt="tabla-colombia-hacker-edition" width="400"/>  

Supongamos que no sabemos la cantidad de muertes del 2019 y queremos hacer una estimación con el método que utilizamos en el proyecto: promediando los datos históricos.  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition02.png" alt="tabla-colombia-hacker-edition" width="400"/>  

Según nuestra predicción, debería haber 4182 muertes en 2019, pero la realidad es que hubo 4548. Aquí podemos ver que nuestra estimación estuvo 366 por debajo de la realidad. Eso es un error de estimación muy grande, que sirve para efectos de nuestro análisis, pero que sin duda podemos mejorar.  

Si graficamos los puntos vamos a ver porque nuestra estimación estuvo tan lejos:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition03.png" alt="grafico-hacker-edition-01" width="600"/>  

En gris podemos observar los puntos históricos que estamos tomando para calcular nuestro promedio. Si te fijas bien, esos cuatro puntos tienen una tendencia al alza, es decir, las muertes van aumentando año a año.  

> 👩‍💻¿Por qué crees que la cantidad de muertes tiene una tendencia al alza en este caso particular? ¿Qué rol juega la demografía del país?  

Nuestro promedio (en amarillo) no toma en cuenta esta tendencia. Simplemente, promedia lo sucedido en años anteriores para calcular su valor, y es por esta razón que el valor real (en verde) se aleja tanto de nuestra predicción. Este valor sigue la tendencia al alza que vemos en el gráfico.  

En rosado pálido podemos ver la regresión lineal. Como vimos, esta es una línea recta que intenta ajustarse a los puntos históricos que le demos como parámetros, en este caso los datos de los años 2015, 2016, 2017 y 2018. Si ocupamos esta regresión lineal para hacer nuestra predicción y buscamos el punto en donde se intercepta el año 2019 (que es el año que queremos predecir) con la recta, obtenemos una mejor predicción:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition04.png" alt="grafico-hacker-edition-02" width="600"/>  

Este pronóstico (punto rosado) todavía está lejos de la realidad, pero al menos es una mejor estimación que el cálculo del promedio simple, ya que se equivoca por 154 muertes versus las 366 del método anterior.  

Las regresiones lineales son una herramienta poderosa en el análisis de datos y tiene un montón de matemática interesante por detrás que te recomiendo que mires si te interesa.  

> ⚠️ Las regresiones lineales funcionan bien para hacer estimaciones cuando los puntos históricos marcan una tendencia clara y se puede trazar una línea que esté muy cerca de los puntos. Cuando la tendencia no es tan clara o los puntos están menos agrupados, entonces  tu predicción va a perder precisión. De todas formas, en la mayoría de los casos va a ser una mejor predicción que el promedio simple.  

Por ahora, no tenemos que preocuparnos de la matemática, ya que Google Sheet cuenta con la función [FORECAST](https://support.google.com/docs/answer/3094000?hl=es-419) que realiza los cálculos por nosotros. En un caso simple, esta función se alimenta de tres parámetros:  

- **x**: es el valor del eje X (horizontal) que queremos pronosticar. En nuestro ejemplo de arriba sería el año 2019
- **data_y**: los valores del eje Y para los años anteriores (4059, 4153, 4183 y 4332)
- **data_x**: los valores del eje X para los años anteriores (2015, 2016, 2017, 2018)  

En nuestro spreadsheet el cálculo se vería así:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition05.png" alt="grafico-hacker-edition-02" width="400"/>  

El problema es que nuestro dataset es un poco más complejo y no está ordenado de esta forma. La primera diferencia es que no tenemos una columna “AÑO”, sino que solo tenemos fechas de inicio y término de la semana. Te recomiendo que crees una columna nueva en tu data set y en la pestaña de tu análisis por país, y extraigas el año de cada fecha de inicio con la función [YEAR](https://support.google.com/docs/answer/3093061?hl=es) (o AÑO en español).

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition06.png" alt="grafico-hacker-edition-02" width="600"/>  

Adicionalmente, en nuestro dataset los datos que necesitamos están desorganizados, ya que tenemos distintos países, distintas semanas, y además nos interesan solo los años previos al covid para alimentar nuestra fórmula. Todo sería más simple si existiera una función FORECAST.SI.CONJUNTO para hacer el cálculo utilizando condiciones como lo hicimos con el promedio, pero lamentablemente no contamos con ella.  

Para lograr nuestro cálculo de pronóstico vamos a tener que usar otra función poderosa dentro de Google Sheets: la [ARRAYFORMULA](https://support.google.com/docs/answer/3093275?hl=es) (o fórmula de matriz). Esta es una función especial, ya que se alimenta de rangos de datos y retorna varios valores, a diferencia de las fórmulas que hemos ocupado hasta ahora, como por ejemplo la función AVERAGE que recibe un rango, pero retorna un solo número.  

Lo que queremos lograr es que nuestra función FORECAST se vea así:  

`=FORECAST(año a pronosticar, solo los años previos al COVID, las muertes de esos años previos al COVID)`  

Para que nuestra ARRAYFORMULA solo nos retorne los años previos al covid tenemos que ocupar la función [IF](https://support.google.com/docs/answer/3093364?hl=es) (o SI en español) para entregarle las condiciones que necesitamos. En una ARRAYFORMULA, como estamos tratando con rangos, para encadenar distintas condiciones ocupamos el operador * que lo que hace es asegurarse de que todas las condiciones que le pongamos se cumplan.  

Mira con atención esta fórmula y pruébala en tu spreadsheet:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition07.png" alt="grafico-hacker-edition-02" width="600"/>  

Si aplicas esta fórmula en tus datos pensarás que no habrá pasado nada. Pero la realidad es que si haces scroll hacia abajo te darás cuenta de que la fórmula te retornó solo valores vacíos en los casos en que las tres condiciones no se cumplían, y en solo algunas filas donde si se cumplían te retorna el año en cuestión:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition08.gif" alt="array-formula-hacker-edition" width="600"/>  

Podemos hacer lo mismo para que ahora nos retorne la cantidad de muertes reportadas si se cumplen las tres condiciones:

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition09.png" alt="array-formula-hacker-edition-02" width="600"/>

Puedes volver a probarlo en tu spreadsheet:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition010.gif" alt="array-formula-hacker-edition-03" width="400"/>  

Ahora vamos a juntar todo. A la fórmula FORECAST le vamos a entregar estos dos conjuntos de datos justo donde lo necesitamos:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition011.png" alt="array-formula-hacker-edition-04" width="700"/>  

Es una fórmula larga, pero lo importante es que nos permite calcular el pronóstico para cada semana de cada año:  

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/hacker_edition012.png" alt="array-formula-forecast-hacker-edition" width="700"/>  

Si te fijas, nuestro pronóstico (2462) de la semana 10 de Perú del año 2020 ya está haciendo una mejor estimación que el promedio que habíamos calculado (2008).  

Si necesitas una guía para armar este cálculo, te recomendamos revisar este [video](https://www.loom.com/share/d770602e9d6b465b98ad02cda27940f0)(📹).

Con esta nueva herramienta, te desafío a que vuelvas a calcular tu exceso de muertes y refines tus gráficos, análisis y conclusiones.  

# Recursos adicionales

A continuación te dejamos algunos videos y artículos adicionales que pueden servirte si deseas profundizar más en los temas que trabajarás en este proyecto.  

- [Perfeccionismo y productividad](https://hbr.org/2020/03/dont-let-perfection-be-the-enemy-of-productivity)
- [Procrastinar no es un asunto de holgazanería, sino de manejo de las emociones](https://www.nytimes.com/es/2019/03/26/espanol/como-evitar-la-procrastinacion.html)
- [Hábitos atómicos](https://open.spotify.com/episode/6nk1LGFOnM0lgRD6C5Kzjd?si=ab4ce28e53ae4b88&nd=1)
- [Dormir es tu superpoder](https://www.youtube.com/watch?v=5MuIMqhT8DM)
