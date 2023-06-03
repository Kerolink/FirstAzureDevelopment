# ¿Cuáles son las características principales de Azure App Service? 

```

Azure App Service es un servicio de plataforma como servicio (PaaS) en Microsoft Azure que permite a los desarrolladores crear, implementar y escalar aplicaciones web y móviles fácilmente. Estas son algunas de las características principales de Azure App Service:

Flexibilidad de lenguaje y plataforma: Azure App Service admite una amplia variedad de lenguajes de programación, como .NET, Java, Node.js, Python y PHP. También es compatible con múltiples plataformas, incluyendo Windows y Linux.

Implementación rápida: Permite implementar aplicaciones rápidamente a través de diferentes opciones, como la implementación continua desde repositorios de código fuente como GitHub, Bitbucket y Azure DevOps. También es posible realizar implementaciones manuales a través de FTP, Git o archivos ZIP.

Escalabilidad automática: Azure App Service proporciona la capacidad de escalar automáticamente la aplicación en función de la demanda. Puede ajustar el número de instancias en función del tráfico y configurar reglas de escalado automático para manejar cargas de trabajo variables.

Alta disponibilidad: El servicio garantiza una alta disponibilidad y tolerancia a fallos al distribuir las aplicaciones en múltiples instancias y regiones de Azure. También ofrece opciones para realizar copias de seguridad y restaurar aplicaciones fácilmente.

Integración con servicios de Azure: Azure App Service se integra estrechamente con otros servicios de Azure, lo que permite agregar funcionalidades adicionales a las aplicaciones. Algunos ejemplos incluyen integración con Azure SQL Database, Azure Blob Storage, Azure Active Directory y Azure Functions.

Gestión de dominios personalizados y SSL: Puede asociar dominios personalizados a las aplicaciones y configurar certificados SSL para garantizar conexiones seguras.

Monitoreo y diagnóstico: Azure App Service proporciona herramientas para monitorear y diagnosticar el rendimiento de las aplicaciones. Puede ver registros de aplicaciones, métricas de rendimiento, realizar pruebas de rendimiento y configurar alertas para detectar problemas.

Escalabilidad vertical y horizontal: Permite escalar verticalmente ajustando los recursos de las instancias (como CPU y memoria) y escalar horizontalmente agregando más instancias a medida que aumenta la carga de trabajo.

Estas son solo algunas de las características principales de Azure App Service. El servicio ofrece muchas más funcionalidades para facilitar el desarrollo, implementación y administración de aplicaciones web y móviles en Azure.
```



# ¿Cómo se configura y escala una aplicación web en Azure App Service?

```

Para configurar y escalar una aplicación web en Azure App Service, sigue los siguientes pasos:

Crear una instancia de Azure App Service: Ve a Azure Portal (portal.azure.com) y crea una instancia de Azure App Service. Proporciona un nombre único para la aplicación, selecciona el plan de servicio (tier) y la región donde se ejecutará la aplicación.

Configurar la aplicación web: Después de crear la instancia de Azure App Service, puedes configurar los ajustes de la aplicación web. Puedes establecer la versión de .NET, lenguaje de programación, configuraciones de la aplicación, ajustes de enrutamiento, etc. También puedes conectar tu código fuente desde un repositorio de código o implementar directamente desde una solución local.

Escalar la aplicación: Azure App Service permite escalar horizontalmente y verticalmente tu aplicación web para satisfacer las demandas de tráfico. Hay varias opciones de escala disponibles:

Escalar verticalmente: Puedes cambiar el tamaño de la instancia de Azure App Service para aumentar la capacidad de recursos, como CPU y RAM, asignados a tu aplicación web.

Escalar horizontalmente: Puedes aumentar el número de instancias de la aplicación web para distribuir la carga de tráfico. Esto se conoce como escalado de instancias. Azure App Service proporciona opciones automáticas y manuales para escalar horizontalmente.

Configurar reglas de enrutamiento: Puedes utilizar las reglas de enrutamiento para dirigir el tráfico de manera específica. Por ejemplo, puedes establecer una regla para enviar una parte del tráfico a una versión de prueba de la aplicación.

Configurar la supervisión y el registro: Azure App Service proporciona herramientas de supervisión y registro integradas que te permiten monitorear el rendimiento de tu aplicación web, ver registros de aplicaciones y configurar alertas en caso de problemas.

Configurar dominios personalizados y SSL: Puedes asociar tu propio dominio personalizado con tu aplicación web en Azure App Service. Además, puedes habilitar SSL para asegurar las comunicaciones mediante certificados SSL.

Estos son solo los pasos básicos para configurar y escalar una aplicación web en Azure App Service. Azure App Service ofrece muchas más características y opciones avanzadas para adaptarse a diferentes escenarios y requisitos.
```



