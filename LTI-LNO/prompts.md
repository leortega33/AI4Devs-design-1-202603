# Prompts utilizados — LTI ATS

Registro cronológico de los prompts utilizados para diseñar y documentar el sistema LTI ATS.

---

## Prompt 1 — PRD completo del ATS

> **Rol:** Product Manager Senior  
> **Modelo:** Claude (Opus)

```
Actúa como un Product Manager senior. Necesito un PRD para un ATS (Applicant-Tracking System) del futuro. Un ATS tiene como objetivo optimizar, centralizar y automatizar todo el proceso de reclutamiento, desde que se crea una vacante hasta que el candidato es contratado. Pero yendo mas lejos el objetivo ideal y esperado es Un ATS moderno busca transformar el proceso de reclutamiento en un flujo inteligente, automatizado y basado en datos que maximiza la eficiencia y la calidad de contratación Genera un PRD completo incluyendo: problema a resolver, objetivos medibles, user stories principales, requisitos funcionales y no funcionales, y criterios de éxito.
```

**Contexto adicional:** Se adjuntó una imagen de referencia de un sistema ATS mostrando el ciclo: Creating Jobs → Jobs Published → Job Applications Received → Applications Reviewed → Online Tests Conducted → Interviews Scheduled → Selected Applicants Hired.

---

## Prompt 2 — Casos de uso con diagramas UML

> **Rol:** Analista de software experto  
> **Modelo:** Claude (Opus)

```
Ahora en el mismo documento vamos a definir los casos de uso. Eres un analista de software experto. Representa estos casos de uso en el tipo de diagrama más adecuado usando el formato Mermaid. Acorde a la sintaxis y buenas prácticas UML, define y describe lo que sea necesario.
```

---

## Prompt 3 — Modelo de datos

> **Rol:** Arquitecto de software  
> **Modelo:** Claude (Opus)

```
Ahora vamos por el modelo de datos, eres un brillante arquitecto de software. Eres capaz de diseñar, explicar y diagramar los diferentes aspectos de un sistema de software. Necesito que lo apliques en el documento actual con Mermaid.
```

---

## Prompt 4 — Arquitectura de infraestructura AWS

> **Rol:** Arquitecto cloud senior especializado en AWS  
> **Modelo:** Claude (Opus)

```
Actúa como un arquitecto cloud senior especializado en AWS y sistemas de alto tráfico.

Necesito diseñar la arquitectura de infraestructura para un sistema ATS (Applicant Tracking System) moderno. Este sistema debe cubrir el ciclo completo de reclutamiento:
- Creación y gestión de vacantes
- Publicación en múltiples canales (job boards, redes sociales)
- Recepción y almacenamiento de aplicaciones
- Filtrado y scoring de candidatos
- Evaluaciones online
- Scheduling de entrevistas
- Gestión de contratación

### Requisitos técnicos:
- Arquitectura basada en microservicios
- Backend desarrollado en Java (Spring Boot)
- Frontend web (React)
- Base de datos relacional (PostgreSQL)
- Soporte para procesamiento asíncrono (colas/eventos)
- API Gateway centralizado
- Autenticación y autorización (RBAC, OAuth2/JWT)
- Almacenamiento de archivos (CVs, documentos)

### Requisitos no funcionales:
- Alta disponibilidad (multi-AZ)
- Escalabilidad automática
- Baja latencia
- Seguridad (cumplimiento tipo PCI-DSS y buenas prácticas)
- Observabilidad completa (logs, métricas, tracing)
- CI/CD automatizado

### Requisitos de negocio:
- Multi-tenant (varias empresas usando el sistema)
- Integración con servicios externos (LinkedIn, portales de empleo)
- Capacidad de incorporar IA en el futuro (ranking de candidatos)

### Lo que necesito que generes:
1. Diagrama de arquitectura en AWS (explicado en texto)
2. Servicios AWS recomendados (por ejemplo: EC2, ECS, EKS, Lambda, RDS, S3, etc.)
3. Flujo de datos entre componentes
4. Estrategia de escalabilidad
5. Estrategia de seguridad (IAM, VPC, WAF, etc.)
6. Pipeline de CI/CD sugerido
7. Consideraciones de costos (alto nivel)
8. Posibles cuellos de botella y cómo mitigarlos

Evita respuestas genéricas. Justifica cada decisión técnica.

Esto en el mismo documento md, si hay algo que falta o pueda mejorarse en este prompt en base al documento actualizarlo y aplicarlo.
```

---

## Prompt 5 — Diagrama C4 en Mermaid

> **Rol:** Arquitecto de software  
> **Modelo:** Claude (Opus)

```
Podes desarrollar un diagrama C4?
```

---

## Prompt 6 — Diagrama C4 en archivo DSL separado

> **Rol:** Arquitecto de software  
> **Modelo:** Claude (Opus)

```
En cuanto al diagrama C4 lo quiero en documento aparte en .dsl archivo válidos siguiendo las convenciones del modelo C4.
```
