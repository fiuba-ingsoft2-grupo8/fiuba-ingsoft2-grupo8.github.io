# 🎶 Proyecto Melodía – Documentación Integral

Bienvenido al repositorio central de **documentación** del proyecto **Melodía**, desarrollado en el marco de la materia **Ingeniería de Software II (FIUBA)**.

Aquí se encuentran recopilados los conceptos principales, la planificación, las decisiones de arquitectura y la organización general del desarrollo.  

Cada repositorio complementario incluye documentación específica de su implementación, pero este espacio busca **unificar la visión global del proyecto**.

👉 [Documentación del Proyecto](https://fiuba-ingsoft2-grupo8.github.io/)

## 📖 Introducción

En este repositorio se encuentra toda la **documentación integral** relacionada al proyecto:

- ✅ Decisiones de arquitectura.
- ✅ Tareas realizadas por sprint.
- ✅ Problemas detectados.
- ✅ Stacks tecnológicos elegidos.
- ✅ Explicaciones de uso y de despliegue.

La idea principal es **englobar los conceptos más grandes** y dejar asentada una planificación tentativa sobre cómo se organizará el desarrollo del trabajo práctico.

## 🏗️ Arquitectura Global

![](img/arquitectura-final.png)

Actualmente la arquitectura esta formada por los siguientes servicios:
- Mobile app: App mobile que se conecta a las distintas apis del backend.
- Backoffice: Página web para administrar.
- User API: Gestión de usuarios.
- Content API: Gestión de contenido como artistas, canciones y playlists.
- Player API: Gestión de la reproducción de las canciones.
- Notification API: Gestión del sistema de notificaciones.
- PostgreSQL.
- MongoDB.
- Supabase.
- Firebase.
- Datadog: Recibe los logs de todos los servicios y se generan dashboards para mejorar la visibilidad sobre todo el sistema.

👉 [Link a Datadog](https://us5.datadoghq.com/logs?query=&agg_m=count&agg_m_source=base&agg_t=count&cols=host%2Cservice&fromUser=true&messageDisplay=inline&refresh_mode=sliding&storage=hot&stream_sort=desc&viz=stream&from_ts=1760482838537&to_ts=1760483738537&live=true)

## ♾️ CI/CD

![CI/CD](img/cicd.png)

Cada microservicio contará con un pipeline de **CI/CD** independiente para garantizar **calidad**, **minimizar errores en producción** y **acelerar el ciclo de feedback**.

### 🔄 Continuous Integration (CI)

El flujo de CI corre cada vez que se realiza un PR o un cambio en las ramas main y develop.

**Infraestructura:** Utilizamos **GitHub Actions** con runners hosteados por GitHub, proporcionando mayor velocidad y confiabilidad.

**Pipeline de CI incluye:**
- 🧪 **Testing automatizado:** Cobertura mínima del 75% con reportes automáticos en cada PR.
- ✅ **Validaciones de calidad:** Linters, formatters y análisis estático de código.

**Flujo específico por tecnología:**
- **Backend (Node.js/Python/Go):** Jest/PyTest/Go test.
- **Frontend (React Native):** Jest + ESLint + Expo CLI validations.

### 🚀 Continuous Deployment (CD)

El flujo de CD corre luego de realizar un merge o un push en la rama main.

**Proceso automatizado en dos etapas:**

1. **Build & Registry:**
   - 📦 Construcción de imagen Docker optimizada (multi-stage builds).
   - ⬆️ Push automatizado a **Docker Hub** con versionado.

2. **Deployment:**
   - 🔄 Pull de la nueva imagen desde el registro.
   - 🗑️ Eliminación controlada del contenedor anterior.
   - 🟢 Despliegue con **zero-downtime** usando health checks.
   - 🔐 Gestión segura de variables de entorno via **GitHub Secrets**.

Se utilizan secretos de Github para compartir variables de entorno.

### ♟️ Estrategias CI/CD por Componente

#### 📊 Microservicios (Backend)
- **CI/CD completo:** Pipeline integral con testing, build y deployment automatizado.
- **Testing robusto:** Pruebas unitarias y de integración con **cobertura mínima del 75%**.
- **Deployment:** Deployment en AWS EC2.
- **Monitoreo:** Health checks, logs estructurados y métricas de performance.

#### 🖥️ Backoffice (Web)
- **CI robusto:** Linting, testing y análisis de bundle size.
- **Deployment:** Deployment en AWS EC2.

#### 📱 Aplicación Móvil (React Native + Expo)
- **CI enfocado en calidad:** Validaciones de linter y formatter.
- **Build automatizado:** Generación de APK/IPA en cada release.
- **Distribución:** Deploy manual del APK.

## 🏗️ Infraestructura y Servicios

Nuestro ecosistema utiliza una infraestructura cloud:

### 🖥️ Compute & Hosting

#### **Amazon EC2 - Instancias t3.micro**
- **user-api:** Microservicio de gestión de usuarios.
- **content-api:** Microservicio de gestión de contenido.
- **player-api:** Microservicio de gestión de reproducción.
- **notifications-api:** Microservicio de gestión de notificaciones.
- **backoffice:** Aplicación web administrativa.

**Características:**
- ⚡ 2 GB de memoria RAM.
- 🌍 Región AWS us-east-2 (Ohio).
- 🔒 Configuración con security groups restrictivos.

### 🗄️ Bases de Datos

#### **Supabase - PostgreSQL**
- 🔧 **Uso:** Base de datos relacional principal.
- ✅ **Beneficios:** Backend-as-a-Service con autenticación integrada, APIs REST automáticas.
- 🔐 **Seguridad:** Row Level Security (RLS) y conexiones SSL/TLS.

#### **MongoDB Atlas - Hosteado en AWS**
- 🔧 **Uso:** Base de datos NoSQL para datos no estructurados.
- ✅ **Beneficios:** consultas flexibles.
- 🌐 **Integración:** Mismo proveedor cloud para minimizar latencia.

#### **Firebase**
- 🔧 **Uso:** Gestión de las notificaciones de usuario.
- ✅ **Beneficios:** Fácil integrabilidad con 'Expo Go'.
- 🌐 **Integración:** Hosteado en Google Cloud.

### 📦 Registry & Contenedores

#### **Docker Hub**
- 🏷️ **Registro de imágenes:** Almacenamiento centralizado de contenedores.
- 🔄 **Versionado:** Gestión semántica de releases.
- ⚡ **Optimización:** Imágenes multi-stage para reducir tamaño.

## ⚙️ Microservicios Planificados

Los siguientes microservicios componen el ecosistema del proyecto:
  
- 🎵 **Reproducción.**  
- 🔔 **Notificaciones.**  
- 👤 **Usuarios.**  
- 📂 **Contenido.**  
- 📊 **Monitoreo.**

Cada uno de ellos está diseñado para ser **autónomo**, alineado con las mejores prácticas de desarrollo distribuido.

## 📚 Historias

La siguiente tabla presenta las historias de usuario organizadas por épicas, con su estado actual de desarrollo:

*Historia de usuario sin ninguna implementación:*  ![TODO](https://img.shields.io/badge/TODO-red)

*Historia de usuario implementada en el Back-End:* ![WIP](https://img.shields.io/badge/WIP-yellow)

*Historia de usuario integrada en el Front-End:* ![DONE](https://img.shields.io/badge/DONE-green)

*Historia de usuario que cumple con todos los criterios de aceptación:* ![FINISHED](https://img.shields.io/badge/FINISHED-purple)

*Historia de usuario que no se va a implementar:* ![REJECTED](https://img.shields.io/badge/REJECTED-brown)

*Historia de usuario planeada (optativas a realizar):* ![PLANNED](https://img.shields.io/badge/PLANNED-blue)

*Historia de usuario descartadas (optativas sobrantes):* ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray)

### Historias Obligatorias

| # | Historia | Épica | Estado |
|---|----------|-------|--------|
| 1 | Registro de usuarios | Usuarios | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 2 | Login con email y contraseña | Usuarios | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 3 | Recupero de contraseña | Usuarios | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 4 | Edición de perfil | Perfil | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 5 | Visualización de perfil propio | Perfil | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 6 | Centro + preferencias + disparadores esenciales | Notificaciones | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 7 | Listar usuarios del sistema | Adm. Usuarios | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 8 | Bloquear/Desbloquear usuario | Adm. Usuarios | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 9 | Catálogo: Listar/buscar/filtrar | Adm. Contenido | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 10 | Contenido: Detalle y trazabilidad | Adm. Contenido | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 11 | Transiciones y estado efectivo | Adm. Contenido | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 12 | Perfil del artista | Artistas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 13 | Discografía | Artistas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 14 | Popular (Top del artista) | Artistas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 15 | Gestión de perfil del artista | Artistas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 16 | Publicación de lanzamientos | Artistas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 17 | Búsqueda unificada por tipo | Explorar | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 18 | Navegación a vistas de detalle | Explorar | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 19 | Creación y gestión de playlists | Biblioteca | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 20 | Reordenamiento en playlists | Biblioteca | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 21 | Historial de reproducción | Biblioteca | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 22 | Liked Songs | Biblioteca | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 23 | Reproducción y controles básicos | Reproducción | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 24 | Controles avanzados del player | Reproducción | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 25 | Gestión de cola | Reproducción | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 26 | Toggle de Liked desde el player | Reproducción | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |
| 27 | Métricas de usuario (panel + export) | Métricas | ![FINISHED](https://img.shields.io/badge/FINISHED-purple) |

### Historias Opcionales (Se requieren 50 puntos)

| # | Historia | Épica | Puntos | Estado | Decisión |
|---|----------|-------|--------|--------|----------|
| 1 | Login con proveedor federado | Usuarios | 2 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 2 | Ver perfil de otros usuarios | Perfil | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 3 | Deep links avanzados en notificaciones | Notificaciones | 5 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 4 | Perfil detallado (admin) | Adm. Usuarios | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 5 | Disponibilidad por región/ventana (backoffice) | Adm. Contenido | 5 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 6 | Bloqueo/desbloqueo con alcance | Adm. Contenido | 3 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 7 | Métricas de canciones/álbumes | Métricas | 3 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 8 | Métricas de artista (panel + export) | Métricas | 5 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 9 | Colaboraciones / "Aparece en" | Artistas | 3 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 10 | Disponibilidad por territorios/ventana (creators) | Artistas | 3 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 11 | Autocompletar metadatos (Fast Complete) [IA] | Artistas | 5 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 12 | Artistas relacionados (Similares a) | Artistas | 4 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 13 | Explorar Home (base) | Explorar | 3 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 14 | "New release from {Artist}" | Explorar | 2 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 15 | "Discover more from {Artist}" | Explorar | 2 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 16 | Made For You (Discover/Daily Mix) | Explorar | 8 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 17 | Mood Mixes asistidos [IA] | Biblioteca | 5 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 18 | Videos musicales asociados | Reproducción | 8 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 19 | Reproducción On-Demand (multidispositivo) | Reproducción | 5 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 20 | Reproducción continua (autoplay sin cola) [IA] | Reproducción | 3 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 21 | Seguir/Dejar de seguir usuarios | Social | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 22 | Feed de actividad de amigos (+ filtros) | Social | 3 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 23 | Compartir canciones/playlists | Social | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 24 | Playlists temáticas por contexto | Vibras | 3 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 25 | Radio por canción [IA] | Vibras | 3 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 26 | Auto Play (nuevo contexto de 15 canciones) [IA] | Vibras | 3 | ![REJECTED](https://img.shields.io/badge/REJECTED-brown) | ![DISCARDED](https://img.shields.io/badge/DISCARDED-gray) |
| 27 | Onboarding: géneros favoritos | Onboarding | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 28 | Onboarding: artistas favoritos | Onboarding | 2 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |
| 29 | Onboarding: preferencias de notificaciones | Onboarding | 1 | ![WIP](https://img.shields.io/badge/WIP-yellow) | ![PLANNED](https://img.shields.io/badge/PLANNED-blue) |

## 📂 Repositorios del Proyecto

- 📘 **fiuba-ingsoft2-grupo8.github.io** → Repositorio actual que contiene la documentación integral.  
- 🏛️ **.github** → Contiene el README de la organización con la introducción y presentación del grupo.  
- 📱 **melodia-app-mobile** → Aplicación móvil desarrollada en React Native + Expo.  
- 🖥️ **melodia-backoffice** → Aplicación web de backoffice utilizada por administradores para interactuar con el sistema.  
- 📂 **content-api** → Microservicio encargado de la gestión de contenido (playlists, canciones, etc.).  
- 👥 **user-api** → Microservicio encargado de la gestión de usuarios.
- 🎵 **player-api** → Microservicio encargado de la gestión de reproducción.
- 🔔 **notifications-api** → Microservicio encargado de la gestión de notificaciones.

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
4. Elección de las historias optativas a implementar, en base a el MVP desarrollado.
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

## 🏆 Conclusión

Este repositorio refleja la **visión global** del proyecto Melodía, alineado con las mejores prácticas de **ingeniería de software**, con foco en:  
- 🔒 Seguridad.   
- 📈 Escalabilidad.   
- 🧹 Calidad de código.   
- 📖 Documentación clara.   

El objetivo final es entregar un producto robusto, bien documentado y de calidad profesional, listo para ser evaluado y utilizado.  
