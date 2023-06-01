# Tema 6: Troubleshoot solutions by using Application Insights

PREGUNTAS

1. ¿Qué es Azure Application Insights y cómo se utiliza para el monitoreo de aplicaciones?

   Azure Application Insights es un servicio de supervisión y diagnóstico ofrecido por Microsoft Azure que permite a los desarrolladores obtener información detallada sobre el rendimiento y el comportamiento de sus aplicaciones en la nube.

   - **Recopilación de datos**: Azure Application Insights recopila datos y métricas de rendimiento de tus aplicaciones en tiempo real. Esto incluye información como tiempos de respuesta, rendimiento de solicitudes, excepciones, trazas de registro y uso de recursos.

   - **Análisis y visualización de datos**: Los datos recopilados se analizan y se muestran en paneles de control intuitivos en el portal de Azure. Puedes explorar y visualizar los datos para comprender mejor el comportamiento y el rendimiento de tu aplicación.

   - **Supervisión proactiva**: Application Insights te permite establecer alertas personalizadas basadas en umbrales y métricas específicas. Esto te permite recibir notificaciones en tiempo real cuando ocurren eventos o condiciones inusuales, lo que te ayuda a identificar y resolver problemas rápidamente.

   - **Diagnóstico de problemas**: Application Insights proporciona herramientas de diagnóstico avanzadas para ayudarte a identificar y solucionar problemas en tus aplicaciones. Puedes rastrear y analizar excepciones, realizar seguimiento de solicitudes y correlacionar eventos para entender las causas fundamentales de los problemas de rendimiento.

   - **Integración con DevOps**: Application Insights se integra con varias herramientas y servicios de DevOps, como Azure DevOps, GitHub y Azure Monitor. Esto permite la implementación continua (CI/CD) y la incorporación del monitoreo en el flujo de trabajo de desarrollo.

   - **Integración con Azure**: Application Insights se integra estrechamente con otros servicios de Azure, lo que te permite correlacionar los datos de supervisión con otros eventos y métricas en tu entorno de Azure. Esto proporciona una visión más completa y contextualizada de tu aplicación.

     

2. ¿Cuáles son las principales características y beneficios de Application Insights?

   - **Mejora del rendimiento**: Application Insights te ayuda a identificar cuellos de botella y áreas de mejora en tu aplicación para optimizar su rendimiento y la experiencia del usuario.

   - **Resolución rápida de problemas**: Al proporcionar datos detallados y herramientas de diagnóstico avanzadas, Application Insights facilita la identificación y solución rápida de problemas en tus aplicaciones.

   - **Mayor disponibilidad**: La supervisión proactiva y las alertas te permiten detectar y responder rápidamente a eventos y condiciones inusuales, lo que ayuda a garantizar la disponibilidad continua de tu aplicación.

   - **Optimización de costos**: Al identificar y solucionar problemas de rendimiento, Application Insights te ayuda a optimizar el uso de recursos y reducir costos innecesarios en la nube.

   - **Mejora continua**: Al obtener información valiosa sobre el rendimiento de tu aplicación, puedes realizar ajustes y mejoras continuas para ofrecer una experiencia cada vez mejor a los usuarios.

     

3. ¿Cómo se configura y se utiliza Application Insights para el diagnóstico y solución de problemas en una aplicación?

