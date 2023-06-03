# Tema 6: Troubleshoot solutions by using Application Insights

- ### **¿Qué es Azure Application Insights y cómo se utiliza para el monitoreo de aplicaciones?**

  Application Insights es una extensión de Azure Monitor y proporciona características para supervisar el rendimiento de aplicaciones (también conocida como "APM"). Las herramientas de APM son útiles para supervisar aplicaciones de desarrollo, pruebas y producción de las siguientes maneras:

- De manera proactiva comprende cómo funciona una aplicación.

- De manera reactiva revisa los datos de ejecución de la aplicación para determinar la causa de un incidente.

  Al utilizar Azure Application Insights para el monitoreo de aplicaciones, se puede realizar lo siguiente:

  - **Recopilar datos de telemetría**: Se recopila automáticamente datos de telemetría de las aplicaciones, como trazas de registro, métricas, eventos y excepciones. También se pueden agregar datos de telemetría personalizados para obtener información específica sobre la aplicación.
  - **Monitorear el rendimiento**: Facilita el análisis del rendimiento de la aplicación, incluyendo tiempos de respuesta, tiempos de carga de página, rendimiento de base de datos y más. Application Insights permite identificar cuellos de botella, consultas lentas y otras áreas problemáticas que pueden afectar el rendimiento de la aplicación.
  - **Identificar errores y excepciones**: El servicio registra y notifica automáticamente errores y excepciones que ocurren en la aplicación, lo que permite detectar y solucionar problemas rápidamente. Se puede ver información detallada sobre los errores, como la pila de llamadas y los datos de contexto relevantes.
  - **Realizar análisis de usuarios**: Proporciona información sobre el comportamiento de los usuarios, como la frecuencia de uso, los flujos de navegación y las características utilizadas. Esto ayuda a comprender cómo los usuarios interactúan con la aplicación y permite realizar mejoras basadas en los datos.
  - **Crear paneles y alertas**: Permite la creación de paneles personalizados para visualizar los datos de telemetría y configurar alertas para recibir notificaciones en caso de que se produzcan eventos críticos o problemas específicos.

Application Insights también se puede usar para recopilar y almacenar datos de registro de seguimiento de aplicaciones.

- ### ¿Cuáles son las principales características y beneficios de Application Insights?

  Las principales características y beneficios de Azure Application Insights son las ya mencionadas **recopilación automática de datos de telemetría**, **monitoreo de rendimiento**, **detección y diagnóstico de errores**, **análisis de usuarios y flujos de usuarios**, **paneles de control personalizados y alertas**. Pero además también hay:

  - **Integración con DevOps o GitHub** : Application Insights se integra con el flujo de trabajo de DevOps o GitHub, lo que contribuye al monitoreo de las aplicaciones a lo largo de su ciclo de vida.
  - **Escalabilidad y disponibilidad**: Al ser un servicio de Microsoft Azure, se beneficia de la escalabilidad y disponibilidad de la plataforma. De forma que, es capaz de manejar grandes volúmenes de datos de telemetría y garantizar la disponibilidad de las aplicaciones monitoreadas.

En resumen, Azure Application Insights proporciona una amplia gama de características y beneficios para monitorear y optimizar las aplicaciones. Desde el monitoreo de rendimiento y la detección de errores hasta el análisis de usuarios y la integración con DevOps, Application Insights ayuda a garantizar un alto rendimiento, una experiencia de usuario óptima y una resolución eficiente de problemas.

