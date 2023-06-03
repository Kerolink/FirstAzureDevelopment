# Tema 2: Implement Azure Functions

- ### **¿Qué son las Azure Functions y para qué se utilizan?**

Azure Functions es una solución sin servidor que permite escribir menos código, mantener menos infraestructura y ahorrar costos. En lugar de tener que hacerse cargo de la implementación y el mantenimiento de los servidores, la infraestructura en la nube proporciona todos los recursos actualizados necesarios para mantener las aplicaciones en ejecución.



- ### **¿Cuáles son los desencadenadores (triggers) más comunes en Azure Functions?**

Los desencadenadores provocan la ejecución de una función. Un desencadenador define cómo se invoca una función y cada función debe tener exactamente un desencadenador. Los desencadenadores tienen datos asociados, que a menudo son la carga de la función.

Los desencadenadores más comunes en Azure Functions son:

1. **Timer** (``TimerTrigger``).
2. **Queue Storage** (``QueueTrigger``).
3. **Blob Storage** ( ``BlobTrigger``).
4. **Azure Service Bus** (``ServiceBusTrigger``).
5. **Azure Cosmos DB** (``CosmosDBTrigger``).
6. **Event Hubs** (``EventHubTrigger``).
7. **HTTP** (``HttpTrigger``).
8. **Event Grid** (``BlobTrigger``).



- ### **¿Cómo se configura y se despliega una Azure Function?**

  - **Se crea una cuenta de almacenamiento en Azure**: Se introduce el nombre del grupo del recursos, el nombre de la cuenta de almacenamiento, la región, el plan (standar) y que sea localmente redundante. Se almacena la cadena de conexión de la llave de acceso.

  - **Se crea la Function App**: Esta debe pertenecer al grupo de recursos creado en el apartado anterior.

  - **Se crea un proyecto local** (más adelante se publicará el código de la función en Azure) de Azure Function en Visual Studio Code. Se establece el lenguaje, el entorno de ejecución, el tipo de desencadenador a emplear, nombre de la función, nivel de autorización y se añade el proyecto al espacio de trabajo.

  - **Se ejecuta la función localmente**: Se crea  una nueva terminal en Visual Studio Code, se presiona F5 abriéndose una ventana que hace de servidor de la función y que además utiliza el storage emulator. Se muestra el punto de conexión de la dirección URL de la función desencadenada que se ejecuta localmente.

    Se destaca el archivo local.settings.json que indica la configuración cuando se trabaja en local. Por defecto asigna el storage para que se use el emulador, pero se empleará la cadena de conexión que se almacenó previamente.

  - **Se despliega la función local en la Azure Function**: Se ejecuta el comando ``func start --build``.

  

- ### **Question 20, pág 20**

  *You develop an HTTP triggered Azure Function app to process Azure Storage blob data. The app is triggered using an output binding on the blob.*

  *The app continues to time out after four minutes. The app must process the blob data.*

  *You need to ensure the app does not time out and processes the blob data.*

  *Solution: Configure the app to use an App Service hosting plan and enable the Always On setting.*

  *Does the solution meet the goal?*

  *A. Yes*
  
  *B. No*

A, en primer lugar en un plan de App Service se habilita el Aways On para que la aplicación se ejecute correctamente. En este plan el tiempo de ejecución de las funciones queda inactivo después de unos minutos de inactividad, pero el tiempo de espera de ejecución para las funciones individuales se controla mediante la opción `functionTimeout`, en el archivo de proyecto host.json. De forma predeterminada, en un plan dedicado el tiempo de espera es de 30 minutos, lo que permitiría el tiempo suficiente para procesar los datos del blob sin agotar el tiempo de espera.

[Planes de hospedaje dedicados en Azure Functions](https://learn.microsoft.com/es-es/azure/azure-functions/dedicated-plan#always-on)

[Referencia de host.json para Azure Functions 2.x y versiones posteriores](https://learn.microsoft.com/en-us/azure/azure-functions/functions-host-json#functiontimeout)



- ### **Question 18, pág 43**  

- *You develop an HTTP triggered Azure Function app to process Azure Storage blob data. The app is triggered using an output binding on the blob.* 

  *The app continues to time out after four minutes. The app must process the blob data.* 

  *You need to ensure the app does not time out and processes the blob data.* 

  *Solution: Use the Durable Function async pattern to process the blob data.* 

  *Does the solution meet the goal?*

  *A. Yes* 

  *B. No*

  

A. Durable Functions proporciona *temporizadores durables* para usarlos en funciones de orquestador para implementar retrasos o configurar tiempos de expiración en acciones asincrónicas, es decir, se emplean para administrar orquestaciones de larga duración. Esto facilita el procesamiento los datos del blob sin estar limitado al tiempo de espera predeterminado de cuatro minutos.

[Temporizadores en Durable Functions (Azure Functions)](https://learn.microsoft.com/es-es/azure/azure-functions/durable/durable-functions-timers?source=recommendations&tabs=csharp)



- ### **Question 3, pág 64**

*HOTSPOT* 

*You need to implement the bindings for the CheckUserContent function.*

*How should you complete the code segment?* 

*To answer, select the appropriate options in the answer area.* 

*NOTE: Each correct selection is worth one point.*

*Hot Area:*

![Opciones](https://github.com/Kerolink/FirstAzureDevelopment.git/Imagenes/checkUserContent.png)

Los bindings especifican cómo se acceden y manipulan los datos de entrada y salida en la función "CheckUserContent". Proporcionan una forma conveniente de interactuar con los blobs almacenados en Azure Blob Storage. Por ello se seleccionan las siguientes opciones:

![Opciones escpgidas](https://github.com/Kerolink/FirstAzureDevelopment.git/Imagenes/opciones_checkUserContent.png)