- **Creación de una instancia de Application Insights**: En el portal de Azure, crea una instancia de Application Insights. Asigna un nombre y selecciona la ubicación y el plan de precios adecuados para tus necesidades.
- **Integración en la aplicación**: Para habilitar la recopilación de datos de Application Insights en tu aplicación, debes agregar el SDK de Application Insights al código fuente de tu aplicación. Dependiendo del lenguaje de programación que estés utilizando, hay diferentes formas de integración, como agregar una dependencia o un paquete NuGet, o importar una biblioteca.
- **Configuración de la telemetría**: Puedes personalizar la recopilación de telemetría según tus necesidades. Por ejemplo, puedes habilitar la recopilación de excepciones, registrar trazas personalizadas o agregar propiedades personalizadas a las solicitudes. Esto se hace mediante la configuración del SDK de Application Insights en tu aplicación.
- **Análisis y visualización de datos**: Una vez que la integración esté configurada y tu aplicación esté en funcionamiento, podrás ver los datos recopilados en el portal de Azure. Utiliza los paneles de control y las herramientas de análisis de Application Insights para explorar y visualizar los datos de rendimiento de tu aplicación. Puedes ver métricas de rendimiento, excepciones, trazas de registro y más.
- **Configuración de alertas**: Puedes configurar alertas personalizadas para recibir notificaciones cuando se superen ciertos umbrales o se produzcan eventos específicos en tu aplicación. Estas alertas te ayudarán a identificar y responder rápidamente a problemas o comportamientos anormales.
- **Diagnóstico de problemas**: Utiliza las herramientas de diagnóstico de Application Insights para investigar y solucionar problemas en tu aplicación. Puedes rastrear excepciones, analizar solicitudes individuales para identificar cuellos de botella, correlacionar eventos y datos, y obtener información detallada sobre el rendimiento de tu aplicación.
- **Mejoras continuas**: Utiliza los datos recopilados por Application Insights para realizar ajustes y mejoras en tu aplicación. Identifica áreas de bajo rendimiento, optimiza el uso de recursos y trabaja en la optimización del rendimiento y la experiencia del usuario.



BATERÍA DE PREGUNTAS

1. **Question 1** **Page 175**. You need to investigate the Azure Function app error message in the development environment.
   What should you do?
   A. Connect Live Metrics Stream from Application Insights to the Azure Function app and filter the metrics.
   B. Create a new Azure Log Analytics workspace and instrument the Azure Function app with Application
   Insights.
   C. Update the Azure Function app with extension methods from Microsoft.Extensions.Logging to log
   events by using the log instance.
   D. Add a new diagnostic setting to the Azure Function app to send logs to Log Analytics.

   - <u>Answer</u>: Option A

   - <u>Explanation</u>: Azure Functions offers built-in integration with Azure Application Insights to monitor functions.

     The following areas of Application Insights can be helpful when evaluating the behavior, performance, and
     errors in your functions:
     Live Metrics: View metrics data as it's created in near real-time.
     Failures
     Performance
     Metrics

     

2. **Question 2 ** **Page 182**. You need to ensure that the solution can meet the scaling requirements for Policy Service.
   Which Azure Application Insights data model should you use?
   A. an Application Insights dependency
   B. an Application Insights event
   C. an Application Insights trace
   D. an Application Insights metric

   - <u>Answer</u>: Option D

   - <u>Explanation</u>: Application Insights provides three additional data types for custom telemetry:
     Trace - used either directly, or through an adapter to implement diagnostics logging using an
     instrumentation framework that is familiar to you, such as Log4Net or System.Diagnostics.

     Event - typically used to capture user interaction with your service, to analyze usage patterns.

     Metric - used to report periodic scalar measurements.
     
     

3. **Question 3 Page 190.** You need to resolve the log capacity issue.
    What should you do?
    A. Create an Application Insights Telemetry Filter
    B. Change the minimum log level in the host.json file for the function
    C. Implement Application Insights Sampling
    D. Set a LogCategoryFilter during startup

  - <u>Answer</u>: Option C
  - <u>Explanation</u>: Scenario, the log capacity issue: Developers report that the number of log message in the trace output for
    the processor is too high, resulting in lost log messages.
    Sampling is a feature in Azure Application Insights. It is the recommended way to reduce telemetry traffic
    and storage, while preserving a statistically correct analysis of application data. The filter selects items that
    are related, so that you can navigate between items when you are doing diagnostic investigations. When
    metric counts are presented to you in the portal, they are renormalized to take account of the sampling, to
    minimize any effect on the statistics.
    Sampling reduces traffic and data costs, and helps you avoid throttling.

 

 

 