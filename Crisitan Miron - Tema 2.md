# Preguntas - Tema 2

**¿Qué son las Azure Functions y para qué se utilizan?**

Azure Functions es un servicio sin servidor en la nube ofrecido por Microsoft Azure. Permite ejecutar pequeños fragmentos de código en respuesta a eventos como solicitudes HTTP, cambios en bases de datos o mensajes en colas. Se utiliza para procesamiento de eventos en tiempo real, integración de sistemas, tareas programadas y desarrollo de aplicaciones web y móviles. La ventaja principal es la escalabilidad y alta disponibilidad, sin preocuparse por la administración de servidores. Además, ofrece compatibilidad con varios lenguajes de programación.

**¿Cuáles son los desencadenadores (triggers) más comunes en Azure Functions?**

En Azure Functions, existen varios desencadenadores (triggers) comunes que puedes utilizar para activar la ejecución de tus funciones. Algunos de los desencadenadores más populares son:

1. HTTP Trigger (Desencadenador HTTP): Permite que tu función sea activada mediante solicitudes HTTP. Puedes configurarla para responder a diferentes métodos HTTP, como GET, POST, PUT, DELETE, entre otros.
2. Timer Trigger (Desencadenador de temporizador): Ejecuta tu función en intervalos regulares basados en una programación definida. Puedes especificar la frecuencia de ejecución utilizando expresiones de cron.
3. Blob Trigger (Desencadenador de blobs): Activa tu función cuando se crea o modifica un archivo en un contenedor de almacenamiento de blobs de Azure. Es útil para procesar archivos de forma automática.
4. Queue Trigger (Desencadenador de colas): Activa tu función cuando se envía un mensaje a una cola de Azure. Puedes utilizarlo para procesar mensajes encolados y realizar acciones específicas.
5. Event Hub Trigger (Desencadenador de Event Hub): Permite que tu función sea activada cuando llegan eventos a un centro de eventos de Azure. Es ideal para procesar grandes volúmenes de datos en tiempo real.
6. Cosmos DB Trigger (Desencadenador de Cosmos DB): Activa tu función cuando se realiza una operación (creación, actualización o eliminación) en una base de datos de Azure Cosmos DB.

Estos son solo algunos de los desencadenadores más comunes en Azure Functions. La plataforma ofrece una amplia gama de opciones para adaptarse a diferentes escenarios y necesidades, lo que te permite crear funciones reactivas y automatizar diversas tareas en la nube.

**¿Cómo se configura y se despliega una Azure Function?**

La configuración y el despliegue de una Azure Function se pueden realizar siguiendo los siguientes pasos:

