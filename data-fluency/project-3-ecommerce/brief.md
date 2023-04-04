# Introducción

En este proyecto realizarás un análisis descriptivo que permitirá mostrar a la CEO de una empresa de comercio online, ecommerce, qué tan bien o mal están yendo las ventas de la compañía. Ejecutarás una **segmentación de clientes aplicando la metodología RFM**, para que el negocio enfoque sus esfuerzos de venta y desarrolle estrategias distintas para cada segmento. Adicionalmente, comprenderás la importancia de la limpieza y el tratamiento de datos previo a la realización de cualquier análisis. Al tratarse de tu último proyecto base en este programa, refinarás tu habilidad de comunicar tus resultados de manera clara y poderosa a través del data storytelling.

# La situación

Eres una analista de datos en una consultora de transformación digital que busca apoyar a sus clientes para mejorar sus negocios a través de la interpretación y el análisis de sus datos. Su servicio más contratado es el de Business Intelligence, cuyo objetivo es integrar, visualizar y analizar grandes volúmenes de datos históricos para apoyar la toma de decisiones estratégicas.

Tu líder te invita a una reunión con un cliente nuevo, UK Merch; una empresa joven, con solo 10 meses de antigüedad en Reino Unido. La empresa se dedica a la venta de ropa al por mayor (20 artículos o más) ofreciendo un precio más competitivo que el retail convencional. Sus clientes son emprendimientos más pequeños que se abastecen comprando a UK Merch.

En la reunión conoces a Federico, Gerente de Administración y Finanzas de la compañía, y a Alejandra, la CEO, *Chief Executive Officer*. Federico relata cómo, en los primeros meses, las ventas iban bien y sus precios eran competitivos; así que decidieron expandir su operación a otros países en Europa.

Alejandra complementa, “Si bien comenzaron a llegar nuevos clientes, desconocemos si fue una decisión acertada. No estamos seguros de dónde provienen nuestros mejores clientes, nos ha faltado rigor en la recolección de datos y no sabemos cómo enfocar el trabajo de nuestro equipo”. Federico añade, "Lo más grave, es que no tenemos foco. Estamos apuntando para todos lados sin saber si ese esfuerzo está trayendo resultados."

Ambos callan y se mantienen atentos mientras tu líder dispara algunas preguntas para hacerse una idea del estado financiero del negocio.

“¿Cuánto venden en promedio al mes? ¿Cuántas ventas tienen en cada mes? ¿Cuál es el mes en que más venden? ¿Quiénes son sus clientes más importantes? ¿Cuál es el monto promedio que gastan sus clientes? ¿Qué porcentaje de sus clientes ha vuelto a comprarles? ¿Cómo se desglosa esta información según los países en donde venden?”

Mientras tomas nota de estas preguntas de exploración, ves cómo Federico y Alejandra se miran confundidos, pues no saben cómo responder ninguna de estas preguntas.

“Si no conocen sus ventas ni el perfil de sus clientes, ¿con qué criterios están enfocando sus esfuerzos de mercadeo? ¿A quién apuntan sus esfuerzos publicitarios? ¿Cuál es su estrategia de venta?” Añade tu líder.

“Nuestro mensaje y estrategia es la misma para todos nuestros clientes” responde la CEO, reconociendo de antemano que no es la mejor respuesta.

Al salir de la reunión acompañas a tu líder por el pasillo mientras conversan. “Aunque hay mucho por hacer, este es un tipo de cliente común. Tiene un buen modelo de negocio entre manos, pero desconoce si la estrategia que está utilizando es la correcta. Además, claramente no están tomando decisiones basadas en datos. Alejandra me compartió un **set de datos de las ventas del año pasado por factura**. Parece que los datos **no están completos**, pero es lo único que tenemos para comenzar a trabajar.”

“Lo primero será revisar la calidad de los datos. Intuyo que no han sido muy rigurosos en la recolección de datos, por lo que primero tendrás que **revisar datos faltantes, datos duplicados donde no correspondan (por ejemplo, que hayan ingresado dos veces la misma boleta) y valores que no tengan sentido, como números negativos en los precios o cantidades de los artículos.** Luego tenemos que hacernos una idea general de la salud del negocio. Para eso tendrás que construir un **reporte que incluya tablas y gráficos que resuman las métricas claves de negocio**, como las que les pregunté en la reunión, pero también me gustaría que pusieras de tu propia cosecha. Investiga y agrega las métricas y gráficos que tú creas convenientes para resumir los datos.”

