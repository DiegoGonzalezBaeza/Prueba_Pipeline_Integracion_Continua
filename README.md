# Pipeline de Integración Continua 

Este proyecto implementa un pipeline de integración continua utilizando Jenkins para una API REST sencilla desarrollada en Node.js con Express.


## Descripción 

Esta aplicación es una API REST simple que proporciona endpoints para obtener información de usuarios. Utiliza un archivo JSON como base de datos y está configurada con un pipeline de CI/CD completo.
 

## Estructura del Proyecto 

```

Prueba_Pipeline_Integracion_Continua/

├── .gitignore

├── app.js           # Aplicación Express

├── db.json          # Base de datos JSON

├── jenkinsfile      # Configuración del pipeline de Jenkins

├── package.json     # Dependencias y scripts

├── README.md

├── img/             # Imágenes de documentación

└── tests/           # Pruebas automatizadas

    └── app.test.js

```

## Tecnologías Utilizadas
 

- Node.js

- Express

- Jest (pruebas)

- Supertest (pruebas de API)

- Jenkins (integración continua)

## Endpoints de la API 

- `GET /users` - Obtiene la lista de todos los usuarios

- `GET /users/:id` - Obtiene un usuario específico por su ID
 

## Configuración del Pipeline 

El pipeline de Jenkins incluye las siguientes etapas:

 

1. **Checkout**: Clonación del repositorio

2. **Build**: Instalación de dependencias

3. **Test**: Ejecución de pruebas automatizadas

4. **Deploy**: Despliegue de la aplicación
 

## Instalación y Ejecución Local
 

1. Clonar el repositorio

2. Instalar dependencias

   ```

   npm install

   ```

3. Ejecutar la aplicación

   ```

   npm start

   ```

4. Ejecutar las pruebas

   ```

   npm test

   ```

## Puerto 

La aplicación se ejecuta por defecto en http://localhost:3000

## Requisitos 

- Node.js (v18 recomendado)

