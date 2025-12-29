diff --git a/README.md b/README.md
index 2a00dec518d5f1cbf1c53d4c9bc73fa9b09d9d28..557b8fd5f2ee6f51c61deca36584b5a2e3115df5 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,391 @@
-# Foro_hub
\ No newline at end of file
+# Foro Hub
+
+## Historia
+
+¡Te damos la bienvenida a nuestro más reciente Challenge Back End!
+
+Un **foro** es un lugar donde todos los participantes de una plataforma pueden colocar sus preguntas sobre determinados asuntos. Aquí en Alura, los estudiantes utilizan el foro para resolver sus dudas sobre los cursos y proyectos en los que están participando. Este lugar mágico está lleno de mucho aprendizaje y colaboración entre estudiantes, profesores y moderadores.
+
+Ya sabemos para que sirve el foro y sabemos cómo se ve, pero ¿sabemos cómo funciona por detrás? Es decir ¿dónde se almacenan las informaciones? ¿cómo se tratan esos datos para que se relacione un **tópico** con una **respuesta**, o como se relacionan los **usuarios** con las respuestas de un tópico?
+
+Ese es nuestro desafío, que se llama **Foro Hub**: vamos a replicar a nivel de back end este proceso, y para eso crearemos una **API REST usando Spring**.
+
+Nuestra API va a centrarse específicamente en los **tópicos**, y debe permitir a los usuarios:
+
+- Crear un nuevo tópico
+- Mostrar todos los tópicos creados
+- Mostrar un tópico específico
+- Actualizar un tópico
+- Eliminar un tópico
+
+Es lo que conocemos comúnmente como CRUD (CREATE, READ, UPDATE, DELETE) y es muy parecido con lo que desarrollamos en el Hotel Alura, pero ahora usando un framework que va a facilitar mucho nuestro trabajo.
+
+Al final de nuestro desarrollo tendremos una API REST con las siguientes funcionalidades:
+
+1. API con rutas implementadas siguiendo las mejores prácticas del modelo REST.
+2. Validaciones realizadas según reglas de negocio.
+3. Implementación de una base de datos para la persistencia de la información.
+4. Servicio de autenticación/autorización para restringir el acceso a la información.
+
+## ¡Manos a la obra!
+
+Tenemos un periodo de tiempo de tres semanas para desarrollar esta primera parte del proyecto y por eso en esta oportunidad también disponibilizaremos la parte del modelo de las entidades del proyecto, para que puedas centrarte en desarrollar las otras funcionalidades y hagas la API funcionar. No olvides que también puedes usar tu creatividad y hacer las modificaciones que creas convenientes. De la misma forma en la que venimos trabajando usaremos el sistema ágil de desarrollo, utilizando el Trello de la siguiente forma:
+
+1. La columna **Listos para iniciar** presenta las tarjetas con elementos que aun no fueron desarrollados.
+2. En la columna **En Desarrollo** estarán los elementos que estés desarrollando en el momento. Al iniciar una tarea, podrás mover la tarjeta que contiene dicha tarea para esta columna.
+3. En la columna **Pausado** estarán los elementos que comenzaste a desarrollar, pero necesitaste parar por algún motivo.
+4. Por fin, en la columna **Concluido** estarán los elementos ya concluidos.
+
+El Trello es una herramienta de uso individual para que puedas controlar el progreso de tus actividades, pero no será evaluada.
+
+Buen proyecto!
+
+## Pasos
+
+### Crear el repositorio de tu proyecto en GitHub
+
+**Labels:** Git/GitHub
+
+**Description**
+
+Git y GitHub son herramientas muy útiles para cualquier desarrollador, así que debes acostumbrarte a trabajar con ellas.
+
+En este desafío queremos proponer que el primer paso a dar sea la creación de este repositorio en GitHub. Aunque aún no hayas desarrollado ningún código, lo importante es que tengas al menos una carpeta específica para tu proyecto, y puedas actualizarlo gradualmente. El material siguiente te ayudará en esta actividad:
+
+- [Git - Configurando Git por primera vez](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez)
+- [Git y GitHub: Herramientas Esenciales para el Control de Versiones y Colaboración en Desarrollo](https://www.youtube.com/watch?v=dw04N616Abw&t=5s)
+- [como subir mi proyecto en GitHub](https://www.youtube.com/watch?v=bhKkeOMysuw)
+
+Utilicemos nuestro README para detallar las funcionalidades de nuestro sistema, capturas de pantalla e incluso un vídeo de tu aplicación funcionando. De esta manera podrás mostrar tu proyecto a la comunidad 😄
+
+Además, tenemos algunos **artículos** que pueden ayudarte a crear y gestionar un repositorio en GitHub:
+
+- [Iniciando un repositorio con Git | Alura Cursos Online](https://www.aluracursos.com/blog/iniciando-repositorio-con-git)
+- [Creando un repositorio remoto en GitHub | Alura Cursos Online](https://www.aluracursos.com/blog/creando-repositorio-remoto-en-github)
+- [Clonando un repositorio con Git y GitHub | Alura Cursos Online](https://www.aluracursos.com/blog/clonando-un-repositorio-remoto)
+- [Git: Los nuevos comandos git restore y git switch | Alura Cursos Online](https://www.aluracursos.com/blog/git-y-los-nuevos-comandos)
+
+### Configurando el entorno Java y Spring
+
+**Labels:** Java, Configuración de entorno, Spring
+
+**Description**
+
+En esta primera fase, nos sumergiremos en la configuración del entorno de desarrollo Java para nuestro desafío de construir el **ForoHub**. Asegúrate de tener los siguientes programas, archivos y versiones:
+
+- Java JDK: versión 17 en adelante - Descarga la última versión LTS de Java gratuita.
+- Maven: versión 4 en adelante.
+- Spring Boot: versión 3 en adelante - https://start.spring.io/.
+- MySQL: versión 8 en adelante - [MySQL :: Download MySQL Installer](https://dev.mysql.com/downloads/installer/) (Instalador para **Windows**).
+- IDE (Entorno de desarrollo integrado) IntelliJ IDEA - opcional - [Descargar IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/download/?section=windows).
+
+**Si tienes más experiencia con otro banco relacional, como PostgreSQL, puedes usarlo sin problemas.**
+
+- Artículo sobre la instalación de **MySQL** en Windows: [MySQL: desde la descarga e instalación hasta su primera tabla | Alura Cursos Online](https://www.aluracursos.com/blog/mysql-desde-la-descarga-e-instalacion-hasta-su-primera-tabla)
+
+Configuración al crear el proyecto con [Spring Initializr](https://start.spring.io/):
+
+- Java (versión 17 en adelante)
+- Maven (Initializr utiliza la versión 4)
+- Spring Boot
+- Proyecto en formato JAR
+
+Dependencias para agregar al crear el proyecto con [Spring Initializr](https://start.spring.io/):
+
+- Lombok
+- Spring Web
+- Spring Boot DevTools
+- Spring Data JPA
+- Flyway Migration
+- MySQL Driver
+- Validation
+- Spring Security
+
+### Diagrama Base de Datos
+
+**Labels:** Base de Datos
+
+**Description**
+
+Necesitarás utilizar una base de datos para almacenar la información de la aplicación.
+
+Para crear un tópico necesitan las siguientes informaciones:
+
+- id
+- título
+- mensaje
+- fecha de creación
+- status (estado del tópico)
+- autor
+- curso
+
+**Observación:** Nuestro challenge se centra en los tópicos, por lo que el diagrama representa una base de datos más completa pero no es obligatorio implementar todas las tablas presentes en él; es suficiente centrarse en la tabla de tópicos.
+
+La modelización de la(s) tabla(s) queda a tu criterio.
+
+Sugerencias de contenido:
+
+- [Guía de Instalación de MySQL Server y MySQL Workbench en Diferentes Sistemas Operativos | Alura Cursos Online](https://www.aluracursos.com/blog/descargar-mysql-serve)
+- [Bases de datos relacionales | Alura Cursos Online](https://www.aluracursos.com/blog/base-de-datos-relacional)
+- [Normalización en base de datos - Estructura | Alura Cursos Online](https://www.aluracursos.com/blog/normalizacion-en-base-de-datos)
+
+Herramientas para modelado:
+
+- [MySQL :: MySQL Workbench](https://www.mysql.com/products/workbench/)
+- [Download Astah Software](https://astah.net/downloads/)
+- [fabFORCE.net](https://www.fabforce.net/dbdesigner4/downloads.php)
+- https://lucid.app/documents#/dashboard
+
+### Construcción de la base de datos
+
+**Labels:** Base de Datos, Configuración de entorno
+
+**Description**
+
+#### Instalación de MySQL
+
+Enlace para descargar el **instalador** para Windows: [MySQL :: Download MySQL Installer](https://dev.mysql.com/downloads/installer/)
+
+→ Artículo Alura Latam: [Guía de Instalación de MySQL Server y MySQL Workbench en Diferentes Sistemas Operativos | Alura Cursos Online](https://www.aluracursos.com/blog/descargar-mysql-serve)
+
+**Si tienes más experiencia con otro banco relacional, como PostgreSQL, puedes usarlo sin problemas.**
+
+#### Configuración en el proyecto
+
+Para integrar una base de datos a nuestro proyecto Spring, debemos agregar dependencias en el `pom.xml`:
+
+- Validation
+- MySQL Driver
+- Spring Data JPA
+- Flyway Migration
+
+Además, también es importante recordar la configuración necesaria en el `application.properties` con los datos de `url`, `nombre de usuario` y `contraseña` de nuestra base de datos.
+
+**Sugerencia**: Antes de pasar a la etapa de migraciones del proyecto, te sugerimos crear la base de datos y configurarla según se mencionó anteriormente.
+
+#### Migración en el proyecto
+
+Las migraciones son comandos en lenguaje SQL para la configuración de la base de datos creada. Es necesario definir las migraciones en archivos con extensión `.sql`.
+
+→ Recuerda siempre pausar/detener la ejecución del proyecto Spring para crear/cambiar las migraciones.
+
+Si lo deseas, realiza pruebas de la aplicación en Insomnia o Postman.
+
+Sugerencia de curso: https://app.aluracursos.com/course/spring-boot-3-desarrollar-api-rest-java/task/84642
+
+### Registro de un nuevo tópico
+
+**Labels:** API, CRUD
+
+**Description**
+
+La API debe contar con un *endpoint* para el registro de tópicos, y debe aceptar solicitudes **POST** para la URI **/tópicos**.
+
+Los datos del tópico (título, mensaje, autor y curso) deben ser enviados en el cuerpo de la solicitud, en formato JSON.
+
+→ No olvides utilizar la anotación `@RequestBody` para que tu proyecto Spring reciba correctamente los datos del cuerpo de la solicitud.
+
+→ Recuerda que el tópico debe ser guardado en la base de datos, usando el método `save` del `JpaRepository`.
+
+**Sugerencia**: para ayudar en la validación de los datos, intenta utilizar la anotación `@Valid`.
+
+**Reglas de negocio**
+
+- Todos los campos son obligatorios.
+- La API no debe permitir el registro de tópicos duplicados (con el mismo título y mensaje).
+
+Recursos:
+
+- [Getting Started :: Spring Data JPA](https://docs.spring.io/spring-data/jpa/reference/jpa/getting-started.html)
+- [JPA Repositories](https://docs.spring.io/spring-data/jpa/docs/1.6.0.RELEASE/reference/html/jpa.repositories.html)
+- [Validation in Spring Boot | Baeldung](https://www.baeldung.com/spring-boot-bean-validation)
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-dessarrola-api-rest-java/task/91193
+
+### Mostrar todos los tópicos
+
+**Labels:** API, CRUD
+
+**Description**
+
+La API debe contar con un endpoint para el listado de todos los tópicos, y debe aceptar solicitudes **GET** para la URI **/tópicos**.
+
+Los datos de los tópicos (título, mensaje, fecha de creación, estado, autor y curso) deben ser devueltos en el cuerpo de la respuesta, en formato JSON.
+
+→ Para la lista usa el método `findAll` de `JpaRepository`.
+
+**Opcionales**:
+
+1. Mostrar los primeros 10 resultados ordenados por fecha de creación del tópico en orden ASC.
+2. Mostrar los resultados usando un criterio de búsqueda (por ejemplo: nombre de curso y año específico).
+
+Otra opción opcional: listado con paginación usando `@PageableDefault`.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-dessarrola-api-rest-java/task/91195
+
+### Detallando un tópico
+
+**Labels:** API, CRUD
+
+**Description**
+
+La API debe contar con un endpoint para consultar un tópico específico, y debe aceptar solicitudes **GET** para la URI **/tópicos/{id}**.
+
+→ Recuerda utilizar `@PathVariable` para recibir el campo de ID.
+
+**Reglas de negocio**
+
+- Es necesario verificar si el campo ID se ingresó correctamente.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-dessarrola-api-rest-java/task/91195
+
+### Actualizar un tópico
+
+**Labels:** API, CRUD
+
+**Description**
+
+La API debe contar con un endpoint para la actualización de un tópico, y debe aceptar solicitudes **PUT** para la URI **/tópicos/{id}**.
+
+**Observación:** las mismas reglas de negocio del registro de un tópico deben aplicarse en su actualización.
+
+→ Recuerda verificar si el tópico existe en la base de datos (`isPresent()` en `Optional`).
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-dessarrola-api-rest-java/task/91196
+
+### Eliminar un tópico
+
+**Labels:** API, CRUD
+
+**Description**
+
+La API debe contar con un endpoint para la eliminación de un tópico específico, el cual debe aceptar solicitudes **DELETE** para la URI **/tópicos/{id}**.
+
+→ Verifica si el tópico existe antes de eliminarlo y usa `deleteById` de `JpaRepository`.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-dessarrola-api-rest-java/task/91112
+
+### Pruebas a la API
+
+**Labels:** Pruebas, API, CRUD
+
+**Description**
+
+Las pruebas de las funcionalidades de la API pueden realizarse utilizando **Postman** o **Insomnia**.
+
+- Postman: https://www.postman.com
+- Insomnia: https://insomnia.rest
+
+Artículo sugerido: [Postman: aprenda cómo instalar y dar sus primeros pasos | Alura Cursos Online](https://www.aluracursos.com/blog/postman-aprenda-como-instalar-y-dar-sus-primeros-pasos)
+
+### Actualiza tu repositorio de proyecto en GitHub
+
+**Labels:** Git/GitHub
+
+**Description**
+
+Ahora que ha desarrollado novedades en su aplicación, es el momento de volver a **actualizar su repositorio**. También recuerde **actualizar README** para incluir las nuevas características de su aplicación.
+
+### Autenticación con Spring Security
+
+**Labels:** Base de Datos, Seguridad, API
+
+**Description**
+
+A partir de ahora, solo los usuarios autenticados pueden interactuar con la API.
+
+Implementa un mecanismo de autenticación en la API para que los usuarios puedan autenticarse y enviar solicitudes a ella.
+
+→ Recuerda agregar la dependencia "Spring Security" en tu archivo `pom.xml`.
+
+#### Configuración de seguridad
+
+Define `SecurityConfigurations` con `@Configuration` y `@EnableWebSecurity`, y usa `HttpSecurity` para configurar el acceso.
+
+Documentación: [Spring Security](https://spring.io/projects/spring-security)
+
+#### Autenticación en el código Java
+
+Implementa un controller para login, un DTO para recibir usuario/contraseña, y usa `AuthenticationManager`.
+
+→ Recuerda usar `@PostMapping`, `@RequestBody` y `@Valid`.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-aplique-mejores-practicas-proteja-api-rest/task/91699
+
+#### Base de datos
+
+Agrega una tabla para datos de autenticación de usuarios y modifica las migraciones.
+
+Artículos sugeridos:
+
+- [Como crear una buena contraseña | Alura Cursos Online](https://www.aluracursos.com/blog/como-crear-una-buena-contrasena)
+- [Tipos de Autenticación: Contraseña, Token, JWT, Dos Factores y Más | Alura Cursos Online](https://www.aluracursos.com/blog/tipos-de-autenticacion)
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-aplique-mejores-practicas-proteja-api-rest/task/91595
+
+### Generar un token con JWT
+
+**Labels:** Seguridad, JWT
+
+**Description**
+
+Agrega la dependencia JWT de Auth0 (https://jwt.io/) y crea un `TokenService` para generar/validar tokens.
+
+La clase debe implementar `generarToken()` usando HMAC256 y una contraseña secreta, con fecha de expiración.
+
+→ Usa `jwt.secret` y `jwt.expiration` en `application.properties`.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-aplique-mejores-practicas-proteja-api-rest/task/91700
+
+Artículo: [¿Qué es JSON Web Token? | Alura Cursos Online](https://www.aluracursos.com/blog/que-es-json-web-token)
+
+### Autenticación con JWT
+
+**Labels:** Seguridad, JWT
+
+**Description**
+
+Usa el token JWT para autenticar la gestión de registros de los tópicos (crear, consultar, actualizar, eliminar). La API debe responder solo si el token es válido.
+
+→ Considera mapear URLs y validar tokens con un `filter` o `interceptor`.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-aplique-mejores-practicas-proteja-api-rest/task/91701
+
+### Haz un README
+
+**Labels:** Git/GitHub, README
+
+**Description**
+
+Uno de los pasos más importantes al participar en un proceso de selección es resolver un desafío propuesto por la empresa, y generalmente esto debe estar descrito en el README. ¿Y qué es el **README**? Es un archivo con extensión **.md** y es un documento con la descripción del proyecto.
+
+### Terminar el Curso
+
+**Labels:** Envío del enlace
+
+**Description**
+
+Ahora que tu proyecto ya está listo, recuerda **enviar el enlace** del repositorio en GitHub al curso del challenge y descargar tu certificado.
+
+https://app.aluracursos.com/course/spring-framework-challenge-foro-hub/task/87075
+
+### Implementa otras rutas en tu aplicación (Opcional)
+
+**Labels:** API, CRUD, Opcional
+
+**Description**
+
+Implementa otras rutas además de tópicos, por ejemplo:
+
+- `/usuario`
+- `/respuestas`
+
+### Documentación con Swagger (Opcional)
+
+**Labels:** Documentación, API, Opcional
+
+**Description**
+
+Documenta tu API con Swagger. Agrega la dependencia y prueba los endpoints desde la interfaz gráfica.
+
+Curso sugerido: https://app.aluracursos.com/course/spring-boot-3-aplique-mejores-practicas-proteja-api-rest
