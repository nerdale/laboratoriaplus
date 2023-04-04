


## El proceso de análisis de datos  COVER
Conoce los 6 pasos que utilizarás para realizar cualquier análisis de datos.

## El proceso de análisis de datos

El análisis de datos es algo tan presente en nuestra vida cotidiana que, en cierta medida, todas hemos sido analistas de datos en algún momento. Si alguna vez buscaste información sobre un producto a comprar (por ejemplo, una laptop), recolectaste la información relevante, evaluaste las diferentes opciones a lo largo de diversas características y finalmente definiste cuál es la mejor compra; entonces, felicitaciones, eres una analista de datos. Utilizaste datos para tomar una decisión informada.  

Seguramente no seguiste ninguna metodología de análisis de datos muy compleja, pero lo más probable es que tu cerebro haya hecho una serie de pasos lógicos para llegar a esa decisión:  

1. **Comenzaste con un problema a resolver** (quiero comprar una laptop)
2. **Recolectaste información** (entendiste cuáles eran las características importantes y buscaste la información necesaria)
3. **Organizaste la información** (homologaste los precios si estaban en distintas monedas o agrupaste características para que sean comparables)
4. **Analizaste la información** (ordenaste de mayor a menor precio, filtraste por características, ponderaste los beneficios, etc.)
5. **Compartiste los resultados** (pintaste las mejores opciones con un color especial y llegaste a una conclusión general)
6. **Actuaste sobre los resultados** (tomaste la decisión de cuál comprar)

