# Introducción COVER
En este proyecto realizarás un análisis descriptivo que permitirá mostrar a la CEO de una empresa de comercio online, ecommerce, qué tan bien o mal están yendo las ventas de la compañía. Ejecutarás una segmentación de clientes aplicando la metodología RFM, para que el negocio enfoque sus esfuerzos de venta y desarrolle estrategias distintas para cada segmento.

## Contexto

En este proyecto simularás ser parte del equipo de una consultora estratégica enfocada en Business Intelligence. Utilizando datos históricos de una empresa de ventas al por mayor deberás generar un análisis completo que incluya:
  
- **Pre-procesamiento de los datos**: revisar la calidad de la base de datos, eliminar datos duplicados que no tengan sentido, encontrar datos faltantes, reemplazarlos o eliminarlos, y buscar datos que no correspondan (por ejemplo, números negativos en columnas que generalmente son números positivos). Recuerda que el preprocesamiento de los datos es un paso fundamental y básico de todo análisis de datos.
- **Análisis exploratorio**: a través de tablas dinámicas, fórmulas y gráficos deberás hacerte una idea de la salud financiera del negocio.
- **Segmentación de clientes**: finalmente, tendrás que hacer una segmentación de los clientes basándote en tres características: Recencia, Frecuencia y Monto. Es un análisis integral que te permitirá hacer recomendaciones a UK Merch para que aprovechen de mejor manera sus recursos.
  
> Recuerda que las empresas capaces de utilizar los datos de los clientes para comprender mejor cómo piensan, sienten y toman decisiones de compra, tienen una ventaja.

# Desarrollo

## Paso 1: Pregunta

Como ya hemos visto, este paso es fundamental para realizar el análisis específico y útil que el cliente necesita. En este caso te invitamos a releer el brief para encontrar las preguntas clave. Recuerda que en una situación real deberás descubrir por ti misma los cuestionamientos que quieres resolver y tener preparadas preguntas relevantes para encontrar aquello que debes descubrir.. En el caso presentado en el brief, varias preguntas que podemos tomar para definir métricas que queremos calcular ya fueron formuladas por tu líder.

Luego de releer el brief, es una buena práctica observar la situación completa desde una perspectiva más amplia. ¿Cuál es el problema que enfrenta UK Merch? ¿Qué información falta para resolver ese problema? ¿Es un problema evidente? ¿Cuál es la raíz del problema? ¿Qué expectativa tiene UK Merch y/o mi líder sobre mi análisis?

Asegúrate de tener anotadas las métricas que debe incluir tu análisis (must-have), aquellas que serían un buen complemento, pero no son indispensables (nice-to-have) y aquellas que definitivamente no vas a tomar en cuenta porque te podrían desenfocar (won’t-have).

Entender el contexto del análisis es parte del proyecto y te ayudará a entender qué analizar, qué investigar y además sacar conclusiones valiosas para el negocio, así validaremos el objetivo de este proyecto.

### Close Question 
¿Cuál es el objetivo del proyecto? C
Analizar si los datos recibidos están correctos
Crear campañas de marketing
Entender y segmentar los perfiles de clientes para direccionar esfuerzos

### Validación
¡Súper! Ahora que conoces el objetivo de este proyecto y el objetivo de este análisis, qué es entender y segmentar los perfiles de clientes para direccionar esfuerzos, podemos continuar con la guía.


## Paso 2: Prepara

Ahora que tenemos claro el objetivo de nuestro análisis, debemos salir a buscar los datos que necesitamos. En una consultoría de Business Intelligence común deberías buscar al cliente, consultar por los datos que tiene disponibles, verificar que los datos contienen la información que necesitas y luego procesarlos. En este caso, UK Merch no ha sido tan prolijo y solo cuenta con una base de datos que ya entregó a tu líder y que, muy probablemente, contiene errores que deberás corregir en el paso 3.

Por ahora comencemos por importar la base de datos a tu hoja de cálculo y entender la estructura de la misma y sus campos relevantes. Fíjate que el dataset cuenta con un diccionario que describe el tipo de dato de cada columna. Revisa bien el diccionario y asegúrate de dominar lo que significa cada variable.

> ⚠️ **Importante**: Muchas veces al importar fuentes de datos externas a Google Sheets se generan errores de transformación. Por ejemplo, un campo de fecha o de número no es leído como tal, sino que como texto. Esto puede perjudicar nuestro análisis, ya que las fórmulas que utilizamos muchas veces dependen de que las celdas estén formateadas correctamente. El origen de muchos de estos errores es la diferencia de unidades, formatos y separadores en distintas regiones. Estas diferencias confunden a Google Sheets. Por ejemplo, en Estados Unidos las fechas se escriben en formato MM/DD/AAAA y los separadores de miles son comas y no puntos (1,000,000 vs 1.000.000). Si tuviste problemas al importar el dataset te recomendamos cambiar la configuración regional a Estados Unidos (o viceversa). Para esto debes ir a Archivo -> Configuración, hacer el cambio y refrescar la página.

![image11](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image11.png)

Comprendamos el primer registro de nuestra base de datos: el cliente 15528 de United Kingdom hizo una compra el 30 de marzo del 2021 por un monto de 229.33 libras esterlinas que incluye 123 productos, y que generó la factura cuyo número es el 548370.

Tenemos 25953 registros como este para trabajar.

Ahora que tenemos nuestros datos importados y conocemos a modo general la estructura de los datos, comencemos con la limpieza (o preprocesamiento) de los datos.

## Paso 3: Procesa

### 3.1 Documenta tu preprocesamiento

En el proyecto 2 reconociste la importancia de mantener la base de datos original, así que recuerda hacer una copia de la misma para comenzar a trabajar en la limpieza de los datos. Puedes hacerlo copiando y pegando o con la ayuda de la función QUERY o IMPORTRANGE.

Es esencial que definas cómo documentar tus pasos, ya que durante el proceso de limpieza tomarás varias decisiones que pueden cambiar tu resultado final. Por ejemplo, cuando tenemos un ID nulo en la variable Customer ID, ¿deberíamos eliminarlo? Tu decisión debe quedar documentada para que puedas rastrearla posteriormente.

Esta y otras preguntas que te harás a lo largo del proceso de limpieza deben documentarse por dos razones. Primero, te permite trazar lo que has hecho sobre la base de datos original y cualquier otra persona externa a tu análisis puede ver los supuestos que usaste en tu limpieza. Además, te da una base de recomendaciones que puedes entregar a tu cliente para que pueda recolectar datos de mejor forma en el futuro. Te invitamos a crear una nueva pestaña titulada "Documentación" para registrar todos los pasos y decisiones que tomaste para limpiar la base de datos.

Ahora sí, vamos a revisar la información.

### 3.2 Detección de registros nulos o vacíos

Después de revisar con mayor detalle las variables que tienes en el dataset, es posible que te encuentres con ciertos registros vacíos o nulos. Estos datos pueden ensuciar tu análisis. Para encontrarlos, selecciona cada columna y usa la opción “**Filtros**” en cada una de ellas, dejando solo los valores vacíos (o Blanks).

![image18.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image18.png)

👩‍💻 Otras formas rápidas de diagnosticar si el dataset tiene valores vacíos son: usar la función “=CONTAR.BLANCO()” o "=COUNTBLANK()", esta función recorre cada valor del rango y cuenta la cantidad de registros vacíos que encuentra. También puedes usar tablas dinámicas (pivot tables) como aprendimos en el proyecto 2.

Revisa columna por columna con la función de filtro o aplica la fórmula que cuenta los blancos en cada columna para encontrar valores vacíos. Luego reflexiona: esos valores vacíos que encontraste, ¿Afectarán a tu análisis? ¿Es mejor dejarlos o borrarlos? **Esta decisión depende de cada situación**. Si para este proyecto es de suma importancia que esos valores no estén vacíos (porque de otra forma ensuciarían el resultado) entonces puedes borrar esos registros (toda la fila). Si no afectan el análisis, los te recomendamos dejarlos para no alterar la base de datos original tanto.

