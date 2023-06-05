### Tema 3: Develop event-based solutions

  # ¿Qué es la Plataforma de Identidad de Microsoft y cómo se utiliza para la autenticación de usuarios?
  
            ```
            La Plataforma de Identidad de Microsoft, también conocida como Azure Active Directory (Azure AD), es un servicio en la nube que proporciona una solución de administración de identidad y acceso para aplicaciones, servicios y recursos en el ecosistema de Microsoft. Es utilizado por organizaciones para autenticar y autorizar a los usuarios que acceden a sus aplicaciones y servicios.

            Azure AD permite a las organizaciones centralizar la administración de identidades y proporciona capacidades de inicio de sesión único (SSO) para que los usuarios puedan acceder a múltiples aplicaciones y servicios con una sola credencial. Al utilizar Azure AD, los usuarios pueden autenticarse en sus cuentas utilizando credenciales de Microsoft, como una cuenta de correo electrónico y una contraseña, o mediante cuentas de redes sociales y otros proveedores de identidad compatibles.

            La autenticación de usuarios en Azure AD se puede lograr mediante diferentes métodos, como:

            1. Nombre de usuario y contraseña: Los usuarios ingresan su nombre de usuario y contraseña para autenticarse en una aplicación o servicio compatible con Azure AD.

            2. Autenticación multifactor (MFA): Se agrega una capa adicional de seguridad al solicitar a los usuarios que verifiquen su identidad mediante un segundo factor, como un mensaje de texto, una notificación en una aplicación móvil o un token físico.

            3. Autenticación federada: Permite a los usuarios autenticarse utilizando credenciales de otros sistemas de identidad federados, como Active Directory local, cuentas de Google o cuentas de Azure AD de otras organizaciones.

            Azure AD también proporciona capacidades de administración de acceso, lo que significa que los administradores pueden controlar los permisos y el acceso de los usuarios a aplicaciones y servicios específicos. Esto se puede lograr mediante la configuración de directivas de acceso, grupos de usuarios y roles personalizados.

            En resumen, la Plataforma de Identidad de Microsoft (Azure AD) es una solución de administración de identidad y acceso en la nube que permite a las organizaciones autenticar y autorizar a los usuarios que acceden a sus aplicaciones y servicios, proporcionando un inicio de sesión único y opciones de autenticación avanzadas como la autenticación multifactor. 
            ```


  # ¿Cuál es el flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft?
 
            ```
            El flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft (Azure AD) es el flujo de autenticación basado en el protocolo OAuth 2.0 y OpenID Connect. A continuación, se describe el flujo básico de autenticación:

            1. El usuario accede a una aplicación o servicio que requiere autenticación utilizando Azure AD.

            2. La aplicación redirige al usuario al punto de conexión de autenticación de Azure AD, donde se le solicitará al usuario que ingrese sus credenciales.

            3. El usuario proporciona sus credenciales (por ejemplo, nombre de usuario y contraseña) en la página de inicio de sesión de Azure AD.

            4. Azure AD autentica las credenciales del usuario y valida su identidad.

            5. Si la autenticación es exitosa, Azure AD genera un token de acceso y un token de identidad para el usuario.

            6. Azure AD redirige al usuario de vuelta a la aplicación con los tokens generados.

            7. La aplicación verifica la validez del token de acceso y utiliza el token de identidad para obtener información sobre el usuario, como su identificador único y otros atributos de perfil.

            8. La aplicación permite el acceso al usuario y establece una sesión para que pueda interactuar con los recursos y datos protegidos.

            Es importante tener en cuenta que este es un flujo básico y pueden haber variaciones según la configuración específica de la aplicación y los requisitos de autenticación. Además, Azure AD también admite otros flujos y protocolos de autenticación, como el flujo de autorización del código de autorización, que permite obtener un token de acceso en nombre del usuario sin revelar sus credenciales a la aplicación.
            ```

  # ¿Cómo se obtienen y se utilizan los tokens de acceso para autorizar solicitudes a recursos protegidos?

            ```
            Para obtener y utilizar tokens de acceso para autorizar solicitudes a recursos protegidos al utilizar la
            Plataforma de Identidad de Microsoft (Azure AD), se siguen los siguientes pasos:

            1. Autenticación del usuario: El usuario inicia sesión en la aplicación o servicio que actúa como cliente y se autentica mediante Azure AD. Esto puede implicar ingresar las credenciales de usuario o usar un método de autenticación adicional, como la autenticación multifactor (MFA).

            2. Solicitud de token de acceso: Una vez autenticado, el cliente realiza una solicitud al punto de extremo de Azure AD para obtener un token de acceso. Esta solicitud incluye información como el identificador de la aplicación (cliente), el ámbito (scope) solicitado y otros parámetros específicos.

            3. Emisión del token de acceso: Azure AD valida la solicitud y, si es exitosa, emite un token de acceso al cliente. El token de acceso es un objeto JSON firmado digitalmente que contiene información sobre el cliente, el usuario autenticado y los permisos concedidos.

            4. Utilización del token de acceso: El cliente incluye el token de acceso en las solicitudes a los recursos protegidos. Esto se logra agregando el token en el encabezado de autorización HTTP utilizando el esquema de portador (Bearer scheme).

            5. Validación del token de acceso: El recurso protegido (por ejemplo, una API) recibe la solicitud del cliente y valida el token de acceso. Esto implica verificar la firma digital del token, comprobar la validez temporal y asegurarse de que el token haya sido emitido por Azure AD y para la aplicación y el usuario correctos.

            6. Autorización de la solicitud: Si el token de acceso es válido, el recurso protegido autoriza la solicitud del cliente basándose en los permisos y alcance otorgados al token. Esto puede incluir permitir o denegar el acceso a recursos específicos o realizar acciones específicas en nombre del usuario autenticado.

            Es importante tener en cuenta que los tokens de acceso tienen una duración limitada y pueden tener un alcance específico definido por los permisos otorgados. Si el token expira o los permisos no son suficientes, el cliente debe solicitar un nuevo token de acceso actualizado.

            Este es un flujo generalizado y simplificado. La implementación exacta puede variar según el protocolo de autenticación utilizado (por ejemplo, OAuth 2.0, OpenID Connect) y las configuraciones específicas de Azure AD y la aplicación cliente.
            ```

