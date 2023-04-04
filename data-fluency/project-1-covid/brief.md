# Introducción

En este proyecto realizarás un análisis utilizando hojas de cálculo a partir de un conjunto de datos sobre las muertes por COVID-19 en ciertos países de Latinoamérica. Para efectuar este análisis deberás entender los datos, pensar críticamente para determinar los indicadores relevantes y construir visualizaciones que permitan comunicar tus hallazgos. Además, al tratarse de tu primer proyecto, enfrentarás el reto de empezar a organizar tu tiempo y planificar tu trabajo para adaptarte a este programa a la par de tus demás responsabilidades y actividades del día a día.

# La situación

Es Mayo del 2022. Eres una analista de datos y trabajas para un prestigioso medio de comunicación internacional que lleva meses cubriendo la noticia del COVID-19. El propósito de tu organización es “informar al público y ayudarles a entender el mundo”. Por eso, te encuentras en una reunión estratégica donde se está debatiendo qué información debe publicarse sobre el COVID-19 para que el público esté mejor informado.  
El equipo editorial ya ha realizado una gran labor de publicar y difundir información clave sobre el COVID-19; desde cómo identificar sus síntomas, hasta cómo se propaga y qué medidas de prevención son las más recomendables. Al mismo tiempo, el equipo periodístico está cubriendo minuto-a-minuto el caso. Pero tú trabajas en el área de datos y la conversación gira en torno a cómo podrían analizarse los datos públicos para mejor informar al público.  

“Cada gobierno está tomando medidas diferentes. Tenemos países que han decidido cerrar sus fronteras y declarar estados de confinamiento estrictos, mientras que otros han decidido seguir el curso normal, bajo el supuesto de que esto es una gripe más. Es nuestra labor **entender cuáles países han sido más afectados** e informar al público para que cada gobierno se haga responsable de sus acciones”, mencionó Débora Salinas, la jefa del departamento.  

Esto motivó al equipo y la conversación entonces se volcó a determinar qué datos exactamente utilizar para el análisis. El COVID-19 ha causado contagios, hospitalizaciones, muertes, pérdidas económicas y laborales, daños psicológicos y un sinfín de efectos adicionales. Tu equipo coincide que tratar de abarcar todos los posibles impactos sería excesivo, y determinan que lo más lógico para un análisis inicial es centrarse en **analizar los datos de muertes por consecuencia de la pandemia.**  

Para esto, alguien sugiere simplemente calcular el total de muertes COVID-19 reportadas y hacer un ranking de los países, pero rápidamente se dan cuenta de que eso no tiene mucho sentido, dado que países con mayor población muy probablemente tengan más muertes reportadas. Para comparar “manzanas con manzanas” acuerdan emplear el indicador: **muertes COVID-19 por cada 100 mil habitantes.**  

En ese momento tú, a pesar de estar algo sobrecargada por tu trabajo, decides llevarte la tarea de realizar estos cálculos y regresar al grupo con algunas conclusiones. Sin embargo, justo cuando ya estabas por empezar a buscar los datos oficiales de muertes por COVID-19 de los gobiernos, Angélica Dueñas, la analista de datos más crack del equipo, mencionó que había que tener mucho cuidado porque **las cifras oficiales de muertes por causa de COVID-19 podrían estar subestimando significativamente la cantidad real de muertes.**  

“Primero, las estadísticas oficiales de muertes por COVID-19 en muchos países excluyen a las víctimas que no dieron positivo por coronavirus antes de morir, lo que puede ser una mayoría sustancial en lugares con poca capacidad de efectuar pruebas. En segundo lugar, es posible que los hospitales y los registros civiles no procesen los certificados de defunción durante varios días, o incluso semanas, lo que genera retrasos en los datos. Y tercero, la pandemia ha dificultado que los médicos traten otras afecciones y ha disuadido a las personas de ir al hospital, lo que puede haber provocado indirectamente un aumento en las muertes por enfermedades distintas del COVID-19”, argumentó Angélica.  

Angélica propone entonces que **un mejor indicador para analizar el impacto del COVID-19 en la mortalidad de los países es calculando el “exceso de muertes”**. Te explica que esto se calcula tomando el número de personas que murieron por cualquier causa (no solo COVID-19) en un período de tiempo determinado y en un lugar determinado, para así compararlo con las muertes que hubiesen acontecido si COVID-19 no hubiese sucedido, lo cual puede estimarse con una línea base histórica de las muertes que sucedieron durante los últimos años pre-pandemia. Por ejemplo, si en México (un lugar determinado), durante la tercera semana de enero del 2021 (un período de tiempo determinado), se reportaron 44,667 muertes totales (por todas las causas, no solo COVID-19), y sabemos que en los 5 años previos a la pandemia, en esa misma semana, en México, en promedio murieron 15,454 personas (línea base histórica), podríamos atribuir la diferencia de 29,213 muertes (44,667 menos 15,454) a la pandemia. Es decir, el “exceso de muertes” (comparado con un estimado del promedio de los 5 años anteriores) es lo que se atribuye a la pandemia.  

