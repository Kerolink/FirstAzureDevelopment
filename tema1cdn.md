# ¿Qué es Azure CDN y cuál es su propósito en el despliegue de aplicaciones web?

```
Azure CDN (Content Delivery Network) es un servicio de Microsoft Azure que se utiliza para distribuir contenido web de manera eficiente a usuarios finales de todo el mundo. Su propósito principal es mejorar el rendimiento y la experiencia del usuario al acelerar la entrega de contenido estático y dinámico, como imágenes, archivos CSS, JavaScript y otros recursos multimedia.

El CDN de Azure se basa en una red global de servidores dispersos estratégicamente en diferentes ubicaciones geográficas. Cuando se implementa una aplicación web en Azure, los recursos estáticos y dinámicos asociados, como imágenes y archivos JavaScript, se pueden almacenar en caché en estos servidores distribuidos en todo el mundo. Cuando un usuario solicita el contenido de la aplicación web, Azure CDN redirige la solicitud al servidor más cercano al usuario, lo que reduce la latencia y el tiempo de carga.

El uso de Azure CDN ofrece varios beneficios en el despliegue de aplicaciones web:

Mejora del rendimiento: Al almacenar en caché el contenido estático y dinámico en servidores cercanos a los usuarios finales, se reduce la latencia y se mejora el tiempo de respuesta de la aplicación web.

Escalabilidad: Azure CDN es capaz de manejar grandes volúmenes de tráfico y adaptarse automáticamente a las demandas cambiantes. Esto asegura que la aplicación web pueda manejar picos de carga sin degradación del rendimiento.

Ahorro de ancho de banda: Al distribuir el contenido desde servidores en ubicaciones geográficas estratégicas, se reduce la carga en los servidores de origen. Esto ayuda a ahorrar ancho de banda y mejora la capacidad de respuesta de la aplicación web.

Seguridad y protección contra ataques DDoS: Azure CDN proporciona funciones de seguridad integradas, como la mitigación de ataques DDoS (Distributed Denial of Service). Esto ayuda a proteger la aplicación web contra amenazas de seguridad y garantiza una experiencia confiable para los usuarios.

En resumen, Azure CDN es un servicio de distribución de contenido que mejora el rendimiento, la escalabilidad y la seguridad de las aplicaciones web al proporcionar una entrega rápida y eficiente de recursos estáticos y dinámicos a través de una red global de servidores.
```

# ¿Cuáles son los beneficios de utilizar Azure CDN en términos de rendimiento y escalabilidad?

```

Azure CDN (Content Delivery Network) ofrece varios beneficios en términos de rendimiento y escalabilidad para aplicaciones y sitios web. A continuación, se detallan algunos de ellos:

Mejor rendimiento global: Azure CDN distribuye contenido a través de una red global de servidores en varios puntos de presencia (PoP) ubicados estratégicamente. Esto permite que el contenido se entregue desde el servidor más cercano al usuario final, lo que reduce la latencia y mejora la velocidad de carga de la página.

Caché de contenido estático: Azure CDN almacena en caché el contenido estático, como imágenes, scripts y archivos CSS, en sus servidores distribuidos. Cuando un usuario solicita ese contenido, se entrega desde el servidor en lugar de tener que acceder al servidor de origen, lo que acelera la entrega y reduce la carga en el servidor de origen.

Escalabilidad automática: Azure CDN se integra con otros servicios de Azure, como Azure Blob Storage y Azure Web Apps. Esto permite una escalabilidad automática en función de la demanda. Si hay un aumento repentino en el tráfico, Azure CDN puede manejar la carga adicional al distribuir el contenido de manera eficiente en toda la red.

Reducción de costos de ancho de banda: Al utilizar Azure CDN, se reduce la cantidad de tráfico que debe pasar a través del servidor de origen. Esto puede ayudar a reducir los costos de ancho de banda, especialmente si tienes un gran volumen de contenido estático que se entrega con frecuencia.

Mejora en la experiencia del usuario: La entrega rápida de contenido a través de Azure CDN mejora la experiencia del usuario al reducir los tiempos de carga de la página. Los usuarios pueden acceder a contenido estático de manera más rápida y experimentar una navegación más fluida.

SSL y seguridad: Azure CDN permite la configuración de SSL (Secure Socket Layer) para garantizar que el contenido se entregue de manera segura a los usuarios. Además, se pueden aplicar reglas de seguridad y filtrado para proteger contra ataques maliciosos.

En resumen, Azure CDN ofrece beneficios significativos en términos de rendimiento y escalabilidad al proporcionar una entrega rápida de contenido estático a través de una red global de servidores, reducir la carga en el servidor de origen y mejorar la experiencia del usuario.
```



# ¿Cómo se configura y se utiliza Azure CDN para acelerar la entrega de contenido estático y dinámico en una aplicación web?

