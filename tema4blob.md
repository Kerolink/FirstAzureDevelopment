### Tema 4: Implement containerized solutions	

  # ¿Cuál es la diferencia entre Azure Container Registry, Azure Container Instances y Azure Container Apps?	

            ```
            Azure Container Registry (ACR), Azure Container Instances (ACI) y Azure Container Apps son servicios relacionados pero tienen diferentes funcionalidades y casos de uso.

            Azure Container Registry (ACR): Es un servicio de registro de contenedores de Azure que permite almacenar y administrar imágenes de contenedores privadas de forma segura. ACR proporciona un lugar centralizado para almacenar y administrar imágenes de contenedores que se utilizan para implementar aplicaciones en Azure. Es similar a un repositorio de imágenes de Docker. ACR permite la implementación de imágenes de contenedores en otros servicios como Azure Kubernetes Service (AKS) o Azure Container Instances (ACI).

            Azure Container Instances (ACI): Es un servicio de Azure que permite ejecutar contenedores sin la necesidad de administrar clústeres de Kubernetes o infraestructura subyacente. ACI permite ejecutar contenedores de forma rápida y sencilla, sin la necesidad de configurar ni administrar servidores. Es ideal para cargas de trabajo puntuales, pruebas rápidas, tareas de procesamiento por lotes y microservicios sencillos que no requieren escalabilidad automática.

            Azure Container Apps: Es un servicio más reciente que se encuentra actualmente en versión preliminar (preview). Azure Container Apps combina las características de ACR y ACI para simplificar la implementación y administración de aplicaciones en contenedores en Azure. Permite definir y ejecutar aplicaciones completas en contenedores, incluyendo sus dependencias, configuraciones y escala, utilizando un modelo declarativo. Azure Container Apps ofrece una abstracción más alta que ACI y proporciona una forma más sencilla de desplegar y escalar aplicaciones en contenedores sin la necesidad de preocuparse por la infraestructura subyacente.

            En resumen, Azure Container Registry se utiliza para almacenar y administrar imágenes de contenedores, Azure Container Instances para ejecutar contenedores de forma rápida y sencilla, y Azure Container Apps para definir y desplegar aplicaciones completas en contenedores de manera simplificada.
            ```

  # ¿Cómo se utiliza Azure Container Registry para almacenar y gestionar imágenes de contenedores?
            
            ```
            Para utilizar Azure Container Registry (ACR) y almacenar y gestionar imágenes de contenedores, puedes seguir los siguientes pasos:

            1. Crear un Azure Container Registry: Inicia sesión en el portal de Azure y crea un nuevo Azure Container Registry. Proporciona un nombre único para el registro y selecciona la suscripción, grupo de recursos y la ubicación.

            2. Obtener las credenciales de acceso: Una vez que se haya creado el registro, ve a la sección "Claves de acceso" en la página del registro. Aquí puedes obtener el nombre del servidor de ACR y las credenciales de inicio de sesión, como el nombre de usuario y la contraseña.

            3. Iniciar sesión en el registro desde tu entorno de desarrollo: Utiliza las credenciales de acceso obtenidas en el paso anterior para autenticarte en el registro desde tu entorno de desarrollo o línea de comandos. Por ejemplo, puedes utilizar el comando docker login con el nombre de servidor de ACR, el nombre de usuario y la contraseña.

            4. Construir y etiquetar imágenes de contenedores: Utiliza Docker o la herramienta de construcción de imágenes de tu elección para crear y etiquetar las imágenes de contenedores que deseas almacenar en ACR. Asegúrate de que las imágenes estén etiquetadas con la dirección del servidor de ACR, por ejemplo, <nombre-de-tu-registry>.azurecr.io/nombre-de-imagen:etiqueta.

            5. Subir las imágenes al registro: Utiliza el comando docker push para subir las imágenes etiquetadas al registro de ACR. Por ejemplo, docker push <nombre-de-tu-registry>.azurecr.io/nombre-de-imagen:etiqueta.

            6. Gestionar las imágenes en el registro: Desde el portal de Azure o utilizando la interfaz de línea de comandos de Azure, puedes administrar las imágenes almacenadas en ACR. Esto incluye la gestión de etiquetas, la configuración de políticas de retención, la eliminación de imágenes antiguas y la administración de permisos de acceso.

            Una vez que hayas almacenado las imágenes en Azure Container Registry, podrás utilizarlas para implementar aplicaciones en otros servicios de Azure, como Azure Kubernetes Service (AKS) o Azure Container Instances (ACI), o compartir las imágenes con otros miembros de tu equipo. ACR proporciona una solución segura y confiable para el almacenamiento y la administración de imágenes de contenedores en Azure.
            ```

  # ¿Cuál es el propósito y la ventaja de utilizar Azure Container Instances para ejecutar contenedores sin necesidad de administrar una infraestructura subyacente?	

            ```
            El propósito principal de Azure Container Instances (ACI) es permitirte ejecutar contenedores de forma rápida y sencilla sin la necesidad de administrar una infraestructura subyacente. Algunas de las ventajas de utilizar ACI son las siguientes:

            1. Simplificación de la administración: ACI se encarga de la administración de la infraestructura subyacente, lo que te permite centrarte en tus aplicaciones y cargas de trabajo sin preocuparte por tareas de administración, como aprovisionamiento, escalado o configuración de servidores.

            2. Implementación rápida: ACI permite ejecutar contenedores casi instantáneamente, lo que reduce significativamente el tiempo necesario para implementar tus aplicaciones y servicios. Puedes iniciar contenedores individuales o múltiples contenedores en paralelo de manera rápida y sencilla.

            3. Facturación por segundos: ACI ofrece un modelo de precios por segundo, lo que significa que solo pagas por el tiempo exacto que tus contenedores están en ejecución. Esto es especialmente útil para cargas de trabajo puntuales o tareas de procesamiento por lotes que no requieren una ejecución continua.

            4. Escalado automático: ACI puede escalar automáticamente los contenedores en función de la carga de trabajo. Puedes definir límites de CPU y memoria para tus contenedores, y ACI ajustará automáticamente los recursos asignados según sea necesario.

            5. Integración con otros servicios de Azure: ACI se integra de manera nativa con otros servicios de Azure, como Azure Virtual Network, Azure Container Registry y Azure Functions, lo que te permite construir aplicaciones y sistemas completos utilizando una combinación de servicios administrados de Azure.

            En resumen, la ventaja principal de utilizar Azure Container Instances es que te permite ejecutar contenedores sin tener que preocuparte por la administración de la infraestructura subyacente. Esto simplifica el proceso de implementación, reduce el tiempo de inactividad y te permite centrarte en el desarrollo de tus aplicaciones y servicios. ACI es especialmente útil para cargas de trabajo puntuales, pruebas rápidas, tareas de procesamiento por lotes y microservicios sencillos que no requieren escalabilidad automática.
            ```

