# Tema 5: Implement Azure App Service Web Apps



PREGUNTAS

1. ¿Cuáles son las características principales de Azure App Service?

   - **Plataforma como servicio (PaaS)**: Azure App Service es un servicio de plataforma como servicio que permite a los desarrolladores crear, implementar y escalar aplicaciones web y móviles sin tener que preocuparse por la infraestructura subyacente.
   - Compatibilidad con múltiples lenguajes: Puedes desarrollar aplicaciones web en varios lenguajes de programación populares como .NET, Java, Node.js, Python y PHP.
   - **Escalado automático**: Azure App Service ofrece capacidades de escalado automático que ajustan automáticamente la capacidad de tu aplicación en función de la carga de trabajo. Esto garantiza un rendimiento óptimo y reduce los costos innecesarios.
   - **Integración con DevOps**: Azure App Service se integra con herramientas y servicios de DevOps como Azure DevOps, GitHub y Azure Pipelines. Esto facilita la implementación continua (CI/CD) y te permite entregar actualizaciones de forma rápida y segura.
   - **Integración con servicios de Azure**: Azure App Service se integra estrechamente con otros servicios de Azure, lo que te permite aprovechar funcionalidades adicionales como bases de datos SQL de Azure, almacenamiento en la nube y servicios de autenticación y autorización.
   - **Administración y supervisión**: Azure App Service proporciona herramientas y paneles de control para administrar y supervisar tus aplicaciones. Puedes ver registros de aplicaciones, métricas de rendimiento y realizar ajustes de configuración.
   - **Seguridad y cumplimiento normativo**: Azure App Service ofrece características de seguridad avanzadas, como autenticación y autorización basadas en Azure Active Directory. 

2. ¿Cómo se configura y escala una aplicación web en Azure App Service?

   - **Creación de la instancia de Azure App Service**: En el portal de Azure, crea una instancia de Azure App Service seleccionando el plan de precios adecuado y configurando los detalles de la instancia, como el nombre, la región y el sistema operativo.

   - **Despliegue de la aplicación**: Sube tu código fuente o el paquete de la aplicación al servicio de Azure App Service. Puedes hacerlo a través del portal de Azure, o mediante el uso de herramientas de línea de comandos como Azure CLI o Azure PowerShell.

   - <u>Hay 2 tipos de escalado</u>: 

     - **Escalado vertical**: Si necesitas aumentar o disminuir los recursos de hardware asignados a tu aplicación, puedes realizar un escalado vertical. Esto implica cambiar el tamaño de la instancia de Azure App Service, lo que ajustará la capacidad de procesamiento y la memoria disponibles para tu aplicación.

     - **Escalado horizontal**: Para manejar aumentos significativos en la carga de trabajo, puedes escalar horizontalmente agregando instancias adicionales de tu aplicación. Esto se conoce como escalado horizontal y se puede configurar manualmente o mediante reglas de escalado automático basadas en métricas de rendimiento, como la CPU o el número de solicitudes por segundo.

3. ¿Qué es un plan de App Service y cómo se relaciona con las aplicaciones web?

   Un plan de App Service en Azure es una entidad que define la capacidad y los recursos asignados a las aplicaciones web alojadas en Azure App Service. Proporciona una infraestructura para ejecutar y escalar las aplicaciones web de manera eficiente. 

   Relación entre plan de App Service y aplicaciones web:

   -  Las aplicaciones web se asignan a un plan de App Service específico. Varias aplicaciones web pueden compartir el mismo plan de App Service, lo que permite optimizar el uso de recursos y reducir costos.
   - Puedes realizar un escalado vertical del plan de App Service para aumentar o disminuir los recursos asignados a todas las aplicaciones web que se ejecutan en él. Esto afectará a todas las aplicaciones web asociadas al plan.
   - Puedes realizar un escalado horizontal del plan de App Service al aumentar o disminuir el número de instancias del plan. Esto implica agregar o quitar instancias de la máquina virtual subyacente que aloja las aplicaciones web.
   - Cada plan de App Service proporciona un nivel de aislamiento para las aplicaciones web. Esto significa que las aplicaciones web en un plan de mayor capacidad tienen recursos dedicados y aislados, lo que garantiza un mejor rendimiento y seguridad.




