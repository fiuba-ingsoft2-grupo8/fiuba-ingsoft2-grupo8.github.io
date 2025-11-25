---
title: CI/CD
nav_order: 3
---

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
