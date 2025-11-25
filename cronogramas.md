---
title: Cronogramas
nav_order: 8
---

## 📅 Cronograma Tentativo

El desarrollo se planificó en checkpoints con objetivos claros y medibles.  
Este cronograma puede adaptarse según los resultados de cada sprint, pero sirve como guía de avance del proyecto.

### 🔹 Segundo Checkpoint (4 semanas)

**Objetivos principales:**
- 📱 Entregar un **APK funcional** para que el corrector pueda probar la app.  
- 🔑 Implementar el **sistema de autenticación de usuarios** mediante **OAuth + JWT**.  
- 🌐 Desarrollar el **API Gateway** para la comunicación entre microservicios.
- 📈 Desarrollar el **Servicio de Métricas** para monitorear el sistema.  
- 🎨 Definir y documentar los **bocetos de las vistas** principales de la aplicación. 
- 📁 Implementar **Firebase**

**Épicas incluidas:**
- Usuarios.  
- Perfil.  
- Artistas.  
- Biblioteca.  
- Administración de Contenido.  
- Administración de Usuarios.  
- Explorar.

### 🔹 Tercer Checkpoint (3.5 semanas)

**Objetivos principales:**
- 📊 Incorporar **métricas en el Backoffice**.  
- ✅ Validar que se cumplen los **requisitos optativos necesarios** para la materia.  

**Épicas incluidas:**
- Reproducción.  
- Métricas.  
- Notificaciones.  
- Social.  
- Onboarding de Usuario.  

### 🔹 Cuarto Checkpoint (3 semanas)

**Objetivos principales:**
- 🧩 Implementar **pruebas de integración** sobre todos los servicios.  
- 📚 Completar y consolidar toda la **documentación integrable**.  
- 🧪 Realizar **testing masivo** de la app y el backoffice, verificando los criterios de aceptación.  
- 📝 Confirmar que todos los **microservicios generan logs consistentes**.  
- 📊 Verificar el correcto funcionamiento de las **métricas en todo el sistema**.  

## 📅 Cronograma Real

### 🔹 Primer Checkpoint (4 semanas)

#### Objetivos del Sprint

1. En esta primera entrega se alcanzó la integración inicial entre el 'Backend', 'Backoffice' y la 'Aplicación Mobile'.
2. Se hizo el despliegue de todos los microservicios en la nube.
3. Se generó todo el flujo de 'CI/CD' en ambos microservicios.
4. Se inicializaron ambas bases de datos.
5. Se definió la arquitectura a seguir.

#### Camila

1. ✅ Armado de la estructura del endpoint. Database, Controller, Model, Schema.
2. ✅ Desarrollo de endpoints de songs.
3. ✅ Armado de las pruebas y debugging en local.
4. ✅ Configuración del testing para deploy.
5. ✅ Documentación sobre stack elegido.

#### Esteban

1. ✅ Puesta en marcha del repositorio con Docker para local y remoto.
2. ✅ Conexión con MongoDB desde content-api.
3. ✅ Armado del deploy para produccion.
4. ✅ Desarrollo de endpoints de playlist.
5. ✅ Documentación integral de los repositorios del Backend.

#### Felipe

1. ✅ Capacitación inicial en TypeScript, React, React Native y JavaScript.
2. ✅ Reuniones de equipo para comprender en profundidad el enunciado.
3. ✅ Definición de arquitectura → elección de Expo por sus ventajas en desarrollo móvil.
4. ✅ Configuración de entorno local y emuladores Android.
5. ✅ Desarrollo de las primeras pantallas y conexión con APIs (local y en la nube).

#### Joaquín

1. ✅ Crear organización en Github.
2. ✅ Levantar instancias en AWS EC2 para user-api, content-api y el backoffice.
3. ✅ Levantar bases de datos en Supabase (PostgreSQL) y Atlas (MongoDB).
4. ✅ Configurar estructura inicial (Dockerfile, Docker Compose, Makefile, etc) de user-api y content-api.
5. ✅ Desarrollar endpoints básicos para la user-api.
6. ✅ Configurar Github Runners.
7. ✅ Configurar CI/CD para user-api y content-api.
8. ✅ Documentar diagrama de arquitectura y CI/CD.

