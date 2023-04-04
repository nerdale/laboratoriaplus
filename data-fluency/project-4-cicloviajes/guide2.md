# Introducción

## Contexto

En este proyecto analizarás el uso de un programa de bicicletas compartidas. Para desarrollarlo, aprenderás a utilizar dos herramientas poderosas de la analítica de datos: DataStudio y Google BigQuery. El primero te ayudará a crear visualizaciones claras e interactivas para presentar tus resultados y conclusiones. El segundo es un motor de bases de datos creado por Google en el que podrás manejar grandes volúmenes de datos en cuestión de segundos. Finalmente, para poder interactuar con los datos, aprenderás el lenguaje más utilizado en el mundo para comunicarnos con bases de datos: SQL.

Como todo nuevo lenguaje, harás frente a una pequeña dificultad inicial mientras te familiarizas con lo básico. Para facilitar este proceso, hemos preparado [este mini curso de SQL](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Introduccion_su3UO?playModeWorkflowId%3D%23_luO8s&sa=D&source=editors&ust=1671545727651100&usg=AOvVaw0kEn8qbkSGXuUZYJVT8c6w) con un dataset similar con algunas diferencias, para que puedas practicar antes de lanzarte con tu proyecto.

## Lifeskills

Ésta es tu oportunidad para conjugar todas las estrategias que has desarrollado a lo largo de los proyectos anteriores. Recuerda que tu puedes:

- Ser una analista de datos muy **organizada**, que estructura su trabajo dentro del tiempo que tiene disponible. Avanzas a paso firme y paulatino, siendo realista con los tiempos libres que manejas para avanzar en tu proyecto. Además, te apoyas de tecnología para facilitar tu organización a través del uso de Trello u alguna otra herramienta de productividad.
- Cuestionar cada cálculo y visualización que haces en el camino de tu proyecto, empleando **pensamiento crítico** elaborado. Miras con detención las tablas que vas desarrollando y encuentras un sentido lógico en los números. Cuestionas tu propio trabajo y los datos con los que cuentas. Además, llegas a conclusiones que van más allá de lo obvio y básico. Complementas tus análisis con información externa.
- Presentar tus resultados y conclusiones con técnicas de **data storytelling** para cautivar a tu audiencia y asegurarte de que tu mensaje resuene de la forma más clara posible en tu audiencia. Tus visualizaciones son eficientes, simples, modernas y conformadas por información útil. Empleas texto para complementar con conclusiones tus reportes y dashboards. Favoreces un diseño minimalista que permita enfocarse en el contenido.

Aprovecha este proyecto electivo para seguir desarrollando estas habilidades importantísimas en el mundo del análisis de datos.

# Desarrollo

A estas alturas, el marco metodológico de los 6 pasos para el análisis de datos que Google propone ya es parte de tu ADN. Vamos por el primer paso.

## Paso 1: Pregunta

Para plantear correctamente la pregunta o las preguntas que guiarán tu análisis, es importante contar con la mayor cantidad de contexto posible. En un proyecto real, deberíamos ir a hacer preguntas a los involucrados, pero en nuestro caso solo contamos con el brief el proyecto, por lo que es una buena idea volver a leerlo. Varias veces.

De la lectura del brief encontramos los siguientes puntos importantes:

- Debemos presentar las conclusiones de nuestro análisis a la nueva CEO de la compañía. Independiente de las conclusiones a las que lleguemos, parece razonable sumar a nuestro análisis una **vista general de los datos** para que ella se pueda hacer una idea de la compañía. De hecho, la misma CEO nos pregunta por la calidad y antigüedad de los datos, por lo que deberíamos intentar **describir de alguna forma el estado del arte de los datos**.
- La CEO tiene un particular interés en entender los perfiles de los clientes. Una pregunta central parece ser **¿cómo se diferencian los “customers” de los “subscribers”?**.  Para comprender mejor su comportamiento podemos generar distintas **métricas diferenciadas para cada perfil**. Como mínimo deberíamos ocupar las que la CEO propone en el brief:

  - Total de viajes
  - Evolución de los viajes en el tiempo
  - Duración de los viajes
  - Uso por horario
  - Uso por día de la semana
- Finalmente, además de entender los perfiles, nuestra CEO parece querer que le entreguemos **recomendaciones para fidelizar ambos perfiles**.

Ahora que tenemos mayor claridad de lo que debemos lograr con nuestro análisis, vamos por los datos.

## Paso 2: Prepara

En este proyecto trabajaremos con una herramienta nueva: Google BigQuery. Si no has trabajado antes con esta herramienta, entonces primero necesitamos habilitar el ambiente de prueba y crear tu primer proyecto.

### 2.1 Habilitar el ambiente

Aun cuando puedes descargar los archivos de datos de la empresa Citibike de su página web, contamos con la ventaja de que la base de datos completa también se encuentra disponible de manera pública en la nube de Google (Google Cloud) y es posible manipularla directamente usando Google BigQuery sin necesidad de importar archivos CSV.

