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
- Agregado de una columna personalizada con la fecha por año y trimestre.

**2  Acceso a Internet fijo por tecnologia y provincia**


 1. Las filas cuyo único carácter era '?' fueron reemplazados por un campo vacío. 
 2. Los nombres de las columnas fueron renombrados en español 
 3. La columna de horas fue uniformada y transformada de formato militar a formato regular
 4. Extrajimos las palabras clave de las descripciones de los accidentes 
 5. Creamos una columna de sobrevivientes como resultado de la ecuación 'Total pasajeros a bordo' menos 'Total Fallecidos'
 6. A partir de la columna 'Fecha' fueron creadas las columnas año, mes y día
 7. A partir de la columna 'Ruta' fueron creadas las columnas 'Ciudad de Origen' y 'Ciudad destino' 
 8. A partir de la columna 'Ubicación accidente' fuer creada y transformada la columna 'País'

Luego de este proceso de análisis y transformación cargamos los datos en una base de datos para ser consultados por la plataforma de visualización. 


KPIs
•	Evaluar el aumento o disminución de la variación porcentual trimestral del servicio de internet, cada 100 hogares por provincia. 
•	Que sería un servicio de calidad y como es la calidad en cada provincia de acuerdo a la cantidad de mg según el rango
•	Evaluar el aumento o disminución de la variación porcentual trimestral del servicio de internet, según cada tecnología por provincia y relacionarlo con la calidad y velocidad a internet.
•	Evaluar el aumento o disminución del consumo de la televisión por suscripción y la televisión satelital.
•	Determinar el pico en la aceleración de la internet (si es que coincide con la pandemia).

Se observa que el cable modem y la fibra óptica aumenta.



## Conclusiones 

En general principales causas que ocasionan accidentes aéreos son las siguientes: 
1. Error de piloto 
2. Fallos mecánicos 
3. Meteorología adversa 
4. Sabotaje 
5. Error humano de controlador aéreo o persona en tierra 

En nuestro análisis identificamos que los períodos, regiones y tipo de aeronaves con mayor cantidad de víctimas por accidentes áereos en la historia coinciden con períodos de conflictos bélicos. Con lo cual hay una destacada tendencia negativa que inició en el año 1972, mismo año que registró el mayor número de victimas, hasta la actualidad donde la cantidad de víctimas se ha reducido en un 94%. 

Por último, en el año 2019 se registraron mas de 39 millones de vuelos de los cuales se registraron apenas 13 accidentes aéreos, con lo cual podemos concluir que en la actualidad las probabilidades de morir en un accidentes aéreo es 1 / 3 millones o 0,00003%. 

 ## Registro técnico del análisis de datos 

### **Análisis exploratorio de los datos y transformaciones**

