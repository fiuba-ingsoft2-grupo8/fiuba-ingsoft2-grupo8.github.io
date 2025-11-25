---
title: Infraestructura y Servicios
nav_order: 4
---

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
