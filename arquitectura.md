---
title: Arquitectura Global
nav_order: 2
---

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