Está bien, quizás no seguiste todos estos pasos al pie de la letra, pero ya entiendes a lo que vamos. Justo estos son los seis pasos que el equipo de analistas y científicas de datos de Google proponen para todos sus análisis. Google publicó originalmente estos pasos en su [Certificado profesional de Google Data Analytics](https://grow.google/certificates/data-analytics/#?modal_active=none)<sup>1</sup>.

<br>

***

 <sup>1</sup> Existen otros marcos de trabajo (frameworks) para definir el proceso de análisis de datos. Sin embargo, todos son muy similares entre sí y fáciles de encontrar en la web. Decidimos compartir el de Google por su simpleza y porque ocuparemos varias de sus herramientas a lo largo de este programa (Google Sheets, Google BigQuery y Google DataStudio)  

<br><br>

![pasos-analisis](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/covid_img02.png)

### 1. Pregunta

 El primer paso es entender el problema. Es muy fácil en el análisis de datos “irse por las ramas” y hacer un análisis muy completo, pero que finalmente no deja ninguna recomendación concreta de utilidad. Al finalizar esta etapa deberías **entender claramente por qué** estás haciendo este análisis, **qué tipo de problema** estás intentando resolver y visualizar **cómo se vería el éxito** en este proyecto. En esta etapa es clave mantener una línea de comunicación abierta con todas las personas involucradas o con interés en el proyecto, a quienes usualmente llamamos stakeholders, y hacer muchas preguntas.  

 Algunas preguntas que te pueden ayudar en esta etapa:

- ¿Cuáles son los problemas que han sido mencionados por mis clientes y *stakeholders*?
- ¿Cómo se pueden resolver las dudas de los clientes y *stakeholders*?
- ¿Es el problema que dicen tener realmente la raíz del problema?
- ¿Cuáles son las expectativas de los clientes y *stakeholders* en cuanto a una solución?

### 2. Prepara

Ahora que ya sabes en lo que consiste el problema, debes buscar y preparar las fuentes de datos que te van a permitir solucionarlo o agregar información relevante para tomar una decisión. Preparar la data significa recolectar o generar la data que vas a necesitar. Esto puede ser tan simple como pedir una base de datos ya existente o más complejo como salir a encuestar personas, conectarte con bases de datos externas o fusionar datos relacionados.  

Un aspecto fundamental de este paso es entender las diferentes **métricas** que necesitas definir para tu análisis. Te dejamos algunas preguntas que te pueden ayudar:

- ¿Qué hay que averiguar para resolver este problema?
- ¿Qué medición ayudaría a evidenciar un cambio en el área problemática?
- ¿Qué debe ser investigado?
- ¿Dónde está guardada la información crucial?

### Closed Question a
¿Por qué es fundamental definir lo que se busca medir antes de iniciar el análisis de mis datos?
a Tener claro el objetivo de la exploración.
b Organizar la data en función del resultado que se pretende confirmar.
c Valorar la utilidad de realizar un análisis de datos en el proceso.

### 3. Procesa

Es hora de hacer **utilizable** la información que encontraste. Somos personas. No somos perfectas. Y nuestra data muchas veces también está lejos de serlo. Es común que te encuentres con fuentes de información desactualizadas, desorganizadas, con datos faltantes, o datos repetidos, o datos derechamente incorrectos (¿puede alguien tener -17 años? No en este mundo). La clave de este paso es llegar a tener **data limpia** con la que podamos trabajar. Las tareas clave de limpieza de datos incluyen:

1. Eliminar errores mayores, duplicados y outliers (datos que se escapan de lo usual en tu dataset).
2. Eliminar puntos de data irrelevantes que no tienen nada que ver con tu análisis.
3. Darle estructura a tus datos. Puedes pensar como un pequeño “orden de casa”: arreglar errores ortográficos, darle un orden a tus columnas. Cualquier cosa que te facilite el análisis posterior.
4. Llenar vacíos grandes. Mientras limpies tus datos te darás cuenta de que hay datos que faltan. Hay veces que la lógica de los datos te permite llenar esos vacíos.  

Entre la comunidad de analistas de datos, se bromea que una analista de datos pasa 80% de su tiempo procesando y limpiando datos y 20% quejándose de la preparación y limpieza de datos. Fuera de bromas, sí es común que gran porcentaje del tiempo (70% o más) se invierta en preparación y procesamiento de datos. Esto puede sonar excesivo, pero enfocarte en puntos de datos irrelevantes o hacer un análisis completo con datos erróneos te puede quitar aún más tiempo y llevar a conclusiones incorrectas. El viejo dicho informático de [GIGO (Garbage In, Garbage Out)](https://en.wikipedia.org/wiki/Garbage_in,_garbage_out), que en español significa “Entra basura, sale basura” es particularmente relevante en este caso.  

Algunas preguntas que te pueden guiar en este paso son:

- ¿Es esta fuente de datos confiable? ¿Es su data de alta calidad?
- ¿Qué errores o inconsistencias podrían haber en este dataset?
- ¿Cómo puedo limpiar esta data para que la información sea más consistente?

### 4. Analiza

Aquí es donde le preguntamos a la data: cuéntame tu historia. La meta en esta etapa es buscar relaciones, tendencias y patrones que nos puedan ayudar a resolver el problema planteado. Para este paso es fundamental ser **analítica**, **crítica** y **creativa**. Quizás debas ordenar y formatear los datos para procesarlos más fácilmente, o puede ser que debas hacer algunas tablas dinámicas para resumir los datos, o también incluir algunos gráficos. Quizás una segmentación es necesaria. Recuerda, esta es una historia que se va a ir contando mientras realizas tu análisis, debes descubrirla.  

Generalmente, los análisis caen en alguna de estas cuatro categorías:

1. **Análisis descriptivo**: en este tipo de análisis identificas lo que ya ha sucedido. Es comúnmente el primer paso en todo tipo de análisis para entender los datos con los que cuentas. Es común mirar los datos en el tiempo, resumir la data con estadística descriptiva (promedios, máximos, mínimos, varianza). Quizás no saques muchas conclusiones de este tipo de análisis, pero te permite determinar cómo continuar.
2. **Análisis diagnóstico**: aquí te enfocas en entender por qué algo sucedió. Literalmente es el diagnóstico del problema. Usando los datos buscas dar respuesta a algunas de las preguntas del negocio. Quizás sea útil vincular variables relacionadas al problema con otro tipo de variables que nos permitan encontrar correlaciones útiles sobre su posible causa. En este análisis comienzan a surgir los insights más útiles.
3. **Análisis predictivo**: este análisis te permite encontrar tendencias futuras basadas en datos históricos. En negocios es frecuente emplear este tipo de análisis para predecir el crecimiento del negocio. Pero en años recientes el análisis predictivo se ha sofisticado cada vez más gracias a la evolución de algoritmos de machine learning que hacen predicciones cada vez más acertadas.
4. **Análisis prescriptivo**: tal como el nombre lo indica, este tipo de análisis te permite hacer recomendaciones para el futuro. Generalmente, es el último paso del proceso de análisis de datos, y muchas veces es el más complejo, ya que reúne aspectos de todos los tipos de análisis anteriores.  

No es necesario que pases por todos los tipos de análisis. Muchas veces un simple análisis descriptivo es suficiente (¿recuerdas el ejemplo de la laptop?). Te dejamos algunas preguntas que te pueden ayudar en esta etapa:

- ¿Qué historia me está contando mi data?
- ¿Más (o menos) X (dinero, tiempo, horas-persona, expertise) nos permitirá resolver el problema?
- ¿Qué patrones visualizamos?
- ¿Cómo podemos segmentar o agrupar los datos?
- ¿Cómo varía X variable en el tiempo?

### Closed Question
¿Una analista de datos experimentada puede evitar realizar la limpieza de los datos?
- Sí, puede distinguir las conclusiones de la observación a través de un análisis en crudo.
- No, sabe que una base de datos limpia es la base para una observación certera.

### 5. Comparte

Terminaste tu análisis y tienes tus hallazgos. Es hora de compartirlos. Esto es más complejo que simplemente compartir tus cálculos o data cruda, por el contrario, esta etapa implica interpretar tus resultados y organizarlos de una manera que sea “digerible” para todo tipo de audiencias. Dado que tus resultados probablemente influenciarán decisiones importantes, debes asegurarte de que tus resultados sean lo más claro posibles. Por eso, una de las habilidades más relevantes para una analista de datos es la **comunicación efectiva**. Para ello, las mejores analistas de datos crean reportes, dashboards y visualizaciones interactivas para apoyar sus conclusiones. Además, es probable que algunos de tus *stakeholders* no tengan conocimientos técnicos de análisis de datos, por lo que un gráfico o una visualización simple, siempre es mejor que un cálculo complejo.  

Es crucial proveer toda la evidencia que has encontrado, incluso aquella que va en contra de las hipótesis inicialmente planteadas. Si hay algún vacío en la data que lleva a conclusiones encontradas, entonces también debes hacerlo saber. La comunicación honesta, clara y transparente es una parte fundamental de este paso.  

Algunas preguntas que te debes hacerte en este proceso:

- ¿Cómo puedo hacer que lo que voy a presentar a los stakeholders sea atractivo y fácil de entender?
- ¿Qué cosa me ayudaría a entender esto si yo fuera parte de la audiencia?
- ¿Cómo puedo presentar esto de una manera visual?  

### 6. Actúa

Después de todos los pasos probablemente ya tienes una buena idea de cómo resolver el problema que inicialmente te planteaste. Ahora es un buen momento para intentar resolverlo. Ninguna de tus conclusiones debería perderse en el olvido, debes convertirlas en acción.  

Es momento de entregar tus recomendaciones a tus *stakeholders* para que puedan tomar una decisión basada en datos. Este también es un buen momento para reflexionar sobre tu proceso. ¿Hubo otras fuentes de datos que podrías haber incluido? ¿Hay alguna parte del análisis que podrías haber hecho de forma más prolija? 

### Open Question
¿Cuál será  tu principal reto en la etapa de comunicar tus resultados con otras personas?

Es momento de entregar tus recomendaciones a tus *stakeholders* para que puedan tomar una decisión basada en datos. Este también es un buen momento para reflexionar sobre tu proceso. ¿Hubo otras fuentes de datos que podrías haber incluido? ¿Hay alguna parte del análisis que podrías haber hecho de forma más prolija?  

### Cierre COVER
¡Felicidades! Ya conoces los 6 pasos del análisis de datos que estaremos utilizando a lo largo de la resolución de tus proyectos. Preguntar, preparar, procesar, analizar, compartir y actuar serán tu guía para llevar cualquier análisis a buen puerto. Recuerda que tú ya utilizas estos seis pasos de forma intuitiva y ten la certeza de que en estas próximas semanas lo habrás integrado en tu rutina de forma exitosa. 
Ahora sí, ¡estás lista para comenzar tu primer proyecto de análisis de datos!
