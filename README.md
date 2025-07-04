<div align="center">

# 🗣️ Foro Hub - Alura - Challenge - G8

### *Plataforma de discusión y comunicación para la comunidad*

[![Java](https://img.shields.io/badge/Java-17-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![Spring Security](https://img.shields.io/badge/Spring_Security-6.x-blue.svg)](https://spring.io/projects/spring-security)
[![JWT](https://img.shields.io/badge/JWT-Auth-purple.svg)](https://jwt.io/)
[![Swagger](https://img.shields.io/badge/Swagger-API_Docs-brightgreen.svg)](https://swagger.io/)



*Una aplicación web robusta y segura que facilita la comunicación efectiva entre usuarios a través de tópicos organizados y respuestas estructuradas.*

</div>

---

## 📋 Tabla de Contenidos

- [🚀 Características](#-características)
- [🛠️ Tecnologías](#️-tecnologías)
- [🏗️ Arquitectura](#️-arquitectura)
- [⚡ Inicio Rápido](#-inicio-rápido)
- [🔧 Configuración](#-configuración)
- [📡 API Reference](#-api-reference)
- [📚 Documentación](#-documentación)
- [🤝 Contribuir](#-contribuir)
- [📄 Licencia](#-licencia)

---

## 🚀 Características

<table>
<tr>
<td width="50%">

### 🔐 Autenticación & Seguridad
- ✅ Registro de nuevos usuarios
- ✅ Autenticación JWT segura
- ✅ Autorización basada en roles
- ✅ Protección de endpoints

</td>
<td width="50%">

### 💬 Gestión de Contenido
- ✅ Creación de tópicos
- ✅ Respuestas a discusiones
- ✅ Edición y eliminación
- ✅ Sistema de estados

</td>
</tr>
<tr>
<td width="50%">

### 📊 Funcionalidades Avanzadas
- ✅ Paginación inteligente
- ✅ Filtros y búsquedas
- ✅ Validaciones robustas
- ✅ Manejo de errores

</td>
<td width="50%">

### 🛡️ Calidad & Documentación
- ✅ API REST bien documentada
- ✅ Swagger UI integrado
- ✅ Arquitectura escalable
- ✅ Buenas prácticas

</td>
</tr>
</table>

---

## 🛠️ Tecnologías

<div align="center">

| Backend | Base de Datos | Seguridad | Documentación | Testing |
|---------|---------------|-----------|---------------|---------|
| ![Java](https://img.shields.io/badge/Java-17-orange?style=for-the-badge&logo=java) | ![H2](https://img.shields.io/badge/H2-Database-blue?style=for-the-badge) | ![JWT](https://img.shields.io/badge/JWT-Auth-purple?style=for-the-badge) | ![Swagger](https://img.shields.io/badge/Swagger-UI-brightgreen?style=for-the-badge) | ![Postman](https://img.shields.io/badge/Postman-Testing-orange?style=for-the-badge) |
| ![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-brightgreen?style=for-the-badge&logo=spring) | ![MySQL](https://img.shields.io/badge/MySQL-Ready-blue?style=for-the-badge&logo=mysql) | ![Spring Security](https://img.shields.io/badge/Spring_Security-6.x-green?style=for-the-badge) | ![OpenAPI](https://img.shields.io/badge/OpenAPI-3.0-lightblue?style=for-the-badge) | ![JUnit](https://img.shields.io/badge/JUnit-Testing-red?style=for-the-badge) |
| ![JPA](https://img.shields.io/badge/JPA-Hibernate-yellow?style=for-the-badge) | | | | |

</div>

---

## 🏗️ Arquitectura

```
src/
├── 🏢 entities/          # Modelos de datos y entidades JPA
├── 📦 dto/               # Data Transfer Objects
├── 🗄️ repository/        # Interfaces de acceso a datos
├── ⚙️ service/           # Lógica de negocio
├── 🌐 controller/        # Controladores REST
├── 🔒 security/          # Configuración de seguridad
├── 🛠️ config/           # Configuraciones de la aplicación
└── 📋 validation/        # Validadores personalizados
```

### 🎯 Principios Aplicados

- **🔄 Separación de Responsabilidades**: Cada capa tiene una función específica
- **🛡️ Seguridad por Diseño**: Implementación de JWT y Spring Security
- **📝 Clean Code**: Código legible y mantenible
- **🔧 SOLID**: Principios de diseño orientado a objetos

---

## ⚡ Inicio Rápido

### 📋 Prerrequisitos

- ☕ **Java 17+**
- 🔨 **Maven 3.8+**
- 🖥️ **IDE** (IntelliJ IDEA, Eclipse, VS Code)

### 🚀 Instalación

1. **Clonar el repositorio**
   ```bash
  [ git clone (https://github.com/pedrogalvis/foro-alura-challenge)
 
   ```

2. **Instalar dependencias**
   ```bash
   mvn clean install
   ```

3. **Ejecutar la aplicación**
   ```bash
   mvn spring-boot:run
   ```

4. **¡Listo!** 🎉
   ```
   Aplicación ejecutándose en: http://localhost:8080
   Swagger UI disponible en: http://localhost:8080/swagger-ui/index.html
   ```

---

## 🔧 Configuración

### 🗄️ Base de Datos

<div align="center">
<img src="(https://github.com/pedrogalvis/foro-alura-challenge)" alt="Database Schema" width="500"/>
</div>

#### H2 (Desarrollo)
```properties
# application.properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driver-class-name=org.h2.Driver
spring.h2.console.enabled=true
```

#### MySQL (Producción)
```properties
# application-prod.properties
spring.datasource.url=jdbc:mysql://localhost:3306/foro-alura-challenge
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
```

### 🔐 JWT Configuration
```properties
jwt.secret=tu_clave_secreta_super_segura
jwt.expiration=86400000
```

---

## 📡 API Reference

### 🔑 Autenticación

<details>
<summary><strong>POST</strong> <code>/login</code> - Iniciar sesión</summary>

**Request:**
```json
{
  "username": "user@gmail.com",
  "password": "123"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiJ9...",
  "type": "Bearer",
  "expiresIn": 86400000
}
```
</details>

### 👥 Usuarios

<details>
<summary><strong>GET</strong> <code>/usuarios</code> - Listar usuarios</summary>

**Headers:**
```
Authorization: Bearer {token}
```

**Response:**
```json
{
  "content": [
    {
      "id": 1,
      "username": "usuario1",
      "email": "user@gmail.com",
      "createdAt": "2024-07-01T10:00:00Z"
    }
  ],
  "totalElements": 10,
  "totalPages": 2
}
```
</details>

### 💭 Tópicos

<details>
<summary><strong>GET</strong> <code>/topicos</code> - Listar tópicos</summary>

**Query Parameters:**
- `page` (int): Número de página (default: 0)
- `size` (int): Tamaño de página (default: 10)
- `sort` (string): Campo de ordenamiento

**Response:**
```json
{
  "content": [
    {
      "id": 1,
      "title": "Introducción a Spring Boot",
      "message": "¿Cuáles son las mejores prácticas para...",
      "status": "ACTIVO",
      "usuario_Id": 1,
      "curso": "Java Backend",
      "date": "2024-07-01T08:00:00Z"
    }
  ],
  "totalElements": 25,
  "totalPages": 3
}
```
</details>

<details>
<summary><strong>POST</strong> <code>/topicos</code> - Crear tópico</summary>

**Request:**
```json
{
  "title": "Nuevo tópico sobre...",
  "message": "Contenido detallado del mensaje...",
  "curso": "Nombre del curso"
}
```

**Response:**
```json
{
  "id": 10,
  "title": "Nuevo tópico sobre...",
  "message": "Contenido detallado del mensaje...",
  "status": "ACTIVO",
  "usuario_Id": 5,
  "curso": "Nombre del curso",
  "date": "2024-07-04T15:30:00Z"
}
```
</details>

---

## 📚 Documentación

### 📖 Swagger UI

La documentación interactiva de la API está disponible en:

```
http://localhost:8080/swagger-ui/index.html
```

![Swagger Documentation](hub/swagger.png)

### 🔍 Características de la Documentación

- 📋 **Listado completo de endpoints**
- 🧪 **Pruebas interactivas en vivo**
- 📝 **Esquemas de datos detallados**
- 🔐 **Autenticación JWT integrada**
- 📊 **Códigos de respuesta explicados**

---

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! 🎉

### 🔄 Proceso de Contribución

1. **Fork** el proyecto
2. **Crea** una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. **Abre** un Pull Request

### 📋 Guías

- 📝 Sigue las convenciones de código existentes
- ✅ Asegúrate de que las pruebas pasen
- 📚 Actualiza la documentación si es necesario
- 🐛 Reporta bugs a través de Issues

---

## 📄 Licencia

Este proyecto está licenciado bajo la **Licencia MIT** - ver el archivo [LICENSE](LICENSE) para más detalles.

```
---

<div align="center">

### 💖 ¡Gracias por usar Foro Hub!

**[⭐ Dale una estrella](https://github.com/pedrogalvis/foro-alura-challenge/)** | **[🐛 Reportar Bug](https://github.com/pedrogalvis/foro-alura-challenge/)** | **[💡 Solicitar Feature](https://github.com/pedrogalvis/foro-alura-challenge/)**

---

*Desarrollado con ❤️ por la comunidad*

</div>