### 3.3 Detección y eliminación de duplicados

Algunas veces los usuarios cometen errores al registrar la información. Un error muy común es que un registro esté duplicado. Hay que entender bien cuando un dato duplicado es erróneo. Para nuestro caso, si encontramos más de una fila que tenga el mismo monto o la misma cantidad, no sería un error. Solo significaría que en momentos distintos, usuarios distintos han comprado la misma cantidad o han gastado el mismo monto. **Lo que no debería suceder en este caso es que tengamos dos veces la misma factura**. Cada factura tiene un valor único, significa que si encontramos otra fila con el mismo número de factura deberíamos borrar el duplicado.

Para eliminar duplicados puedes ocupar la función Quitar duplicados (Datos > Borrado de datos > Quitar duplicados). A esta herramienta debemos decirle que columnas queremos que compare entre las filas. Como vimos anteriormente, queremos eliminar las filas que compartan valores en la columna de número de factura.

![image37.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image37.jpg)

### 3.4 Detección y eliminación de cantidades negativas

Si revisaste visualmente algunas columnas habrás notado que tanto en la columna de Monto como la de Cantidad hay valores negativos.

> 👩‍💻 **Pro tip**: Ocupa la función “**Estadísticas de columna**” en la pestaña Datos para que Google Sheets te muestre un resumen de los datos de cada columna. Ahí puedes observar la frecuencia de aparición de cada dato, cantidad de celdas vacías, máximos, mínimos y más. Ocupa esta funcionalidad para echar un vistazo rápido a cada columna y **asegurarte de que los valores están dentro de parámetros normales**.

**Estos valores negativos no necesariamente están incorrectos**. De hecho, si revisaste con atención el diccionario de datos del dataset te habrás dado cuenta de que aquellas facturas que comienzan con la letra C corresponden a devoluciones, por lo que podríamos asumir que esos valores negativos son normales (una venta es positiva, una devolución negativa).

Como solo queremos analizar las ventas del negocio (y no las devoluciones), deberíamos eliminar esos valores de nuestro dataset. Para hacerlo puedes usar filtros, en particular la opción "**Filtrar por condición**", y luego eliminar las filas que tengan valores negativos.

> 👀 ¿Se te queda pegado el navegador? Esto es común. Como estamos trabajando con una fuente de datos grande (más de 20.000 registros) es común que esto suceda. En futuros proyectos aprenderemos herramientas para manejar grandes volúmenes de datos en un instante.

¿Se te ocurren algunas otras validaciones que podríamos hacer con este dataset? Coméntalo con tus compañeras en Slack.

A veces es necesario limpiar la base de datos para que solo se consideren los registros relevantes para el análisis. Echemos un vistazo a lo que hemos visto hasta ahora.

### Close Question 
¿Cuántos registros hay en la base cruda? A
25953
25956
25980

¿Cuántos registros hay en la base limpia? A
Aproximadamente 18536
Aproximadamente 15880
Aproximadamente 20450

### Validación
¡Súper! Ya tenemos una base limpia y documentada, por lo que podemos continuar con nuestro análisis y si en el futuro necesitas rehacer este mismo estudio, ya sabrás los pasos que seguiste y las decisiones que tomaste. Luego procedemos al siguiente paso.

## Paso 4: Analiza

### 4.1 Análisis exploratorio de los datos

¡Enhorabuena! Ya tienes limpio el dataset, sin embargo, todavía no estamos seguras de cómo se componen nuestros datos. Al ser más de 20.000 registros es difícil entenderlos simplemente mirándolos y viendo algunas filas. Se vuelve importante extraer información que pueda resumir los aspectos más claves de las variables para comprender por dónde se mueven. Para esto es útil hacer un análisis exploratorio.

Adicionalmente, en el brief, tu jefe comentó que parte de los entregables que le quieren dar a UK Merch es un entendimiento más completo de la salud de su negocio, por lo que puedes aprovechar este análisis exploratorio para responder algunas de las preguntas que tu jefe hizo a la empresa.

Primero comenzaremos revisando la cantidad de facturas que genera cada país.

#### 4.1.1 Análisis de número de facturas por país

Una variable interesante para analizar es la cantidad de facturas que emite cada país y el porcentaje de las facturas que cada uno representa. De esta forma podemos ver cuál es el país que genera más ventas (facturas).

![image7.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image7.png)

>⚠️ **Importante**: Como revisamos durante la documentación de tu limpieza de datos, cada decisión que tomes influirá en tus resultados, así que no te preocupes por encontrar exactamente los mismos números que se muestran en las imágenes; úsalos como un guía, pero no los consideres una solución.

Intenta generar una tabla como esta utilizando tablas dinámicas, y resumiendo la cantidad de facturas según cantidad y según porcentaje del total.

🤓 **Análisis** 🤓

Es evidente que los clientes de UK son aquellos que realizan la mayor cantidad de compras en el supermercado, dado que el negocio nació en ese país. Los siguientes 5 países con mayor cantidad de compras son Alemania, Francia, Irlanda, Bélgica y Holanda.

¿Por qué crees que estos países Europeos son los que más compran en UK Merch?

#### 4.1.2 Análisis del monto total por país

Podemos hacer algo similar, pero ahora tomando en cuenta la variable monto. Aquí podemos aprovechar de hacer un análisis un poco más profundo. Además del monto sumado y el porcentaje que cada país representa del total, sería interesante conocer el monto promedio, el monto mínimo y el monto máximo en cada caso.

![image23.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image23.png)

🤓 **Análisis** 🤓

En esta ocasión se puede observar que UK representa cerca de 82% del monto de las ventas, sin embargo, tenía casi el 90% de las transacciones. Esto quiere decir que existen países que en promedio gastan más por transacción en UK Merch. Esto se puede validar en la columna de “Monto Promedio” donde vemos que UK tiene uno de los promedios más bajos por transacción, mientras que Holanda y Australia tienen los promedios más altos.

Otro tema importante y que puede causar ruido es que tenemos transacciones cuyo monto es 0. Este es un punto que vale la pena levantar al cliente para entender más el contexto. Puede ser un error de digitación o puede ser que en algunos casos regalen la mercancía (quizás sin estar al tanto de ello).

> 👩‍💻 Puedes probar con otros campos calculados como la mediana (MEDIAN) o la desviación estándar (STDEV) y complementar tus conclusiones.

Una buena idea sería hacer este mismo análisis, pero ahora para la cantidad de productos de cada factura 🤓.

#### 4.1.3 Facturas generadas por mes

Una buena idea para complementar un análisis exploratorio de un dataset es agregando gráficos. Estos son muy útiles para identificar diferentes patrones de datos de una forma visual, o vislumbrar comportamientos atípicos o estacionales.

Para realizar análisis por mes, tendremos que hacer un procesamiento a la columna “Fecha de factura”. En esa columna se aloja la fecha de la factura pero con mucha información que no necesitamos. Para esto tenemos que crear una nueva columna "AÑO - MES" en donde nos gustaría que apareciera la fecha de la forma 2021-03 para cada fila.

