# CALL CENTER ANONYMOS BANK

Este proyecto está desarrollado en un dashboard de Power Bi y muestras la operatividad del Call Center  del Banco para el año 1999

![Logo](https://github.com/AngelaMina/proyectointegradorcallcenter/blob/main/Portada.PNG)

## Dataset

Para este trabajo se utilizó una base de datos proporcionada por Henry, para realizar el proyecto integrador del módulo M5 llamado Data Anality.
El archivo se encuentra en formato csv, entre su contenido se encuentran columnas con el tiempo de duración de la llamada, tiempo en cola, prioridad de cliente, quién es el servidor, él id del cliente, entre otros, que ayudan al proceso de análisis, también se utilizó un archivo llamado "Ejercicio Call Center - Descripción del DataSet.docx" el cual ayuda a entender mejor la descripción de la operatividad.

[Dataset (comprimido)]
[Diccionario de datos]

## Objetivo 

El objetivo de este trabajo es entender la operatividad del call center, entendiendo las variables del negocio y su operatividad, para proponer las mejores soluciones.

Puntos a tratar

- Volumen de llamadas por motivo
- Porcentaje de llamadas (se dio servicio, se cortó la llamada, se ignora lo que sucedió)
- Meses de mayor demanda
- Tipos de solicitudes para segmento Alta prioridad (Premiun),
- Top 10 de cliente recurrentes
- Comparación de promedio duración premiun vs regular
- Comparación de promedio espera premiun vs regular
- Comparación de tasa resultado positivo para premiun vs regular

## ETL Limpieza, transformación y carga de datos

Para realizar este proceso se utilizó las herramientas proporcionadas por Power Bi, como lo son Power Query.
Se realizaron algunas tablas de soporte para poder calcular mejor la diferencia entre clientes premiun y regulares, también se crearon otras tablas de dimensiones para formar un modelo tipo estrella.
tablas que se relacionaron
- Resultado [Outcome] = Esta tabla es sobre el resultado de servicio, creándole un id para cada posible salida (Agent: se dio servicio, hang: se cortó la llamada, phantom: se ignora que sucedió)
- Tipo de servicio [Type] = En esta tabla se clasifican los 6 tipos de servicios de acuerdo al código dado en el documento de la descripción del data set
- Prioridad [Priority] = Clasificación de los clientes, id 2 para cliente premiun o alta prioridad, y clasificación 0 y 1 para clientes no identificados o clientes regulares.
- Calendario [Calendar] =  Se realiza tabla calendario para tener mejor manejo de las fechas trabajadas
- Llamadas [CallCenter] = Es la tabla principal en donde tiene todos los atributos anteriormente mencionados y otros datos que ayudan al análisis de negocio.

## Modelo de datos

Como anteriormente se mencionó, se crea un modelo tipo estrella en el cual se unen las tablas en la vista "Modelo" y se conectan. El modelo quedo de la Siguiente forma

![Logo]

## Visualización

El dashboard se compone de 1 portada y 3 páginas navegables a través de la botonera

En la primera página encontramos el registro de llamadas, para los clientes premiun o regulares, en función del motivo de la llamada o resultado de la llamada, si fue contestada o no todo esto respecto a los meses.

- Número de llamadas
- Filtro cliente según la prioridad
- Volumen de llamadas por motivo
- Porcentaje de llamadas por resultado
- Total de llamadas en meses

![Logo] (https://github.com/AngelaMina/proyectointegradorcallcenter/blob/main/Esquematipoestrella.PNG)

En la segunda llamada "ALTA PRIORIDAD" se visualiza como se está comportando el manejo a este tipo de clientes.

- Total de llamadas para clientes premiun 
- Total de llamadas por servicio para clientes premiun
- Tiempo promedio en servicio en segundos
- Tiempo promedio espera en segundos
- Top 10 para clientes recurrentes
- Histórico de llamadas clientes premiun por mes y trimestre
- Distribución motivo de llamada.

![Logo]

## Conclusiones 


A medida que avanzamos en el proceso de analizar, visualizar y explorar los datos, llegamos a las siguientes deducciones:

- En promedio, cada agente del call center está atendiendo aproximadamente 23.60 llamadas por hora. Esto proporciona una idea de la carga de trabajo y la eficiencia de los agentes en términos de cuántas llamadas pueden manejar en un período determinado.

- El ritmo de llamadas entrantes es de aproximadamente 123.46 llamadas por segundo. Esto indica la cantidad total de interacciones que el call center está manejando en un corto período de tiempo.

- El tiempo promedio que cada agente pasa atendiendo a un cliente es de 152.56 segundos. Esto incluye el tiempo de manejo de la llamada, la interacción con el cliente y cualquier tarea posterior

- El tiempo promedio que cada agente pasa atendiendo a un cliente es de 152.56 segundos. Esto incluye el tiempo de manejo de la llamada, la interacción con el cliente y cualquier tarea posterior

- Los clientes premium experimentan un tiempo de espera promedio de 86.80 segundos antes de ser atendidos, esto cumpliría con lo establecido que es 90 segundos, mientras que los clientes regulares tienen una espera promedio de 46.56 segundos. Esto podría sugerir que los clientes premium pueden tener necesidades más complejas que requieren una mayor preparación por parte de los agentes.

- Las llamadas de clientes premium tienen una tasa de resultados positivos del 84.72%, mientras que las llamadas regulares tienen una tasa de resultados positivos del 77.10%. Esto significa que las llamadas premium tienden a tener un mayor éxito en términos de resolver las consultas o problemas de los clientes.

En general, estas conclusiones sugieren que las llamadas de clientes premium pueden requerir más tiempo y atención, pero también tienen una tasa de resultados positivos más alta. Por otro lado, las llamadas regulares tienen tiempos más cortos de servicio y espera, pero una tasa de resultados ligeramente menor en comparación. Estos insights pueden ayudar al call center a asignar recursos y estrategias adecuadas para diferentes tipos de llamadas y clientes.

Otros detalles que podemos concluir son:

- lunes y miércoles son los días de mayor demanda y que los domingos y sábados de menor demanda.
- Los meses donde se registraron más llamadas fueron diciembre, agosto y noviembre, respectivamente, y los de menor registro son septiembre, abril y enero.
- La distribución principal de las llamadas se dividió entre actividades regulares o transaccionales en español, que lideraron el conjunto, seguidas por llamadas de clientes potenciales y negociación de acciones. En esa época, las llamadas relacionadas con actividades en línea no constituyeron una parte significativa, y las llamadas relacionadas con actividades regulares en inglés representaron la proporción más baja.