Para ayudarte a entender, Angélica dibuja este gráfico en la pizarra:

![esquema](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img01.png)

La explicación de Angélica te hace sentido. Todos acuerdan, gracias a esta nueva pieza de información, que una mejor forma de medir el impacto real de la pandemia en cada país es con el **exceso de muertes por cada 100 mil habitantes**, más que solo basarse en las cifras oficiales reportadas. Dado que eres Latinoamericana, decides hacer un primer análisis con los datos de 4 países de la región: Perú, Chile, Colombia y México.  

# Entregable

Para considerar completado este proyecto deberás entregar tu copia de la hoja de cálculo (con tu nombre agregado al título) por medio de la [plataforma de aprendizaje](http://plus.laboratoria.la).

Tu hoja de cálculo deberá incluir, como mínimo, lo siguiente:

- Una tabla comparativa con el total de muertes reportadas por COVID-19 por cada 100 mil habitantes, el total de “exceso de muertes” por cada 100 mil habitantes y la diferencia entre ambas cifras, por país.
- Un gráfico que muestre los datos de la tabla anterior en forma de gráfico de barras.
- Un gráfico por cada país que muestre el comparativo de la evolución en el tiempo de las muertes reportadas por COVID-19 vs. el cálculo de “exceso de muertes” semana a semana, ambos datos por cada 100 mil habitantes.
- Un gráfico por cada país que muestre las mismas variables que el punto anterior, pero acumuladas en el tiempo.

Además, de manera opcional, deberás entregar un video de máximo 5 minutos explicando tus conclusiones y tus hallazgos. Para grabarte te recomendamos la plataforma [Loom](https://loom.com/).

> 👩‍💻 ¿Te parece complejo? No te preocupes, hemos preparado una súper guía paso-a-paso, que encontrarás en la plataforma, para ayudarte a resolver este proyecto. Estamos seguras de que con tu esfuerzo, esta guía y el apoyo de tus compañeras por [Slack](https://join.slack.com/t/laboratoria-plus/shared_invite/zt-1ggn9x78k-fVHITFfXJe~jMMbxHzHGFQ) podrás resolver el proyecto y aprender en el proceso.

# Objetivos de aprendizaje

Al resolver este proyecto serás capaz de:  

- **Recolección y Preparación:**

    1. Entender diferentes tipos de datos de las hojas de cálculo (texto, numérico, fecha, etc.)
    2. Importar fuentes estáticas hacia las hojas de cálculo como archivos ".csv" u otras hojas de cálculo.
    3. Transformar data de un formato hacia otro en una hoja de cálculo.
- **Análisis y descripción:**

    1. Entender y reconocer los diferentes tipos de datos como variables categóricas ordinales, categóricas nominales, numérica discreta, numérica continua.
    2. Distinguir y aplicar los principales tipos de estadística descriptiva como: media, moda, mediana, desviación estándar.
    3. Aplicar funciones que permitan contar y sumar registros que cumplan una determinada condición en una hoja de cálculo (CONTAR, CONTAR.SI, SUMAR.SI).
    4. Crear e interpretar gráficos básicos (line chart, area chart, column chart, bar chart) usando hojas de cálculo.  

- **Comunicación de hallazgos:**

    1. Realizar un análisis utilizando hojas de cálculo y compartirlo con otros.
    2. Comunicar tus hallazgos de una forma clara.

# Consideraciones generales

- Este proyecto debe ser realizado de forma individual. Sin embargo, como uno de los principios de este programa es la colaboración, fomentamos el apoyo entre compañeras.
- **IMPORTANTE:** el objetivo de este proyecto es que desarrolles las habilidades descritas en los objetivos de aprendizaje. Bajo ninguna circunstancia busca ser un análisis profundo y conclusivo del impacto de la pandemia en América Latina. Tampoco buscamos que los cálculos aquí efectuados nos lleven a tomar conclusiones apresuradas, solo buscamos que aprendas. Al mismo tiempo, a pesar de que este proyecto nos recuerda lamentablemente las pérdidas de muchas personas queridas en el mundo a raíz de la pandemia, reconocemos que este tipo de análisis es el que emplean líderes mundiales para afrontar la crisis sanitaria, para por ejemplo, definir qué países requieren más asistencia en términos de donaciones de vacunas, oxígeno u otros recursos. También, es un análisis que se hace desde la ciudadanía para exigir una mejor gestión y transparencia a sus gobernantes. De hecho, este caso de estudio está inspirado en publicaciones reales como las siguientes:
  - [The Economist: Tracking covid-19 excess deaths across countries](https://www.economist.com/graphic-detail/coronavirus-excess-deaths-tracker). La intervención de Angélica en la situación anterior es un extracto de este reporte.
  - [Financial Times: Coronavirus tracker: the latest figures as countries fight the Covid-19 resurgence](https://www.ft.com/content/a2901ce8-5eb7-4633-b89c-cbdf5b386938).

 ¡Te deseamos mucho éxito!