1. Crear una función: En el portal de Azure, puedes crear una nueva Azure Function desde cero o elegir una plantilla predefinida que se ajuste a tus necesidades. También puedes utilizar herramientas de desarrollo como Visual Studio Code con la extensión de Azure Functions para crear y configurar tus funciones localmente.
2. Configurar los desencadenadores y enlaces: Una vez creada la función, debes configurar el desencadenador que activará la ejecución de la función (por ejemplo, un desencadenador HTTP, un desencadenador de temporizador, etc.). Además, puedes definir enlaces que permitan la comunicación con otros servicios, como conexiones a bases de datos o almacenamiento.
3. Escribir el código de la función: A continuación, debes escribir el código de la función en el lenguaje de programación que elijas (como C#, JavaScript, Python, etc.). El código se encargará de procesar el evento activado por el desencadenador y realizar las acciones necesarias.
4. Probar y depurar localmente: Antes de desplegar la función en Azure, es recomendable probarla y depurarla localmente utilizando las herramientas de desarrollo. Puedes ejecutar la función en tu entorno de desarrollo y realizar pruebas para asegurarte de que funciona correctamente.
5. Crear el recurso de Azure Function: En el portal de Azure, crea un recurso de Azure Function en tu suscripción. Durante el proceso, deberás seleccionar una ubicación geográfica, un plan de consumo o un plan de aplicaciones dedicado, y otros detalles de configuración.
6. Desplegar la función: Una vez que tienes el recurso de Azure Function creado, puedes desplegar tu función desde tu entorno de desarrollo o utilizar las herramientas de implementación proporcionadas por Azure para subir el código y la configuración al recurso de Azure Function.
7. Configurar ajustes adicionales: Puedes configurar ajustes adicionales en Azure Function, como escalado automático, configuración de variables de entorno, configuración de seguridad y otros parámetros según tus requisitos específicos.
8. Monitorear y administrar: Una vez desplegada la función, puedes utilizar las herramientas de monitoreo y administración de Azure para supervisar su rendimiento, ver registros de ejecución, establecer alertas y realizar ajustes según sea necesario.

Estos son los pasos generales para configurar y desplegar una Azure Function.

# Preguntas relacionadas con Azure Functions

**Pregunta 1:**

QUESTION 1 -- Pagina 175

You need to investigate the Azure Function app error message in the development environment. What should you do? 

A. Connect Live Metrics Stream from Application Insights to the Azure Function app and filter the metrics. 

B. Create a new Azure Log Analytics workspace and instrument the Azure Function app with Application Insights. 

C. Update the Azure Function app with extension methods from Microsoft.Extensions.Logging to log events by using the log instance. 

D. Add a new diagnostic setting to the Azure Function app to send logs to Log Analytics. 

Correct Answer: A 

Explanation/Reference: 

Explanation: Azure Functions offers built-in integration with Azure Application Insights to monitor functions. 

The following areas of Application Insights can be helpful when evaluating the behavior, performance, and errors in your functions: 

Live Metrics: View metrics data as it's created in near real-time. Failures, Performance, Metrics

**Pregunta 2:**

QUESTION 5 -- Pagina 131

HOTSPOT 

You need to correct the Azure Logic app error message. Which configuration values should you use? To answer, select the appropriate options in the answer area.

![image-20230602132903410](C:\Users\marin\AppData\Roaming\Typora\typora-user-images\image-20230602132903410.png)

Correct Answer: Box 1: function
						   Box 2: system-assigned

Explanation/Reference: 

Explanation: 

Scenario: You test the Logic app in a development environment. The following error message displays: '400 Bad Request' Troubleshooting of the error shows an HttpTrigger action to call the RequestUserApproval function. 

Note: If the inbound call's request body doesn't match your schema, the trigger returns an HTTP 400 Bad Request error. 

Box 1: function If you have an Azure function where you want to use the system-assigned identity, first enable authentication for Azure functions. 

Box 2: system-assigned Your logic app or individual connections can use either the system-assigned identity or a single userassigned identity, which you can share across a group of logic apps, but not both.

**Pregunta 3:**

QUESTION 21 -- Pagina 45

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution. 

After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen. 

You develop a software as a service (SaaS) offering to manage photographs. Users upload photos to a web service which then stores the photos in Azure Storage Blob storage. The storage account type is Generalpurpose V2. 

When photos are uploaded, they must be processed to produce and save a mobile-friendly version of the image. The process to produce a mobile-friendly version of the image must start in less than one minute. 

You need to design the process that starts the photo processing. 

Solution: Move photo processing to an Azure Function triggered from the blob upload. Does the solution meet the goal? 

A. Yes 

B. No

Correct Answer: A

Explanation/Reference: 

Explanation: Azure Storage events allow applications to react to events. Common Blob storage event scenarios include image or video processing, search indexing, or any file-oriented workflow. 

Events are pushed using Azure Event Grid to subscribers such as Azure Functions, Azure Logic Apps, or even to your own http listener. 

Note: Only storage accounts of kind StorageV2 (general purpose v2) and BlobStorage support event integration. Storage (general purpose v1) does not support integration with Event Grid.