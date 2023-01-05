# **PROYECTO INDIVIDUAL Nº3 - Analytics**
# **`Telecomunicaciones`**

<img src = 'https://media.minutouno.com/p/5d02740cf5a38fe1fda99ecd86335882/adjuntos/150/imagenes/039/854/0039854730/tablets-gratuitas.jpg' height = 400>

La industria de las telecomunicaciones ha jugado un papel vital en nuestra sociedad, facilitando la información a escala internacional y permitiendo la comunicación continua incluso en medio de una pandemia mundial. La transferencia de datos y comunicación se realiza en su mayoría a través de internet, líneas telefónicas fijas, telefonía móvil, casi en cualquier lugar del mundo. 

En comparación con la media mundial, Argentina está a la vanguardia del desarrollo de las telecomunicaciones, teniendo para el 2020 un total de [62,12 millones conexiones](https://www.datosmundial.com/america/argentina/telecomunicacion.php). 

## Investigación preliminar 

### **Sobre ENACOM**

El Enacom es un ente autárquico y descentralizado que funciona en el ámbito de la Jefatura de Gabinete de Ministros de la Nación. Su objetivo es conducir el proceso de convergencia tecnológica y crear condiciones estables de mercado para garantizar el acceso de todos los argentinos a los servicios de internet, telefonía fija y móvil, radio, postales y televisión.

Enacom fue creado en Diciembre del 2015 a través del Decreto 267 en el cual se establece su rol como regulador de las comunicaciones con el fin de asegurar que todos los usuarios del país cuenten con servicios de calidad.

**Misión**

Promover la plena inclusión digital, facilitando a toda la población el acceso a las oportunidades que brindan las Tecnologías de la Información y las Comunicaciones, generando un mayor balance y competencia entre los distintos actores del mercado, agilizando su desarrollo, resguardando la debida defensa de los usuarios y fomentando la prestación de servicios con altos estándares de calidad, en el contexto de un regulador activo que refuerce el marco normativo e institucional, garantizando que la pluralidad de voces y los beneficios de la sociedad de la información estén disponibles para todos los que habitan el territorio nacional, en especial a los que viven en zonas rurales, extremas y de bajos ingresos.  

**Visión**

Posicionarse como un referente internacional en regulaciones y control de las comunicaciones, habiendo logrado altos estándares de calidad de servicios a precios competitivos, generando espacios de inclusión digital y defensa de los usuarios, e impulsando una política pública e institucional para el correcto desarrollo del mercado.

**Lineamientos**

*Universalizar* la inclusión digital,  para que los beneficios de las tecnologías de la información estén disponibles para todos los argentinos, potenciando las economías regionales.

*Proteger* a los usuarios de comunicaciones, reforzando las facultades de fiscalización y control, simplificando los trámites y generando las modificaciones regulatorias necesarias para lograrlo.

*Aumentar* la calidad de servicio en las comunicaciones, a través de la implementación de normativas técnicas y la incorporación de estándares de calidad de nivel internacional.

*Impulsar* la competencia para el desarrollo de las Tecnologías de la Información y las Comunicaciones, a partir de la publicación de estadísticas del mercado y la modificación de regulaciones, normas y gravámenes que ayuden a fomentar la competencia en el sector.

*Promover* las inversiones en infraestructura para el desarrollo digital, estableciendo condiciones regulatorias y económicas  propicias tanto para el fortalecimiento de redes existentes como para nuevos despliegues.

*Fomentar* la transparencia y la integridad en la gestión, desarrollando una cultura organizacional basada en las buenas prácticas y en los códigos de ética y comportamiento.

## **Objetivos del análisis sobre Telecomunicaciones:** 

 1. **Evaluar** la evolucion del acceso a Internet fijo desde el 2014 hasta el 2022 por trimestre y por provincia, así como también la suma de ingresos por año, investigando si efectivamente la Pandemia produjo un crecimiento en la utilización de Internet.
 2. **Comparar** la velocidad del acceso a internet fijo de cada provincia para realizar una mejor distribución del acceso a internet según la velocidad categorizada por rangos.
 3.  **Definir** cuál es el tipo de tecnología mas elegida, con mayor crecimiento para cubrir las necesidades de los usuarios acorde a la demanda. 
 4.  **Determinar** cuales son las localidades con servicio nulo de internet para posibilitar la llegada de la tecnología y medios de comunicación a sectores de la sociedad que aún no han tenido esa posibilidad. 
 5.  **Analizar** otros servicios como la televisión por suscripción o satelital, para ofrecer como parte de paquetes y promociones, junto al servicio de internet.


### **Análisis exploratorio de los datos y transformaciones (EDA)**

Descargué los datos proporcionados por la plataforma del Enacom a través de la API directamente a Power Bi para realizar al instante la transformación necesaria con Power Query de las tablas que seleccioné con información entre los años 2014 y 2022:

	1  Acceso a Internet fijo por rango de velocidad por provincia
	2  Acceso a Internet fijo por tecnologia y provincia
	3  Acceso a Internet, cada 100 hogares por provincia  
	4  Accesos a Internet fijo por tecnología y localidad  
	5  Accesos de internet de banda ancha y dial up por provincia
	6  Accesos TV por suscripcion y TV satelital 
	7  Calendario
	8  Ingresos por la operacion del servicio de internet fijo  
	9  Listado de localidades con conectividad a internet
	10  Velocidad media de bajada por provincia

En las tablas identifiqué datos faltantes, inconsistentes y errores que fueron subsanados siguiendo los siguientes criterios: 

**1 Acceso a Internet fijo por rango de velocidad por provincia** (Objetivo 2)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Cambio del tipo de dato a tipo numérico de las columnas con Mbps
- Agregado de una columna personalizada con la fecha por año y trimestre 
(Query utilizada:"1/"&Number.ToText([Trimestre]*2+([Trimestre]-2))&"/"&Number.ToText([Año])]).

