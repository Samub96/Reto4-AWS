# Informe de Actividad

> Laboratorio: Creación de un Sitio Web Dinámico para el Café en AWS

 ## Introducción


El presente informe documenta la implementación de un laboratorio orientado a la creación y despliegue de un sitio web dinámico para un café, utilizando servicios de Amazon Web Services (AWS). La actividad tuvo como objetivo aprender el proceso de aprovisionamiento, configuración y despliegue de aplicaciones web en entornos en la nube, además de aplicar buenas prácticas de replicación y separación de entornos de desarrollo y producción.

 ## Objetivos


Implementar un servidor web dinámico en Amazon EC2.

Instalar y configurar una aplicación basada en PHP con base de datos MariaDB.

Integrar AWS Systems Manager Parameter Store para la gestión de parámetros de la aplicación.

Validar la conectividad y disponibilidad del sitio web desde internet.

Crear una AMI (Amazon Machine Image) para replicar el entorno.

Desplegar la aplicación en una segunda región de AWS, diferenciando ambientes de desarrollo y producción.

 ## Desarrollo de la Actividad

 #### Configuración inicial

Se utilizó una instancia Amazon EC2 con Amazon Linux.

Se instaló y configuró el servidor Apache (httpd), PHP y MariaDB.

Se activaron y configuraron los servicios para iniciar automáticamente tras reinicios.

Se vinculó el entorno AWS Cloud9 con el directorio de Apache para facilitar la edición de archivos.

#### Prueba inicial

Se creó un archivo index.html con un mensaje de prueba.

Se configuró el grupo de seguridad para permitir acceso HTTP (puerto 80) desde cualquier origen.

Se validó la disponibilidad del sitio desde el navegador.

#### Instalación de la aplicación del café

Se descargaron y desplegaron los archivos de la aplicación (setup.zip, db.zip, cafe.zip).

Se configuró la aplicación PHP para conectarse con parámetros almacenados en AWS Systems Manager Parameter Store.

Se inicializó la base de datos y se crearon las tablas necesarias.

Se ajustó la configuración de PHP para la zona horaria.

Se validó el acceso al sitio dinámico (/cafe), incluyendo menú y órdenes en línea.

#### Replicación en otra región

Se creó una AMI del servidor configurado.

Se copió la imagen a la región us-west-2 (Oregón).

Se lanzó una nueva instancia con las mismas características para producción.

Se replicaron los parámetros en Parameter Store de la nueva región.

Se probó el acceso al sitio web desde la nueva instancia, validando que las funcionalidades estuvieran operativas.

 ## Resultados

Se logró desplegar correctamente un sitio web dinámico en AWS con soporte para órdenes en línea.

Se implementaron dos entornos diferenciados:

Desarrollo: us-east-1 (N. Virginia).

Producción: us-west-2 (Oregón).

La aplicación es accesible públicamente, con base de datos operativa y parámetros gestionados de forma segura.

Se cumplió con los objetivos planteados del laboratorio en un tiempo estimado de 60 minutos.

## Preguntas 
Question 1: Is the instance in a public subnet?

✅ Yes
 


Question 2: Does the EC2 instance have an IPv4 Public IP address assigned to it?

✅ Yes
 


Question 3: What inbound TCP port numbers are open for this instance?
 
 ✅TCP port 22 only, open to a specific range of IP addresses


Question 4: Does the EC2 instance have an AWS Identity and Access Management (IAM) role associated with it?
 
✅ No


Question 5: When you create an AMI from an instance, will the instance be rebooted?
 
 ✅ You have the option not to reboot, but by default it will be rebooted


Question 6: In what ways can you modify the root volume properties when you create an AMI from an instance?

 ✅ You can edit the size and 'delete on termination' setting, but not the volume type.
 


Question 7: Can you add more volumes to an AMI that you create from an instance that only has one volume?
 ✅ Yes
 


 ## Conclusiones

AWS proporciona una infraestructura flexible para desplegar aplicaciones web de forma rápida y escalable.

La creación de AMIs permite replicar entornos de manera sencilla y confiable.

La separación de entornos de desarrollo y producción en distintas regiones mejora la resiliencia, la continuidad del negocio y las pruebas de nuevas funcionalidades sin afectar a los usuarios finales.

El uso de Parameter Store mejora la seguridad en el manejo de credenciales y configuraciones.

## 👨‍💻 Autor 
**SAMUEL BARONA - Estudiante ingenieria Telematica** 