#### Martín

1. ✅ Creación del repositorio con un Backoffice muy básico.
2. ✅ Levantar el backoffice con un compose que funcionaba para hacer pruebas de manera local.
3. ✅ Levantar el backoffice con el compose-remote que se conectaba con la base de datos y le pegaba a los Endpoints de la API del usuario.
4. ✅ Emprolijar un poco el frontend (botoón y título).
5. ✅ Creacion de un archivo CI que corre un Linter al pushear.
6. ✅ Creación del archivo CD para que al pushear o realizar un pr a main se haga el Deploy a AWS.
7. ✅ Documentar bien el Readme, explicando como se levanta el backoffice y justificaciones del stack elegido.

### 🔹 Segundo Checkpoint (4 semanas)

#### Objetivos del Sprint

1. Creación de todos los microservicios restantes.
2. Realizó el despliegue de las métricas.
3. Integró la funcionalidad de gestión y reproducción canciones en la 'Aplicación Mobile' y el 'Backoffice'.
4. Implementaron las funcionalidades de administración de usuarios y contenido en el 'Backoffice'.
5. Redefinición del scope de las entidades.
6. Añadido del sistema de autenticación.
7. Conexión de 'Firebase' y 'Datadog' con el resto del sistema.

#### Camila

1. ✅ Bocetos del 'Home'.
2. ✅ Backend de la Biblioteca.
3. ✅ Lógica de gestión de imágenes.
4. ✅ Refactorización de la funcionalidad de la Playlists.
5. ✅ Integración de la 'Content API' con la 'Player API' desde el lado de la 'Content API'.

#### Esteban

1. ✅ Integración de la 'Content API' con la 'Player API' desde el lado de la 'Player API'.
2. ✅ Desarrollo de la 'Player API'.
3. ✅ Gestión de las canciones.
4. ✅ Relevamiento de los criterios de aceptación para las distintas funcionalidades.
5. ✅ Redefinición del scope del Sprint.

#### Felipe

1. ✅ Estrucutra inicial de la 'Chat API' (Mas adelante se modificó el enunciado y se descartó el microservicio del scope).
2. ✅ Estructura inicial de la 'Notification API'.
3. ✅ Creación de 'Supabase' e 'Firebase'.
4. ✅ Desarrollo de las vistas del 'Home' y los 'Perfiles'.
5. ✅ Integración de las nuevas 'APIs' con la 'Aplicación Mobile'.
6. ✅ Integración del sistema de autenticación en la 'Aplicación Mobile'.

#### Joaquín

1. ✅ CI/CD de la 'Chat API' (Mas adelante se modificó el enunciado y se descartó el microservicio del scope)..
2. ✅ CI/CD de la 'Notification API'.
3. ✅ CI/CD de la 'Player API'.
4. ✅ Implementación de API Gateway.
5. ✅ Despliegue de las métricas y logs en Datadog de todos los servicios.
6. ✅ Implementación de token de autorización.
7. ✅ Reseteo de contraseña con código por mail.
8. ✅ Implementación de la gestión de perfiles.

#### Martín

1. ✅ Implementación de la administración de usuarios.
2. ✅ Implementación de la administración de contenido.
3. ✅ Integración del sistema de autenticación en el 'Backoffice'.
4. ✅ Diseño 'UX/UI' de la interfaz del 'Backoffice'.
5. ✅ Testing integral del funcionamiento de las 'APIs'.

### 🔹 Tercer Checkpoint (3.5 semanas)

1. Integración de todos los logs en una única plataforma (Datadog).
2. Implementación de todas las historias obligatorias en la 'Aplicación Móvil' (Backend + Frontend).
3. Implementación de todas las historias obligatorias en el 'Backoffice' (Backend + Frontend).
4. Elección de las historias opcionales a implementar, en base a el MVP desarrollado.
5. Eliminación del microservicio 'Chat API' (Por cambio de enunciado).
6. Añadido del sistema de autorización y autenticación en todos los microservicios.

#### Camila