La fórmula que nos puede ayudar a lograr esto es [TEXTO](https://support.google.com/docs/answer/3094139?hl%3Des-419). Esta función transforma un número o fecha en texto con un formato establecido. En la documentación puedes encontrar algunos ejemplos de transformación de fecha a texto. Intenta dar con una fórmula que te permita crear una columna “AÑO-MES” con formato AAAA-MM

> 👀 Es importante que la variable creada siga el orden "AÑO - MES", porque estamos creando una variable de texto y de esta manera al hacer un gráfico o tabla dinámica la información estará en el orden correcto.

![image9.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image9.png)

Con esta nueva columna ya podemos generar una tabla dinámica que nos cuente la cantidad de facturas en cada mes, para luego graficar esos valores:

![image57.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image57.png)

🤓 **Análisis** 🤓

No podemos asegurar que hay una estacionalidad dado que sólo tenemos un año de historia de datos. Pero algo que se aprecia es que en noviembre hay un crecimiento grande en las ventas, tal vez esto pueda deberse a las ventas pre fiestas navideñas, sin embargo vemos que existe una caída pronunciada en el mes de diciembre del 2021 😱.

¿Por qué crees que se da esta caída? ¿Será mismo una caída o hay algo en los datos? Revisa las fechas de las compras de diciembre del 2021 y tendrás tu respuesta 🧙‍♀️.

#### 4.1.4 Número de facturas UK vs extranjeros por mes

Dado que UK Merch abrió sus fronteras a otros países, sería una buena idea reportar como están yendo estas ventas y poder evidenciar si existe el mercado. Por lo que vamos a segmentar nuestros clientes en dos grupos: aquellos que pertenecen a UK y aquellos que no pertenecen a UK.

Para esto creamos una columna "¿Pertenece a UK?" y ocupamos la fórmula:

```SQL
=IF(PAIS="United Kingdom","SI","NO")
```

Lo que hace esta fórmula es evaluar la condición (primer argumento). Si esa condición es verdadera, entonces nos retorna el segundo argumento, si es falsa nos retorna el tercer argumento.

Por lo tanto, si en esta fórmula el país que estamos comparando es "United Kingdom" nos devuelve en la celda "SI", y "NO" en caso contrario.

![image20.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image20.png)

Con esta nueva variable podemos crear una tabla dinámica que cuente la cantidad de facturas para cada uno de los casos de la nueva columna "¿Pertenece a UK?". A diferencia de las otras tablas dinámicas que hemos armado, esta necesita que le digamos qué valores debe contar en las columnas:

![image42.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image42.png)

Con esta nueva tabla dinámica podemos generar una serie temporal que compare a ambos tipos de clientes:

![image28.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image28.png)

🤓 **Análisis** 🤓

Sin tomar en cuenta el mes atípico de diciembre 2021, podemos ver que ambos segmentos van creciendo.

¿Qué conclusión puedes sacar con respecto al mercado de clientes no-UK?

#### 4.1.5 Cantidad de clientes nuevos por mes

Ya vimos que noviembre fue un mes muy bueno para UK Merch. Se generaron muchas más facturas. Este aumento en venta se puede deber a que algunos pocos clientes hicieron muchas compras, o que una gran cantidad de clientes hicieron aumentar el volumen de compras. Para resolver esta duda, una buena idea es graficar mes a mes la cantidad de clientes únicos y ver si el aumento de las facturas está relacionado con el aumento de clientes únicos.

Nuevamente, puedes hacer una tabla dinámica que use como filas los meses-años y que el valor que calcule sea la cantidad de clientes. Esto se puede calcular ocupando la columna ID Cliente y haciendo un recuento único (COUNTUNIQUE) para que solo tome valores únicos.

> 🤔 ¿Qué pasa si no ocupamos esta función y hacemos un recuento simple (COUNTA)?

![image60.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image60.png)

Esta nueva tabla dinámica también la podemos graficar:

![image48.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image48.png)

🤓 **Análisis** 🤓

Viendo este nuevo gráfico, ¿el éxito de noviembre se debe a que unos pocos clientes hicieron muchas compras?, ¿o a que también creció el número de clientes que hicieron compras ese mes?

#### 4.1.6 Agrega otros indicadores y ordena la información

¡Hasta el momento has generado tablas y gráficos muy útiles! Ellos te han permitido entender de mejor manera como se comportaron las ventas del negocio el año pasado. Pero hay muchas otras métricas que puedes revisar, ¡anímate a complementar tu reporte! Algunas ideas:

- Analizar el monto total de venta por mes
- Tabular los clientes que más compras han realizado
- Graficar los clientes que más han gastado
- Analizar cómo se comporta el monto mes a mes en clientes UK y no-UK
- Lo mismo pero también para la cantidad de productos

¡Agrega las que a ti te parezcan útiles!

En esta fase vimos cómo hacer un análisis exploratorio de los datos para comprenderlos mejor, encontrar patrones y extraer ideas. Echemos un vistazo a lo que hemos visto hasta ahora.

### Close Question 
¿Qué país tiene el mayor porcentaje de facturas? A
United Kingdom
Germany
France

¿Qué país tiene el mayor monto promedio por cliente? B
United Kingdom
Singapore
USA

¿Cuál es el mes con mayor número de facturas? A
2021-11
2021-12
2020-12

¿Por qué en el siguiente gráfico vemos una caída en el número de facturas en diciembre de 2021? A
![grafico-facturas_01](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/validacionP3_01.png)
Porque la base de datos no contiene registros de ventas del mes completo de diciembre de 2021
Porque hubo una baja en las ventas de diciembre por alguna razón externa
No es posible decir lo que paso

### Open Question 
¿Qué conclusión puedes sacar con respecto al mercado de clientes no-UK?
![grafico-facturas_02](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/validacionP3_02.png)

Viendo este nuevo gráfico, ¿el éxito de noviembre se debe a que unos pocos clientes hicieron muchas compras?, ¿o a que también creció el número de clientes que hicieron compras ese mes?
![grafico-facturas_03](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-1-covid/images/validacionP3_03.png)

### Validación
¡Súper! Ahora que conocemos bien los datos y que hay un patrón de crecimiento en ambos mercados, vemos una gran diferencia en el volumen de ventas en los dos mercados, podemos pasar a la segmentación de clientes y entender quiénes son nuestros clientes, quién compra con frecuencia y quién lleva mucho tiempo sin comprar.

### 4.2 Segmentación de clientes

En el enunciado de proyecto habrás leído que tu jefe recomendó hacer una segmentación por Recencia, Frecuencia y Monto, o RFM por sus siglas. ¿Qué es esto 😕?

Esta metodología permite clasificar a los clientes en las tres variables mencionadas:

![image33](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image33.png)

- **Recencia**: Los clientes que han comprado recientemente tienen mayor tendencia a adquirir nuevos productos que aquellos que tienen tiempo sin hacer ninguna compra. Esta variable mide el tiempo que ha transcurrido desde la última compra. Para calcularla es necesario identificar la última compra que realizó el cliente y restarlo de la fecha de hoy. Esta puede estar en días, meses, etc.
- **Frecuencia**: Los clientes que han comprado repetidas veces al ser comparados con aquellos que no, son más propensos a seguir haciendo compras. Está variable se puede calcular como el número de visitas del cliente, número de meses distintos que visitó el cliente, número de productos que compró.
- **Monto**: Los clientes que en el pasado han sumado más dinero en todas sus compras, son mayoritariamente más propensos a seguir generando ingresos a una empresa. Para calcular esta variable, básicamente tendríamos que sumar todo el gasto del cliente en el periodo de análisis.

Una vez que tenemos calculadas las 3 variables para todos los clientes, los categorizamos de acuerdo al **cuartil** en que se encuentra cada cliente para cada variable. Es importante notar que este análisis se puede hacer por cuartiles, como también por quintiles, tercios, percentiles, o la división que prefiera la analista de datos. Mientras más divisiones, más fino el análisis.

> 🤔 [¿Qué es un cuartil?](https://www.loom.com/share/6d80794b67d14d048dfbf112e67e4a79)  (📹) Si ordenas tus datos de menor a mayor y los divides en cuatro grupos, obtienes cuartiles, es decir, dividirá tus datos en cuatro grupos iguales que contendrán el 25% de tus datos en cada grupo. Cuando decimos que un cliente pertenece al primer cuartil de monto, quiere decir que está en el primer grupo de cuatro de los que menos gasta. Si por ejemplo, otro cliente está en el cuartil 3 en monto, quiere decir que está en el tercer grupo que más gasta, por sobre el primer y el segundo.

Entonces un buen cliente pertenece en recencia al cuartil 1 (ya que compró hace poco), en frecuencia al cuartil 4 (por qué compra muy frecuentemente) y en monto al cuartil 4 (porque es de los que más gasta). Para crear la codificación buscamos el cuartil de cada cliente en cada una de las variables y luego unimos esos valores en un "código" que resuma su perfil. Veamos un ejemplo:

![image26.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image26.png)

Miremos algunos ejemplos:

- **El cliente 1 es un excelente cliente**, ya que ha comprado hace poco (pertenece al primer cuartil en recencia, Recencia=1), ha comprado varias veces (pertenece al cuarto cuartil en frecuencia, Frecuencia=4) y ha gastado montos grandes en sus compras (pertenece al cuarto cuartil en monto, Monto=4). A ellos los codificamos como 144 (Recencia=1, Frecuencia=4, Monto=4)
- El cliente 4 es **un cliente que compró hace mucho tiempo** (cuarto cuartil en recencia, Recencia=4), pero ha hecho varias compras en su historia (cuarto cuartil Frecuencia, Frecuencia=4) y hace compras relativamente caras (tercer cuartil en monto, Monto=3). Si juntamos los números su codificación es 443.

Luego podemos ir creando distintas codificaciones con caracterizaciones de los clientes:

- **Los mejores clientes (RFM=144)**: Clientes altamente comprometidos que han comprado lo más reciente, con mayor frecuencia, y han generado la mayor cantidad de ingresos.
- **Los clientes leales (RFM=X4X)**: En este tipo de codificación la “X” hace referencia a que el cliente puede pertenecer a cualquier cuartil en Recencia, pertenece al cuartil 4 en Frecuencia y puede estar en cualquier cuartil en Monto. Esto quiere decir que el cliente codificado con 242 o 344 serán considerados dentro de la categoría “Más leales”. Estos clientes son los que compran más a menudo en UK Merch.
- **Los clientes que más pagan (RFM=XX4)**: Los clientes que han hecho las compras más caras en UK Merch.
- **Los clientes fieles (RFM=X41, RFM=X42)**: Son clientes que suelen volver a tu tienda pero no gastan mucho.
- **Nuevos clientes (RFM=11X):** Compradores por primera vez en UK Merch
- **Los durmientes (RFM=44X)**: Grandes clientes del pasado que no han comprado en un tiempo.

> 👀 Según esta categorización es posible que **un cliente pueda pertenecer a más de un segmento**, en este caso se tendrá que priorizar a qué segmento asignarlo de acuerdo a la necesidad del negocio. Por otro lado, habrá clientes que no estén segmentados, podrías hacer una refactorización en las categorías (volver a pensar las categorías con más información) como por ejemplo tus clientes que más pagan pasarán a ser XX3 y XX4, de esta forma agregarás a los clientes que pertenecen al cuartil 3 y 4 de la dimensión Monto.

¡Vamos por esa segmentación 🤘!

#### 4.2.1 Preparar un nuevo dataset

Para mantener el orden, vamos a volver a crear una nueva pestaña donde copiaremos solo las columnas que necesitamos de nuestro dataset original. Para calcular la recencia necesitaremos las fechas, para la frecuencia la cantidad de facturas (y por ende, el número de factura) y para el monto claramente necesitamos el monto. Como todo esto va asociado al cliente, también necesitamos su ID.

![image13.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image13.png)

Con esta información crearemos una tabla dinámica en donde las filas sean los ID de todos los clientes y en las columnas podamos ver tres piezas de información importantes:

1. La última fecha de compra del cliente
2. La cantidad de facturas que están asociadas a cada cliente
3. La suma total del monto gastado por el cliente (aquí puedes ocupar el agregador SUM)

Te recomiendo volver a copiar esta información en otro lugar de la pestaña para poder agregarle columnas y hacer la categorización ahí (¡gracias función QUERY!)

![image27.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image27.png)

Como ves hay varias columnas que debemos comenzar a calcular. La primera es Días, en donde queremos calcular la cantidad de días que han pasado desde la última compra del cliente y hoy (el día que estamos haciendo el análisis). Para esto es útil la función [DAYS](https://support.google.com/docs/answer/9061296?hl%3Des-419) que cuenta la cantidad de días entre dos fechas. Con esto vamos a poder ver hace cuantos días compró cada cliente y definir en qué nivel de Recencia se encuentra cada uno. Si ha comprado hace pocos días, probablemente lo categoricemos en el primer o segundo cuartil, pero si su última compra fue hace muchos días, puede que termine en el tercer o cuarto cuartil.

> 👀 La fórmula DAYS cuenta la cantidad de días entre dos fechas. Tú eliges la fecha contra la que quieres que cuente los días. Puede ser hoy, o cualquier fecha. Esto no va a afectar tu cálculo de cuartiles. Los siguientes ejemplos se hicieron tomando como fecha de contraste el 20 de enero de 2022 (que fue la fecha en que se hizo por primera vez este análisis).

#### 4.2.2 Calcular los límites de los cuartiles

Antes de categorizar cada valor en su cuartil, necesitamos saber cuáles son los rangos de los cuartiles. Para esto, crearemos una nueva tabla en donde calcularemos los cuartiles para los días, frecuencia de facturas y monto total, utilizando la función [CUARTIL](https://support.google.com/docs/answer/3094041).

![image4.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image4.png)

Estos valores que calculaste en la tabla son los límites entre cuartil y cuartil. Para entender esto mejor veamos un ejemplo. Supongamos que usaste la fórmula sobre todos los valores de frecuencia y obtuviste estos resultados para cada cuartil:

![image17](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image17.png)

Esto quiere decir que un cliente cuya última compra fue entre 42 y 59 días atrás, se encuentra en el cuartil 1 (los que han hecho compras más próximas). En contraste, un cliente cuya última compra fue entre 183.5 y 415 días atrás, se encuentra en el cuarto cuartil (los que han hecho compras más lejanas). De esa forma podemos categorizar a cada cliente en uno de los cuatro cuartiles para la recencia. Preparamos este [video](https://www.loom.com/share/e552c7d5d2b3444d8f7be544892e1721) sobre cómo usar la fórmula CUARTIL (QUARTILE) y cómo calcular el cuartil para cada cliente que es el siguiente paso.

#### 4.2.3 Calcular los cuartiles para cada cliente

Una forma rápida de hacer esto es usando la fórmula [IFS](https://support.google.com/docs/answer/7014145?hl%3Den), que se comporta de forma similar a los IF encadenados que hemos utilizado en proyectos anteriores. Esta fórmula acepta varias condiciones y devuelve varios resultados dependiendo de esas condiciones:

```SQL
=IFS(CONDICION_1,VALOR_SI_ SE_CUMPLE_1,CONDICION_2,VALOR_SI_ SE_CUMPLE_2...)
```

En esta fórmula el primer argumento es una condición, el segundo argumento es el valor a dejar en la celda si la primera condición se cumple. Si esto no se cumple, entonces prueba la segunda condición. Si esta se cumple deja el valor 2 en la celda, si no sigue con el resto de las condiciones.

Ocupemos esta fórmula para asignarle el cuartil correspondiente a cada cliente dependiendo de su cantidad de días:

![image14.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image14.png)
Esta fórmula puede interpretarse de la siguiente manera:

- **Condición 1 (AG2<=AP34;AO34)**: Si AG2 es menor o igual a AP34 (que es el primer límite de rango del cuartil), entonces deja el valor de AO34 (que es el valor 1, para indicar que pertenece al primer cuartil).
- **Condición 2 (AG2<=AP35;AO35)**: Si AG2 es menor o igual a AP35 (que es el segundo límite de rango del cuartil), y como ya sabemos que no pertenece al primer cuartil, entonces deja el valor de AO35 (que es el valor 2, para indicar que pertenece al segundo cuartil).
- **Condición 3 (AG2<=AP36;AO36)**: Si AG2 es menor o igual a AP36 (que es el tercer límite de rango del cuartil), y como ya sabemos que no pertenece al segundo cuartil, entonces deja el valor de AO36 (que es el valor 3, para indicar que pertenece al tercer cuartil).
- **Condición 4 (AG2<=AP37;AO37)**: Si AG2 es menor o igual a AP37 (que es el cuarto límite de rango del cuartil), y como ya sabemos que no pertenece al tercer cuartil, entonces deja el valor de AO37 (que es el valor 4, para indicar que pertenece al cuarto cuartil).

En el ejemplo de la foto AG2=367 no se cumple la primera condición (porque no es menor o igual que 59). No se cumple la segunda condición (porque no es menor o igual que 92). Tampoco se cumple la tercera (porque no es menor o igual que 183.5), pero si se cumple la cuarta condición (si es menor o igual a 415), por lo que dejamos el valor de AO37=4. Es decir, ese valor pertenece al cuarto cuartil.

Esta categorización tenemos que hacerla para todos los clientes y en las tres columnas de RFM.

![image30.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image30.png)

🤓 **Análisis** 🤓

Veamos estos resultados. El cliente 12346 quedó categorizado como 4 en Recencia, 1 en Frecuencia y 4 en Monto. Y esto sí tiene sentido, ya que él hizo su última compra hace mucho tiempo (367 días), no ha comprado muchas veces en UK Merch (solo tiene una factura a su nombre) y si ha gastado mucho (más de 77.000 libras esterlinas, lo que es una compra grande).

¿Puedes hacer un análisis similar con el cliente 12347?

#### 4.2.4 Categorizar cada cliente según su código

Ya tenemos los valores de cuartil para la recencia, frecuencia y monto de cada cliente. Ahora que lo que resta es clasificarlo según alguna de las categorías que definimos más arriba.

Para hacer esto de una forma más automática, primero debemos crear una tabla con todas las combinaciones de códigos posibles y el nombre que queremos asignarle.

![image40.png](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image40.jpg)

Por otro lado, debemos crear una columna “Código” en nuestra tabla de clientes que resuma la información del RFM en un código de tres números. Podemos hacer esto usando la fórmula CONCATENATE que conocimos en el primer proyecto.

![image56](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image56.png)

Y ahora debemos “conectar” ambas tablas para que la tabla de cliente “busque” el código en la tabla que creamos con las combinaciones y recupere el nombre de la categoría. Esto es un caso de uso muy común en Google Sheets, y para eso utilizamos la función BUSCARV (o [VLOOKUP](https://support.google.com/docs/answer/3093318?hl%3Den)).

```SQL
=VLOOKUP(search_key, range, index, [is_sorted])
```

Los argumentos de esta fórmula son:

- **search_key**: este es el código que comparten ambas tablas. En nuestro caso es el código RFM.

- **range**: es el rango de datos donde vamos a buscar la referencia (search_key) y el valor a devolver, en este caso el rango de datos es toda nuestra tabla de matriz de segmentación.

- **index**: este es el número de la columna con el valor que queremos devolver, es decir, comenzamos a contar desde la primera columna del rango de datos seleccionado (en este caso, la columna será 2).

- **[is_sorted]**: esto es muy importante, siempre incluimos 0 en este parámetro, porque queremos que devuelva el primero dato que encuentre para nuestra search_key.

![image8.jpg](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image8.jpg)

> Tip: si usas la fórmula CONCATENATE para crear los códigos, copia y pega (solo valores) los valores de esta columna para que la fórmula Vlookup funcione correctamente.

Cuando tengas las categorías, puedes resumir la información en una tabla dinámica y hacer recomendaciones específicas a UK Merch. Por ejemplo, si el número de clientes durmientes es muy alto, una buena estrategia de marketing sería contactarlos y motivarlos a volver a comprar (por ejemplo, por medio de descuentos), ya que sabemos que son clientes que compran muy seguido, pero que hace tiempo no compran. Otro caso hipotético podría ser el lanzamiento de un nuevo producto. En este caso podría convenir apuntar las estrategias de marketing a tus clientes leales (los que compran más frecuentemente) para que así tu nuevo producto agarre tracción en el mercado. [Este artículo](https://blog.elogia.net/rfm-recency-frecuency-y-money-qu%25C3%25A9-valor-tiene-nuestro-cliente) te puede dar algunas buenas ideas.

Otra estrategia inteligente sería agregar la variable de si pertenece o no a UK al análisis y ver cómo cambia la segmentación. Y de esa forma se pueden hacer recomendaciones de publicidad más enfocada en clientes de UK (con un lenguaje y modismos del país) si vemos que hay oportunidades ahí.

De esta forma, UK Merch puede aplicar la ley de Pareto y enfocar sus esfuerzos para que sus mejores clientes le traigan la mayor cantidad de ganancias. Una campaña pequeña bien ejecutada a un segmento específico de clientes puede ser mucho más efectiva que una campaña publicitaria grande y cara sin un foco claro.

Como vimos, la segmentación de clientes es una buena práctica para entender los perfiles de clientes que tenemos y saber dónde poner esfuerzos para hacer crecer el mercado o fortalecer la marca. Echemos un vistazo a lo que hemos visto hasta ahora.

### Close Question
¿Has podido llegar a una tabla de cuartiles similar a esta?
![validacion_tabla](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/validacionP3_tabla.png)
Sí
No

¿Cuántos clientes fueron clasificados como mejores clientes (código 144)? Elija la respuesta que aplica a su caso
Aproximadamente 456
No seguí la segmentación propuesta en la guía

### Validación
¡Súper! No existe una única forma de segmentar a los clientes, ni un número ideal de categorías, por lo que si decides seguir otro camino y complementar la segmentación con otras categorías o abarcar más perfiles en una misma, no es problema, nos encanta que lo hagas y que te desafíes a timisma buscando nuevas formas de completar una tarea.

## Paso 5: Comparte

Ya terminaste tu análisis y cuentas con muchísimas tablas, datos y gráficos que resumen los datos y que entregan información útil. Pero esta información está desperdigada en distintas pestañas y sin una estructura lógica.

En este paso debes tomar toda la información que creas que sea relevante para el cliente y la debes organizar en un dashboard que sea fácil de entender y estéticamente armónico.

![image58](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image58.png)

Utiliza mapas, gráficos, métricas y texto para que tu dashboard de cuenta de tu análisis por si solo. Si necesitas algo de inspiración para tu diseño, una simple búsqueda de Google (“Templates de dashboards”) te puede arrojar [resultados muy útiles](https://colorlib.com/wp/free-dashboard-templates/).

Complementa tu trabajo en esta sección con la siguiente en donde hablaremos de data storytelling y te entregaremos recomendaciones para crear un relato interesante en base a tu análisis de datos.

## Paso 6: Actúa

Hasta el momento has empleado solo habilidades técnicas (o hard skills) en tu análisis. Sin embargo, las habilidades técnicas necesariamente deben ser complementadas con las habilidades socioemocionales (o lifeskills, o soft skills). No es suficiente solamente analizar la data, debes ser capaz de comunicar la historia que los datos van contando de una manera clara y convincente. Una habilidad fundamental a la que llamamos data storytelling.

El data storytelling es la habilidad de comunicar hallazgos extraídos de un dataset de forma eficiente usando narrativas y visualizaciones. Su objetivo crucial es inspirar acción en tu audiencia.

### ¿Por qué utilizar data storytelling?

Los seres humanos hemos contado historias desde la era del Cromañon para comunicarnos efectivamente con otros y mejorar nuestras posibilidades de supervivencia. [Algunos historiadores](https://www.youtube.com/watch?v%3Dnzj7Wg4DAbs) argumentan que nuestra capacidad de contar historias es la característica que nos llevó, como especie, a dominar el mundo.

Han pasado muchos años desde nuestros antepasados cavernarios, pero nuestras estructuras mentales se mantienen prácticamente idénticas. Cuando escuchamos historias se activan múltiples partes del cerebro que controlan la comprensión del lenguaje (el área de Wernicke), nuestras respuestas emocionales (la amígdala) y nuestra empatía hacia otros (neuronas espejo). Cuando múltiples áreas del cerebro se activan, el hipocampo se pone a trabajar. Esta estructura es la encargada de convertir una experiencia auditiva en una memoria de largo plazo. **Por lo tanto, desde una perspectiva neurobiológica, tiene sentido organizar nuestro análisis de datos en un relato si queremos que la audiencia recuerde nuestras conclusiones y recomendaciones**.

Si todavía no estás convencida, te dejo algunos datos:

- Un estudio conducido por Chip Heath, autor de “Made to stick” y profesor de Stanford, demostró que en un ejercicio de **memoria**, un 63% de los participantes pudo recordar una historia, en contraste con solo un 5% que puso recordar una estadística.
- En otro estudio, a un grupo de participantes se les mostró dos tipos de infográficas invitando a donar. La infografía que se estructuraba en torno a una narrativa recaudó el doble de fondos, mostrando el poder **persuasivo** de las historias.
- Un tercer estudió demostró el efecto **cautivador** de las historias. Cuando escuchamos una narrativa, somos más propensas a bajar nuestra “guardia” intelectual, y tomamos una postura menos crítica y escéptica.

### Los tres elementos claves

El data storytelling reúne tres elementos que ya hemos mencionado: narrativa, visuales y datos.

- Cuando tomas una **narrativa** apoyada en **datos**, entonces puedes ser capaz de **explicar** a tu audiencia rasgos generales de la data.
- Si generas **visuales** a partir de tus **datos**, es probable que alguien se pueda **informar** de insights particulares que no podría ver sin gráficos.
- Al combinar **narrativa** con **visuales**, puedes **cautivar** a tu audiencia. El ejemplo clásico son las películas que mezclan imágenes con narrativas para generar emociones en los espectadores.

| ![image50](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image50.png) |
|---|
| *Imagen tomada de [este artículo](https://www.forbes.com/sites/brentdykes/2016/03/31/data-storytelling-the-essential-data-science-skill-everyone-needs/?sh%3D5750c5ca52ad) de Forbes* |

La magia sucede combinas estos tres elementos. El data storytelling es una herramienta que puede influenciar y generar cambio.

| ![image38](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image38.png) |
|---|
| *Imagen tomada de [este artículo](https://www.forbes.com/sites/brentdykes/2016/03/31/data-storytelling-the-essential-data-science-skill-everyone-needs/?sh%3D5750c5ca52ad) de Forbes* |

### El proceso

Toda esta sección se basa en el excelente libro “[Storytelling with Data](https://www.amazon.com/Storytelling-Data-Visualization-Business-Professionals-ebook/dp/B016DHQSM2/ref%3Dtmm_kin_swatch_0?_encoding%3DUTF8%26qid%3D%26sr%3D)” de la científica de datos Cole Nussbaumer. Las imágenes e ideas contenidas aquí son de Cole y su libro. Si te interesa este tema, te recomendamos profundizar con su libro.

#### 1. Entender el contexto

Aquí debes ser capaz de responder tres preguntas

- **¿Quién?**: Es muy importante pensar a quién le vas a presentar tus resultados porque así puedes definir si será una presentación más técnica mostrando, además de los resultados, cómo se desarrolló el análisis. O quizás es una presentación al CEO de la empresa, que necesita conocer directamente los resultados obtenidos y los próximos pasos.
- **¿Qué?**: Esto es lo que quieres lograr con tu storytelling. Quizás quieres convencer a alguien que debe tomar una decisión sobre un producto digital, o un área de finanzas que debe subir el presupuesto de mercadeo. Esto es lo que descubriste en tu análisis y quieres contar.
- **¿Cómo?**: Las herramientas, visualizaciones o datos que vas a utilizar para lograr tu objetivo. Puede ser un análisis descriptivo. O una predicción basada en datos históricos. Debes buscar la forma de lograr que tu audiencia (quien) entienda y actúe sobre el problema (qué).

Veamos un ejemplo. Supongamos que eres una profesora de ciencias que desarrolló un taller de verano con algunos estudiantes. El taller fue un éxito y ahora quieres hablar con el director de tu colegio para que apruebe mayor presupuesto para los talleres del próximo año. Estructuras tus elementos básicos de storytelling:

- **¿Quién?**: El director del colegio, quien aprueba los aumentos de presupuesto.
- **¿Qué?**: El taller de verano fue un éxito. Por favor, aprueba un aumento de $X del presupuesto para los talleres del próximo año.
- **¿Cómo?**: Mostrar el éxito de taller comparando los resultados de una encuesta hecha antes y después del programa en donde se les pregunta a los niños sobre su interés en la ciencia.

#### 2. Elegir las visualizaciones correctas

Hay muchas formas distintas de mostrar los mismos datos. La elección de la visualización es clave para no confundir y mostrar tus hallazgos de la forma más clara posible.

##### 2.1 Texto simple

Menos es más. A veces es mejor mostrar la información con texto bien resaltado que con una visualización que puede ser compleja o innecesariamente informativa.

Mira este ejemplo:

| ![image16](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image16.png) | ![image39](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image39.png) |
|---|---|
| Este gráfico muestra el porcentaje de niños/as que tienen una madre que se queda en casa y en donde el marido es quien trabaja. Compara los porcentajes de 1970 vs 2012. | Esta visualización de solo texto muestra la misma información pero de forma más clara y simple. |

##### 2.2 Tablas

Las tablas son una buena forma de mostrar mucha información de forma organizada. Debes esperar que tu audiencia se demore en leer tus tablas.

Puedes mejorar la legibilidad de tu tabla con bordes angostos, o eliminando completamente los bordes de tu tabla.

![image46](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image46.png)

Otra forma de mejorar la legibilidad de tus tablas es con mapas de calor:

![image21](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image21.png)

##### 2.3 Gráfico de línea

Ocúpalos para mostrar la evolución de una o más variables en el tiempo.

![image25](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image25.png)

Si tu gráfico de línea representa alguna medida de tendencia central, como por ejemplo el promedio, es una buena idea mostrar también el rango en donde se mueve tu variable:

![image55](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image55.png)

El gráfico de arriba también muestra otra buena práctica de los gráficos de línea: delimitar el inicio y fin de cada año.

##### 2.4 Gráfico de pendiente

Este gráfico es una versión simplificada de los gráficos de línea. Se ocupan cuando quieres mostrar como aumenta o decrece una variable entre dos periodos específicos.

![image61](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image61.png)

Como veremos más adelante, y como se muestra en este ejemplo, siempre es una buena idea resaltar los puntos de datos que quieres que tu audiencia se fije.

##### 2.5 Gráfico de barra

Los gráficos de barra son fáciles de leer. Con un solo vistazo puedes ver hasta donde llega cada barra y, por consiguiente, concluir que categoría es mayor, menor y la diferencia entre ellas.

Un punto importante con los gráficos de barra es que siempre deben comenzar desde el cero, si no se pueden dar comparaciones injustas como esta:

| ![image51](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image51.png) | ![image1](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image1.png) |
|---|---|
| Este fue un gráfico que salió en Fox News mostrando como subirían los impuestos luego de que expirara una política de recorte de la administración de Bush. Al mirarlo rápidamente uno siente que el aumento es significativo. | Pero si el eje Y comienza desde cero (como debería ser) podemos ver que la diferencia visual disminuye. |

Al igual que los gráficos de línea, los gráficos de barra pueden tener más de una “serie”.

| Una serie | Dos series | Múltiples series |
|---|---|---|
| ![image64](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image64.jpg) | ![image65](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image65.jpg) | ![image66](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image66.jpg) |

Ten en cuenta que, a medida que vas agregando series, es cada vez más difícil leer los datos del gráfico, por lo tanto, procura resaltar las series más importantes para captar la atención de tu audiencia y deja el resto de las series como soporte para aquellos que quieran revisar toda la información.

En el caso de que tengas muchas categorías que mostrar, y si además su nombres son largos, es una buena idea girar el sentido del gráfico de barra a uno horizontal. Este tipo de gráficos son más fáciles de leer, dado que la audiencia tiene a leer de izquierda a derecha y de arriba a abajo.

| Una serie | Dos series | Múltiples series |
|---|---|---|
| ![image67](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image64.jpg) | ![image68](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image65.jpg) | ![image69](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image66.jpg) |

Los gráficos horizontales tiene una variante que resulta útil utilizar en algunas ocasiones: los gráficos de barra horizontal apilados al 100%. Este tipo de gráficos son útiles para mostrar los resultados de datos en escalas likert, ya que da una sensación rápida de “escala”.

![image54](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image54.png)

##### 2.6 Algunos gráficos a evitar

Está bien documentado en la comunidad de analistas de datos que los gráficos “de postre” (gráfico de torta o gráfico de donut) son una mala idea. En general, los seres humanos no somos muy buenos para detectar diferencias en espacios en dos dimensiones.

![image6.gif](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image6.gif)

Es por esta razón que un gráfico de torta o donut con diferencias pequeñas puede confundir a la audiencia. ¿Cuál de los dos arcos es mayo? ¿El A o el B?

![image29](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image29.png)

Esto se agrava aún más cuando hacemos gráficos en tres dimensiones.

![image36](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image36.png)

A simple vista pensaríamos que el área del Supplier B es más grande que el del Supplier A. Pero la verdad es que la perspectiva nos está engañando.

![image45](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image45.png)

Por lo mismo, evita los “gráficos de postre”. Evita los gráficos en 3D. Y más aún, evita los gráficos "de postre" en 3D.

Una mejor alternativa para este mismo ejemplo sería un gráfico de barras que nos permite comparar cantidades entre categorías fácilmente.

![image24](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image24.png)

#### 3. Elimina los excesos

Con “exceso” nos referimos a todo lo que ocupe un espacio visual, pero que no agrega valor al entendimiento de tu visualización.

Los gráficos predeterminados de Excel o Google Sheets vienen con un montón de funcionalidades activadas que no necesariamente necesitamos para hacernos entender. Recuerda, menos es más.

Veamos un ejemplo que nos puede ayudar a entender algunas recomendaciones. Supongamos que eres la líder de un equipo de tecnología que recibe solicitudes de clientes a través de un sistema de tickets (tickets received). Hace algunos meses se fueron dos personas de tu equipo y el resto se está quejando de que tiene mucha más carga laboral y que no están alcanzando a resolver todos los tickets (tickets processed). Tu jefe te está preguntando si vas a necesitar hacer crecer tu equipo el próximo año y para responderle con evidencia te vuelves a los datos. Haces un gráfico que efectivamente muestra como desde un mes en particular tu equipo está recibiendo más tickets de los que está procesando. Con esta evidencia quieres donde tu jefe. Pero primero debes preparar tu storytelling. Vamos al gráfico.

| Visualización | Descripción |
|---|---|
| ![image43](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image43.png) | Este es el gráfico original. Cuando creamos gráficos con nuestras herramientas de hoja de cálculos (como excel o gsheets) obtenemos un gráfico como este. |
| ![image32](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image32.png) | Los bordes generalmente son innecesarios en las visualizaciones, por lo que los eliminamos. Una mejor forma de “separar” visualizaciones es con “espacio en blanco”. |
| ![image10](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image10.png) | Si sientes que puede ser útil para tu audiencia poder seguir las líneas de cuadrícula para ver el valor de cada punto, puedes dejarlas. En ese caso te recomendamos hacerlas muy finas y con colores grises. En caso contrario, es buena idea eliminarlas. |
| ![image49](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image49.png) | Misma idea con los marcadores de valores. Si sientes que agregan valor, los puedes dejar. En la mayoría de los casos, los “vértices” de las líneas son suficientes para marcar cada punto de dato. |
| ![image59](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image59.png) | Limpiamos las etiquetas de los ejes. Los números lo más simple posible. Abrevia las etiquetas de texto siempre cuando se pueda. |
| ![image31](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image31.png) | A veces es una mejor idea etiquetar directamente las líneas o barras de un gráfico que ocupar una leyenda. La leyenda implica “ir y volver” a leerla cada vez que se nos olvide cuál línea es cuál. Recuerda, el objetivo de esta sección es eliminar los excesos. |
| ![image44](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image44.png) | Mejor aún si podemos ocupar colores para apoyar el proceso de “etiquetado” de los datos. De esa forma, con un solo vistazo puedes entender cuál línea es cuál. |

Los datos en esta nueva visualización “light” son los mismos que el gráfico original, sin embargo, hemos ayudado a la audiencia (tu jefe) ponga foco en lo más importante (la diferencia entre las dos líneas), y hemos eliminado todo aquello que agregaba complejidad innecesaria.

| Antes | Después |
|---|---|
| ![image70](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image70.jpg) | ![image71](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image71.jpg) |

#### 4. Enfoca la atención de tu audiencia

Aunque no lo creamos, vemos con nuestros cerebros, no con nuestros ojos. Cuando “vemos” algo con nuestros ojos, antes de entender lo que estamos viendo, nuestro cerebro ya “vio” esa imagen y ya procesó algunas cosas importantes de forma inconsciente, antes de que podamos “digerir” esa imagen.

Estas “cosas” que procesa nuestro cerebro antes de que veamos realmente las imágenes se llaman atributos preatentivos. Como el nombre lo indica, son cosas que procesamos antes de prestar atención a algo.

Por ejemplo, en los siguientes párrafos tu cerebro ya identificó dónde están las secciones importantes antes de que comiences a leer el texto:

| Sin atributos preatentivos | Con negrita | Con color |
|---|---|---|
| ![image72](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image72.jpg) | ![image73](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image73.jpg) | ![image74](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image74.jpg) |

Este efecto de “enganchar” a la audiencia en los lugares que a ti te interesa es algo que podemos lograr también con nuestras visualizaciones.

| Visualización | Descripción |
|---|---|
| ![image63](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image63.png) | Este gráfico muestra los 10 mayores problemas reportados por clientes de una marca de autos. Como CEO, si quisieras extraer algo de información útil para cambiar el diseño, tendrías que leer toda la tabla. |
| ![image19](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image19.png) | Con atributos preatentivos puedes enfocar su atención en los problemas que tienen 10 o más quejas por cada 1000. |
| ![image47](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image47.png) | Y si quisieras ir un paso más allá, podrías destacar aquellas que estén relacionadas. En el ejemplo se destacan tres problemas que están relacionados a “ruidos” en el auto. Con esta información el CEO si puede accionar cambios. |

Para dejar claro el proceso de enfoque, podemos continuar nuestro ejemplo de la sección anterior.

| Visualización | Descripción |
|---|---|
| ![image15](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image15.png) | Habíamos quedado en este gráfico sin excesos |
| ![image62](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image62.png) | Una buena estrategia para comenzar a destacar cosas, es dejando toda la data “neutra” para luego ir selectivamente “activando” lo que creamos relevante. |
| ![image22](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image22.png) | Utilizamos color para destacar la curva de tickets procesados, para hacer notar que en algún punto esta comienza a ser menor a la cantidad de tickets recibidos. |
| ![image34](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image34.png) | Queremos llevar la atención de nuestra audiencia a esa brecha que se genera desde mayo. Una buena alternativa sería volver a poner las etiquetas de datos para que sea evidente la diferencia en cantidades entre ambas curvas. |
| ![image5](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image5.png) | Sin embargo, se ve muy desordenado y denso. Mejor eliminemos todas las etiquetas previas a la brecha y dejemos solo las que nos interesan. Mucho mejor. |

Gracias a colores y etiquetas bien utilizadas podemos resaltar la información que queremos que la audiencia vea, incluso antes de que la “vean”.

#### 5. Los textos son tus aliados

Aun cuando nuestras visualizaciones estén libres de exceso y enfocando la atención de nuestra audiencia en los lugares que queremos con atributos preatentivos, siempre es bueno complementar lo obvio con algunos textos dentro de las visualizaciones. Esto sirve para las personas que escucharán tu presentación en vivo, pero por sobre todo para aquellas personas que verán tus visualizaciones cuando tú no estés.

Una simple adición a nuestro ejemplo anterior sería algo como esto:

![image53](https://raw.githubusercontent.com/Laboratoria/laboratoriaplus/main/data-fluency/project-3-ecommerce/images/image53.png)

Esta nueva visualización agrega elementos de texto muy importantes:

- Etiquetas de datos de los ejes para dar más contexto
- La acción que quieres intencionar en tu audiencia en el título (“Por favor aprueba la contratación de 2 personas más”)
- Un párrafo en la misma visualización que explica el punto en donde se van las dos personas de tu equipo y la consecuencia que eso tiene en la brecha entre tickets recibidos y tickets procesados
- La fuente de los datos por si alguien quiere hacer un análisis en profundidad

#### 6. Cuenta la historia

¿Qué es exactamente una historia? En su nivel más fundamental, una historia está compuesta de tres actos.

- El **primer acto** establece el contexto de la historia. Se introduce el personaje principal, sus relaciones y el mundo donde vive. En general, en este acto se muestra que existe un cierto **equilibrio** en el mundo que luego es perturbado por algo.
- El **segundo acto** constituye la mayor parte de la historia. Aquí se muestra como el protagonista intenta resolver el problema que se originó en el primer acto.
- En el **tercer acto** resuelve el conflicto de la historia y da un sentido de completitud.

La lucha, el conflicto y el suspenso son componentes críticos de las historias. Nuestro data storytelling también debe seguir esta secuencia narrativa.

##### El inicio

Aquí configuramos los elementos esenciales de la historia, dándole a tu audiencia un terreno común en donde moverse. Tu audiencia se está preguntando ¿por qué debería prestar atención?. Muéstrales cuál es el conflicto que está perturbando el equilibrio y dales un pequeño vistazo de la posible solución que encontraste.

##### El desarrollo

En esta sección debes convencer a tu audiencia de que tu solución es la correcta y que, al aplicarla, se soluciona el conflicto, se dispersa la tensión y se vuelve al equilibrio. Algunas ideas que podrías incluir en esta sección:

- Entrega mayor información sobre el contexto
- Incluye información externa y como esta se compara con la situación actual
- Da ejemplos para ilustrar el problema
- Comenta que sucedería si no se toma acción para solucionar el problema
- Discute posibles soluciones para solucionar el problema
- Muestra los beneficios de tu solución propuesta
- Muestrale a tu audiencia porque están en un momento crítico e idóneo para tomar la decisión y solucionar el problema

##### El final

Debes terminar con un **llamado a la acción**. Este es el propósito de todo este paso 6 del sistema de Google: **actúa**.

Una forma clásica de cerrar la historia es volviendo al principio, mostrando nuevamente el conflicto que generó el desequilibrio y como tu solución lo resuelve. Agrega el sentido de urgencia para llamar a tu audiencia a actuar inmediatamente.

# Hacker edition

Si quieres ir al siguiente nivel y aprender una herramienta muy útil en el proceso, te desafiamos a que realices tu análisis y reporte en [Google Data Studio](https://datastudio.google.com/) 😱. Esta es una herramienta que te permite conectar diversas fuentes de datos y luego crear visualizaciones y reportes dinámicos. Este tipo de herramientas, llamadas visualizadores, son elementales en el que hacer de una Analista de Datos.

Primero comencemos importando tus datos desde Google Sheets a Data Studio, mire este [video](https://www.loom.com/share/0cce98d5bbc7482ea421444e2f850cc1) para aprender cómo importar datos de la spreadsheet.

Ahora que hemos importado los datos a Data Studio, podemos comenzar a crear nuestros gráficos y elementos visuales. Mire [este video](https://www.loom.com/share/9c7505eb3c2a4612bdfb7c9d43c40051) para aprender cómo comenzar a crear sus gráficos.

Si desea mejorar aún más su conocimiento de Data Studio, realice este [curso online](https://www.youtube.com/watch?v%3D6FTUpceqWnc%26list%3DPLI5YfMzCfRtag7tBfbVvA4_a6YZxWHEO4) gratuito de Google, con subtitulos en español (en el video de youtube seleccione configuración > subtítulos > español).

👩‍💻 Si has llegado hasta aquí, no olvides agregar tu dashboard en Data Studio a tu presentación y comparte el link de tu dashboard.

# Recursos adicionales

A continuación te dejamos algunos videos y artículos adicionales que pueden servirte si deseas profundizar más en los temas que trabajarás en este proyecto.

Para temas técnicos de spreadsheets, RFM y estadística:

- Este [artículo](https://www.zendesk.com.mx/blog/segmentacion-de-clientes/) para que aprendas sobre segmentación.
- Este [podcast](https://www.youtube.com/watch?v%3DCM0L1rftBfA) que profundiza en la metodología de segmentación RFM.
- Este [video](https://www.youtube.com/watch?v%3Dn3xpKz0SYlQ) que explica el concepto de pareto y como aplicarlo a los negocios.
- Este [articulo](https://lasmatesfaciles.com/2021/06/21/cuartiles-deciles-y-percentiles-para-datos-agrupados/) sobre cuartiles.
- Este [video](https://www.youtube.com/watch?v%3DHjE4C4p7U2w) de youtube que muestra como hacer reportes ordenados y con diseños modernos.
- Este [artículo](https://medium.com/@miramontesayelen/claves-del-dise%25C3%25B1o-ux-para-visualizaci%25C3%25B3n-de-datos-8faeca47a709) que habla sobre buenas prácticas al momento de crear reportes con datos.

Para complementar tu conocimiento en data storytelling:

- [How to tell a story with data](https://venngage.com/blog/data-storytelling/)
- [5 amazing ways to impact your audience with data storytelling](https://www.meltwater.com/en/blog/5-amazing-ways-to-impact-your-audience-with-data-storytelling)
- [Telling stories with data in 3 steps](https://www.youtube.com/watch?v%3Dr5_34YnCmMY)
- [Making data mean more through storytelling](https://www.youtube.com/watch?v%3D6xsvGYIxJok)
- [Ejemplo de storytelling con datos - Netflix](https://www.youtube.com/watch?v%3DihltOyKn9I0%26t%3D2s)
- [Visualizar y comunicar datos](https://elartedemedir.com/blog/visualizar-comunicar-datos/)
- [Consejos de Retórica para persuadir (con datos)](https://www.linkedin.com/pulse/consejos-de-la-ret%25C3%25B3rica-para-persuadir-con-datos-eduardo-valencia/?originalSubdomain%3Des)
