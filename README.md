# CRUD Application

Este repositorio incluye un proyecto CRUD con un backend y un frontend separados, configurados para ejecutarse utilizando Docker.

## Repositorios

- **Backend:** [GitHub - Backend](https://github.com/lDavidSantiago/crud-backend)
- **Frontend:** [GitHub - Frontend](https://github.com/lDavidSantiago/crud-frontend)

## Video de Sustentación

Puedes ver el video de la sustentación del proyecto en el siguiente enlace:
[Video de Sustentación](https://www.youtube.com/watch?v=aCPlL7aPEIQ&t=24s&ab_channel=WILLIAMALEXANDERFRANCOOTERO)

## Configuración con Docker Compose

Este proyecto incluye un archivo `docker-compose.yml` para ejecutar el backend y el frontend de manera conjunta. A continuación se describe la configuración:

```yaml
version: '3.8'
services:
  backend:
    build:
      context: ./crud-backend
      dockerfile: Dockerfile
    ports:
      - "3000:3000"
    env_file:
      - ./crud-backend/.env
    volumes:
      - ./crud-backend:/app

  frontend:
    build:
      context: ./crud-frontend
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    depends_on:
      - backend
```

## Instrucciones para Ejecutar el Proyecto

1. Clona ambos repositorios (backend y frontend) en el mismo directorio:
   ```bash
   git clone https://github.com/lDavidSantiago/crud-backend.git
   git clone https://github.com/lDavidSantiago/crud-frontend.git
   ```

2. Asegúrate de que tengas Docker y Docker Compose instalados.

3. Desde el directorio principal que contiene los repositorios, ejecuta:
   ```bash
   docker-compose up --build
   ```

4. Accede a las aplicaciones:
   - **Frontend:** [http://localhost:8080](http://localhost:8080)
   - **Backend:** [http://localhost:3000](http://localhost:3000)

## Estructura del Proyecto

- `crud-backend/`: Código fuente del backend.
- `crud-frontend/`: Código fuente del frontend.
- `docker-compose.yml`: Configuración para orquestar los servicios Docker.

## Tecnologías Utilizadas

- **Backend:** Node.js, Express
- **Frontend:** React, Vite
- **Base de datos:** PostgreSQL (configuración necesaria en el backend)
- **Contenerización:** Docker, Docker Compose

