# Introducción COVER


En este proyecto realizarás un análisis utilizando hojas de cálculo a partir de un conjunto de datos sobre clientes que utilizan un software de gestión de gastos en la nube. Para responder las preguntas de negocio que se plantean, deberás entender la estructura de los datos, analizarlos y comprender las métricas relevantes para la toma de decisiones. 

### La situación  

Eres una analista de datos y trabajas para una startup que ofrece un software de gestión de gastos en la nube a través de una suscripción mensual. A pesar de que tienes menos de un mes en la compañía, tu jefe te ha invitado a la reunión de planeación anual donde se definen las prioridades del año y el presupuesto.  

La reunión fue moderada por la Directora de Finanzas, quien presentó un resumen de las propuestas de inversión de cada área. Las primeras partidas presupuestarias se revisaron rápido porque eran montos relativamente pequeños y no presentaban una variación significativa contra el presupuesto del año anterior. Sin embargo, la cosa se volvió tensa cuando tocó explorar el presupuesto de mercadeo. Arturo, el Director de Mercadeo, propone triplicar la inversión para adquisición de usuarios en comparación al presupuesto del año pasado, argumentando que **es el momento de hacer crecer el negocio.**  

“Es el momento de pisar el acelerador y escalar. Tenemos el doble de usuarios que el año pasado, lo cual es una buena masa crítica. Es hora de invertir en crecer y expandirnos a nuevos mercados. Nuestro producto es bueno; yo mismo he entrevistado a usuarios que están felices con el servicio. ¡Tenemos *Product-Market-Fit*! Además, tenemos el capital porque acabamos de levantar la ronda de inversión más grande de nuestra historia. No sé qué estamos esperando”, mencionó Arturo.  

Para muchas personas en la reunión, ese término *Product-Market-Fit (PMF)* era nuevo. Lo habían escuchado, pero no necesariamente entendían bien qué significaba. Simplemente, sabían que, tal como indica el nombre, era una forma de decir que **el producto “calzaba” con el mercado**. Pero para Mercedes, la Directora de User Experience Design (UX), no era nada nuevo. Por eso, abrió debate con Arturo.  

“Arturo, estoy de acuerdo contigo en que muchos de nuestros usuarios están felices y que tenemos un buen producto entre manos. Sin embargo, tal como lo hemos conversado antes, a nuestro producto le faltan muchas funcionalidades aún. Además, sabemos de usuarios que se han dado de baja y esto parece suceder cada vez con mayor frecuencia. Es cierto que hemos duplicado la cantidad de usuarios, pero porque duplicamos la inversión. Realmente no tenemos la certeza de haber alcanzado *PMF*”. Mercedes hizo una pausa breve y luego continuó. “Algo que aprendí con el curso ‘*Cómo empezar una startup*’ de Sam Altman es que **la retención es una de las mejores métricas para determinar si se ha alcanzado *PMF***. Esto se hace confirmando que una base de usuarios de tamaño considerable permanece usando el producto a lo largo del tiempo. Es decir, si no podemos retener un porcentaje saludable de usuarios al cabo de 12, 18 o 24 meses, quiere decir que no tenemos un producto apto para el mercado aún, y toda la inversión de mercadeo es dinero que estamos botando a la basura”.  

La CEO para entonces se había impacientado porque no era la primera vez que se tenía esta discusión. Interrumpió la conversación. “Esto lo hemos conversado antes y por eso es importante que tengamos el **análisis de retención por cohortes** que les pedí la reunión pasada. Efectivamente, Mercedes tiene razón. No estoy segura si hemos alcanzado *PMF* y necesitamos ver la data de **retención a lo largo del tiempo para determinar si es momento de escalar o no**. Hasta que no resolvamos esto, no podemos dar luz verde al plan de mercadeo. Quizá debamos más bien destinar esa inversión a mejorar el producto”. En eso se volteó a mirar a tu jefe, el Director de Producto. “Necesito que por favor tengamos ese análisis para la próxima reunión y así poder definir la estrategia de la empresa para el año, junto con el presupuesto.”  

Al salir de la reunión, tu jefe te pide que tomes este desafío porque puede ser una buena experiencia de aprendizaje para ti. Asumiste este reto algo nerviosa, pero con entusiasmo, ya que mientras escuchabas atentamente toda la discusión que se generó en la reunión, surgían demasiadas preguntas y cuestionamientos en tu mente y realmente te interesa aprender más al respecto para poder tener una postura informada y que agregue valor a la empresa.  


## Conceptos clave

Primero revisemos algunos conceptos clave.

### ¿Qué es un servicio SaaS?

SaaS significa *Software as a Service* (Software como Servicio). Es un modelo de negocio bajo el cual una empresa desarrolla un producto de software y lo pone a disposición de los clientes, a través de Internet. El software se aloja en la nube y el usuario accede de forma remota mediante una suscripción. Algunos ejemplos de SaaS son Dropbox, Google Docs, Mailchimp, HubSpot, herramientas de gestión, entre otros.

### ¿Qué es una Startup SaaS?

Una startup SaaS es una empresa que ofrece software por medio de Internet. Estas startups tienen la responsabilidad de gestionar el acceso, mantener la estructura de datos, la conectividad y los servidores necesarios para que el servicio funcione.

### ¿Qué es el *Product-Market Fit* (PMF)?

El *Product Market Fit* (PMF) se puede traducir como “Encaje de tu Producto al Mercado”. Tal como lo indica su nombre, tu negocio ha alcanzado el PMF cuando tu producto o servicio ha encontrado un espacio de mercado fiel.

En el mundo de las startups y pequeñas empresas el concepto de *Product-Market Fit* es muy común e importante pues implica que tus clientes buscan por sí mismos consumir tu producto o servicio porque lo necesitan y ya es parte de sus vidas. Ha dejado de ser percibido como una “vitamina” para convertirse en una “medicina” (pain killer) porque resuelve un problema, o dolor específico.

También es importante observar lo que ocurre cuando tu producto o servicio no ha encontrado su PMF:

> *“Uno siempre puede sentir cuando tu producto no ha alcanzado Product/Market Fit. Tus clientes no están obteniendo valor del producto. El “boca a boca” no se está extendiendo, y el uso no se está expandiendo tan rápido como uno quisiera.”*

— Marc Andreessen (Fundador de Netscape, el primer navegador de internet)

### ¿Por qué es importante el *Product-Market Fit* (PMF)?

En este caso, el PMF es esencial para determinar si se asignan recursos a “la optimización o mejora del producto/servicio” o se usan para invertir en crecimiento.

Es relevante conocerlo, ya que algunas empresas han fracasado porque en realidad pretendían escalar sin haber conseguido primeramente su *product-market fit*, por lo que los recursos invertidos en crecimiento no representaron una ganancia para la empresa.

