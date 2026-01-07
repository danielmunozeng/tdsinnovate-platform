# ADR-001: Elección de Stack y Arquitectura (Next.js + FastAPI)

- **Estado:** Aceptada
- **Fecha:** 2026-01-06
- **Decisores:** Daniel Muñoz
- **Contexto:** Plataforma web corporativa y base escalable para TDS Innovate

## Contexto
Se requiere una plataforma web que funcione como carta de presentación profesional y que permita evolucionar sin reescrituras significativas.

Se busca:
- Sitio moderno con buen SEO y performance.
- Backend API desacoplado.
- Arquitectura mantenible y testeable.
- Evitar lock-in fuerte a un framework.

## Decisión
Arquitectura desacoplada con:

### Frontend
- **Next.js (App Router)** + **TypeScript** + **Tailwind CSS**

### Backend
- **FastAPI** + **PostgreSQL**
- Arquitectura: **Clean / Hexagonal**

### Comunicación
- **REST API (JSON) sobre HTTPS**

## Alternativas consideradas
1. **React SPA + API**
   - Pros: simple para dashboards.
   - Contras: SEO/performance inicial peor para sitio corporativo.

2. **Monolito MVC/MTV**
   - Pros: rápido para CRUD.
   - Contras: acoplamiento alto; menos flexible a futuro.

3. **GraphQL desde el inicio**
   - Pros: queries flexibles.
   - Contras: complejidad innecesaria para MVP.

## Consecuencias
### Positivas
- SEO y performance sólidos.
- API-first y desacoplamiento real.
- OpenAPI/Swagger automático.
- Core de negocio independiente del framework.
- Preparado para escalar.

### Negativas / Costos
- Mantener dos componentes (web + api).
- Requiere disciplina en versionado de API y CORS.

## Reglas acordadas
- La lógica de negocio no vive en los endpoints.
- API versionada bajo `/api/v1`.
- Secrets nunca se commitean.
- Documentación oficial vive en `docs/`.

## Próximos pasos
- Definir contrato API v1.
- Documentar arquitectura backend en detalle.
- Implementar endpoints iniciales: health, services, contact.