- ### ¿Cómo se configura y se utiliza Application Insights para el diagnóstico y solución de problemas en una aplicación?

  - **Se crea una instancia de Application Insights**: En el portal de Azure, se crea una instancia de Application Insights siguiendo los pasos correspondientes. En particular, se asigna un nombre único, se selecciona la suscripción, el grupo de recursos y la ubicación adecuada.
  - **Se integrar Application Insights en la aplicación**: Application Insights ofrece SDKs para diferentes lenguajes y plataformas. Se selecciona el SDK correspondiente a la aplicación y se siguen las instrucciones de instalación y configuración proporcionadas por Microsoft.
  - **Se agrega la clave de instrumentación**: Se alamcena la clave de instrumentación de la instancia de Application Insights creada. Esta clave se agrega a la configuración de la aplicación para que pueda enviar los datos de telemetría a la instancia de Application Insights.
  - **Se recopilan los datos de telemetría**: Con la integración y la clave de instrumentación configuradas, Application Insights empezará a recopilar automáticamente datos de telemetría de la aplicación. Dichos datos se enviarán a la instancia de Application Insights para que sean analizados.
  - **Explorar y analizar los datos**: Desde el portal de Azure se accede a la instancia creada de Application Insights. En el portal, encontrarás diversas herramientas y paneles para explorar y analizar los datos de telemetría recopilados. 
  - **Se establecen las alertas**: Se configuran las alertas para recibir notificaciones cuando se produzcan eventos importantes o problemas críticos en la aplicación. 
  - **Se utilizan las herramientas de diagnóstico y solución de problemas**:  Se utilizan herramientas como el explorador de solicitudes, el análisis de excepciones, el seguimiento de dependencias y más para investigar y solucionar los diferentes problemas.

- ### Question 1, pág 175

*You need to investigate the Azure Function app error message in the development environment. What should you do?*

*A. Connect Live Metrics Stream from Application Insights to the Azure Function app and filter the metrics.*

*B. Create a new Azure Log Analytics workspace and instrument the Azure Function app with Application Insights.*

*C. Update the Azure Function app with extension methods from Microsoft.Extensions.Logging to log events by using the log instance.* 

*D. Add a new diagnostic setting to the Azure Function app to send logs to Log Analytics.*

A, dado que Azure Functions ofrece integración incorporada con Azure Application Insights para monitorear funciones. De modo que, el monitoreo de aplicaciones, contenido con application Insights,  puede evaluar el comportamiento, el rendimiento y los errores en las funciones.

- ### Question 2, pág 182

*You need to ensure that the solution can meet the scaling requirements for Policy Service.* 

*Which Azure Application Insights data model should you use?* 

*A. an Application Insights dependency.* 

*B. an Application Insights event.* 

*C. an Application Insights trace.*

*D. an Application Insights metric.*

D, pues las métricas proporcionan un modo de medir y rastrear valores específicos. Esto facilita la obtención de información sobre el rendimiento y la escalabilidad de las aplicaciones, lo que te permite tomar decisiones informadas sobre la escalabilidad del servicio de políticas. 

Por otro lado, las dependencias se usan para rastrear dependencias externas, como llamadas a bases de datos o APIs, y sus tiempos de respuesta. Un evento es un modelo de datos de propósito general para rastrear eventos discretos u ocurrencias en tu aplicación, pero no están diseñados para monitoreo y escalabilidad. Finalmente, las trazas se emplean para registrar información de diagnóstico y puede ser útil para solucionar problemas, pero al igual que los eventos, no presentan las características necesarias para el monitoreo y la escalabilidad.

- ### Question 6, pág 197

*You are developing an ASP.NET Core Web API web service. The web service uses Azure Application Insights for all telemetry and dependency tracking. The web service reads and writes data to a database other than Microsoft SQL Server.* 

*You need to ensure that dependency tracking works for calls to the third-party database.* 

*Which two dependency telemetry properties should you use? Each correct answer presents part of the solution.* 

*NOTE: Each correct selection is worth one point.*

*A. Telemetry.Context.Cloud.RoleInstance*

*B. Telemetry.Id* 

*C. Telemetry.Name* 

*D. Telemetry.Context.Operation.Id* 

*E. Telemetry.Context.Session.Id*

Para que el seguimiento de dependencias funcione con las llamadas a la base de datos de terceros en el servicio web ASP.NET Core Web API utilizando Azure Application Insights, se recurren a las siguientes propiedades de telemetría de dependencia:

D. Telemetry.Context.Operation.Id: Propiedad que representa el ID de la operación, que es un identificador único para la operación que se está realizando. Ayuda a correlacionar diferentes eventos de telemetría relacionados con la misma operación.

E. Telemetry.Context.Session.Id: Propiedad asociada al ID de la sesión, que es un identificador único para la sesión de usuario o un grupo lógico de operaciones relacionadas. Ayuda a agrupar y analizar eventos de telemetría dentro de la misma sesión.

Estas propiedades permitirán rastrear y correlacionar las llamadas realizadas a la base de datos de terceros, lo que facilitará un mejor análisis y comprensión de las dependencias del servicio web.