## Preguntas AZ-204

### QUESTION 11

            You are developing an Azure Web App. You configure TLS mutual authentication for the web app.
            You need to validate the client certificate in the web app. To answer, select the appropriate options in the
            answer area.

            - Explicación:

            Si estás utilizando ASP.NET y configuras tu aplicación para utilizar la autenticación mediante certificado de cliente, el certificado estará disponible a través de la propiedad HttpRequest.ClientCertificate. Para otras pilas de aplicaciones, el certificado del cliente estará disponible en tu aplicación a través de un valor codificado en base64 en el encabezado de la solicitud "X-ARR-ClientCert". Tu aplicación puede crear un certificado a partir de este valor y luego utilizarlo para fines de autenticación y autorización en tu aplicación.

            - Referencias:
            https://docs.microsoft.com/en-us/azure/app-service/app-service-web-configure-tls-mutual-auth


### QUESTION 5 page 145

            You are building a website to access project data related to teams within your organization. The website
            does not allow anonymous access. Authentication is performed using an Azure Active Directory (Azure AD)
            app named internal.
            The website has the following authentication requirements:
            Azure AD users must be able to login to the website.
            Personalization of the website must be based on membership in Active Directory groups.
            You need to configure the application’s manifest to meet the authentication requirements.
            How should you configure the manifest? To answer, select the appropriate configuration in the answer area.

            - Explicación:

            Box 1: groupMembershipClaims
            Escenario: La personalización del sitio web debe basarse en la pertenencia a grupos de Active Directory.
            A6319EC1AC83D57E5BA185C098116365
            También se pueden configurar reclamaciones de grupo en la sección de Reclamaciones Opcionales del Manifiesto de la Aplicación.
            Habilita las reclamaciones de pertenencia a grupos cambiando el valor de groupMembershipClaim.
            Los valores válidos son:

            "All"
            "SecurityGroup"
            "DistributionList"
            "DirectoryRole"

            Box 2: oauth2Permissions
            Escenario: Los usuarios de Azure AD deben poder iniciar sesión en el sitio web.
            oauth2Permissions especifica la colección de ámbitos de permisos OAuth 2.0 que la aplicación de la API web (recurso) expone a las aplicaciones cliente. Estos ámbitos de permisos pueden otorgarse a las aplicaciones cliente durante el consentimiento.
            Respuestas incorrectas:
            oauth2AllowImplicitFlow. oauth2AllowImplicitFlow especifica si esta aplicación web puede solicitar tokens de acceso de flujo implícito OAuth 2.0. El valor predeterminado es false. Este indicador se utiliza para aplicaciones basadas en navegadores, como aplicaciones de página única en Javascript.

            - Referencia:
            https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-fed-group-claims

### QUESTION 22 page 247

            You develop a gateway solution for a public facing news API.
            The news API back end is implemented as a RESTful service and hosted in an Azure App Service instance.
            You need to configure back-end authentication for the API Management service instance.
            Which target and gateway credential type should you use? To answer, drag the appropriate values to the
            correct parameters. Each value may be used once, more than once, or not at all. You may need to drag the
            split bar between panes or scroll to view content.

            - Explicación:

            Caja 1: Recurso de Azure
            Caja 2: Certificado de cliente
            API Management permite asegurar el acceso al servicio de back-end de una API utilizando certificados de cliente.

            - REferencia:
            https://docs.microsoft.com/en-us/rest/api/apimanagement/apimanagementrest/azure-api-management-restapi-backend-entity
            

