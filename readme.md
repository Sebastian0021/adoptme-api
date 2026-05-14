# AdoptMe API

Este proyecto es una API RESTful desarrollada en Node.js y Express, diseñada para gestionar de principio a fin el sistema central de una plataforma de adopción de mascotas. La aplicación maneja la lógica de usuarios, el registro de animales, el flujo de adopciones y cuenta con documentación interactiva integrada.

### Características Principales

- **Gestión de Mascotas (Pets):** Endpoints para registrar nuevas mascotas, actualizar su estado y listarlas.
- **Flujo de Adopciones:** Creación y seguimiento de procesos de adopción, vinculando usuarios con mascotas disponibles.
- **Gestión de Usuarios y Sesiones:** Registro de usuarios, autenticación y manejo seguro de sesiones.
- **Generación de Datos (Mocks):** Rutas específicas para poblar la base de datos con información de prueba de manera rápida.
- **Documentación Interactiva:** La API está completamente documentada utilizando Swagger, lo que permite explorar y probar los endpoints visualmente.
- **Arquitectura Escalable:** Estructura basada en controladores, servicios, repositorios y DTOs para un código limpio y mantenible.
- **Manejo de Errores y Logging:** Implementación de errores personalizados y un sistema de logging para facilitar el monitoreo y la depuración.
- **Dockerizada:** Lista para ser desplegada en cualquier entorno gracias a su configuración de contenedores.

### Tecnologías Utilizadas

- **Node.js & Express.js**
- **MongoDB & Mongoose:** Base de datos NoSQL y modelado de objetos.
- **Swagger:** Para la documentación de la API.
- **Docker:** Para la virtualización del entorno.
- **Winston / Custom Loggers:** Para el registro de actividad de la aplicación.
- **Dotenv:** Para la gestión de variables de entorno.

### Requisitos Previos

- Node.js (v18 o superior)
- MongoDB instalado localmente o un clúster en MongoDB Atlas
- Docker y Docker Compose (opcional, para entornos en contenedores)

### Instalación Local

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/Sebastian0021/adoptme-api.git](https://github.com/Sebastian0021/adoptme-api.git)
    cd adoptme-api
    ```

2.  **Instalar las dependencias:**
    ```bash
    npm install
    ```

3.  **Configurar variables de entorno:**
    Crea un archivo `.env` en la raíz del proyecto basándote en la configuración esperada en `src/config/dotenv.config.js`. Ejemplo:
    ```env
    PORT=8080
    MONGO_URL=tu_string_de_conexion_a_mongodb
    SESSION_SECRET=tu_secreto_para_sesiones
    ```

4.  **Ejecutar la aplicación:**
    ```bash
    npm start
    ```
    *Para entorno de desarrollo, puedes usar `npm run dev` (si tienes nodemon configurado).*

### Despliegue con Docker

Si prefieres levantar la aplicación utilizando contenedores, puedes construir y ejecutar la imagen con los siguientes comandos:

1.  **Construir la imagen de Docker:**
    ```bash
    docker build -t adoptme-api .
    ```

2.  **Correr el contenedor:**
    ```bash
    docker run -d -p 8080:8080 --env-file .env --name adoptme-container adoptme-api
    ```
    *La aplicación estará disponible en `http://localhost:8080`.*

### Documentación de la API

Una vez que el servidor esté corriendo, puedes acceder a la interfaz interactiva de la documentación generada con Swagger visitando:

`http://localhost:8080/api-docs` *(Asegúrate de verificar la ruta exacta según tu configuración de swagger en el código).*

Allí encontrarás el detalle completo de las colecciones de endpoints disponibles:
* `/api/users`
* `/api/pets`
* `/api/adoptions`
* `/api/sessions`
* `/api/mocks`