1. ✅ Creación del sistema de subida de imágenes.
2. ✅ Rediseño de la gestión de colecciones.
3. ✅ Pulida de bocetos visuales.
4. ✅ Diseño del menú desplegable en la Aplicación.
5. ✅ Desarrollo de los endpoints de Explorar.

#### Esteban

1. ✅ Creación del sistema de subida de canciones.
2. ✅ Desarollo de los endpoints de Biblioteca.
3. ✅ Desarrollo de los endpoints de Reproducción.
4. ✅ Diseño de funcionalidades desde la interfaz gráfico.
5. ✅ Control de consistencia en las bases de datos.
6. ✅ Sistema de Búsqueda.

#### Felipe

1. ✅ Desarollo de los endpoints de Notificaciones.
2. ✅ Diseño de funcionalidades desde la interfaz gráfico.
3. ✅ Integración de el sistema de Notificaciones en la Aplicación Móvil.
4. ✅ Integración de las historias de Contenido obligatorias en la Aplicación Móvil.
5. ✅ Integración de las historias de Usuarios obligatorias en la Aplicación Móvil.
6. ✅ Integración de las historias de Notificaciones obligatorias en la Aplicación Móvil.

#### Joaquín

1. ✅ Integración de todos los logs en una única plataforma (Datadog).
2. ✅ Desarrollo de los endpoints de perfil de Usuario.
3. ✅ Desarrollo de los endpoints de perfil de Artista.
4. ✅ Desarrollo de los endpoints de métricas.
5. ✅ Añadido de los sistemas de autenticación y autorización en los microservicios restantes.
6. ✅ Creación del sistema de subida de imágenes.

#### Martín

1. ✅ Desarollo de los endpoints de Administración de Contenido.
2. ✅ Desarollo de los endpoints de Administración de Usuarios.
3. ✅ Integración de los endpoints de Administración en el Backoffice.
4. ✅ Integración de los endpoints de Métricas de usuario en el Backoffice.
5. ✅ Testing de usuario de la Aplicación Móvil.

### 🔹 Cuarto Checkpoint (3 semanas)

1. Implementación de todas las historias opcionales en la 'Aplicación Móvil' (Backend + Frontend).
2. Implementación de todas las historias opcionales en el 'Backoffice' (Backend + Frontend).
3. Testing integral de la 'Aplicación Móvil'.
4. Testing integral del 'Backoffice'.
5. Corrección de bugs encontrados.
6. Finalización de documentaciones.
7. Preparación de la entrega final.

#### Camila

1. ✅ Finalización de la documentación.
2. ✅ Preparación de la exposición para la entrega.
3. ✅ Testing integral de la 'Aplicación Móvil'.
4. ✅ Desarrollo del Backend para las funcionalidades de Onboarding.
5. ✅ Desarrollo del Backend para las funcionalidades del Home.

#### Esteban

1. ✅ Finalización de la documentación.
2. ✅ Preparación de la exposición para la entrega.
3. ✅ Desarrollo del Backend para las funcionalidades opcionales para los Artistas.
4. ✅ Desarrollo del Backend para las funcionalidades opcionales del Reproductor.
5. ✅ Preparación de la Base de Datos para la entrega final.

#### Felipe

1. ✅ Finalización de la documentación.
2. ✅ Preparación de la exposición para la entrega.
3. ✅ Integración de las historias opcionales en la 'Aplicación Móvil'.
4. ✅ Testing integral de la 'Aplicación Móvil'.
5. ✅ Corrección de los bugs encontrados en la 'Aplicación Móvil'.

#### Joaquín

1. ✅ Finalización de la documentación.
2. ✅ Preparación de la exposición para la entrega.
3. ✅ Desarrollo del Backend para las funcionalidades opcionales para los Usuarios.
4. ✅ Desarrollo del Backend para las funcionalidades opcionales para las Métricas.
5. ✅ Desarrollo del Backend para las funcionalidades Sociales opcionales.

#### Martín

1. ✅ Finalización de la documentación.
2. ✅ Preparación de la exposición para la entrega.
3. ✅ Desarrollo del Backend para las funcionalidades opcionales para el 'Backoffice'.
4. ✅ Integración de las historias opcionales en el 'Backoffice'.
5. ✅ Testing integral del 'Backoffice'.