## Preguntas AZ-204


### QUESTION 10 page 94

            You are building a website that uses Azure Blob storage for data storage. You configure Azure Blob storage
            lifecycle to move all blobs to the archive tier after 30 days.
            Customers have requested a service-level agreement (SLA) for viewing data older than 30 days.
            You need to document the minimum SLA for data recovery.

            Which SLA should you use?
            A. at least two days
            B. between one and 15 hours
            C. at least one day
            D. between zero and 60 minutes
            Correct Answer: B

            - Explicación:
            The archive access tier has the lowest storage cost. But it has higher data retrieval costs compared to the
            hot and cool tiers. Data in the archive tier can take several hours to retrieve depending on the priority of the
            rehydration. For small objects, a high priority rehydrate may retrieve the object from archive in under 1 hour.
            
            - Referencia:
            https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-storage-tiers?tabs=azure-portal


### QUESTION 15 page 104

            You are developing an Azure solution to collect point-of-sale (POS) device data from 2,000 stores located
            throughout the world. A single device can produce 2 megabytes (MB) of data every 24 hours. Each store
            location has one to five devices that send data.
            You must store the device data in Azure Blob storage. Device data must be correlated based on a device
            identifier. Additional stores are expected to open in the future.

            You need to implement a solution to receive the device data capture.
              Does the solution meet the goal?
              A. Yes
              B. No

            - Correct Answer: A          

            - Referencia:
            https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services

### QUESTION 17 page 156

            You are developing an application to securely transfer data between on-premises file systems and Azure
            Blob storage. The application stores keys, secrets, and certificates in Azure Key Vault. The application uses
            the Azure Key Vault APIs.
            The application must allow recovery of an accidental deletion of the key vault or key vault objects. Key vault
            objects must be retained for 90 days after deletion.
            You need to protect the key vault and key vault objects.
            Which Azure Key Vault feature should you use? To answer, drag the appropriate features to the correct
            actions. Each feature may be used once, more than once, or not at all. You may need to drag the split bar
            between panes or scroll to view content.

            -Explicación:

            Caja 1: soft delete
            Cuando se habilita la soft delete, los recursos marcados como eliminados se conservan durante un período especificado (90 días de forma predeterminada). El servicio proporciona además un mecanismo para recuperar el objeto eliminado, deshaciendo efectivamente la eliminación.
            Caja 2: Purge protection
            La Purge protection es un comportamiento opcional de Key Vault y no está habilitada de forma predeterminada. La protección de purga solo se puede habilitar una vez que se haya habilitado la eliminación suave.
            Cuando la protección de purga está activada, una bóveda o un objeto en estado eliminado no se pueden purgar hasta que haya transcurrido el período de retención. Las bóvedas y los objetos eliminados de forma suave aún se pueden recuperar, lo que garantiza el cumplimiento de la política de retención.

            -Referencia:
            https://docs.microsoft.com/en-us/azure/key-vault/general/soft-delete-overview
            