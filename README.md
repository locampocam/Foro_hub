# Foro Hub API

API REST para la gestión de tópicos de un foro educativo. El proyecto replica el flujo de creación, consulta, actualización y eliminación de tópicos, además de incluir autenticación y autorización.

## 🚀 Funcionalidades

- Crear un nuevo tópico.
- Listar todos los tópicos.
- Consultar un tópico por ID.
- Actualizar un tópico existente.
- Eliminar un tópico.
- Autenticación y autorización con Spring Security + JWT.
- Persistencia en base de datos relacional.

## 🧰 Tecnologías

- Java 17+
- Spring Boot 3+
- Maven 4+
- Spring Web
- Spring Data JPA
- Flyway Migration
- Validation
- Spring Security
- JWT
- MySQL 8+ (o PostgreSQL si se prefiere)

## ✅ Requisitos previos

- JDK 17+ instalado
- Maven 4+
- Base de datos MySQL 8+ (o PostgreSQL)

## ⚙️ Configuración del entorno

1. Clonar el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd Foro_hub
```

2. Configurar la base de datos en `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/foro_hub
spring.datasource.username=TU_USUARIO
spring.datasource.password=TU_PASSWORD
spring.jpa.hibernate.ddl-auto=validate

jwt.secret=TU_SECRETO
jwt.expiration=3600000
```

3. Crear la base de datos:

```sql
CREATE DATABASE foro_hub;
```

4. Ejecutar la aplicación:

```bash
./mvnw spring-boot:run
```

## 🧪 Pruebas de API

Puedes probar los endpoints con **Postman** o **Insomnia**.

### Ejemplo de login

```http
POST /login
Content-Type: application/json

{
  "email": "usuario@correo.com",
  "password": "123456"
}
```

### Ejemplo de creación de tópico

```http
POST /topicos
Authorization: Bearer <TOKEN>
Content-Type: application/json

{
  "titulo": "Duda sobre Spring",
  "mensaje": "¿Cómo configuro Spring Security?",
  "autor": "Pedro",
  "curso": "Spring Boot"
}
```

## 📂 Estructura sugerida del proyecto

```
src/main/java
├── controller
├── domain
├── dto
├── repository
├── security
└── service
```

## 📌 Estado del proyecto

Este proyecto se encuentra en desarrollo como parte del challenge **Foro Hub** de Alura Latam.

## 📜 Licencia

Este proyecto es para fines educativos y puede ser modificado libremente.