# API Contract v1 (TDS Innovate Platform)

Este documento define el contrato de la API REST entre el **Frontend (Next.js)** y el **Backend (FastAPI)**.

> **Regla de oro:** el frontend consume este contrato; el backend lo implementa.  
> Si algo cambia, se versiona y se documenta aquí.

---

## 1) Base URL y versionado

- **Base path:** `/api/v1`
- **Formato:** JSON
- **Transporte:** HTTPS

Ejemplo:
- `GET /api/v1/health`

---

## 2) Convenciones generales

### 2.1 Headers
- `Content-Type: application/json`
- `Accept: application/json`

### 2.2 Identificadores
- IDs como `UUID` cuando aplique.

### 2.3 Fechas
- Formato: `ISO 8601` (UTC recomendado)

Ejemplo:
- `2026-01-06T22:15:30Z`

---

## 3) Estándar de respuestas y errores

### 3.1 Respuesta estándar (success)
Las respuestas devuelven un JSON con los datos del recurso.

### 3.2 Error estándar
Formato común de error para todas las rutas:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid request payload.",
    "details": [
      { "field": "email", "issue": "Invalid email format" }
    ]
  }
}