# ¿Qué es un plan de App Service y cómo se relaciona con las aplicaciones web?

```

Un plan de App Service es un servicio de Azure que proporciona los recursos necesarios para hospedar y escalar aplicaciones web en la nube. En términos sencillos, es un entorno de hospedaje para aplicaciones web en Azure.

Cuando se crea una aplicación web en Azure, debe asignarse a un plan de App Service. Un plan de App Service define las características y los recursos disponibles para la aplicación web. Estos recursos incluyen potencia de procesamiento, memoria, almacenamiento y capacidad de escalado.

El plan de App Service establece un límite para los recursos disponibles y también afecta al costo del servicio. Azure ofrece diferentes niveles de planes de App Service, como Free, Shared, Basic, Standard y Premium, cada uno con diferentes características y precios.

Una vez que una aplicación web está asignada a un plan de App Service, puede aprovechar las ventajas de la escalabilidad automática y el equilibrio de carga. Por ejemplo, si una aplicación web experimenta un aumento en el tráfico, el plan de App Service puede escalar automáticamente los recursos para manejar la carga adicional.

En resumen, un plan de App Service es el entorno de hospedaje y los recursos asociados que proporciona Azure para las aplicaciones web. Permite escalar y administrar las aplicaciones web de manera eficiente en la nube.
```

# Preguntas de la Batería

# QUESTION 3 Pag 23
HOTSPOT
You are implementing a software as a service (SaaS) ASP.NET Core web service that will run as an Azure Web App. The web service will use an on-premises SQL Server database for storage. The web service also includes a WebJob that processes data updates. Four customers will use the web service.
Each instance of the WebJob processes data for a single customer and must run as a singleton
instance.
Each deployment must be tested by using deployment slots prior to serving production data.
Azure costs must be minimized.
Azure resources must be located in an isolated network.
You need to configure the App Service plan for the Web App.
How should you configure the App Service plan? To answer, select the appropriate settings in the answer
area.

## Respuesta

Each deployment must be tested by using deployment slots prior to serving production data

**Por lo tanto 4 porque serán los dos servers que necesitamos y los otros dos de deployment**

Azure resources must be located in an isolated network

**Pricing Tier Isolated evidentemente**



# QUESTION 5 pag 27

## Respuesta

Está correcto el pdf

El primer cuadro es un solo comando ``az appservice plan create`` para crear el service plan

Los dos siguientes cuadros constituyen el mismo comando: creates an Azure web app and related services in Azure App Service

``az webapp create`` primero, creamos el Web App

``--plan $webappname`` segundo que indica que lo meteremos en el service plan

Los dos últimos son un único comando: You need to automatically deploy code from GitHub to the newly created web app.

``az webapp deplyment``

``--repo-url $gitrepo --branch master --manual-integration``

the manual-integration means it won't automatically update when the repo does

git clone is a command you would use to clone the repo to your computer, we don't want to do that

1. we want to tell azure that when it wants to get the code for your web app, where the repo is



# QUESTION 16 pag 39

HOTSPOT
A company is developing a Java web app. The web app code is hosted in a GitHub repository located at
https://github.com/Contoso/webapp.
The web app must be evaluated before it is moved to production. You must deploy the initial code release
to a deployment slot named staging.
You need to create the web app and deploy the code.
How should you complete the commands? To answer, select the appropriate options in the answer area.

## Respuesta

pdf correcto

1. ``az group`` because -> $resourcegroupname
2. ``appservice plan`` becuase-> --sku y obviamente crearemos el plan antes que el web app
3. `webapp` because -> Lo estamos metiendo en el plan ``--plan $webappname`` (You need to create the web app and deploy the code)
4. ``webapp deployment slot`` Creamos un slot para nuestras pruebas (The web app must be evaluated before it is moved to production)
5. ``webapp deplyment source`` Al slot creado le metemos nuestro codigo de github (You must deploy the initial code release to a deployment slot named staging)