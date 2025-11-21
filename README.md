🧠 Memorama Full Stack | Proyecto Final

Este proyecto es una aplicación de juego de memoria interactiva con una arquitectura Full Stack completa. El objetivo es ofrecer una experiencia dinámica y accesible que mide la concentración y la memoria visual, con la funcionalidad de ranking persistente utilizando MongoDB Atlas.

🚀 Arquitectura del Proyecto

El sistema sigue un modelo de servicio RESTful y está dividido lógicamente:

Componente

Carpeta

Tecnologías

Propósito

Frontend (Cliente)

/frontend

HTML5, CSS3, JavaScript (Vanilla JS)

Interfaz de usuario, lógica del juego (niveles, vidas, cronómetro), y consumo de la API (fetch).

Backend (Servidor)

/backend

Node.js, Express.js

Creación de endpoints RESTful (/api/scores), lógica de la API y seguridad.

Base de Datos

MongoDB Atlas

NoSQL (Mongoose)

Almacenamiento persistente de los puntajes del ranking (Top 10).

⚙️ Estructura del Repositorio

/memorama-fullstack-final
   /backend                  # Servidor Express y API
       /models               # Definición del esquema Mongoose (Score.js)
       .env                  # ¡Archivo SECRETO! Contiene la clave de MongoDB (ignorada por Git).
       index.js              # Punto de entrada del servidor (conexión a DB y rutas)
       package.json          # Dependencias: express, mongoose, cors, dotenv
   /frontend                 # Aplicación del cliente (Juego)
       index.html            # Estructura con menú, juego y ranking
       style.css             # Estilos modernos y responsivos
       script.js             # Lógica del juego, manejo de menú y API (fetch)
       /sounds               # Recursos de audio locales


🔐 Seguridad y Despliegue (Puntos Clave del 3er Parcial)

1. Variables de Entorno y Seguridad

La clave de conexión de MongoDB (MONGO_URI) no está codificada directamente en index.js.

Se utiliza la librería dotenv para cargar la clave desde un archivo .env local.

El archivo .env está en el archivo .gitignore, garantizando que las credenciales nunca se suban al repositorio público.

2. Despliegue (Hosting)

El proyecto está diseñado para un Despliegue Dividido:

Frontend: Se puede alojar en servicios de archivos estáticos (ej. Netlify o Vercel), que proveen una CDN rápida.

Backend: Se puede alojar en un servicio de Web Services (ej. Render o Cyclic), donde se establecería la variable de entorno MONGO_URI para que el servidor pueda conectarse a la Base de Datos.

▶️ Instrucciones de Ejecución Local

Para correr el proyecto completo en tu máquina:

A. Configuración del Servidor

Abre Git Bash y navega a la carpeta /backend.

Instala las dependencias: npm install

Crea el archivo .env y añade tu URL de MongoDB Atlas (esta es la clave que NO se sube a GitHub).

Inicia el servidor (se recomienda Nodemon): nodemon index.js

B. Ejecutar el Juego

Una vez que el servidor esté activo (puerto 3000), abre la carpeta /frontend.

Abre el archivo index.html en tu navegador.

Autor: Omar G.
Repositorio: https://docs.github.com/es/repositories/creating-and-managing-repositories/quickstart-for-repositories