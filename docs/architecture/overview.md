# Arquitectura – Overview

## Objetivo
Construir una plataforma web moderna para TDS Innovate que funcione como:
- Sitio corporativo (SEO + performance + confianza).
- Base escalable para futuras funcionalidades (auth, portal, dashboards, productos).

## Diseño de alto nivel
Arquitectura desacoplada:

- **Frontend (Next.js)**: UI/UX + SSR/SSG + consumo de API.
- **Backend (FastAPI)**: API REST + reglas de negocio + integración con DB/servicios.
- **DB (PostgreSQL)**: persistencia.
- Comunicación: **HTTPS + JSON (REST)**.

## Razones de elección

### Next.js (Frontend)
- SSR/SSG para SEO y performance.
- Estructura por rutas y layouts.
- Escala bien desde landing a aplicación.

### FastAPI (Backend)
- API-first, simple y potente.
- OpenAPI/Swagger automático (documentación y carta de presentación).
- Compatible con arquitectura Clean/Hexagonal para evitar lock-in.

### Clean/Hexagonal (Backend)
- Aísla la lógica de negocio del framework.
- Permite testear con facilidad.
- Facilita migraciones futuras con menos impacto.

## Principios clave
- Separación estricta de responsabilidades.
- Versionado de API (`/api/v1`).
- Seguridad por defecto (no secrets en repo, CORS controlado).
- Documentación versionada junto al código.
