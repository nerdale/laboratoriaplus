# Introducción

En este proyecto opcional, analizarás el uso que le dan los clientes a un servicio de bicicletas compartidas en la ciudad de Nueva York. Comenzarás a trabajar con bases de datos de mayor tamaño, por lo que aprenderás a interactuar con un motor de bases de datos (Google BigQuery) a través del lenguaje SQL, ya que resulta impráctico trabajar este tipo de bases de datos con hojas de cálculo. Además, ocuparás una herramienta de visualización de datos (Google DataStudio) que te permitirá crear dashboards interactivos.

# La situación

Es mayo del 2018. Eres una analista de datos trabajando en el equipo de datos de una empresa que brinda un servicio de bicicletas compartidas en la ciudad de Nueva York.

La empresa ha contratado una nueva CEO, Julia Jiménez, y como parte de su proceso de onboarding solicitó una reunión con el equipo de analítica de datos. Siendo solo 3 personas en el equipo, tienes el privilegio de conocer a la nueva CEO y responder sus preguntas:

“Háblenme acerca de los datos que tenemos. ¿Qué tan antiguos son? ¿Cuáles son sus características?” comienza preguntando.

“Tenemos casi sesenta millones de registros de viajes de las diez mil bicicletas que tenemos disponibles en cerca de seiscientas estaciones distribuidas entre Manhattan, Brooklyn, Queens y Jersey City. Esto incluye todos los viajes que se han realizado desde que comenzó el programa en 2013” responde tu líder de equipo.

Tú complementas con aspectos técnicos que consideras importantes: “la data ha sido procesada para dejar fuera viajes que duren menos de 60 segundos, puesto que los consideramos ‘partidas falsas’, donde el usuario probablemente no logró realizar el viaje. Adicionalmente, nos hemos dado cuenta de que hay un error con nuestros scripts de recolección de datos, puesto que hay varios registros que están vacíos o con valores null”.

“Para cada viaje, contamos con características de la estación de inicio y término, como su nombre, coordenadas y el tiempo de duración del viaje. Contamos con algunas características adicionales particulares al usuario como género y tipo de membresía.” Agrega tu líder de equipo.

“Eso último me interesa” comenta la CEO “¿Cuáles son los distintos tipos de membresía que tenemos?”

Con seguridad le compartes: “Tenemos dos tipos de usuarios. Los subscribers o suscriptores, que compran una membresía anual del programa; y los customers o clientes, que pagan un pase diario o semanal para ocupar las bicicletas”.

“¿Y entendemos cuáles son sus perfiles? ¿Qué tipo de usuarios son los que prefieren la membresía anual versus el pago por uso limitado?” indaga la CEO.

“La verdad es que solo contamos con los datos del género y edad de los clientes que optan por compartir su información” añade tu líder, sabiendo que no es una respuesta suficiente.

“En ese caso, lo primero que vamos a necesitar es armar un perfil de cada tipo de usuario. Para comenzar me gustaría saber: ¿Quién es? ¿Para qué utiliza nuestro servicio? ¿De qué forma le saca provecho a las bicicletas? Y más importante aún, ¿Qué más podríamos ofrecerle o cómo podríamos ajustar nuestro servicio para resolver de mejor manera sus necesidades?” Hizo una pausa y les preguntó directamente. “¿Creen que podamos tener respuestas a estas preguntas con los datos que contamos actualmente?”

Todas en la sala asintieron.

Tu nueva CEO agrega; “Genial. Entonces por favor ayúdenme con un dashboard que muestre los aspectos más relevantes de la data para visualizar esto.” Contando con los dedos de su mano, empieza a enumerar ejemplos: “Total de viajes, crecimiento de los viajes a lo largo del tiempo, duración promedio de los viajes, desglose de uso según horario y día de la semana, y todo lo que se les ocurra que me pueda ayudar a entender mejor el estado del arte. Lo más crucial es conocer las características distintivas de cada perfil de usuario según su uso. No olviden agregar sus recomendaciones según lo que aprendan. Gracias y manos a la obra equipo”.

# Entregable

Para que este proyecto optativo se dé por completado debes entregar a través de tu plataforma de aprendizaje, un dashboard de [Google Data Studio](https://www.google.com/url?q=https://support.google.com/datastudio/answer/6283323?hl%3Den&sa=D&source=editors&ust=1671544629053894&usg=AOvVaw15zJDyFRvgwoWJvePX6P9A)  que detalle las métricas más importantes de uso, tanto las que enumera tu CEO como otras que consideres relevantes para entender el negocio y responder las preguntas de tu CEO.

Adicionalmente, te recomendamos agregar un video de máximo 5 minutos en donde presentes tus hallazgos utilizando data storytelling, tal como aprendiste en el proyecto anterior. Resalta los aspectos más importantes de la data, los perfiles que hayas encontrado según el uso que le dan a las bicicletas, los usuarios y las recomendaciones que creas que puedan ser relevantes para tu CEO.

# Objetivos de aprendizaje

Al resolver este proyecto serás capaz de:

- **Preparar**

    1. Distinguir entre los distintos tipos de datos de los campos de una tabla, tales como DATETIME, BOOLEAN, INTEGER, STRING.
    2. Manipular datos de fuentes de datos públicas utilizando consultas de SQL.
    3. Usar la función CAST para transformar el tipo de dato de un campo en otro.

- **Analizar**

    1. Utilizar comandos básicos como SELECT y DISTINCT para llamar campos de datos específicos de una tabla.
    2. Filtrar datos desagrupados que cumplan una condición específica utilizando el comando WHERE.
    3. Emplear el comando GROUP BY para agrupar datos según uno o más campos.
    4. Usa fórmulas de agregación como COUNT, MIN, MAX y AVG para calcular estadísticas sobre agrupaciones de datos.

- **Comunicación de hallazgos**

    1. Diseñar y desarrollar dashboards en línea en herramientas de visualización.

# Consideraciones generales

- Tu reporte, con las visualizaciones, el análisis y las conclusiones necesarias, debe estar desplegado en la web. (por ejemplo, a través de un link de Data Studio)
- Para construir el reporte utilizarás la información pública del programa [Citi Bike New York City](https://www.google.com/url?q=https://www.citibikenyc.com/homepage&sa=D&source=editors&ust=1671544629056799&usg=AOvVaw2gNmHmu_ZiMjHPKOQQVUJ9), el programa de bicicletas compartidas más grande de los Estados Unidos. Este conjunto de datos público está alojado en Google BigQuery y puedes acceder a él por medio del siguiente enlace: [NYC Citi Bike Trips](https://www.google.com/url?q=https://console.cloud.google.com/marketplace/product/city-of-new-york/nyc-citi-bike?project%3Ddata-sandbox-319716%26folder%3D%26organizationId%3D&sa=D&source=editors&ust=1671544629057152&usg=AOvVaw2LHUBt6_4yx1dUypynKsps). Para los propósitos de este proyecto, este conjunto de datos es apropiado y te permitirá construir el reporte solicitado.
- Dado que en este proyecto estarás trabajando en una herramienta y lenguaje completamente nuevos, hemos preparado [este mini curso](https://www.google.com/url?q=https://coda.io/d/Videos-BigQuery-Cicloviajes_dmIxCiY2-NQ/Introduccion_su3UO?playModeWorkflowId%3D%23_luO8s&sa=D&source=editors&ust=1671544629058089&usg=AOvVaw2i2TVxT3KKKxq--V6-nIxR) (1 hr y 15 min de videos) en donde puedes conocer lo básico de SQL y BigQuery.
