# Preguntas - Tema 1

**¿Qué es Azure CDN y cuál es su propósito en el despliegue de aplicaciones web?**

Azure CDN es un servicio de entrega de contenido que acelera y mejora la disponibilidad de aplicaciones web. Almacenando en caché contenido estático en servidores distribuidos globalmente, reduce la latencia y acelera la carga para los usuarios. Además, ofrece características como compresión de archivos, manejo de contenido enriquecido y protección contra ataques DDoS. En resumen, Azure CDN optimiza la entrega de contenido estático en aplicaciones web, brindando una experiencia de usuario más rápida y confiable.

**¿Cuáles son los beneficios de utilizar Azure CDN en términos de rendimiento y escalabilidad?**

Utilizar Azure CDN ofrece varios beneficios en términos de rendimiento y escalabilidad. Estos son algunos de ellos:

1. Mejora del rendimiento: Azure CDN distribuye el contenido estático a través de una red global de servidores, lo que permite a los usuarios recibir el contenido desde el servidor más cercano físicamente. Esto reduce la latencia y acelera la velocidad de carga de la aplicación web, brindando una mejor experiencia de usuario.
2. Tiempos de carga más rápidos: Al almacenar en caché el contenido estático en servidores distribuidos, Azure CDN entrega el contenido de manera más rápida y eficiente. Esto resulta en tiempos de carga más rápidos para los usuarios, lo que reduce la posibilidad de abandono de la aplicación.
3. Escalabilidad global: Al utilizar una red de servidores distribuidos en todo el mundo, Azure CDN puede manejar cargas de tráfico significativas y escalarse automáticamente según las necesidades. Esto garantiza que la aplicación web pueda manejar altos volúmenes de usuarios simultáneos sin comprometer el rendimiento.
4. Ahorro de ancho de banda: Al utilizar Azure CDN, se reduce la carga de tráfico en el servidor central, ya que gran parte del contenido estático se entrega desde los servidores de CDN distribuidos. Esto ahorra ancho de banda y permite que el servidor se enfoque en tareas más críticas.
5. Disponibilidad mejorada: Al tener múltiples servidores distribuidos globalmente, Azure CDN proporciona una mayor disponibilidad para los usuarios. Si un servidor falla o está fuera de servicio, la red de CDN automáticamente enruta el tráfico a servidores alternativos, evitando interrupciones en el acceso al contenido.

En resumen, Azure CDN mejora el rendimiento al acelerar la entrega de contenido estático, proporciona escalabilidad global para manejar grandes volúmenes de usuarios y garantiza una mayor disponibilidad al distribuir el tráfico en servidores redundantes. Estos beneficios contribuyen a una experiencia de usuario más rápida y confiable, así como a la capacidad de escalar la aplicación según las necesidades del negocio.

**¿Cómo se configura y se utiliza Azure CDN para acelerar la entrega de contenido estático y dinámico en una aplicación web?**

Para configurar y utilizar Azure CDN para acelerar la entrega de contenido estático y dinámico en una aplicación web, puedes seguir los siguientes pasos:

1. Crear una cuenta de Azure CDN: Accede al portal de Azure (portal.azure.com) y crea una cuenta de Azure CDN en tu suscripción. Selecciona el tipo de CDN adecuado según tus necesidades, como Azure CDN Standard o Azure CDN Premium.
2. Configurar un punto de conexión (endpoint): Un punto de conexión es la URL que utilizarás para acceder al contenido a través de Azure CDN. Configura un nuevo punto de conexión y proporciona la URL del origen de tu aplicación web, que puede ser un servidor web o un almacenamiento en la nube como Azure Blob Storage.
3. Configurar reglas de origen: Puedes definir reglas de origen para especificar qué contenido se debe almacenar en caché y cómo se debe manejar. Por ejemplo, puedes configurar reglas para cachear archivos con una determinada extensión o establecer tiempos de expiración para el contenido en caché.
4. Asignar un dominio personalizado (opcional): Si deseas utilizar un dominio personalizado en lugar de la URL predeterminada proporcionada por Azure, puedes asignar tu propio dominio al punto de conexión de Azure CDN.
5. Configurar la propagación de DNS (opcional): Si has asignado un dominio personalizado, deberás configurar la propagación de DNS para que apunte al punto de conexión de Azure CDN. Esto permitirá que las solicitudes de los usuarios se dirijan al CDN.
6. Validar y probar la configuración: Una vez configurado, valida que el CDN esté funcionando correctamente accediendo al contenido a través de la URL del punto de conexión. Puedes probar la entrega de contenido estático y dinámico para asegurarte de que el CDN está acelerando la carga correctamente.
7. Monitorear y optimizar el rendimiento: Utiliza las herramientas de monitoreo proporcionadas por Azure CDN para evaluar el rendimiento y la utilización del servicio. Puedes realizar ajustes en las reglas de origen y en la configuración del CDN para optimizar aún más la entrega de contenido.

Recuerda que la configuración exacta puede variar dependiendo de tu caso de uso y de la versión específica de Azure CDN que estés utilizando.



# Preguntas relacionadas con Azure CDN

**Pregunta 1:**

QUESTION 1 -- Pagina 4

HOTSPOT 

You need to configure Azure CDN for the Shipping web site. 

