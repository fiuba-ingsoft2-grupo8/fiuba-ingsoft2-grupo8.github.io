---
title: Retrospectiva
nav_order: 9
---

## 🗓️ Retrospectiva

### 🗃️ Principales lecciones aprendidas

El trabajo de estos últimos 3 meses hizo que todo el equipo adquiera diversos conocimientos en diferentes áreas para alcanzar todos los requisitos solicitados.

Además de las capacitaciones correspondientes a las tecnologías específicas de cada sector del desarrollo (Backend, Frontend, Bases de Datos, etc.), los principales conceptos adoptados por el equipo en su integridad fueron:

#### Técnicos

1. Flujos 'CI-CD'.
2. Despliegue de servicios en la nube.
3. Integración de componentes.
4. Testing intensivo de servicios, aplicación y backoffice.
5. Uso de herramientas de despliegue, integración y medición de rendimiento (AWS y Datadog).

#### Equipo

1. Trabajo en simultáneo sobre un mismo servicio.
2. Definición de contratos entre diferentes componentes.
3. Reuniones profesionales de desarrollo, que optimizan duración y utilidad de las mismas.
4. Pair-Programming.
5. Habilidades de capacitación hacia otros compañeros.

### 📉 Objetivos descartados

Durante la implementación de la aplicación, fueron descartados algunas implementaciones en post de cumplir los tiempos de entrega y ajustarse a los plazos brindados.

Por lo que a continuación se detallan los features que creemos aportarían mucho valor al producto realizado:

1. Sistema de notificaciones mejorado, con 'Deep Links'.
2. Login con preveedor federado.
3. Reproducción 'On-Demand'.

### 📈 Puntos fuertes del producto

Al dar por terminado el proyecto, gracias a las buenas decisiones de arquitectura y diseño tomadas, se detectaron grandes puntos fuertes en la aplicación.

Principalmente se destacan los siguientes:

1. Alta performance: La mayor parte del procesamiento se realiza en los microservicios, garantizando altas cotas de rendimiento en la aplicación.
2. Arquitectura y Diseño: Desde un principio se planteó la cantidad de Microservicios adecuada, consiguiendo una distribución de responsabilidades correcta, sin exagerar el número de los mismos.
3. Seguridad: Los sistemas de 'Autenticación' y 'Autorización' garantizan gran seguridad en el sistema, dando la tranquilidad a los usuarios de que su información está bien resguardada. La adopción temprana del 'JWT' compartido entre Microservicios y el 'API Gateway' fueron vitales para los resultados obtenidos.
4. Datadog: La integración de todos los 'Logs' de los Microservicios en esta plataforma, la hizo una herramienta vital en el desarrollo para agilizar muchísimo el desarrollo, y comparar interacciones de múltiples Microservicios con la aplicación, en simultáneo.
5. UX / UI: No solo se logró un diseño agradable para los usuarios. Sino que también se consiguió adoptar varios diferenciadores visuales, para darle entidad a nuestra propia marca, y no obtener una simple copia de la aplicación de referencia (Spotify).

### 👨🏻‍💼 Trabajo en equipo 👩🏻‍💼

Por último, se destaca el gran trabajo en equipo durante todo el desarrollo de la aplicación.

Cada integrante del mismo hizo su aporte de la mejor manera posible, lo que generó un entorno de trabajo muy agradable, y que brindó grandes resultados.

### 💀 Post Mortem 💀

En este apartado se deja el detalle de cuales fueron los principales problemas que se encontró cada integrante durante el desarrollo del proyecto.

La idea es dejar documentado cuales fueron los puntos donde se encontraron grandes dificultades de desarrollo, y que requirieron mas tiempo para ser implementados de forma correcta.

#### Camila

1. Primera experiencia real construyendo y consumiendo 'APIs'.
2. Añadido de nuevas funcionalidades con un estado muy avanzado del proyecto.
3. Aprender a usar la herramienta 'Figma' para diseños 'UX/UI'.

#### Esteban

1. Aprender a trabajar con múltiples 'APIs' al mismo tiempo.
2. Manejo de autenticación y 'JWTs'.
3. Mantener la coherencia entre entorno local y remoto.

#### Felipe

1. Aprender en profundidad todas las herramientas necesarias de 'React Native' y 'Expo'.
2. Preparar el entorno de desarrollo para soportar tanto el uso de un emulador local, como un dispositivo externo (Celular).
3. Integrar la 'Notifications API' con la 'App Mobile'.

#### Joaquín

1. Armar los workflows de deploy de cada 'API'.
2. Configurar el 'API Gateway'.
3. Implementar autenticación con JWT que funcione a traves de todas las'APIs'.

#### Martín.

1. Adaptación a 'Next.js App Router'.
2. Configuración del entorno local con 'Docker' y comunicación con la 'API' de usuarios.
3. Automatización del despliegue en 'AWS' con 'CI/CD' (Docker + GitHub Actions).