BATERÍA DE PREGUNTAS.

1. **Question 11** **Page 32**. You are developing an Azure Web App. You configure TLS mutual authentication for the web app.
   You need to validate the client certificate in the web app. To answer, select the appropriate options in the
   answer area.

   - <u>Answer</u>:

     HTTP request header y Base64

   - <u>Explanation</u>: Si estás utilizando ASP.NET y has configurado tu aplicación para usar la autenticación con certificado de cliente, el certificado estará disponible a través de la propiedad HttpRequest.ClientCertificate. Para otras pilas de aplicaciones, el certificado de cliente estará disponible en tu aplicación a través de un valor codificado en base64 en el encabezado de solicitud "X-ARR-ClientCert". Tu aplicación puede crear un certificado a partir de este valor y luego utilizarlo para fines de autenticación y autorización en tu aplicación

     

2. **Question 12** **Page 33**. You are developing a Docker/Go using Azure App Service Web App for Containers. You plan to run the container in an App Service on Linux. You identify a Docker container image to use.
   None of your current resource groups reside in a location that supports Linux. You must minimize the
   number of resource groups required.
   You need to create the application and perform an initial deployment.
   Which three Azure CLI commands should you use to develop the solution? To answer, move the
   appropriate commands from the list of commands to the answer area and arrange them in the correct
   order.
   
   - <u>Answer</u>: 
   
     az group create
   
     az appservice plan create
   
     az webapp create
   
   - <u>Explanation</u>: Puedes alojar aplicaciones nativas de Linux en la nube utilizando Azure Web Apps. Para crear una aplicación web para contenedores, debes ejecutar comandos de Azure CLI que creen un grupo, luego un plan de servicio y, finalmente, la propia aplicación web.
   
     Paso 1: az group create En Cloud Shell, crea un grupo de recursos con el comando az group create.
   
     Paso 2: az appservice plan create En Cloud Shell, crea un plan de servicio de App Service en el grupo de recursos con el comando az appservice plan create.
   
     Paso 3: az webapp create En Cloud Shell, crea una aplicación web en el plan de servicio myAppServicePlan con el comando az webapp create. No olvides reemplazar <nombre-de-aplicación> con un nombre único para tu aplicación y <docker-ID> con tu ID de Docker.
   
     
   
3.  **Question 13** **Page 35**. Fourth Coffee has an ASP.NET Core web app that runs in Docker. The app is mapped to the
   www.fourthcoffee.com domain. Fourth Coffee is migrating this application to Azure.
   You need to provision an App Service Web App to host this docker image and map the custom domain to
   the App Service web app.
   A resource group named FourthCoffeePublicWebResourceGroup has been created in the WestUS region
   that contains an App Service Plan named AppServiceLinuxDockerPlan.
   Which order should the CLI commands be used to develop the solution? To answer, move all of the Azure
   CLI commands from the list of commands to the answer area and arrange them in the correct order.

   - <u>Answer and Explanation</u>: 

     Step 1: #bin/bash
     The appName is used when the webapp-name is created in step 2.

     Step 2: az webapp config hostname add
     The webapp-name is used when the webapp is created in step 3.
     Step 3: az webapp create
     Create a web app. In the Cloud Shell, create a web app in the myAppServicePlan App Service plan with the
     az webapp create command.

     Step 4: az webapp confing container set

     In Create a web app, you specified an image on Docker Hub in the az webapp create command. This is
     good enough for a public image. To use a private image, you need to configure your Docker account ID and
     password in your Azure web app.
     In the Cloud Shell, follow the az webapp create command with az webapp config container set.