Hay diversas [métricas](https://medium.com/@nicolasbenenzon/c%C3%B3mo-identificar-y-medir-lo-m%C3%A1s-importante-en-una-startup-product-market-fit-ff5d099fa95#:~:text=Hay%20varias%20estrategias%20para%20medir,seguir%20con%20cualquier%20otra%20cosa.) para determinar si un producto ha alcanzado PMF. Una muy común es la [encuesta de PMF que popularizó Sean Ellis](https://blog.growthhackers.com/using-product-market-fit-to-drive-sustainable-growth-58e9124ee8db); inversionista y experto en crecimiento de EEUU. Consiste en preguntarles a las/os usuarias/os cómo se sentirían si ya no pudieran usar el producto, y ver si al menos un 40% responde “Muy decepcionada/o”. Otra forma de evaluar PMF es midiendo qué tanto recomiendan el producto, con, por ejemplo, una encuesta de [NPS](https://www.hotjar.com/net-promoter-score/). La lógica acá es que un producto que alcanza PMF cuenta con usuarias/os que lo recomiendan constantemente.

**Sin embargo, otra forma de medir PMF es a través de la retención y es la que utilizarás en este proyecto**. En palabras del inversionista [Fred Wilson](https://avc.com/2015/07/growth-vs-retention/):

> *“Si no puedes retener un porcentaje saludable de tus usuarios luego de noventa días, todavía no tienes un producto apto para el mercado y toda la inversión que se realiza en tu negocio es solo dinero que se pierde. Así que concéntrate primero en los números de retención a 90 días. Luego escala.”*

### ¿Qué es la retención de clientes?

Significa que los usuarios al cabo de X tiempo (por ejemplo: 3, 6, 12, 18, 24 meses) siguen usando tu producto o servicio con la frecuencia deseada. Una tasa de retención de clientes alta significa una mayor lealtad del cliente.

Un término asociado a la retención de clientes es el [Churn](https://blog.hubspot.es/service/que-es-churn). El **churn rate** o tasa de abandono es el porcentaje de clientes que dejan de utilizar los servicios que ofrece una empresa. En otras palabras, **el churn rate es lo opuesto a la tasa de retención** y se calcula de la misma forma que la retención (total de clientes que abandonaron la empresa en ese período sobre el total de clientes en el período de tiempo).

Por ejemplo, [Facebook y Netflix tienen un churn rate muy bajo](https://www.cnbc.com/2015/04/07/these-social-apps-have-the-highest-retention-rates.html), porque son servicios de uso continuo y diario, que pocas personas tienden a dejar de usar (¡y pagar!).

En este proyecto realizarás un análisis para observar la retención y abandono de clientes. Para ayudarte a comprenderlo mejor, crearás un análisis por cohortes de los datos.

### ¿Qué es el análisis por cohortes?

Un cohort es un grupo de usuarios que comparten características en común durante un período específico, por ejemplo, usuarios que visitaron tu sitio web por primera vez en el mismo día, quienes descargaron una aplicación en enero, etc. Una clasificación típica (y la que utilizarás en este proyecto) es agrupar a usuarios por fecha de registro o fecha en la que usaron por primera vez tu producto. Esto te permitirá monitorear el porcentaje de retención de los distintos grupos a través del tiempo.

### ¿Qué preguntas te permite responder un análisis por cohortes?

Dependiendo del contexto y del alcance que elijas, el análisis por cohortes te permite responder a preguntas como:

- ¿Cuántos de tus clientes siguen consumiendo tu producto después de 3 días? ¿Y después de una semana? ¿Cuántos continúan tras un año?

- Si realizas un cambio en tu producto, ¿cómo se comportan tus usuarios con el nuevo cambio este mes en comparación con el anterior?

- ¿Tus usuarios responden mejor a la misma oferta en una promoción semanal frente a una mensual?

- Si lanzas un nuevo producto, con este tipo de análisis podrías responder ¿están los usuarios dispuestos a pagar por el nuevo producto?

¡Estás lista! Ahora conoces el contexto y los conceptos necesarios para resolver el problema. Recuerda que entender el contexto del análisis es parte esencial del arranque de cualquier proyecto y te ayudará a entender qué debes analizar, qué investigar y además, generar conclusiones valiosas para el negocio. 
Antes de comenzar, te invitamos a validar el objetivo de este proyecto.

### Closed Question A
¿Cuál es el objetivo del proyecto?
- Analizar el PMF a través de la retención
- Entender el comportamiento del cliente
- Entender lo que es una cohorte

### Validación
¡Excelente! Ahora que tienes claro el objetivo de este proyecto y, por ende el objetivo de este análisis, podemos continuar con la guía para descubrir cómo podemos analizar el Product Market Fit a través de la retención.




# Desarrollo

Al igual que en tu primer proyecto, y en el resto del programa, ocuparemos los 6 pasos para realizar un correcto análisis de datos que propone Google.

## Paso 1: Pregunta

Este primer paso es esencial. Einstein [(o tal vez una persona no tan influyente)](https://quoteinvestigator.com/2014/05/22/solve/) alguna vez dijo: “Si tuviera una hora para resolver un problema, gastaría 55 minutos en pensar sobre el problema y 5 minutos en pensar soluciones”. Si definimos incorrectamente la intención del análisis, entonces todo nuestro esfuerzo será en vano. Hay algunas acciones que nos pueden ayudar a definir de mejor manera el problema:

- **Relee el brief e intenta plantear el problema.** En nuestro caso estamos apoyando a una compañía SaaS que tiene una duda fundamental: invertir en marketing o en el desarrollo del producto. Existen opiniones encontradas en la reunión porque algunos creen que el producto está listo y se debe invertir en adquisición de nuevos usuarios, mientras que otros creen que todavía no han alcanzado product-market fit. La métrica clave que han definido para resolver esta disputa es el cálculo de la **retención** de los clientes.

- Una vez definido el problema, es importante **enfocarse constantemente en él y evitar distracciones**. En un análisis de datos es tentador generar muchas métricas distintas para enriquecer el análisis, pero esto solo es válido si esos aportes buscan solucionar el problema definido. Todo lo demás debe evitarse.

- Da un paso atrás e intenta mirar el **contexto del problema**. Muchas veces la misma métrica merece ser medida de forma distinta dependiendo del contexto. En nuestro caso hay varias formas de medir retención de clientes. ¿Cuál será la correcta? Aquí vale la pena investigar para complementar lo que sabes.

Si es necesario, **involucra a más personas**. Si no estás segura de algo, anda a preguntar. En un contexto laboral real les preguntarías a tus stakeholders, clientes o a tu equipo de trabajo. En nuestro caso, aprovechamos a la comunidad y las coaches.

## Paso 2: Prepara

Con el problema definido, ahora es momento de “preparar la cancha”. En nuestro caso eso implica salir a buscar todo lo necesario para hacer el análisis y resolver el problema planteado. En un contexto laboral real esto implica buscar datos en distintas áreas, entrevistar personas y realizar encuestas para generar los datos necesarios. Felizmente en este caso contamos con una base de datos recolectados que podemos utilizar.

Lo primero que debemos hacer es acceder a [la base de datos](https://docs.google.com/spreadsheets/d/1545E5lVl6qsqoCS9pXb3Wb-ZHsm3RXGxNqyNds1DpqE/edit?usp=sharing) y hacer una revisión general de los datos con los que contamos: la cantidad de filas, la cantidad de columnas (o variables) y qué representa cada una.

![dataset](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/startup-img01.png)

El dataset cuenta con 330 filas, en donde cada fila representa un cliente único.

Las columnas que almacena son:

- **Nombre Cliente**: Nombre del cliente

- **Apellido Cliente**: Apellido del cliente

- **Estado del Cliente**: Puede ser “Active” (sigue pagando la suscripción) o “Churned” (no sigue pagando)

- **Mes de Registro**: Mes en que comenzó a pagar la suscripción mensual

- **Mes de Abandono**: Mes en que dejó de pagar la suscripción mensual

- **24 columnas**, una por cada mes del año (Del 1/2019 al 12/2020) en donde se muestra si el cliente pagó (con un 1) o no (con una celda vacía)

### 2.1 Copia la base de datos en un nuevo archivo

Te habrás dado cuenta de que no podemos trabajar directamente en el archivo de Google Sheets disponible, ya que no tiene permisos de edición. Esto es una práctica común que te recomendamos para conservar la integridad de los datos originales, por lo que tendremos que generar una copia de los datos para nuestro uso.

Esta base de datos probablemente se actualiza constantemente con nuevos datos, por lo que no sería muy útil simplemente hacer copy-paste de los datos. Una mejor solución es hacer una copia dinámica con la función IMPORTRANGE. Si no conoces esta fórmula, puedes revisar [este video](https://www.loom.com/share/80681eee41704fd1a919a8fabde781ac).

> 👀 ¿Tienes tu Google Sheets en español y quieres entender las fórmulas en inglés? ¿O viceversa? En [esta página](https://excelyvba.com/formulas-de-excel-en-ingles-y-espanol/) puedes encontrar su traducción. Recuerda también que en algunos idiomas las fórmulas pueden tener distintos separadores, es decir, en inglés se usa una coma "," para separar los argumentos de las fórmulas, mientras que en otros idiomas un punto y coma ";".

### 2.2 Comprende la estructura de los datos

Ahora que tenemos nuestra copia de la base de datos, vale la pena mirar detenidamente el significado de cada una de las filas. Si revisas con atención las primeras filas de tus datos podrás comenzar a entender lo que sucede con cada cliente. Por ejemplo:

- El primer cliente es George García. Observamos que su Mes de Registro es enero del 2019 (1/2019) y que su Mes de Abandono está vacío, lo que significa que este cliente está **activo** y sigue pagando la suscripción mensual. Lo podemos confirmar porque todas las columnas relacionadas con las fechas de pago (de 1/2019 al 12/2020) se encuentran llenas con el valor de 1, es decir, ha estado pagando una suscripción mensual por 24 meses seguidos.

- El segundo cliente, James Johnson, también se registró en enero del 2019, pero su estado es **churned** (abandono), ya que solo tiene llenas las columnas **1/2019** y **2/2019**, es decir, el cliente solo pagó dos meses de suscripción (enero y febrero) por lo tanto, su mes de abandono sería en marzo del 2019.

- El cliente en la línea 15, Daniel White, se registró en febrero del 2019, pero según vemos en el dataset solo pagó por 4 meses (de 2/2019 a 5/2019) es decir abandonó el servicio en junio del mismo año, por lo tanto, su estado también es **churned**.

De los 3 clientes analizados, solamente un cliente continúa pagando la suscripción mensual, es decir, **de los 3 clientes únicamente hemos retenido uno** y los otros dos abandonaron el servicio.

Ahora, para saber cuál es la cantidad total de clientes que siguen pagando la suscripción o dejaron de hacerlo, vamos a agruparlos por el mes de registro. ¡Vayamos al dataset!

## Paso 3: Procesa

Recuerda que en todo análisis de datos es esencial verificar que la calidad de los datos es óptima antes de comenzar a procesar nuestros datos.

Como vimos en el Proyecto 1, las tablas dinámicas (**pivot table**) son muy útiles para explorar los datos, resumir información, además de identificar posibles errores a corregir.

Una parte importante del análisis de datos es revisar que cada columna contenga datos correctos y que hagan sentido en el contexto del proyecto. Para eso vamos a comenzar revisando la columna “Estado Cliente” para corroborar las posibles categorías que utilizamos para clasificar a los clientes. Si hacemos una tabla dinámica con esa variable, vemos que hay un guión bajo en algunos términos, lo que hace que parezca que tenemos 4 categorías en lugar de solo “Churned” y “Active”.

![tabla-dinamica](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/procesa-01.jpeg)

Este es un error muy común en algunos datasets, posiblemente originado por errores de tipeo o por categorías que no fueron actualizadas. Necesitamos limpiar esos casos y eliminar el guión para que solo queden las dos categorías “Active” y “Churned”. Una opción es revisar celda por celda y eliminar manualmente el guión cuando corresponda. Pero si la base de datos es muy grande puede tomar mucho tiempo.

Una forma más eficiente de corregir este error es utilizando la función SUBSTITUTE que busca una cadena de caracteres y la reemplaza por otra cuando la encuentra. Podemos agregar una nueva columna al final de la tabla con las categorías corregidas.

> 👀 Cuando utilizamos la fórmula IMPORTRANGE para traer los datos de la tabla original, cada vez que queremos incluir una nueva columna, la incluimos al final. O usamos la fórmula IMPORTRANGE de forma dividida, primero importamos las columnas A, B y C, dejamos algunas columnas para realizar las operaciones de ajuste y volvemos a incluir en una nueva columna la función importrange para incluir el resto de las columnas (D:AC).

La fórmula SUBSTITUTE, según [la documentación oficial de google](https://support.google.com/docs/answer/3094215?hl%3Den), se ocupa de la siguiente forma:

```SQL

=SUBSTITUTE(text_to_search, search_for, replace_with, [occurrence_number])

```

Los argumentos de esta fórmula son:

- **text_to_search**: Celda donde está el texto con error (en este caso, la celda C2, donde aparece el primer registro de la columna “Estado del Cliente”).

- **search_for**: Caracteres a buscar (en este caso, el guión bajo, no olvides ponerlo entre comillas).

- **replace_with**: carácter o secuencia de caracteres correctos (en esta caso, reemplacemos con "”, es decir, una cadena vacía para eliminar el guión).

- **occurrence_number**: campo opcional en donde se define la cantidad de “ocurrencias” de “search_for” que queremos reemplazar por “replace_with”. Si lo dejamos vacío, entonces cambia todas las que encuentra.

Nuestra fórmula debería verse así:

![substitute](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/procesa-02.png)

Luego podemos aplicar esta fórmula a toda la columna C y tendremos una nueva columna “Estado Cliente Corregido” unificado, sin variaciones de captura.

Ahora que tenemos la columna “Estado Cliente Corregido” correcta, podemos seguir arreglando el dataset para que muestre los datos como los necesitamos. Por ejemplo, nos gustaría que en vez de mostrar el nombre y el apellido del cliente por separado, estos se muestren en una sola columna “Nombre y Apellido”. Para esto podemos ocupar la función [CONCATENATE](https://support.google.com/docs/answer/3094123?hl%3Den) que justamente, concatena dos o más textos en uno solo.

```SQL

=CONCATENATE(string1, [string2, …])

```

Importante notar que debemos concatenar, además, un espacio en blanco para que los nombres queden separados, es por eso que agregamos la cadena “ ” a la fórmula.

![concatenate](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/procesa-03.png)

Al aplicar la fórmula en toda la columna te habrás dado cuenta de que algunos nombres cuentan con caracteres de espacio innecesarios.

![trim](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/procesa-04.png)

Afortunadamente, Google Sheets cuenta con una fórmula que elimina automáticamente los espacios innecesarios en cadenas de texto. Esta función es [TRIM](https://support.google.com/docs/answer/3094140?hl%3Den). Puedes ocupar esta fórmula en una nueva columna o, mejor aún, encadenar las dos fórmulas CONCATENATE y TRIM en una sola para que el resultado de CONCATENATE pase luego por TRIM y elimine los espacios adicionales.

```SQL

=TRIM(CONCATENATE(A2," ",B2))

```

La base de datos con las 2 nuevas columnas se vería así:

![resultado](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/procesa-05.png)

Ahora que todo está arreglado, podemos continuar con nuestro análisis. Si te interesan las fórmulas de manipulación de texto te recomendamos revisar otras funciones muy útiles como [PROPER](https://support.google.com/docs/answer/3094133?hl%3Den) (para poner mayúsculas solo en las primeras letras), [UPPER](https://support.google.com/docs/answer/3094219?hl%3Den) y [LOWER](https://support.google.com/docs/answer/3094083?hl%3Den) (para poner todas en mayúsculas o minúsculas respectivamente), y [LEFT](https://support.google.com/docs/answer/3094079?hl%3Den) y [RIGHT](https://support.google.com/docs/answer/3094087?hl%3Den) (para cortar la sección izquierda o derecha de una cadena de texto, respectivamente).

> 👩‍💻 Recuerda que uno de nuestros principios es la Apropiación del aprendizaje. Cuando te encuentres con un bloqueo en tu proyecto, siempre puedes recurrir al vasto conocimiento almacenado en internet (y ordenado por Google 😎) o a tus compañeras en Slack. 

Hasta ahora hemos visto que hay varias formas de importar una base de datos a las hojas de cálculo de Google que son una excelente herramienta para el análisis de datos, ya que con fórmulas simples podemos ajustar y limpiar la base de datos. Echémos un vistazo a lo que hemos aprendido hasta ahora.

### Closed Question C

¿Cuántos registros hay por Status (Active y Churned)?
- 233 Active y 97 Churned 
- 330 Active y 97 Churned
- 233 Active y 120 Churned

### Open Question
¿Qué otras funciones de manipulación de texto consideras útiles aunque se mencionaron en este ejercicio?

### Validación
¡Adelante! Ahora que terminanos el proceso de importación, tienes la base de datos organizada, corregida y lista para ser analizada, es momento de procesar.
Si te gustaría consultar otras funciones para manipular texto te invitamos a revisar el [siguiente enlace](https://support.google.com/docs/table/25273?hl=es#query=texto)


## Paso 4: Analiza

Si investigaste lo que es un análisis por cohorte por tu cuenta, o leíste [el artículo](https://es.modyo.com/blog/el-analisis-de-cohortes-como-entender-los-habitos-del-cliente) de la sección de recursos recomendados, habrás notado que los análisis por cohorte agrupan a los clientes según un criterio, por ejemplo por fecha de ingreso, en donde cada fila representa un rango de tiempo.

En nuestro spreadsheet debemos replicar una estructura similar. Para esto vamos a crear una tabla dinámica cuyas filas sean las fechas de mes de registro, y que en cada fila el valor sea la cantidad de clientes que ingresaron en esa fecha.

> 👩‍💻 Ya hemos aprendido a hacer una tabla dinámica, si deseas profundizar más en este tema, también puedes complementar tu conocimiento buscando algunos contenidos en youtube.

Comienza con una tabla similar a esta:

![inicio](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-01.png)

🤓 **Análisis** 🤓

En el resultado de la agrupación podemos ver la cantidad de clientes registrados por mes. Por ejemplo, en el mes de enero del 2019 (1/2019) se registraron 11 clientes, en febrero del 2019 (2/2019) 13 clientes y así sucesivamente, con un total de 330 clientes.

🤔 **Reflexión 1**: ¿Cuál es el mes con más y con menos clientes registrados? ¿Qué otros hallazgos puedes observar? Anota tus observaciones para compartirlas con tus compañeras.

### 4.1 Calcula clientes activos por mes

Para contar la cantidad de clientes que pagan el servicio mes a mes de forma activa, agregaremos columnas a la tabla dinámica. Por ejemplo, la primera columna que queremos agregar es la de 1/2019, ya que nos gustaría saber para cada fila cuántos clientes pagaron en ese mes. La columna siguiente debería ser la del 2/2019 y así sucesivamente hasta completar 24 columnas (y llegar al 12/2020).

En una tabla dinámica podemos ir agregando columnas al añadir más valores.

![columnas](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-02.png)

> ⚠️ En este caso queremos que la tabla dinámica sume los valores de los clientes que cumplen con el criterio de cliente activo por mes, por lo que resumimos la información (summarize by) SUM y no COUNTA como en el caso de la primera columna, en donde si queríamos contar la cantidad de clientes en cada fecha.

Después de sumar los 24 valores (😮‍💨) deberías haber llegado a algo similar a esto:

![resultado](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-03.png)

🤓 **Análisis** 🤓

Al observar los datos podemos comenzar a descubrir los siguientes ejemplos:

- En la columna “Nuevos Clientes” hay 13 clientes registrados en marzo del 2019 (3/2019)

- De estos 13 clientes (cohort marzo 2019), 11 continúan pagando en octubre 2019 (10/2019) y solo 4 continuaron pagando hasta diciembre del 2020 (12/2020).

- En los totales inferiores, vemos que a finales de diciembre de 2019, teníamos un total de 112 clientes de pago.

- Notarás que conforme van pasando los meses la cantidad de clientes disminuye. Esto muchas veces es inevitable, pero se desea que los números a lo largo de la línea horizontal disminuyan lo más lentamente posible a medida que pasa el tiempo, o en otras palabras, que la retención de clientes sea lo más alta posible mientras pasa el tiempo.

🤔 **Reflexión 2**: ¿Por qué crees que en el cohort de marzo 2019 de los 13 nuevos clientes registrados, solo 4 continuaron pagando en diciembre del 2020? ¿El producto no fue lo suficientemente bueno para continuar con la suscripción?

### 4.2 Organizar datos

Ahora vamos a pensar en cómo podemos organizar los datos para comparar los cohortes. En este caso nos interesa conocer el comportamiento de los clientes a lo largo de los meses desde que se inscriben (Mes Registro). No nos interesa la fecha en particular. Dicho de otra forma, nos interesa saber qué pasó con los clientes de cada cohorte en un mes específico desde su inscripción. Por ejemplo, si quisiéramos ver qué pasa con nuestros clientes 5 meses después de su inscripción, dicho mes sería distinto para cada cohorte. Para el primer cohort (1/2019) el mes 5 corresponde al 5/2019, para el segundo (2/2019) es el 6/2019, para el tercero (3/2019) su quinto mes es el 7/2019. Para el cohorte de la fila 10 (9/2019) su mes 5 es el 1/2020. Así, cada cohorte está "corrido" un mes con respecto a su cohorte anterior.

Si queremos comparar 🍎 con 🍎 y 🍐 con 🍐 tenemos que alinear el primer mes de cada cohorte. Dicho gráficamente, tenemos que mover cada inicio de cohorte a la primera columna de la tabla:

![mover-filas](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-04.png)

En donde cada inicio de cohorte sigue su mes de registro (podemos verlo por los nombres de los encabezados de las columnas), a una tabla en donde el inicio de cada cohorte esté en la primera columna y los encabezados no sean las fechas, sino que el mes con el número que corresponda. Algo como:

![analiza-06](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-06.png)

Si te fijaste bien, te diste cuenta de que hay que mover cada fila individualmente al inicio de la tabla 😩. No te preocupes, Google Sheets nos da algunas opciones para hacerlo más rápido. Conócelas y elige la que prefieras.

#### Opción 1: Utiliza la fórmula INDEX

Antes de comenzar, crea una tabla vacía conservando las primeras dos columnas: fecha de inicio de la cohorte “Mes Registro” y cantidad de clientes “Usuarios Nuevos”. Puedes copiar y pegar. Nombra los encabezados de las columnas como Mes 1, Mes 2, etc.

> 👀 Si se te pegó toda la tabla dinámica puedes ocupar Edit > Pegado Especial > Solo Valores.

![analiza-07](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-07.png)

Para usar la fórmula [INDEX](https://support.google.com/docs/answer/3098242?hl%3Den), primero entendamos los argumentos de la fórmula. Los argumentos son:

- **reference**: rango de datos donde buscaremos la información

- **row**: índice de la línea donde está la información que queremos

- **column**: índice de la columna donde está la información que queremos.

Por ejemplo, una fórmula =INDEX(datos, 2, 5) te retornará el valor de la quinta columna que está en la segunda fila del conjunto “datos”.

Para que podamos arrastrar la fórmula de forma automatizada, incluiremos una columna con el rango de meses que tenemos en nuestra base de datos.

![analiza-08](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-08.png)

En la fórmula seleccionaremos como referencia el rango de datos considerando desde la primera celda que contiene la información deseada hasta la última celda con datos de retención de clientes (B2:Z25). Como vamos a arrastrar la fórmula tenemos que “bloquear” la celda de término con un signo $ en la letra y el número, ya que, de otra forma, el rango completo se iría moviendo y no tendría sentido. Preparamos este [video](https://www.loom.com/share/e0542f98ce28415e92b372060ae23b72) sobre cómo usar la fórmula del índice y el signo $ para bloquear la columna o fila.

Para indicar el número de línea usaremos el número 1, porque nuestra fórmula siempre traerá la información de la primera línea (por eso no bloqueamos la primera parte del rango de referencia). Para la columna utilizaremos la nueva columna que creamos (Rango Meses). Aquí también ocuparemos un signo $ en la letra para que cuando nos movamos hacia la derecha la fórmula llame correctamente siempre a esa columna.

La fórmula queda así:

```SQL

=INDEX(C2:$Z$25,1,$A31)

```

Donde C2:Z25 es el rango donde están tus datos de la tabla dinámica y A31 es la primera celda de la columna Rango Meses.

Ahora, puede arrastrar la fórmula hacia abajo y hacia un lado, de modo que tenga su tabla lista para los siguientes pasos, como se muestra en la siguiente imagen:

![analiza-09](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-09.jpeg)

> 👀 Si obtuviste algunos errores en la tabla, ¡no te preocupes! En tu proyecto anterior ya aprendiste a cómo manejar errores en spreadsheet 😏 recuerda usar SI.ERROR (o [IFERROR](https://support.google.com/docs/answer/3093304?hl%3Den)).

#### Opción 2: Ocupar la función Query

¿Recuerdas esta función del proyecto COVID? Es una herramienta muy versátil, que nos permite manipular data como queramos.

Como en la opción 1, primero crea una tabla vacía conservando las primeras dos columnas (de la fecha de inicio del cohorte y la cantidad de clientes). Puedes copiar y pegar. Y nombra los encabezados de las columnas como Mes 1, Mes 2, etc...

Ahora ocuparemos la función [QUERY](https://support.google.com/docs/answer/3093343?hl%3Den) para llamar a cada fila individualmente.

Si te sitúas en la primera celda vacía del primer cohort puedes llamar a todos los datos de la pestaña donde está tu tabla dinámica. Algo como:

```SQL

=QUERY(RANGO_DONDE_ESTAN_LOS_DATOS,"SELECT *")

```

Recuerda que el SELECT seguido de un * pide todos los datos del rango, por lo que esto traerá todos datos y los copiará en tu tabla. Debería quedar algo igual a tu tabla dinámica

![analiza-10](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-10.png)

Pero queremos tratar cada fila individualmente, por lo que podemos limitar nuestra QUERY para que nos retorne solo la primera fila.

```SQL

=QUERY(RANGO_DONDE_ESTAN_LOS_DATOS,"SELECT * LIMIT 1")

```

![analiza-11](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-11.png)

Si fijas la fila del segundo valor del rango (con un signo peso) y luego bajas la fórmula volverás a tu tabla inicial como la de tu tabla dinámica. Solo que esta vez puedes controlar cada fila independientemente.

Si cambias el rango de tu QUERY y lo vas "moviendo hacia la derecha" de forma de que tu primera columna de tu rango siempre sea la columna donde hay un valor (y no cero) puedes ir trasladando los resultados hacia la primera columna. Aquí te muestro como están las fórmulas de esa primera columna para mi caso:

![analiza-12](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-12.png)

> 👩‍💻 Si no entendiste del todo la fórmula, ¡no te preocupes! Este tipo de conceptos se demoran en decantar. Te recomendamos mirar otros ejemplos en tu spreadsheet y seguir el mismo camino hasta encontrar patrones.

Como vimos, para calcular la retención, es necesario organizar los datos para que podamos entender el comportamiento de cada cohorte a lo largo del tiempo. Echemos un vistazo a lo que hemos visto hasta ahora.

### Closed Question C

¿Cuál es la cohorte con más clientes?
- 05/2020
- 10/2019
- 08/2020

¿Ya tienes una visualización como ésta?
(Anexar imagen)
- Sí. ¡Adelante!
- No. Pediré ayuda vía slack.

### Validación

¡Excelente! Organizar los datos nos ayuda a entender cómo se comporta cada cohorte (grupo de personas que se convirtieron en clientes en un mismo mes) después de pasado 1 mes de ser nuestros clientes, después de 2 meses y así sucesivamente. Ahora, con los datos organizados, podríamos analizar el porcentaje de retención de cada cohorte después de 12 meses.

### 4.3. Resaltar visualmente la información

Sea como sea, lograste llegar a una tabla que te muestra la cantidad de clientes que estaban pagando en cada mes para cada cohorte (o fecha de inscripción).

![analiza-13](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-13.png)

🤓 **Análisis** 🤓

Al observar los datos podemos comenzar a entenderlos con los siguientes ejemplos:

- El cohort de marzo de 2019 cuenta con 13 usuarios, es decir, 13 personas comenzaron a usar el software ese mes. Al cabo de 8 meses solo 11 usuarios seguían pagando la mensualidad.

- El cohort de enero de 2020 cuenta con 21 usuarios. Al cabo de 5 meses todos seguían activos.

- Para el cohort de diciembre del 2020 solo tenemos información del primer mes: 16 usuarios comenzaron a pagar el software.

🤔 **Reflexión 3**: ¿Cuál es el cohort con peor retención? ¿Y el cohort con mejor retención? ¿Hay algún mes donde existe mayor fuga de usuarios?

De buenas a primeras te darás cuenta de que no es fácil extraer información rápidamente solo mirando la tabla. Es por esto que para hacer nuestro análisis de cohortes más atractivo y eficiente visualmente es que vamos a calcular el porcentaje de usuarios que queda en cada mes, más que solo el número absoluto.

Para calcular el porcentaje en cada celda debemos dividir el número que aparece en la celda de cada mes, por el total de clientes de ese cohort. Por ejemplo, en el primer cohort tenemos 11 usuarios nuevos. El primer mes todavía quedan 11, eso representa el 100% de los usuarios (11/11*100%=100%). Para el mes 3 quedan 10 usuarios, eso representa el 91% del total (10/11*100 = 90,9*100 ~ 91%). Google Sheet nuevamente nos facilita este proceso, podemos ocupar una fórmula que divida el número de cada celda por el total de los usuarios de su fila y luego formatear como porcentaje gracias a la opción del menú.

![analiza-14](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-14.png)

> 👀 Al arrastrar la fórmula es muy importante que fijes (con un signo $) el denominador de la división, ya que siempre vas a estar dividiendo por el mismo número en cada cohort.

Una vez que tengas los porcentajes calculados es una buena idea formatear el color de cada celda utilizando escalas de colores. Para hacerlo seleccionamos todo el rango de celdas con los porcentajes y nos dirigimos a la opción Formato -> Formato condicional

Elegimos “Escala de Colores” y seleccionamos los colores rojo, verde y amarillo, así como los porcentajes 0, 50 y 100 como lo muestra la imagen.

![analiza-15](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-15.jpeg)

Tu resultado final se debería ver más o menos así:

![analiza-16](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-16.png)

🤓 **Análisis** 🤓

Este análisis por cohorte muestra el porcentaje de clientes retenidos, lo que facilita ver cómo se desarrolla la retención a lo largo del tiempo, así como comparar diferentes cohortes (meses de registro) entre sí. Veamos algunos ejemplos para entender cómo interpretar este resultado:

- Lo común es ver una tendencia (flecha vertical) que muestre que las cohortes más jóvenes (ejemplo 3/2020 o 4/2020) están mejorando que las cohortes mayores (1/2019), mientras más joven es una cohorte se espera que haya más clientes retenidos porque significaría que el producto ha ido mejorando a lo largo del tiempo y, por lo tanto, los clientes regresan a consumirlo. Para este caso, ¿se cumple esto?

- Es normal notar que el porcentaje de clientes retenidos va disminuyendo al pasar el tiempo (ver flecha horizontal). Por ejemplo, el cohort 1/2019 inició con 100% y después de 12 meses su retención es de 72.73%. La disminución es inevitable, pero se desea que los porcentajes a lo largo de la línea horizontal disminuyan lo más lentamente posible.

- Ejemplo de lectura de las celdas: 69.23% de todos los clientes adquiridos en 11/2019 siguen pagando la suscripción 14 meses después de registrarse. ¿Puedes notar cuál es la cohorte con mayor retención de clientes? ¿Cuál fue la que tuvo peor retención? ¿A qué se puede deber?

- Veamos los totales, 5 meses después de registrarse, el promedio de clientes retenidos era 88.58%

- El punto más crítico fue en el mes 20 y 21 con un 51% ¿Qué otros insights puedes notar? ¿Por qué crees que sucede? Anota todas las observaciones para agregarlas a tu informe.

Si el concepto de cohorte aún no está claro, mira esta [explicación](https://www.loom.com/share/ab7b1707d23d40d7aaf9e55b1521d3e2).

¡Felicitaciones! Lograste hacer tu primer análisis por cohortes. Como vimos al comienzo, este tipo de análisis nos permite mirar a nuestros clientes agrupándolos por su comportamiento (en este caso por su fecha de inicio de suscripción).

Ahora te desafiamos a que realices un análisis similar pero ahora tomando en cuenta la tasa de deserción (o Churn).

> 👀 Para calcular el churn, recuerda que este valor se refiere al porcentaje de clientes no retenidos, por ejemplo, si retuve el 90% de los clientes en el Mes 2, mi churn en el mes 2 fue del 10% (100 - 90).

### 4.4 Visualizar la tendencia de la retención

Otra herramienta que puede utilizar para analizar estos datos es una [línea de tendencia](https://support.microsoft.com/es-es/office/elegir-la-mejor-l%C3%ADnea-de-tendencia-para-los-datos-1bb3c9e7-0280-45b5-9ab0-d0c93161daa8).

Para esto, calcularemos la retención promedio por mes e incluimos un gráfico de dispersión con una línea de tendencia lineal. Nuestras variables para construir el gráfico serán los meses y la retención media.

![analiza-17](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/analiza-17.jpeg)

🤓 Aquí tienes toda la información sobre cómo construir e interpretar [este gráfico](https://www.loom.com/share/e456c569d0554799b747ec41bf782a0c).

Como puedes ver, con los datos organizados podemos utilizar una ayuda visual para identificar los porcentajes más bajos y así facilitar el análisis. Comprobemos tu avance.

### Closed Question B
¿Cuál es la cohorte con la mejor retención en el mes 13?
- 05/2020
- 12/2019
- 10/2020

### Closed Question B C
¿Cuántas cohortes tienen retención por cima de 80% en el mes 12?
5
4
3

### Open Question
¿Por qué crees que en la cohorte de marzo 2019 de los 13 nuevos clientes registrados, solo 4 continuaron pagando en diciembre del 2020? ¿El producto no fue lo suficientemente bueno para continuar con la suscripción?

### Validación
Podemos observar que la plataforma tiene una buena retención por el primer año, ya que 12 meses desde la inscripción del usuario, un 74% de ellos sigue utilizándola. Sin embargo, cerca de los 15 meses su uso disminuye bastante, y esto es exactamente lo que pasa en la cohorte de marzo/19. Si comparamos a la cohorte marzo/20 también vemos una baja en el porcentaje de retención. Esto puede indicar una estacionalidad, pero no se puede definir por completo lo que paso sin un análisis más profundo de esta cohorte, así que a veces el análisis generan otro análisis. Esto es normal, lo importante es no perder el foco de tu análisis principal.

## Paso 5: Comparte

Ya realizamos todo el análisis necesario, ahora falta organizar la información. Muchas analistas de datos se caen en este paso. Son muy buenas calculando indicadores, generando gráficos y creando tablas, pero no son capaces de transmitir los hallazgos más importantes al resto de la organización.

Para organizar nuestra información te recomendamos utilizar Google Slides, una herramienta de presentación similar a Microsoft Power Point.

### 5.1 Recomendaciones de la estructura

👩‍💻 Antes de hacer tu presentación, recuerda el propósito del análisis. Es una buena idea volver a leer el brief e identificar los puntos de conflicto de la situación. ¿Tu análisis, logra dar respuesta a las interrogantes que se plantearon en la reunión?

Ahora que estamos familiarizados con Google Slides, comencemos a pensar en qué y cómo presentar. Una forma interesante de hacerlo es dividir tu presentación en 3 temas: Contexto y objetivo, Análisis y resultados, Conclusión y recomendaciones.

#### Contexto y objetivo

Recuerda el contexto del proyecto y a quién le presentarás estos datos. Es importante tener esto en cuenta al definir el nivel de detalle de tu presentación.

Otro punto relevante es dejar claro, al comienzo de su presentación, el propósito del análisis y lo que se pretende responder con los resultados obtenidos. De esta manera, tu audiencia comprenderá mejor su análisis.

#### Análisis y resultados

Busca centrarte en los indicadores más fundamentales. Presenta los gráficos, tablas, números, porcentajes que responderán al objetivo del análisis y evita traer demasiada información. Presentar la información de una manera **simple y bien explicada** siempre es la mejor opción. Menos es más.

Verifica que tus gráficos tengan toda la información visible. No te preocupes si necesitas una slide completa para mostrar solo un gráfico. Es mejor tener varios slides que uno con varios gráficos e informaciones, pero que no se puede ver ni comprender ningún número.

#### Conclusión y recomendaciones

Ahora es tu momento de brillar, muestra tus conclusiones y recomendaciones en base a tu análisis. Aprovecha la oportunidad de mostrar nuevamente los números más importantes de tu análisis que respalden sus hallazgos.



### 5.2 Recomendaciones de diseño

No todas somos diseñadoras y es fácil perderse en slides con mucha información, desordenadas y sin un objetivo claro. Además, la información entra por los ojos. Si tu presentación es agradable visualmente tienes más probabilidad de que tu audiencia la tome en cuenta como el resultado de un análisis profesional, prolijo y detallado.

Felizmente, hay muchos recursos que nos pueden ayudar a tener una presentación que se vea profesional y ordenada.

#### Ocupa una plantilla

Hay muchas páginas de internet que ofrecen presentaciones pre-hechas con diseños predeterminados. Te recomendamos mirar [Slides Carnival](https://www.slidescarnival.com/) y [Slides Go](https://slidesgo.com/).

> ⚠ ¡Cuidado! Escoge una plantilla con diseño minimalista, simple y elegante. Las plantillas con muchos colores, imágenes y adornos se ven poco profesionales y distraen la atención de lo relevante.

#### Mantente fiel a una paleta de colores y una tipografía

La paleta de colores es una herramienta que ocupan los diseñadores gráficos para darle consistencia a sus diseños. Es importante tener una variedad de colores que se complementen entre sí y que sean agradables a la vista, pero sin buscar exagerar o incluir demasiados colores.

Hay páginas como [Color Hunt](https://colorhunt.co/) o [Coolors](https://coolors.co/) que facilitan el proceso de elección de una paleta de colores. Puedes utilizar la paleta de colores que viene en la plantilla que elegiste o, si prefieres, cambiarla por alguna que te guste de las páginas anteriores.

En cuanto a la tipografía, la recomendación es la misma: menos es más. Intenta emplear tipografías sin muchos adornos (se les llaman Sans Serif) que vienen incluidas en Google Slides por defecto como Roboto, Open Sans, Helvetica o Arial. Escoge una y utiliza la misma durante toda la presentación. Puedes emplear otra tipografía para los títulos si lo deseas, pero es crucial que sea una tipografía que juegue bien con la que escogiste. Si quieres recorrer este camino te recomiendo que uses [esta herramienta](https://www.fontpair.co/).

#### Imágenes vs íconos

Intenta utilizar imágenes solo en slides que creas que agregan valor, no como un adorno. Muchas veces es mejor idea utilizar un ícono que una imagen. Recuerda, menos es más.

Para elegir íconos de buena calidad puedes ocupar [el complemento de Google Slides de Flaticon](https://workspace.google.com/marketplace/app/icons_for_slides_docs/381578326502) que te permite crear íconos directamente en tus dispositivas o descargarlos directamente de [su página](https://www.flaticon.com/).

## Paso 6: Actúa

Ahora si está lista para grabar un video con tus recomendaciones a tu jefe. Quizás ya tienes una idea de cómo responder la pregunta ¿El producto ha alcanzado Product-Market Fit? 👀 No te preocupes si no lo tienes tan claro, no hay respuestas correctas o incorrectas, solo debes argumentar bien y compartir tus conclusiones. En el mundo del análisis de datos muy pocas veces hay una respuesta unívoca y sin dudas, por el contrario, en general las conclusiones se mueven en áreas grises. Por lo que tus argumentos son importantes al momento de entregar una recomendación.

### Open Question
¿Consideras que se debe invertir en triplicar la inversión de adquisición de usuarios? ¿La empresa alcanzo el PMF?

### Validación
Como te comentamos previamente, no existen respuestas absolutamente correctas o incorrectas. Lo importante es realizar una recomendación bien fundamentada. En este caso, para realizar una recomendación fundada a nuestro jefe sobre si nuestra plataforma retiene lo suficiente a sus clientes como para considerar que hemos logrado alcanzar PMF, tenemos que comparar estas tasas con la industria. [Este artículo](https://sixteenventures.com/saas-churn-rate) indica que una tasa aceptable de churn para una startup Sass es del 5-7% anual. Nuestro software está hasta este momento muy por sobre ese valor. Por lo que la recomendación para la startup puede ser que no aumente el presupuesto de mercadeo hasta alcanzar una retención mayor. Podemos recomendar también utilizar ese presupuesto en el desarrollo de nuevas funcionalidades que haga que los clientes quieran mantenerse por más tiempo con la suscripción.

# Hacker edition

¿Volaste por este proyecto? ¿Te encantó el concepto de product market fit y quieres aprender más? Esta sección es para ti 😎.

En este proyecto hicimos un análisis mes a mes del comportamiento de los clientes. Muchas veces la forma en que agrupamos los datos genera distintos hallazgos, por lo que una analista de datos profesional siempre intenta buscar nuevos ángulos para mirar la información. Una forma distinta de hacer este análisis sería en un horizonte de tiempo mayor, por ejemplo, agrupando los clientes en trimestres. Una de las razones que pueden llevarte a la decisión de probar agrupando por trimestre podrían ser:

- **Cantidad de usuarios registrados por mes**, algunos meses la cantidad de usuarios es baja, por lo que los resultados podrían no ser concluyentes.

Para realizar el análisis de cohorts trimestral, la estructura de tu tabla de análisis debería verse como la siguiente imágen:

<img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/hacker-edition-01-.png" alt="estructura-cohort-tri" width="600"/>

  > Figura: Estructura de análisis de cohorts trimestral

Para crear la estructura previa puedes seguir los siguientes pasos:

1. Copia las columnas Nombre Cliente, Apellido Cliente, Estado Cliente, Mes Registro y Mes de Abandono (Churn) a una nueva hoja.

2. Procesar el dataset para que tenga dos columnas adicionales: trimestre (T1 si es el primero, T2 si es el segundo, y así en adelante) y el año de ese trimestre. Para lograr esto vamos a ocupar las [IF](https://support.google.com/docs/answer/3093364?hl%3Den) y [MONTH](https://support.google.com/docs/answer/3093052?hl%3Den) para clasificar a los clientes en trimestres.

  Para usar la fórmula IF, primero entendamos los argumentos de la fórmula. Los argumentos son:

- **logical_expression**: información que desea verificar, si el valor en la celda es, por ejemplo, igual o mayor que otro valor determinado.

- **value_if_true**: valor a devolver si el logical_expression es verdadero

- **value_if_false**: valor a devolver si el logical_expression es falso.

  La fórmula MONTH() devuelve el número que representa el mes de una variable de fecha.

  > 👀 A veces las celdas de fecha no están en formato fecha, aun cuando parezca que si lo son. Para asegurarnos, podemos ocupar la fórmula [TO_DATE()](https://support.google.com/docs/answer/3094239?hl%3Den) para transformar la variable y confirmar que la variable está en formato de fecha.

  Ahora que entendemos las tres fórmulas, podemos ocuparlas para calcular el trimestre de ingreso de cada cliente. Por ejemplo, nuestro primer cliente George García se registró el 01/2019. Con la fórmula MONTH() podemos extraer el mes (1) y luego ocupar la función IF para verificar si este mes corresponde al primer, segundo, tercer o cuatro trimestre.

  Nuestra fórmula debería verse así:

  ```SQL
  =IF(MONTH(F2)<=3,"T1",IF(MONTH(F2)<=6,"T2", IF(MONTH(F2)<=9,"T3",IF(MONTH(F2)<=12,"T4",""))))

  ```

  Traducción:

- Si el mes del cliente es menor o igual a 3, entonces escribe "T1" porque corresponde al primer trimestre.
- Si eso no funciona, prueba que el mes sea menor o igual a 6. Dado que no es menor o igual a 3 (porque la condición anterior no funcionó), entonces si se cumple esta condición el trimestre de registro debería ser el segundo, por lo tanto, escribe "T2".
- Siguiendo la lógica anterior, si el mes del cliente es menor o igual a 9 escribe "T3" porque corresponde al tercer trimestre.
- Si nada de lo anterior se cumple entonces el registro es del cuarto trimestre ("T4").

  > 👩‍💻 La fórmula IFS cumple una función similar a la encadenación de funciones IF. Te recomendamos probarla, ya que, en casos como estos donde tienes muchas condiciones, es una fórmula más limpia y simple de utilizar.

  Ya tenemos el trimestre, pero este puede corresponde a cualquiera de los dos años del dataset. Por lo que se vuelve necesario crear una nueva columna que contenga el año del trimestre. Para esto puedes usar la fórmula [YEAR()](https://support.google.com/docs/answer/3093061?hl%3Den).

  Su base de datos al final debería verse así:

  ![hacker-edition-01](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/hacker-edition-01.png)

Aplicaremos el proceso del paso 2 pero está vez con la columna "Mes de Abandono (Churn). ¿Qué hacer con los registros en blanco? Un posible tratamiento es ponerle un TRIMESTRE posterior al último que tienes como registro, por ejemplo si tienes "2020-T4"como último trimestre de registro, podrías llenar los valores vacíos con "2021-T1".

Luego, alcularemos las cabeceras de las columnas de medición de deserción

  ![hacker-edition-01](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/hacker-edition-02-.png)

  Para generar estos datos puedes hacer una concatenación de funciones como sigue:
  
  ```SQL
  =TRANSPOSE(UNIQUE([COLUMNA QUE CONTIENE TRIMESTRE DE REGISTRO]))
  ```

La función UNIQUE(), te permite obtener los valores únicos de toda la columna y finalmente la función TRANSPOSE() se utiliza para pasar los datos que están a nivel fila a nivel de columnas.

Ahora toca llenar los datos con 1 cuando el usuario estuvo activo y vació el trimestre que abandonó.

  <img src="https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-2-startup/images/hacker-edition-03-.png" alt="estructura-cohort-tri" width="600"/>

  Para que el valor de la celda C1 de la imagen previa sea 1 necesitamos validar dos condiciones
  
- Primera condición: Que la celda C1 sea menor que el trimestre de abandono es decir menor que la celda B1
- Segunda condición: Que el trimestre de registro (celda A1) sea mayor igual que el periodo de medición (celda C1).

  **Hint:** Utiliza la función IF para validar las condiciones previas.

  Si no se cumple estás condiciones deberás devolver espacio en blanco ("")

Después de crear y organizar sus datos por trimestre, puedes generar tu tabla dinámica, como hicimos para el análisis mensual, usando las variables trimestre y año para agrupar la información.
  
Con tu tabla creada, puedes elegir la fórmula INDEX o QUERY para organizar sus datos y luego formatear la información para ver como se comporta la retención y el abandono en cada trimestre.


Ahora sabes que además de realizar análisis mensuales, también puedes realizarlo en otras temporalidades, trimestral en este caso. ¡Vayamos a comprobar lo que hemos aprendido hasta ahora!

### Closed Question A
Cuál la cohorte trimestral con la mejor retención en el T5?
- 2019T4
- 2019T3
- 2020T4

### Open Question
¿Qué aprendizaje personal te llevas de haberte retado con la Hacker Edition?

### Validación

Nos encanta que te hayas desafiado a ti misma en la Hacker Edition. Ahora que podemos comparar los dos análisis realizados, veremos que las cohortes mensuales y trimestrales siguen el mismo comportamiento, disminuyendo por debajo del 70% al cabo de un año. De esta manera, podemos elegir uno de los dos análisis (trimestral o mensual) para presentar tu estudio de la forma que consideres más clara.