Primero tenemos que ingresar a la [plataforma de Google Cloud](https://www.google.com/url?q=https://console.cloud.google.com/getting-started&sa=D&source=editors&ust=1671545727654291&usg=AOvVaw3bmqX8u5_WsY3BGU1SCmLJ) y acceder con nuestra cuenta de Google (presiona el botón de “Acceder” arriba a la derecha).

Si es tu primera vez en la plataforma, se te abrirá una ventana dándote la bienvenida. Acepta las condiciones del servicio y luego dale a “Aceptar y Continuar”.

La nube de Google ofrece muchísimos servicios, pero el que nos interesa es BigQuery:

![buscar bigquery](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image32.png)

Para guardar y organizar nuestro trabajo, vamos a crear un nuevo proyecto

![crear nuevo proyecto](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image25.png)

Cuando le das en “CREAR PROYECTO”, te llevará a un formulario donde tendrás que colocar el nombre de tu proyecto, en “Ubicación” y “Location” puedes dejar el valor por defecto. El nombre del proyecto tiene que ser único e irrepetible, en este caso le pondremos “Cicloviajes” y finalmente le das en el botón “CREAR”.

![vista general bigquery](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image33.png)

¡Ya estás lista para hacer tus primeras consultas con BigQuery! Si te fijas en la barra superior, estás trabajando en la “Zona de pruebas” de la plataforma, que es gratuita. Esta versión no-paga tiene algunas [limitaciones](https://www.google.com/url?q=https://cloud.google.com/bigquery/docs/sandbox?hl%3Des-419%23limitations&sa=D&source=editors&ust=1671545727655239&usg=AOvVaw37PktAhtEiVPzMnsXjRhW-), pero para efectos de este proyecto tendrás recursos más que suficientes.

### 2.2 Importar el dataset

Como comentamos anteriormente, el dataset que utilizaremos está disponible de manera pública en la nube de Google. En [este enlace](https://www.google.com/url?q=https://console.cloud.google.com/bigquery&sa=D&source=editors&ust=1671545727655758&usg=AOvVaw30kMB6vgU0b_kicraNNE5h) puedes encontrar este dataset y muchos otros sets de datos públicos con los que puedes jugar/entrenar.

Para agregar el dataset de Citibike tenemos que utilizar el buscador:

![buscar dataset publico](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image12.png)

> 👀 Si no te retorna resultados, entonces haz clic en “Ampliar la búsqueda”

Otra forma en la que puedes explorar los datasets públicos desde BigQuery, es haciendo clic en el botón “+ Agregar Datos” -> “Conjuntos de datos públicos”.

![agregar fuentes de datos](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image22.png)

Una vez que lo encuentres, te recomiendo que lo “Destaques”. De esa forma lo tendrás disponible en tu barra lateral para fácil acceso.

![destacar dataset](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image6.png)

Te habrás dado cuenta de que tu dataset tiene una estructura anidada de tres niveles.

Los niveles son:

- **Primer nivel (Proyecto)**: El nombre del proyecto que almacena el dataset. Un proyecto puede tener muchos datasets. En este caso, el proyecto “bigquery-public-data” alberga todos los datasets publicos de la plataforma.
- **Segundo nivel (Dataset)**: El dataset agrupa una o varias tablas.
- **Tercer nivel (Tablas)**: Contiene la información almacenada de manera estructurada.

### 2.3 Explorar el dataset

Tal como viste en [el video del mini-curso](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Explorando-tablas_sufEr?playModeWorkflowId%3D%23_luHYS&sa=D&source=editors&ust=1671545727657095&usg=AOvVaw2WsR24GVnySnSXR2JCfcbr), te recomendamos explorar las dos tablas del dataset. Algunas cosas que deberías tomar en cuenta en tu exploración:

- En la pestaña “ESQUEMA” puedes encontrar los distintos campos de las tablas. Intenta entender que es lo que representa cada campo. Apóyate en la descripción que se proporciona. Una buena idea es revisar el video sobre [tipos de datos](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Tipos-de-datos_sufb0?playModeWorkflowId%3D%23_lubka&sa=D&source=editors&ust=1671545727657430&usg=AOvVaw0pEg1yUheTkCD__qkHdJfo) para entender que tipo de valores almacena cada campo.
- En la pestaña “DETALLES” intenta recordar el ID de la tabla, ya que lo utilizarás en tus consultas. Además, mira la cantidad de filas que tiene cada tabla. De esa forma te podrás hacer una idea del tamaño de las consultas que debes hacer, y la cantidad de filas que deberían tener tus resultados de consultas.
- En la pestaña “VISTA PREVIA” puedes ver directamente los datos que están almacenados. Es una buena idea mirar rápidamente los datos para completar tu entendimiento de los campos. Te darás cuenta de que algunos campos son números negativos, otros son textos que se repiten y otros son únicos. Este entendimiento te ayudará al momento de hacer tus consultas.

## Paso 3: Procesa

En tu exploración te habrás dado cuenta de que una de las tablas tiene valores “null” en gran parte de sus filas. Los valores “null” representan un valor vacío en una tabla de datos SQL. Como buena analista de datos ya debes estar planeando la mejor estrategia para limpiar esa tabla, ¡felicitaciones!

Sin embargo, la limpieza de datos en tablas de SQL no es tan simple como en spreadsheet. Para borrar, sobreescribir o crear nuevos datos y tablas se requiere un set de herramientas que está por fuera de este pequeño proyecto electivo. Si optas por seguir en L+ es algo que si aprenderás en el siguiente curso de “Data Analysis”.

Por lo pronto, en este tercer paso “Procesa” vamos a dejar los datos tal y como están. Pero haremos nota mental de las precauciones que tenemos que hacer al momento de realizar nuestras consultas, ya que si podemos filtrar los datos que no queramos que aparezcan, como por ejemplo, los nulls. Esto lo aprenderás en el siguiente paso.

## Paso 4: Analiza

Como ya sabes, es buena idea comenzar este paso con un pequeño análisis exploratorio de los datos. Además, hacer este análisis inicial te va a ayudar a reforzar algunas de las consultas básicas que aprendiste en el mini curso.

### 4.1 Análisis exploratorio

Comencemos explorando las primeras 100 filas de la tabla “citibike_stations”.

```SQL
SELECT
  *
FROM
  `bigquery-public-data.new_york_citibike.citibike_stations`
LIMIT
  100
```

> 👩‍💻 Si no estás muy segura de cómo llegamos a esta consulta, vuelve a revisar [la sección 2 del mini curso](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Seleccionar-una-o-varias-columnas_suXsN?playModeWorkflowId%3D%23_luJRX&sa=D&source=editors&ust=1671545727659109&usg=AOvVaw1--lqUqZrlDe5K3ciJUFUO).

Muchas veces, en lugar de mostrar todas las columnas, queremos seleccionar solo algunas columnas. Este tipo de consultas son menos demandantes en términos de procesamiento de información y nos entregan solo las variables (columnas) que necesitamos. Para realizar esto tendrás que reemplazar el carácter asterisco (*) por los nombres de las columnas que te interesan, separadas por una coma (,).

Escribe una consulta que muestre los resultados de los primeros 100 registros, mostrando solo las columnas “station_id”, “name”, “latitude”, “longitude”, “region_id”. Deberías obtener algo parecido a esto.

![Seleccionando columnas específicas](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image11.png)

Otra estrategia útil cuando estás haciendo un análisis exploratorio en SQL es conocer el “dominio” de las variables que tienen valores que se repiten. El “dominio” se refiere a todos los valores que adopta la columna.

Por ejemplo, el campo “rental_methods” muestra el mismo valor para las primeras filtas: “KEY, CREDITCARD”. ¿Será este el único valor que adopta esa columna? ¿O tendrá otros valores? Para saberlo utilizamos la sentencia DISTINCT en SQL, que nos retorna solo los valores únicos de la columna que le digamos.

```SQL
SELECT
  DISTINCT rental_methods
FROM
  `bigquery-public-data.new_york_citibike.citibike_stations`
```

Nos retornó solo una fila con un único valor: “KEY, CREDITCARD”. Eso nos dice que todas las 1798 filas de la tabla tienen ese mismo valor en ese campo. Por lo que podemos concluir que todas las estaciones aceptan dos tipos de pago que son “CREDITCARD” y “KEY”.

> 👩‍💻 ¡Ahora es tu turno!, ¿Cuáles son los valores únicos de la variable “name” (nombre de la estación) y cuántos valores distintos hay?

¡Bien hecho! Otra forma útil de explorar los datos es contando registros. Por ejemplo, si quisiéramos contar cuantas filas tiene todo nuestro dataset podemos correr:

```SQL
SELECT
  COUNT(*)
FROM
  `bigquery-public-data.new_york_citibike.citibike_stations`
```

Podemos observar que el conjunto de datos contiene un total de 1798 registros, que es la misma cantidad de nombres únicos que te retornó el DISTINCT anteriormente. La función COUNT la podemos ocupar en todas las columnas (y por eso el operador * ) como también en algunas columnas específicas. Para hacer eso escribimos el nombre de la columna dentro del paréntesis.

> 🧐 Recuerda que siempre puedes consultar la historia de tus QUERIES o guardar consultas que te parezcan útiles en BigQuery. Para recordarlo revisa esta [sección](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Historia-de-consultas-y-guardar-queries_suKnq?playModeWorkflowId%3D%23_luk3z&sa=D&source=editors&ust=1671545727660911&usg=AOvVaw1KLXqlCPnsT0DeP6AkoHdj) del curso.

Hasta ahora hemos podido aprender comandos que nos permiten visualizar un número establecido de registros, conocer el dominio de nuestras variables y a su vez cuantificar el número de registros para cada variable. Pero cuando trabajamos un conjunto de datos no siempre necesitamos el 100% de los registros, gran parte de los análisis se requiere de filtros para trabajar con subconjuntos del conjunto de datos. El comando WHERE nos permitirá realizar los filtros necesarios para obtener el subconjunto requerido.

Este filtro nos va a ayudar a resolver el problema con los valores null que encontramos en el paso 3 en la tabla “trips”. Veamos cómo podemos resolverlo.

```SQL
SELECT
  *
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
```

El operador IS NOT nos permite filtrar el set de datos y dejar solo aquellos que cumplan que NO tienen un valor NULL en la columna start_station_id.

![Seleccionando columnas específicas](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image23.png)

> 👩‍💻 ¿Puedes contar cuántos registros SI tienen un valor NULL en la columna start_station_id? Puedes ocupar el operador IS en vez de IS NOT.

También podemos filtrar registros haciendo [comparaciones con números](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/WHERE-con-integers_su9hI?playModeWorkflowId%3D%23_luPxf&sa=D&source=editors&ust=1671545727662249&usg=AOvVaw3YJCnopQlTnkb0pfaa50tZ). Intenta seleccionar solo los viajes que han durado más de 5 minutos. Recuerda que la columna “tripduration” muestra la duración del viaje en segundos, por lo que tendrás que hacer la conversión dividiendo por 60.

![Usando where](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image24.png)

Puedes encadenar lo que has aprendido hasta ahora. Por ejemplo, si quisiéramos saber cuál es el porcentaje de viajes que tuvieron una duración mayor a 5 minutos, podemos aplicar un filtro con WHERE y luego contar ese resultado con COUNT. Para este primer caso realizaremos dos consultas.

```SQL
-- Esta consulta retorna la cantidad total de viajes

SELECT
  COUNT(*)
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS NOT NULL
```

```SQL
-- Esta consulta retorna solo aquellos que han durado más de 5 minutos

SELECT
  COUNT(*)
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  tripduration >=  300
```

> 🧐 ¿Qué son esos dos guiones en la consulta? En SQL puedes hacer comentarios, es decir, escribir texto sin que BigQuery piense que estás escribiendo una consulta. Los comentarios son útiles para guiar a otras personas en consultas muy complejas o para recordarte a ti misma (del futuro) porque hiciste algo en una consulta.

La primera consulta te devuelve el número de registros en la tabla de viajes, esto representaría el total de viajes realizados por los usuarios. Por otro lado, la segunda consulta te devuelve el total de viajes que duraron 5 minutos o más. Por lo que el porcentaje de viajes que duraron 5 minutos o más es de 84,5%.

> 👩‍💻 ¡Ahora es tu turno!, ¿Podrías indicarnos cuál es el porcentaje de viajes realizados por el tipo de cliente “Customer”?. Si no recuerdas cómo filtrar por un texto, vuelve a ver [este video](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Filtrando-segun-Strings_suOA3?playModeWorkflowId%3D%23_luaJm&sa=D&source=editors&ust=1671545727664161&usg=AOvVaw2Ybx51ERBzBkTl2cQIzDef) del mini curso.

¡Excelente!, ahora que comprendes que tan importante es el uso de los filtros, es probable que requieras aplicar más de un filtro simultáneamente, para ello cuentas con el comando [AND](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Encadenando-filtros-con-AND_suiWl?playModeWorkflowId%3D%23_luim_&sa=D&source=editors&ust=1671545727664491&usg=AOvVaw0FYdCVqL7gssWpjuxq7wfG) (cuando necesitas que se cumplan todas las condiciones simultáneamente) y el operador  [OR](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Combinar-filtros-con-OR_suhbP?playModeWorkflowId%3D%23_luxiM&sa=D&source=editors&ust=1671545727664780&usg=AOvVaw0fqb8Daxifi6_mbpl2vEFu) (cuando necesitas que se cumpla alguna de las condiciones pero no necesariamente todas).

Supongamos que queremos filtrar los viajes que hicieron los clientes “Customer” y que duraron 5 minutos o más. ¿Crees que puedes llegar al resultado de la siguiente imagen?. Si te fijas, todos los registros tienen un valor mayor igual a 300 segundos en la variable “tripduration” y la variable “usertype” todos los registros son “Customer”.

![Seleccionando columnas especificas](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image3.png)

Muy bien. Supongamos que en nuestro análisis exploratorio nos gustaría conocer cuáles viajes fueron iniciados en alguna estación que está en la calle “Columbia St”. Si te fijas en la columna “start_station_name” te darás cuenta de que los nombres de las estaciones son las esquinas entre dos calles: “calle 1 & calle 2”. Por ejemplo, una estación que pasa por la calle “Columbia St” es la estación “Columbia St & Kane St”.

Intentemos filtrar nuestra base de datos para que nos retorne los nombres de las estaciones que pasan por la calle “Columbia St”, o dicho de otra manera, filtremos la columna “start_station_name” por aquellas que comiencen con “Columbia St”. Para lograr eso ocupamos el operador LIKE (si no recuerdas cómo ocuparlo mira [esta](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Usando-LIKE-con-Strings_su7gI?playModeWorkflowId%3D%23_lu8tq&sa=D&source=editors&ust=1671545727665476&usg=AOvVaw34Twi_hvV32YgHNP-1aeax) sección del mini curso.

```SQL
SELECT
  DISTINCT start_station_name
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_name LIKE  'Columbia St%'
```

Gracias a esa consulta podemos ver todas las estaciones que comienzan con “Columbia St”.

¡Genial! Ya entiendes mejor cómo se componen los datos y además aprovechaste de refrescar tus habilidades de SQL mientras hacías tu análisis exploratorio. Pasemos ahora a generar la data que necesitaba la CEO para perfilar los distintos tipos de clientes.

En las siguientes secciones vamos a ir uno por uno resolviendo las métricas que pidió la CEO con consultas que luego vamos a importar a Google DataStudio para visualizar.

### 4.2 Total de viajes

En nuestro análisis exploratorio ya revisamos como contar la cantidad de viajes totales que no son null.

```SQL
SELECT
  COUNT(*)
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS NOT NULL
```

Tratemos de ir un paso más allá y contar la cantidad de viajes totales por tipo de cliente (Customer y Subscriber). Para poder agrupar el conteo por tipo de usuario debemos ocupar la cláusula GROUP BY. Si no recuerdas cómo hacerlo, te recomendamos ver [la sección 5](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Agrupando-datos-con-GROUP-BY_su5QT?playModeWorkflowId%3D%23_lut-A&sa=D&source=editors&ust=1671545727667277&usg=AOvVaw07B1NvtyupbBY3U-ue1EQ-) del mini curso.

```SQL
SELECT
  usertype,
  COUNT(*) AS num_trips
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
GROUP  BY
  usertype
```

> 🧐 Ocupamos el operador AS para nombrar los campos que estamos creando con nombres que tengan sentido. Si no le ponemos “AS num_trips” entonces BigQuery va a pasar a llamar esa columna con algún nombre extraño como “f(0)”. Siempre es buena idea nombrar tus campos y tablas de forma de que tus consultas sean más legibles.

Lo importante es tener en cuenta que debes agrupar (GROUP BY) por el tipo de usuario (usertype) y dentro de nuestro SELECT deben estar tanto el usertype como el conteo de cada uno (COUNT*).

> 👩‍💻 Recuerda ir guardando tus consultas para luego llamarlas fácilmente cuando queramos importarlas al DataStudio.

### 4.3 Evolución de los viajes a lo largo del tiempo

Uno de los indicadores que le gustaría conocer al negocio es la cantidad de viajes diarios que se realizan usando las bicicletas de “CitiBike”. Para que puedas conseguir el número de viajes por día, necesitas trabajar con la columna “starttime”.

La columna “starttime” se encuentra en un formato DATETIME, un ejemplo de esta columna es el siguiente “2017-09-16T13:07:41”, la cual está conformada en la primera parte por la Fecha (YYYY-MM-DD) y la segunda parte por la Hora (HH:MM:mm) separados por el carácter T.

Para conocer como evolucionan los viajes a través del tiempo solo necesitas trabajar con la parte de la Fecha. Para esto ocuparemos la función DATE() de BigQuery, que acepta una columna DATETIME y retorna solo la parte de la fecha.

Pruébala con la siguiente consulta:

```SQL
SELECT
  *,
  DATE(starttime)  AS starttime_date
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
LIMIT  
  100
```

Esta consulta retorna todas las columnas de la tabla original (por eso está el operador del asterisco *), pero le agrega al final una columna nueva que llamamos “starttime_date” con únicamente la fecha del campo starttime. Para conocer más sobre el tipo de datos DATETIME, DATE, puedes revisar el siguiente [artículo](https://www.google.com/url?q=https://cloud.google.com/bigquery/docs/reference/standard-sql/date_functions&sa=D&source=editors&ust=1671545727670291&usg=AOvVaw0LUY4l3KqlOrFebXmFKKqK).

> 🧐 Hay otras formas de extraer la fecha de un campo DATETIME. La más común es la función CAST() que transforma el tipo de un campo en otro. Es útil para transformar DATETIME en DATE, pero también para transformar números en textos y muchas otras transformaciones. Te recomendamos leer [la documentación de Google](https://www.google.com/url?q=https://cloud.google.com/bigquery/docs/reference/standard-sql/conversion_functions&sa=D&source=editors&ust=1671545727670705&usg=AOvVaw2_lSC0dqITMJRK8M8WZHXu) sobre la función CAST.

Bien, ahora que ya sabes cómo extraer u obtener solo la fecha de un campo datetime es momento de obtener la cantidad de viajes para cada fecha. Para realizar esto, necesitas agrupar los datos por esta fecha creada y pasar a contar la cantidad de viajes que tienes. Ocupa GROUP BY tal como lo hicimos en la sección anterior.

```SQL
SELECT
  DATE(starttime)  AS starttime_date,
  COUNT(*)  AS num_trips
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
GROUP  BY
  starttime_date
```

Si miras bien el resultado, observarás que las fechas no están ordenadas. Para forzar su orden ocupa la cláusula [ORDER BY](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Ordenar-con-ORDER-BY_sudgX?playModeWorkflowId%3D%23_lu13l&sa=D&source=editors&ust=1671545727672145&usg=AOvVaw2wyfb2KYxkDqKmEn0ruqxD).

Deberías llegar a un resultado similar a este:

![Resultado order by](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image14.png)

### 4.4 Duración promedio por tipo de cliente

BigQuery tiene funciones que nos permite identificar de forma rápida un estadístico de una variable. Entre estas funciones tenemos AVG(), SUM(), COUNT(), MIN(), MAX(). Estas funciones también son conocidas como funciones de agregación. En [la sección 4](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Contando-filas-con-COUNT_suKzJ?playModeWorkflowId%3D%23_luiQQ&sa=D&source=editors&ust=1671545727672778&usg=AOvVaw15cc1XYTHW737z8REeqnj0) del mini curso puedes encontrar información valiosa con respecto a estas funciones.

En este caso nos interesa sacar el promedio de la duración del viaje para cada tipo de usuario. Al igual que con la función COUNT() para lograr esto tenemos que agrupar por usertype. Además, a la función AVG() tenemos que decirle que campo queremos que promedie.

```SQL
SELECT
  usertype,
  AVG(tripduration) AS avg_duration_sec,
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
GROUP  BY
  usertype
```

Recuerda que el campo “tripduration” almacena el tiempo en segundos, por lo que si quisieras conocer el resultado en minutos, tendrías que dividir lo obtenido por 60. Este tipo de operadores matemáticos los podemos aplicar directamente dentro de la sentencia SELECT.

```SQL
SELECT
  usertype,
  AVG(tripduration)/60  AS avg_duration_mins,
  
-- ...el resto de la consulta...
```

### 4.5 Desglose de uso por horario

A nuestra CEO le gustaría saber cuáles son las horas del día en donde se utilizan más las bicicletas. Nuestro campo “starttime” es del tipo DATETIME, que reúne tanto la fecha como la hora. Para poder “extraer” únicamente la hora del viaje, que es lo que nos interesa, vamos a ocupar la función [EXTRACT](https://www.google.com/url?q=https://cloud.google.com/bigquery/docs/reference/standard-sql/timestamp_functions%23extract&sa=D&source=editors&ust=1671545727674773&usg=AOvVaw0pPQcQhFK8ew7jM_nsc-IB).

```SQL
SELECT
  EXTRACT(HOUR FROM starttime) AS hour,
  COUNT(*) AS num_trips
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips`
WHERE
  start_station_id IS  NOT  NULL
GROUP  BY
  hour
ORDER  BY
  hour
```

La función EXTRACT necesita dos cosas: lo que necesitamos que extraiga del DATETIME (día, hora, minuto, año, etc.) y el campo del cual queremos extraer eso. En nuestro caso queremos extraer la hora (HOUR) del campo “starttime”.

Una vez hecho eso, aprovechamos de agrupar por ese campo y contar cuántos viajes se han hecho en cada hora.

Finalmente, ocupamos un GROUP BY porque, de otra forma, el resultado estaría todo desordenado.

La consulta nos entrega información valiosa sobre los horarios más concurridos. Sin embargo, a nuestra CEO le interesa perfilar a los clientes que utilizan el servicio. ¿Los “Customers” ocupan las bicicletas en los mismos horarios que los “Subscribers”? Esa es una pregunta que tenemos que ser capaces de responderle a nuestra CEO.

Por lo que vamos a hacer una agrupación por más de un campo. Si no recuerdas cómo se hace, refresca la memoria con [este video](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Agrupar-por-multiples-columnas_suzEI?playModeWorkflowId%3D%23_luSA3&sa=D&source=editors&ust=1671545727676788&usg=AOvVaw3bkOO1hRMxBITYbY1GDFHa) del mini curso. Deberías agrupar, además de por “hour”, también por “usertype”, y llegar a un resultado que muestre la hora del día y al tipo de usuario, además de la cantidad de viajes hechos por cada uno a esa hora.

![tipo de cliente por hora](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image1.png)

Recuerda ir guardando estas consultas, ya que las utilizaremos más adelante en nuestro dashboard de Google DataStudio.

### 4.6 Desglose de uso por día de la semana

Esta consulta es similar a la anterior. La única particularidad es que, en vez de extraer la hora del “starttime”, vamos a extraer el día de la semana.

Si revisaste [la documentación de Google](https://www.google.com/url?q=https://cloud.google.com/bigquery/docs/reference/standard-sql/timestamp_functions%23extract&sa=D&source=editors&ust=1671545727677555&usg=AOvVaw3TO8nIT9mcprGH3Hou2ntM) sobre la función EXTRACT te habrás dado cuenta de que, convenientemente, podemos extraer el DAYOFWEEK (día de la semana).

Construye la consulta para llegar a un resultado como este:

![Tipo de cliente por día de la semana](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image8.png)

¡Bien! Ya tenemos todas las métricas que mencionó la CEO en la reunión. Como buena analista de datos siempre es buena idea complementar con otras métricas que creas que puedan ser relevantes para el negocio, ¡así que anímate a crear más consultas!

## Paso 5: Comparte

Nuestras consultas tienen información valiosa, pero no son tan simples de ver para alguien que no es técnico. Además, todos los resultados están en formato tablas que no nos dicen mucho en un primer vistazo.

Debemos disponibilizar esta información en un formato que la CEO y cualquier persona de la organización pueda ver y entender.

Para esto vamos a ocupar una herramienta de visualización que, si hiciste el hacker edition del proyecto anterior, ya debes conocer: Google DataStudio.

Esta herramienta recibe datos de múltiples fuentes: CSVs, spreadsheets, consultas de BigQuery y muchas otras. Nosotros vamos a entregarle las consultas que fuimos creando y guardando para generar nuestras visualizaciones con esa información.

### 5.1 Importar las consultas a DataStudio

Para crear un reporte en DataStudio debes ir a [www.datastudio.google.com](https://www.google.com/url?q=http://www.datastudio.google.com&sa=D&source=editors&ust=1671545727678796&usg=AOvVaw0b9j0dBxQYr1i-f_uk3fsB) y crear un informe vacío.

![Informe Vacío](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image26.png)

Una vez dentro, lo primero que nos preguntará DataStudio es que importemos nuestros datos. Como puedes ver hay muchísimas formas de traer datos a DataStudio. Nosotros vamos a ocupar nuestras consultas de BigQuery.

![Seleccionar bigquey](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image27.png)

Para que DataStudio tenga acceso a tus proyectos debes darle a “Autorizar”.

Cuando hayas autorizado, se te desplegarán varias opciones. Pero la que nos interesa es “Consulta Personalizada”, ya que nos va a permitir ir copiando y pegando nuestras consultas para acceder a la data.

![Escribir la consulta](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image18.png)

Por ejemplo, en la imagen puedes ver la consulta que generamos en el paso 4.2. Presiona “Añadir” y dale “Añadir al informe” en el cuadro de diálogo que te aparezca.

¡Logramos cargar nuestra primera consulta! Puedes verificar que está correcta al ver el panel de la derecha, donde aparecen los nombres de las columnas de la tabla que generamos.

![Editar fuente de datos](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image20.png)

En cualquier momento puedes editar tu fuente de datos. Una buena práctica es ponerle un nombre representativo.

![Titulo editado](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image30.png)

Ahora que sabes cómo importar tus consultas, agregar todas las restantes.

![Todos los títulos editados](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image29.png)

### 5.2 Creando un gráfico de barras

En DataStudio, crear gráficos es muy sencillo. Primero debemos Añadir el gráfico que queremos ocupar. Para practicar, vamos a crear el gráfico de barras para la consulta de cantidad de viajes por hora del día.

![Añadir un gráfico de barras](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image10.png)

DataStudio automáticamente genera un gráfico que cree que nos puede interesar. Probablemente, no es el que necesitamos, por lo que cambiamos la fuente de datos a la que queremos.

![Seleccionar la fuente de datos correcta](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image31.png)

Ya nos estamos acercando. En la barra de la derecha, la “métrica” es el valor que queremos que cuente el eje Y. En nuestro caso, nos gustaría que muestre la cantidad de viajes “num_trips”.

![Elegir la métrica correcta](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image15.png)

Y la dimensión determina el eje X. Para nuestro gráfico queremos que muestre las distintas horas del día.

![Seleccionar dimensión](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image17.png)

Si te fijas bien, no aparecen todas las horas del día. Esto es porque, por defecto, DataStudio genera gráficos de barra con un máximo de 10 barras. Esto se puede cambiar en la pestaña de “Estilo”.

![Sumar barras](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image13.png)

Ya estamos casi listas. Solo falta ordenar las barras según el número de la hora.

![Orden](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image5.png)

El gráfico resultante nos muestra todos los viajes totales para cada hora. Pero algo muy interesante sería ver el comportamiento de cada cliente, por lo que tenemos que agregar dimensión de desglose.

![Tipo de usuario](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image2.png)

¡Y ya estamos! ¿Puedes ver en que horarios los clientes tipo “Subscriber” ocupan más las bicicletas? ¿Y cómo contrasta esto con el uso que le dan los “Customers”?

![Gráfico de barras](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image16.png)

Recuerda ir anotando todas tus observaciones para compartirlas luego con tu CEO.

### 5.3 Creando una serie temporal

Para mostrar la evolución de una variable en el tiempo, es recomendable utilizar un gráfico de línea. Su creación es muy similar al caso del gráfico de barras.

![Añadir una serie temporal](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image9.png)

Recuerda escoger la fuente de datos correcta. En este caso queremos graficar la cantidad de viajes a lo largo del tiempo, con la consulta que creamos en el punto 4.3.

Para este gráfico la dimensión (eje X) son las fechas y la métrica es la suma de los viajes.

![Resultado serie temporal](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image19.png)

Jugando con la pestaña “Estilo” podemos llegar a una versión más limpia que siga las recomendaciones de data storytelling que aprendimos en el proyecto anterior, y agregar una línea de tendencia.

![Serie temporal con data storytelling](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image4.png)

Con este conocimiento sobre gráficos de barra y series temporales termina de armar tu dashboard. Recuerda seguir las indicaciones en cuantos diseño y estructura de los proyectos anteriores. Menos es más.

Además, si sientes que podría sumar valor a tu dashboard, agrupar los datos por más características, como por ejemplo género, edad u otro campo, siempre puedes volver a tus consultas y ocupar GROUP BY para agrupar más campos.

## Paso 6: Actúa

Con tu dashboard construido, puedes pasar a dejarle las recomendaciones a tu CEO. Vuelve al paso 1 para asegurarte de que tomaste en cuenta todos los puntos que misma definiste como importantes para este proyecto.

# Hacker edition

¿Quieres aprender más sobre SQL? Esta sección es para ti.

Si te das cuenta, gran parte de la información que ocupaste para tu reporte viene de una sola tabla: la tabla de viajes. Pero en la otra tabla del dataset, “citibike_stations” hay información muy útil para complementar tu análisis. ¿Cómo creerías que se sorprendería tu CEO si le muestras un gráfico como este, que muestra un mapa de calor de dónde se comenzaron los viajes?

![Mapa de calor](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image7.png)

Esto se puede lograr gracias a los campos “Latitud” y “Longitud” de la tabla “citibike_stations”. Sin embargo, esa tabla no tiene la información de la cantidad de viajes que comenzaron en cada estación. Es por esto que tenemos que UNIR ambas tablas para lograr el resultado esperado.

En SQL se utiliza la sentencia JOIN para juntar dos tablas que tengan un campo en común. En nuestro dataset, ambas tablas comparten el campo “station_id” (en el caso de la tabla de estaciones) y “start_station_id” (para la tabla de viajes).

Si no sabes cómo hacer un JOIN en SQL, te recomendamos ver [la sección de hacker edition](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Combinando-dos-tablas-con-JOIN_su2w9?playModeWorkflowId%3D%23_luxSy&sa=D&source=editors&ust=1671545727684630&usg=AOvVaw0V6SrnsdrOfafFXzieyKTw) del mini curso de SQL.

Para aprender a hacer JOINS, vamos por parte. Primero intentemos unir ambas tablas y mostrar todos los campos:

```SQL
SELECT
  *
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips` AS trips
JOIN
  `bigquery-public-data.new_york_citibike.citibike_stations`  AS stations
ON
  trips.start_station_id = stations.station_id
WHERE
  trips.start_station_id IS  NOT  NULL
LIMIT
  100
```

Esta consulta nos retorna todos los campos de ambas tablas, en donde la tabla “trips” haya encontrado a algún par en la tabla “stations”, que compartan su “station_id”.

> 🧐 Importante agregar el “LIMIT 100”, porque de otra forma el resultado sería gigantesco. Piensa que cada fila de la tabla “trips” busca todas las ocurrencias en la tabla “stations” que tengan el mismo id de estación. Esto hace un efecto multiplicador que deriva en un resultado de más de 40 millones de filas.

Ahora que ya sabemos como juntar las dos tablas, quedémonos solo con la información que nos interesa: la latitud y la longitud. DataStudio recibe este parámetro como una cadena de caracteres del tipo “latitud,longitud”. Como tenemos esos dos campos separados, vamos a tener que unirlos de alguna forma. Para eso es útil la función CONCAT que, al igual que en spreadsheet, junta los campos que le pases en un solo campo.

```SQL
SELECT
  CONCAT(stations.latitude, ',', stations.longitude)  AS lat_long,
  COUNT(*) AS num_trips
FROM
  `bigquery-public-data.new_york_citibike.citibike_trips` AS trips
JOIN
  `bigquery-public-data.new_york_citibike.citibike_stations` AS stations
ON
  trips.start_station_id = stations.station_id
WHERE
  trips.start_station_id IS  NOT  NULL
LIMIT
  100
```

Por último, nos gustaría contar cuantos viajes ha tenido cada “lat_long” ¿Recuerdas cómo logramos eso? Inténtalo tu misma usando una combinación de COUNT() y GROUP BY. Deberías llegar a una tabla como esta:

![Cantidad de viajes por latlong](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image28.png)

Con esta tabla ya podemos llevar la consulta a nuestro DataStudio. Ahí elegimos una visualización de la categoría “Google Maps” que se llama “Mapa de Calor”

![Seleccionar mapa de calor](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-4-cicloviajes/images/image21.png)

Luego modifica tu gráfico utilizando la pestaña “Estilo”. Utiliza esta nueva información para complementar las recomendaciones que entregarás a tu CEO.