```

Azure CDN (Content Delivery Network) es un servicio de Microsoft Azure que te permite acelerar la entrega de contenido estático y dinámico en una aplicación web al distribuirlo a través de una red global de servidores ubicados estratégicamente. Para configurar y utilizar Azure CDN en tu aplicación web, puedes seguir los siguientes pasos:

Paso 1: Crear un perfil de Azure CDN

Inicia sesión en el Portal de Azure (https://portal.azure.com).
Haz clic en "Crear un recurso" y busca "CDN" en el marketplace.
Selecciona "Content Delivery Network" y haz clic en "Crear".
Proporciona un nombre único para tu perfil de CDN, selecciona la suscripción, el grupo de recursos y la ubicación.
Selecciona la opción "Habilitar" junto a "Crear un endpoint de CDN".

Paso 2: Configurar el punto de conexión (endpoint)

Después de crear el perfil de CDN, haz clic en él para acceder a su configuración.
Haz clic en "Endpoints" en el menú de la izquierda y luego en "Agregar".
Proporciona un nombre para el endpoint y selecciona el origen del contenido (por ejemplo, la URL de tu aplicación web).
Configura las opciones de caché, como la duración del tiempo de retención de la caché y las reglas de purga.
Selecciona la ubicación geográfica para el endpoint.

Paso 3: Configurar el dominio personalizado (opcional)

Si deseas utilizar tu propio dominio personalizado con Azure CDN, puedes configurarlo en la sección "Dominio personalizado" del perfil de CDN.
Sigue las instrucciones para verificar y asociar tu dominio con el perfil de CDN.

Paso 4: Asignar el endpoint a tu aplicación web

Una vez que hayas configurado el endpoint de CDN, deberás actualizar la configuración de tu aplicación web para utilizarlo.
Esto generalmente implica modificar la configuración de DNS para que el dominio o subdominio utilizado por la aplicación web apunte al dominio del endpoint de CDN.

Paso 5: Validar y probar la configuración

Después de completar la configuración, asegúrate de validar que la entrega de contenido a través de Azure CDN está funcionando correctamente.
Puedes realizar pruebas accediendo a los archivos estáticos o dinámicos de tu aplicación web a través de la URL del endpoint de CDN y verificando que se entreguen correctamente y de manera más rápida.
Recuerda que la configuración exacta y los pasos pueden variar dependiendo de la versión actual del Portal de Azure y el servicio de Azure CDN. Te recomiendo consultar la documentación oficial de Microsoft Azure para obtener instrucciones actualizadas y más detalladas sobre cómo configurar y utilizar Azure CDN en tu aplicación web.
```

# Preguntas de la Batería

# Question 6 pag 88

pdf correcto

Step 1: A user requests the image.. A user requests a file (also called an asset) by using a URL with a special domain name, such as .azureedge.net. This name can be an endpoint hostname or a custom domain. The DNS routes the request to the best performing POP location, which is usually the POP that is geographically closest to the user. 

Step 2: If no edge servers in the POP have the.. If no edge servers in the POP have the file in their cache, the POP requests the file from the origin server. The origin server can be an Azure Web App, Azure Cloud Service, Azure Storage account, or any publicly accessible web server. 

Step 3: The origin server returns the.. The origin server returns the file to an edge server in the POP. An edge server in the POP caches the file and returns the file to the original requestor (Alice). The file remains cached on the edge server in the POP until the time-to-live (TTL) specified by its HTTP headers expires. If the origin server didn't specify a TTL, the default TTL is seven days. 

Step 4: Subsequent requests for.. Additional users can then request the same file by using the same URL that the original user used, and can also be directed to the same POP. If the TTL for the file hasn't expired, the POP edge server returns the file directly from the cache. This process results in a faster, more responsive user experience.



# Question 8 Pag 199

pdf correcto

You are developing an Azure App Service hosted ASP.NET Core web app to deliver video-on-demand
streaming media. You enable an Azure Content Delivery Network (CDN) Standard for the web endpoint.
Customer videos are downloaded from the web app by using the following example URL: http://
www.contoso.com/content.mp4?quality=1
All media content must expire from the cache after one hour. Customer videos with varying quality must be
delivered to the closest regional point of presence (POP) node.
You need to configure Azure CDN caching rules.
Which options should you use? To answer, select the appropriate options in the answer area.

**box 1: Override**

we want to force it to use our defined caching duration,
Bypass cache just doesn't cache
and set if missing will only use our defined caching duration if the webapp doesn't specify one

**box 2: 1 hour**

Está especificado en el texto no tiene perdida

**box 3: Cache every unique url**

each unique url is a different video file
blah.mp4?quality=3
is different to
blah.mp4?quality=1
so you will want to cache them seperately



so the cache sits between your web app and the user 
and when your user requests a video, the user requests that video from the cache, if your cache doesn't have the video it requests it from your web app
your web app sends the video to the cache and the cache sends it to the user
now if the user requests the video again, the cache will have it stored and can send it directly to the user without querying your app