**2  Acceso a Internet fijo por tecnologia y provincia** (Objetivo 3)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Cambio del tipo de dato a tipo numérico
- Errores quitados y reemplazados de la columna año y trimestre.
- Agregado de una columna personalizada con la fecha por año y trimestre.

**3  Acceso a Internet, cada 100 hogares por provincia** (Objetivo 1)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Cambio del tipo de dato a tipo numérico
- Agregado de una columna personalizada con la fecha por año y trimestre.

**4  Accesos a Internet fijo por tecnología y localidad** (Objetivo 3) 
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Valores reemplazados : - 0 por 0
- Cambio del tipo de dato a tipo numérico
- Se eliminó una columna con datos vacíos
- Errores reemplazados y filas ordenadas
- Agregado de una columna personalizada con la fecha por año y trimestre.

**5  Accesos de internet de banda ancha y dial up por provincia**
Esta columna la descargué y transformé pero finalmente no fue utilizada para el análisis

**6  Accesos TV por suscripcion y TV satelital** (Objetivo 5)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)

**7  Calendario**
Realizada con la siguiente Query: Calendario = CALENDAR("01/01/2014","31/12/2022"), para generar la relación entre los datos de todas las tablas.

**8  Ingresos por la operacion del servicio de internet fijo** (Objetivo 1)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Cambio del tipo de dato a tipo numérico
- Agregado de una columna personalizada con la fecha por año y trimestre.

**9  Listado de localidades con conectividad a internet**(Objetivo 4)
- Cambio del tipo de dato
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Agregado de una Columna condicional con el título de conectividad donde se resume si cada localidad por provincia posee o no al menos algún servicio de internet.

**10  Velocidad media de bajada por provincia** (Objetivo 2)
- Encabezados Promovidos (los títulos se encontraban en la primera fila)
- Cambio del tipo de dato a tipo numérico
- Agregado de una columna personalizada con la fecha por año y trimestre.


### **KPIs**
- Aumento o disminución de la variación porcentual trimestral del servicio de internet, cada 100 hogares por provincia. 
- Acceso a Internet cada 100 habitantes por provincia
- Suma total del Accesos a Internet por provincia
- Promedio o velocidad media de bajada por provincia

## *La elección de los gráficos*

*Gráfico de líneas:*
Fueron seleccionados para el análisis de la evolucion de los datos en el paso del tiempo, así como para realizar una comparación entre los distitntos items:

1 Suma de Accesos por cada 100 hogares por *año y trimestre*.

2 Accesos a Internet fijo por tecnología y provincia por *año y trimestre*.

3 Suma de ingresos por *año y trimestre*.

*Gráfico Circular:* Fueron utiliados para realizar comparativas entre las proporciones en cantidad de accesos por rango de velocidad, y en el otro caso por TV satelital o por suscripcion.

*Gráfico de Barras:* Utilizado para delimitar el top 10 de provincias con menor velocidad media de bajada.

*Mapa de Argentina:* Importé un mapa externo para poder realizar este gráfico. En el podemos ir visualizando geográficamente los datos analizados en la tabla de acceso a internet cada 100 hogares.

*Tabla:* Aquí figuran todas las localidades segun sus provincias, que NO poseen conectividad ni acceso a internet a través de ningun tipo de tecnología.

*Treemap:* Muestra la distribución por provincia a partir de la proporción en tamaño de la cantidad de accesos por localidad que poseen conectividad a internet.

*Tooltip:* Al seleccionar cada Provincia del gráfico Treemap se aparece una ventana con la tabla completa de las localidades de cada una de esas provincias que tienen o no conectividad a internet.

*Filtros*
La mayoría de los gráficos estan filtrados por año, trimestre y provincia.

## *La paleta de colores, el diseño y la tipografía*
El diseño está construido sobre la base de tres colores que son el azul, el verde azulado y el rosado. Esta paleta fue extraída del logo de ENACOM y luego utilizada en claros y oscuros para generar distintas combinaciones. El blanco y el gris de los cuadros y el fondo quedan prolijos, buscan generar esa tranquilidad y contraste para que los colores resalten los graficos y la información reelevante. 
La tipografía es standard (Calibri) en casi todos los casos, normalizando la información para generar armonía, que la letra sea legible y entendible. 
Los bordes de los graficos y las formas coinciden en los costados, hay una coherencia entre las distitnas páginas. 
La lectura esta pensada de izquierda a derecha y de arriba a abajo, colocando los filtros al principio a la izquierda para indicar que aquellos modifican el resto de los gráficos, así como los KPIs están ubicados en la parte superiror del dashboard, con información mas importante, general e introductoria, dándole la importancia que necesita.

## Conclusiones 

Se observa que el cable modem y la fibra óptica aumenta.





