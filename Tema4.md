# Tema 4

## Develop solutions that use blob storage

*1.-* ¿Qué es Azure Blob storage y cómo se utiliza para almacenar datos no estructurados?

    Azure Blob storage es un servicio de almacenamiento en la nube de Microsoft Azure que permite almacenar grandes cantidades de datos no estructurados, como imágenes, videos, archivos de audio y documentos. Se utiliza para almacenar datos que no se ajustan a un modelo de datos relacional o jerárquico, y que no requieren una estructura definida.

    Los datos se pueden cargar en el contenedor de Blob a través de una variedad de métodos, como la carga manual de archivos, la integración con aplicaciones y servicios de terceros, o la automatización de procesos mediante scripts y herramientas de línea de comandos. Una vez que los datos están almacenados en Azure Blob storage, se pueden acceder y gestionar a través de una variedad de herramientas y servicios de Azure, como Azure Portal, Azure Storage Explorer y Azure Functions.

*2.-* ¿Cuáles son los tipos de blobs que se pueden almacenar en Azure Blob storage?

    En Azure Blob storage se pueden almacenar diferentes tipos de blobs:
        1- Blobs de bloque.
        2- Blobs de página.
        3- Blobs de anexo.

*3.-* ¿Cómo se accede y se administra el almacenamiento de blobs en Azure?

    Se puede utilizar el portal de Azure, la CLI de Azure, PowerShell de Azure o una de las bibliotecas de cliente de Azure Storage. En el portal de Azure, se puede crear una cuenta de almacenamiento y luego crear un contenedor de blobs dentro de esa cuenta. Desde allí, se pueden cargar, descargar y eliminar blobs, así como configurar permisos de acceso y configuraciones de almacenamiento.

## Preguntas 

*1.-* You develop a software as a service (SaaS) offering to manage photographs. Users upload photos to a web service which then stores the photos in Azure Storage Blob storage. The storage account type is General- purpose V2.
When photos are uploaded, they must be processed to produce and save a mobile-friendly version of the image. The process to produce a mobile-friendly version of the image must start in less than one minute.

You need to design the process that starts the photo processing.

 Solution: Trigger the photo processing from Blob storage events. 
 
Does the solution meet the goal?

    A. Yes

    B. No

    Correct Answer: B 

    Explanation:
    You need to catch the triggered event, so move the photo processing to an Azure Function triggered from the blob upload
    Note: Azure Storage events allow applications to react to events. Common Blob storage event scenarios include image or video processing, search indexing, or any file-oriented workflow.
    Events are pushed using Azure Event Grid to subscribers such as Azure Functions, Azure Logic Apps, or even to your own http listener.
    Note: Only storage accounts of kind StorageV2 (general purpose v2) and BlobStorage support event integration. Storage (general purpose v1) does not support integration with Event Grid.


*2.-* You develop a software as a service (SaaS) offering to manage photographs. Users upload photos to a web service which then stores the photos in Azure Storage Blob storage. The storage account type is General- purpose V2.
When photos are uploaded, they must be processed to produce and save a mobile-friendly version of the image. The process to produce a mobile-friendly version of the image must start in less than one minute.

You need to design the process that starts the photo processing.

Solution: Move photo processing to an Azure Function triggered from the blob upload.

Does the solution meet the goal?

    A. Yes 

    B. No

    Correct Answer: A

    Explanation:
    Azure Storage events allow applications to react to events. Common Blob storage event scenarios include image or video processing, search indexing, or any file-oriented workflow.
    Events are pushed using Azure Event Grid to subscribers such as Azure Functions, Azure Logic Apps, or even to your own http listener.
    Note: Only storage accounts of kind StorageV2 (general purpose v2) and BlobStorage support event integration. Storage (general purpose v1) does not support integration with Event Grid.

*3.-* QUESTION 24
You are developing an Azure Function App that processes images that are uploaded to an Azure Blob container. Images must be processed as quickly as possible after they are uploaded, and the solution must minimize latency. You create code to process images when the Function App is triggered.

You need to configure the Function App. 

What should you do?

    A. Use an App Service plan. Configure the Function App to use an Azure Blob Storage input trigger.

    B. Use a Consumption plan. Configure the Function App to use an Azure Blob Storage trigger.

    C. Use a Consumption plan. Configure the Function App to use a Timer trigger.

    D. Use an App Service plan. Configure the Function App to use an Azure Blob Storage trigger.

    E. Use a Consumption plan. Configure the Function App to use an Azure Blob Storage input trigger.

    Correct Answer: B

    Explanation:
    The Blob storage trigger starts a function when a new or updated blob is detected. The blob contents are provided as input to the function.
    The Consumption plan limits a function app on one virtual machine (VM) to 1.5 GB of memory.