“Creo que el aporte más significativo que podemos hacer a UK Merch es ayudarlas a segmentar a sus clientes para poder tomar decisiones estratégicas entendiendo a su público objetivo. ¿Has escuchado sobre el principio de Pareto?". Al ver tu cara de confusión procede a explicar: "Pareto postula que el 80% de los resultados provienen del 20% de las causas. Viene de un economista italiano, Vilfredo Pareto, que mostró que aproximadamente el 80% de la tierra en Italia era propiedad del 20% de la población. Aplicado a los negocios, este principio nos dice que usualmente el 80% de las ventas provienen del 20% de los clientes. En el caso de UK Merch, hacer este análisis del 80/20 puede ser de mucha utilidad porque intuyo que están malgastando sus recursos. Podrían enfocar su comunicación de forma mucho más eficiente, dirigida a un público acotado de buenos clientes. Para esto sugiero que hagamos **una segmentación basada en Recencia, Frecuencia y Monto (RFM).** De esta forma podremos recomendar a UK Merch estrategias concretas para atender a sus mejores clientes.”

Con este contexto, muchas preguntas, pero también muchas ganas de aprender, comienzas tu trabajo. Además, sabes que en tu próxima reunión con tu líder vas a tener que presentarle todo tu análisis, y quieres hacerlo de manera profesional, para que siga confiándote tareas tan retadoras y también para aportar valor a UK Merch. Has escuchado un poco acerca de data storytelling y decides investigar un poco más al respecto para aplicarlo en tu presentación.
  
# Entregable

Para considerar completado este proyecto deberás entregar, por medio de la [plataforma de aprendizaje](plus.laboratoria.la), lo siguiente:
  
1. Una hoja de cálculo que contenga, como mínimo, lo siguiente:

   - Fuente de datos pre-procesada (datos limpios).
   - Una pestaña de reporte con tablas y gráficos de las métricas principales del negocio.
   - Una segmentación de clientes usando la metodología RFM.
   - Todos los datos, tablas y visualizaciones adicionales que te sumen en tu análisis.
   - **Importante**: Si hiciste el desafío del Hacker edition, comparte el link de tu dashboard en DataStudio.

2. **Recomendado:** Además, de manera opcional, grabarás un video de máximo 5 minutos simulando una reunión con tu líder, en donde le expliques tus conclusiones y recomendaciones utilizando data storytelling (¡en la guía de resolución te contamos más al respecto!) Para presentar, apóyate en tu spreadsheet o arma una presentación en Google Slides. Para grabarte, te recomendamos la plataforma Loom. En particular, tu video debe presentar un diagnóstico de las ventas del negocio y recomendaciones concretas con base en tu análisis.

> 👩‍💻 Recuerda que la lifeskill que desarrollaremos en este proyecto es la comunicación a través del datastorytelling, por lo que te recomendamos desafiarte haciendo la presentación y video.

# Objetivos de aprendizaje

Al resolver este proyecto serás capaz de:

- **Recolección y Preparación**
  - **Preprocesar datos en hojas de cálculo**: identificar datos duplicados, en blanco o fuera de su dominio (por ejemplo, valores negativos cuando no corresponde) con el fin de preparar tus datos para su posterior análisis.
  - **Manejar funciones lógicas para probar diferentes condiciones**: manipular datos según criterios con las funciones IF e IFS.

- **Análisis y descripción**

  - **Utilizar funciones avanzadas para conectar conjuntos de datos con Vlookup**: obtener un valor de otra tabla a través de la función Vlookup.
  - **Segmentar clientes utilizando el modelo RFM**: comprender la regla de Pareto (80/20), identificando clientes clave de negocio con el fin de enfocar los esfuerzos y obtener el mayor retorno.

- **Comunicación de hallazgos**

  - **Visualizar datos en hojas de cálculo**: confeccionar gráficas de línea y barra para visualizar información con el fin de resumir hallazgos en un Dashboard, encontrar patrones o comparar distintas series de datos.
  - **Comunicar ideas de manera efectiva utilizando técnicas de Data Storytelling**: organizar tu presentación tomando en cuenta a tu audiencia, el contexto y el objetivo ofreciendo respuestas a una serie de interrogantes del negocio y/o sugiriendo cursos de acción que impactan en el mismo.

# Consideraciones generales

- El trabajo completo de tu análisis debe estar desarrollado en Google Sheets y al finalizar es importante que compartas el link público con tu trabajo.
- Este proyecto requiere que cada estudiante entregue su propio informe. Sin embargo, en Laboratoria fomentamos el trabajo colaborativo entre pares para que aprendan unas de otras, así que no dudes en colaborar con tus compañeras para resolver este desafío.
