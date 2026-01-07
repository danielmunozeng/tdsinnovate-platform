# TDS Innovate – Web Platform

Plataforma web corporativa de **TDS Innovate**, diseñada como una solución **moderna, desacoplada y escalable**, que sirve tanto como sitio institucional como base para futuros productos y servicios tecnológicos.

Este proyecto sigue principios de **arquitectura limpia**, buenas prácticas de ingeniería de software y estándares actuales de la industria.

---

## 🧭 Visión del Proyecto

El objetivo de esta plataforma es:

- Presentar profesionalmente los servicios de TDS Innovate
- Servir como **carta de presentación técnica**
- Permitir evolución futura sin reescrituras
- Mantener una separación clara entre frontend y backend
- Facilitar mantenimiento, pruebas y escalabilidad

---

## 🏗️ Arquitectura General

La solución adopta una **arquitectura desacoplada**:
┌──────────────┐        HTTP / JSON        ┌──────────────┐
│              │  ─────────────────────▶   │              │
│  Frontend    │                           │   Backend    │
│  (Next.js)   │  ◀─────────────────────   │  (FastAPI)   │
│              │        REST API           │              │
└──────────────┘                           └──────────────┘
│
▼
┌──────────┐
│ Database │
│PostgreSQL│
└──────────┘

---

## 🖥️ Frontend

### Stack
- **Next.js** (App Router)
- **TypeScript**
- **Tailwind CSS**

### Responsabilidades
- Renderizado de la web pública (SSR / SSG)
- UI / UX
- Consumo de la API REST
- Validaciones de interfaz
- No contiene lógica de negocio crítica

---

## ⚙️ Backend

### Stack
- **FastAPI**
- **PostgreSQL**
- **SQLAlchemy**
- **Alembic**
- **Pydantic**

### Estilo arquitectónico
- **Clean Architecture / Hexagonal**

FastAPI se utiliza únicamente como **capa de entrada (API layer)**.  
La lógica de negocio es independiente del framework, evitando acoplamientos innecesarios.

---

## 🔗 Comunicación Frontend ↔ Backend

- **Protocolo:** HTTPS
- **Formato:** JSON
- **Estilo:** REST API

### Endpoints iniciales
- `GET /health`
- `GET /api/v1/services`
- `POST /api/v1/contact`

---

## 🧪 Calidad y Buenas Prácticas

- Separación de responsabilidades
- Validación de datos en backend
- Manejo centralizado de errores
- Logging estructurado
- Versionado de API (`/api/v1`)
- Preparado para testing automatizado

---

## 🚀 Despliegue

- Frontend: **Vercel**
- Backend: **Docker + VPS/Cloud**
- Secrets vía variables de entorno

---

## 👤 Autor

**Daniel Muñoz**  
Software Engineer · Backend · Infrastructure · Cybersecurity