Which configuration options should you use? To answer, select the appropriate options in the answer area

![image-20230602132103636](C:\Users\marin\AppData\Roaming\Typora\typora-user-images\image-20230602132103636.png)

Correct Answer: Box 1:Standard
						   Box 2:Akamai 
						   Box 3:Dynamic site acceleration

Explanation/Reference:

Explanation: 

Scenario: Shipping website Use Azure Content Delivery Network (CDN) and ensure maximum performance for dynamic content while minimizing latency and costs. 

Tier: Standard 

Profile: Akamai 

Optimization: Dynamic site acceleration Dynamic site acceleration (DSA) is available for Azure CDN Standard from Akamai, Azure CDN Standard from Verizon, and Azure CDN Premium from Verizon profiles. 

DSA includes various techniques that benefit the latency and performance of dynamic content. Techniques include route and network optimization, TCP optimization, and more. 

You can use this optimization to accelerate a web app that includes numerous responses that aren't cacheable. Examples are search results, checkout transactions, or real-time data. You can continue to use core Azure CDN caching capabilities for static data.

**Pregunta 2:**

QUESTION 8 -- Pagina 199

HOTSPOT 

You are developing an Azure App Service hosted ASP.NET Core web app to deliver video-on-demand streaming media. You enable an Azure Content Delivery Network (CDN) Standard for the web endpoint. Customer videos are downloaded from the web app by using the following example URL: http:// www.contoso.com/content.mp4?quality=1 

All media content must expire from the cache after one hour. Customer videos with varying quality must be delivered to the closest regional point of presence (POP) node. 

You need to configure Azure CDN caching rules. Which options should you use? To answer, select the appropriate options in the answer area. 

![image-20230602132424226](C:\Users\marin\AppData\Roaming\Typora\typora-user-images\image-20230602132424226.png)

Correct Answer: Box 1:Override
						   Box 2:1 hour 
						   Box 3:Cache every unique URL

Explanation/Reference: 

Explanation: Box 1: Override Override: Ignore origin-provided cache duration; use the provided cache duration instead. This will not override cache-control: no-cache. Set if missing: Honor origin-provided cache-directive headers, if they exist; otherwise, use the provided cache duration. 

Incorrect: Bypass cache: Do not cache and ignore origin-provided cache-directive headers. 

Box 2: 1 hour All media content must expire from the cache after one hour. 

Box 3: Cache every unique URL 

Cache every unique URL: In this mode, each request with a unique URL, including the query string, is treated as a unique asset with its own cache. For example, the response from the origin server for a request for example.ashx?q=test1 is cached at the POP node and returned for subsequent caches with the same query string. A request for example.ashx?q=test2 is cached as a separate asset with its own time-tolive setting. 

Incorrect Answers: Bypass caching for query strings: In this mode, requests with query strings are not cached at the CDN POP node. The POP node retrieves the asset directly from the origin server and passes it to the requestor with each request. 

Ignore query strings: Default mode. In this mode, the CDN point-of-presence (POP) node passes the query strings from the requestor to the origin server on the first request and caches the asset. All subsequent requests for the asset that are served from the POP ignore the query strings until the cached asset expires.

**Pregunta 3:**

QUESTION 6 -- Pagina 88

DRAG DROP 

Your company has several websites that use a company logo image. You use Azure Content Delivery Network (CDN) to store the static image. You need to determine the correct process of how the CDN and the Point of Presence (POP) server will distribute the image and list the items in the correct order. In which order do the actions occur? To answer, move all actions from the list of actions to the answer area and arrange them in the correct order.

![image-20230602132539216](C:\Users\marin\AppData\Roaming\Typora\typora-user-images\image-20230602132539216.png)

Correct Answer: Step 1: A user requests the image.. A user requests a file (also called an asset) by using a URL
						   Step 2: If no edge servers in the POP have the.. If no edge servers in the POP have the file in their cache, the POP requests the file from the origin server
						   Step 3: The origin server returns the.. The origin server returns the file to an edge server in the POP. An edge server in the POP caches the file and returns the file to the original requestor
							Step 4: Subsequent requests for.. Additional users can then request the same file by using the same URL that the original user used, and can also be directed to the same POP.

Explanation/Reference: 

Explanation: 

Step 1: A user requests the image.. A user requests a file (also called an asset) by using a URL with a special domain name, such as .azureedge.net. This name can be an endpoint hostname or a custom domain. The DNS routes the request to the best performing POP location, which is usually the POP that is geographically closest to the user. 

Step 2: If no edge servers in the POP have the.. If no edge servers in the POP have the file in their cache, the POP requests the file from the origin server. The origin server can be an Azure Web App, Azure Cloud Service, Azure Storage account, or any publicly accessible web server. 

Step 3: The origin server returns the.. The origin server returns the file to an edge server in the POP. An edge server in the POP caches the file and returns the file to the original requestor (Alice). The file remains cached on the edge server in the POP until the time-to-live (TTL) specified by its HTTP headers expires. If the origin server didn't specify a TTL, the default TTL is seven days. 

Step 4: Subsequent requests for.. Additional users can then request the same file by using the same URL that the original user used, and can also be directed to the same POP. 

If the TTL for the file hasn't expired, the POP edge server returns the file directly from the cache. This process results in a faster, more responsive user experience.