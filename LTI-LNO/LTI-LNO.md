# LTI ATS — Resumen Ejecutivo de Diseño

> **Producto:** LTI ATS  
> **Versión:** 1.0  
> **Fecha:** 3 de mayo de 2026

---

## 1. Descripción del Software LTI

### ¿Qué es LTI ATS?

**LTI ATS** es un Applicant Tracking System de próxima generación desarrollado por la startup LTI. Transforma el proceso de reclutamiento en un flujo **inteligente, automatizado y basado en datos**, cubriendo el ciclo completo: desde la creación de una vacante hasta la contratación del candidato.

A diferencia de los ATS tradicionales que funcionan como repositorios pasivos de CVs, LTI ATS incorpora inteligencia artificial en cada etapa del proceso para reducir el tiempo de contratación, eliminar sesgos y mejorar la experiencia tanto del reclutador como del candidato.

### Valor Añadido

| Diferenciador | Descripción |
|---|---|
| **IA nativa en todo el flujo** | No es un add-on: el screening automático con scoring (0-100), la generación de descripciones de puesto optimizadas y la detección inteligente de duplicados son parte del core del producto. |
| **Publicación multicanal con un clic** | Publica simultáneamente en LinkedIn, Indeed, Glassdoor y otros portales, adaptando automáticamente el formato a cada canal. |
| **Experiencia del candidato como prioridad** | Aplicación en menos de 3 minutos, portal de seguimiento en tiempo real, y comunicaciones automáticas transparentes en cada etapa. |
| **Decisiones colaborativas basadas en datos** | Scorecards estructuradas, panel de decisión con feedback consolidado de todos los entrevistadores y métricas de calidad de contratación. |
| **Analytics predictivo** | Dashboards con KPIs en tiempo real, detección de cuellos de botella y estimación de tiempo de cierre basada en datos históricos. |

### Ventajas Competitivas frente a Greenhouse, Lever y Workday

| Aspecto | ATS Tradicionales | LTI ATS |
|---|---|---|
| Screening de CVs | Manual o con filtros básicos por keywords | IA con scoring multidimensional (skills, experiencia, educación, ubicación) |
| Tiempo para publicar en múltiples canales | 15-30 min por canal, uno por uno | < 30 segundos en todos los canales simultáneamente |
| Experiencia del candidato | Formularios largos (+15 campos), sin visibilidad | ≤ 5 campos, portal con estado en tiempo real, NPS objetivo ≥ 70 |
| Scheduling de entrevistas | Manual, emails ida y vuelta | Automático con detección de disponibilidad cruzada en calendarios |
| Modelo de pricing | Enterprise ($$$), implementación 3-6 meses | SaaS accesible, onboarding en días, enfocado en startups y mid-market |
| Compliance GDPR | Parcial, configuración manual | Privacy by design, derecho al olvido automatizado en < 72h |

---

## 2. Funciones Principales

```mermaid
graph LR
    subgraph "1. Crear"
        A["📋 Gestión de Vacantes<br/>Crear, clonar, aprobar.<br/>Descripción asistida por IA."]
    end
    subgraph "2. Publicar"
        B["🌐 Publicación Multicanal<br/>LinkedIn, Indeed, Glassdoor.<br/>Un clic, todos los canales."]
    end
    subgraph "3. Recibir"
        C["📨 Recepción de Aplicaciones<br/>Parsing de CVs con OCR/NLP.<br/>Detección de duplicados."]
    end
    subgraph "4. Evaluar"
        D["🤖 Screening con IA<br/>Score 0-100 automático.<br/>Ranking por matching."]
    end
    subgraph "5. Entrevistar"
        E["🗓️ Gestión de Entrevistas<br/>Scheduling automático.<br/>Scorecards y feedback."]
    end
    subgraph "6. Contratar"
        F["📄 Oferta y Contratación<br/>Firma electrónica.<br/>Exportación a HRIS."]
    end
    subgraph "Transversal"
        G["📊 Analytics y Reportes<br/>KPIs en tiempo real.<br/>Análisis predictivo."]
        H["💬 Comunicaciones<br/>Emails automáticos.<br/>Notificaciones multicanal."]
    end

    A --> B --> C --> D --> E --> F
```

| Función | Descripción |
|---|---|
| **Gestión de Vacantes** | Creación con descripción asistida por IA, ciclo de vida completo (borrador → publicada → cerrada), clonación de vacantes previas y aprobaciones configurables. |
| **Publicación Multicanal** | Publicación simultánea en 5+ job boards con un clic. Adaptación automática del formato a cada plataforma. Tracking de efectividad por canal. |
| **Recepción y Parsing** | Parsing inteligente de CVs (PDF, DOCX, imágenes) con Amazon Textract + Comprehend. Extracción automática de skills, experiencia y educación. Detección de candidatos duplicados. |
| **Screening con IA** | Scoring automático de 0-100 por candidato basado en matching multidimensional contra los requisitos de la vacante. Labels automáticos y ranking en tiempo real. |
| **Pipeline Kanban** | Vista drag-and-drop con etapas configurables. Acciones masivas (mover, rechazar, contactar). Talent pool para futuras vacantes. |
| **Evaluaciones Técnicas** | Banco de preguntas propio + integración con HackerRank, Codility y TestGorilla. Envío automático con deadline y scoring integrado al perfil. |
| **Entrevistas** | Programación automática con sincronización de calendarios (Google, Outlook). Scorecards estructuradas. Panel de decisión colaborativa con feedback consolidado. |
| **Ofertas y Contratación** | Generación de ofertas con templates, cadena de aprobación, firma electrónica (DocuSign) y exportación a HRIS (Workday, SAP, BambooHR). |
| **Comunicaciones** | Templates de email con variables dinámicas. Triggers automáticos por cambio de etapa. Historial completo por candidato. Multicanal: email, SMS, push, in-app. |
| **Analytics** | Dashboard ejecutivo con KPIs (time-to-hire, cost-per-hire, source effectiveness). Reportes exportables. Detección de cuellos de botella. Análisis predictivo. |

---

## 3. Lean Canvas

Lean Canvas de Ash Maurya adaptado para LTI ATS, renderizado **en Mermaid** (`flowchart`). Se previsualiza en GitHub, GitLab, Notion, VS Code (extensión Mermaid) o en [mermaid.live](https://mermaid.live).

```mermaid
%%{init: {'flowchart': {'htmlLabels': true, 'curve': 'linear', 'nodeSpacing': 30, 'rankSpacing': 30}, 'themeVariables': {'fontSize': '14px'}}}%%
flowchart TB

    subgraph CANVAS["**LEAN CANVAS — LTI ATS**  ·  Producto: Applicant Tracking System  ·  Versión 1.0"]
        direction TB

        subgraph ROW1[" "]
            direction LR
            PROBLEM["**1 · PROBLEMA**<br/>━━━━━━━━━━<br/>• Reclutamiento fragmentado en<br/>5-12 herramientas distintas<br/>• Time-to-hire alto: 36-44 días<br/>• Procesos manuales, baja trazabilidad<br/>y sesgo inconsciente<br/>• 60% de candidatos abandona<br/>por mala experiencia<br/><br/>**Alternativas existentes:**<br/>Greenhouse, Lever, Workday,<br/>hojas de cálculo + email"]

            SOLUTION["**4 · SOLUCIÓN**<br/>━━━━━━━━━━<br/>• ATS SaaS multi-tenant cloud-native<br/>• Publicación multicanal con 1 clic<br/>• Parsing de CV + screening<br/>IA automático (score 0-100)<br/>• Pipeline Kanban + entrevistas<br/>+ ofertas integradas<br/>• Comunicaciones automáticas<br/>en cada etapa"]

            UVP{{"**3 · PROPUESTA DE VALOR ÚNICA**<br/>━━━━━━━━━━━━━━━━━━━━━━━<br/><br/>**Contratar mejor, más rápido y<br/>con menos fricción.**<br/><br/>LTI reduce el time-to-hire hasta un<br/>**60%**, automatiza el 70% de tareas<br/>operativas y mejora la calidad de<br/>contratación con IA explicable y<br/>datos accionables.<br/><br/>━━━━━━━━━━━━━━━━━━━━━━━<br/>**High-level concept:**<br/>_'El Stripe del reclutamiento:<br/>API-first, IA-first, candidato-first'_"}}

            ADVANTAGE["**9 · VENTAJA COMPETITIVA**<br/>━━━━━━━━━━━━<br/>• IA nativa, no un add-on<br/>• UX de candidato superior:<br/>aplicación ≤ 3 minutos<br/>• Arquitectura cloud-native<br/>lista para alto tráfico<br/>• Privacy by design:<br/>GDPR y audit trail completo<br/>• Modelo propietario entrenado<br/>con datos de contrataciones"]

            SEGMENTS["**2 · SEGMENTOS DE CLIENTES**<br/>━━━━━━━━━━━━━<br/>• Startups en crecimiento<br/>(50-500 empleados)<br/>• Mid-market LATAM / Europa<br/>• Equipos Talent Acquisition<br/>de 2-20 personas<br/>• Empresas con contratación<br/>recurrente y roles técnicos<br/><br/>**🎯 Early Adopters:**<br/>Scale-ups tech 100-300 empleados<br/>contratando 20+ roles/trimestre"]
        end

        subgraph ROW2[" "]
            direction LR
            METRICS["**8 · MÉTRICAS CLAVE**<br/>━━━━━━━━━━<br/>• Activación: time-to-first-hire<br/>≤ 14 días desde alta<br/>• Producto: time-to-hire ≤ 20 días<br/>• Calidad: screening IA correlación<br/>≥ 0.75 vs evaluación humana<br/>• Retención: NRR ≥ 110%<br/>• Satisfacción: NPS candidato ≥ 70,<br/>NPS reclutador ≥ 50<br/>• North Star: 200 empresas activas<br/>en 12 meses"]

            CHANNELS["**5 · CANALES**<br/>━━━━━━━━━━<br/>• Product-led growth:<br/>trial 30 días + freemium portal<br/>• Partnerships con consultoras<br/>de RRHH y headhunters<br/>• Integraciones con job boards y<br/>HR tech marketplaces<br/>• Content marketing: benchmarks,<br/>guías y calculadora ROI<br/>• Inbound SEO: 'mejor ATS para...'<br/>• Sales-led para enterprise"]
        end

        subgraph ROW3[" "]
            direction LR
            COSTS["**7 · ESTRUCTURA DE COSTOS**<br/>━━━━━━━━━━━━━━<br/>• Infraestructura AWS: ~USD 4.750/mes<br/>(optimizable a USD 3.400 con Savings Plans)<br/>• Equipo ingeniería + producto:<br/>8-12 personas<br/>• Servicios IA: Textract, Comprehend, SageMaker<br/>• Licencias / fees de job boards y calendarios<br/>• Soporte, compliance, seguridad y legal<br/>• Sales & Marketing (CAC objetivo < 6 meses LTV)"]

            REVENUE["**6 · FUENTES DE INGRESO**<br/>━━━━━━━━━━━━━<br/>• SaaS mensual recurrente por empresa<br/>• 3 planes: **Starter** / **Pro** / **Enterprise**<br/>• Escalado por vacantes activas + usuarios<br/>+ volumen de candidatos<br/>• Add-ons: IA avanzada, evaluaciones premium,<br/>integraciones custom, white-label<br/>• Servicios profesionales: onboarding<br/>e implementación enterprise<br/>• Marketplace de integraciones (rev share)"]
        end
    end

    style CANVAS fill:#FAFAFA,stroke:#37474F,stroke-width:3px,color:#111
    style ROW1 fill:transparent,stroke-width:0px
    style ROW2 fill:transparent,stroke-width:0px
    style ROW3 fill:transparent,stroke-width:0px

    style PROBLEM fill:#FFEBEE,stroke:#C62828,stroke-width:2px,color:#111
    style SOLUTION fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px,color:#111
    style UVP fill:#E3F2FD,stroke:#0D47A1,stroke-width:4px,color:#111
    style ADVANTAGE fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px,color:#111
    style SEGMENTS fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px,color:#111
    style METRICS fill:#E0F7FA,stroke:#00838F,stroke-width:2px,color:#111
    style CHANNELS fill:#F1F8E9,stroke:#558B2F,stroke-width:2px,color:#111
    style COSTS fill:#FFF8E1,stroke:#F9A825,stroke-width:2px,color:#111
    style REVENUE fill:#FFFDE7,stroke:#F57F17,stroke-width:2px,color:#111
```

> **Cómo leer el canvas:** los números (1-9) siguen el orden recomendado por Ash Maurya para completarlo: primero el problema y los segmentos (1-2), luego la propuesta de valor única (3), después la solución y canales (4-5), y por último el modelo económico (6-7), métricas (8) y ventaja competitiva (9).

---

## 4. Casos de Uso Principales (Top 3)

### 4.1 Caso de Uso 1 — Aplicar a Vacante con Screening Automático

Este es el caso de uso más crítico del sistema: representa el momento en que un candidato entra al pipeline y el sistema genera valor inmediato mediante parsing e IA.

**Actores:** Candidato (primario), Sistema de IA (secundario), Reclutador (beneficiario)

**Flujo:**
1. El candidato accede al portal y selecciona una vacante.
2. Completa un formulario de máximo 5 campos y sube su CV.
3. El sistema parsea el CV con Textract (OCR) y Comprehend (NLP), extrayendo skills, experiencia y educación.
4. El sistema detecta si el candidato ya existe (duplicados por email o fuzzy matching).
5. El candidato responde killer questions eliminatorias (si están configuradas).
6. El sistema registra la aplicación y envía confirmación instantánea.
7. El motor de IA genera un score de matching (0-100) contra los requisitos de la vacante.
8. El candidato aparece rankeado automáticamente en el pipeline Kanban del reclutador.

```mermaid
sequenceDiagram
    actor C as Candidato
    participant P as Portal Web
    participant API as API Gateway
    participant APP as Application Service
    participant S3 as S3 (CVs)
    participant CAND as Candidate Service
    participant TX as Amazon Textract
    participant CO as Amazon Comprehend
    participant IA as SageMaker (IA)
    participant DB as PostgreSQL
    participant N as Notification Service

    C->>P: Selecciona vacante + "Aplicar"
    P->>API: POST /api/v1/applications
    API->>APP: createApplication()

    APP->>S3: Upload CV
    APP->>DB: INSERT application (status: received)
    APP-->>C: 201 Created

    APP--)N: Evento: application.received
    N-->>C: Email "Aplicación recibida"

    APP--)CAND: Evento → cv-parsing-queue
    CAND->>S3: Download CV
    CAND->>TX: ExtractText()
    TX-->>CAND: Texto estructurado
    CAND->>CO: DetectEntities()
    CO-->>CAND: Skills, empresas, títulos
    CAND->>DB: UPDATE candidate (perfil parseado)
    CAND->>DB: Check duplicados

    CAND--)IA: Evento → ai-screening-queue
    IA->>DB: READ requisitos vacante
    IA->>IA: Score matching (0-100)
    IA->>DB: INSERT screening_result
    IA->>DB: UPDATE application (ai_score, ai_label)
```

---

### 4.2 Caso de Uso 2 — Programar Entrevista con Decisión Colaborativa

Cubre el flujo completo desde que un candidato pasa a la etapa de entrevistas hasta que el hiring manager toma la decisión final.

**Actores:** Reclutador (primario), Hiring Manager (primario), Candidato (participante), Servicio de Calendario (secundario)

**Flujo:**
1. El reclutador mueve al candidato a la etapa "Entrevista" en el pipeline Kanban.
2. Selecciona los entrevistadores del panel.
3. El sistema consulta disponibilidad cruzada en Google Calendar / Outlook.
4. Propone 3 bloques horarios al candidato.
5. El candidato elige un horario; el sistema crea el evento en todos los calendarios.
6. Se programan recordatorios automáticos (24h y 1h antes).
7. Tras la entrevista, cada entrevistador completa un scorecard estructurado.
8. El sistema consolida feedback y notifica al hiring manager.
9. El hiring manager revisa scores, comentarios y recomendaciones en el panel de decisión.
10. Registra su decisión final (contratar / rechazar / segunda ronda).
11. El sistema actualiza el pipeline y dispara la comunicación automática.

```mermaid
sequenceDiagram
    actor R as Reclutador
    actor HM as Hiring Manager
    actor C as Candidato
    participant PIPE as Pipeline Service
    participant INT as Interview Service
    participant CAL as Google Calendar
    participant DB as PostgreSQL
    participant N as Notification Service

    R->>PIPE: Mover candidato → etapa "Entrevista"
    PIPE->>DB: UPDATE application.current_stage

    R->>INT: POST /interviews (entrevistadores[], tipo)
    INT->>CAL: FreeBusy query (entrevistadores)
    CAL-->>INT: Slots disponibles
    INT->>INT: Calcular 3 bloques cruzados
    INT->>DB: INSERT interview (status: pending)

    INT--)N: Enviar slots al candidato
    N-->>C: Email con 3 opciones de horario

    C->>INT: POST /interviews/{id}/confirm (slot)
    INT->>CAL: Crear evento (todos los participantes)
    INT->>DB: UPDATE interview (status: confirmed)
    INT--)N: Confirmación a todos

    Note over INT,N: 24h antes → recordatorio automático

    Note over HM: Después de la entrevista

    HM->>INT: POST /interviews/{id}/feedback
    Note right of HM: Scorecard: comunicación 4/5,<br/>técnico 5/5, cultural 3/5.<br/>Recomendación: "hire"

    INT->>DB: INSERT interview_feedback
    INT->>INT: Verificar si todos evaluaron
    INT--)N: Notificar: "Feedback completo"
    N-->>HM: Notificación push

    HM->>INT: GET /interviews/{id}/decision-panel
    INT-->>HM: Vista consolidada (scores, comentarios)

    HM->>INT: POST /decisions (candidateId, decision: "hire")
    INT->>DB: UPDATE application.status
    INT--)PIPE: Evento: decision.made
    PIPE--)N: Trigger comunicación
    N-->>C: Email "Avanzas a la siguiente etapa"
```

---

### 4.3 Caso de Uso 3 — Crear y Publicar Vacante Multicanal

Cubre el flujo desde que surge la necesidad de contratar hasta que la vacante está visible en todos los canales de empleo.

**Actores:** Reclutador (primario), Hiring Manager (aprobador), Sistema de IA (genera descripción), Job Boards (receptores)

**Flujo:**
1. El reclutador crea una nueva vacante ingresando título, departamento, ubicación y requisitos clave.
2. El sistema de IA genera una descripción optimizada para atracción de talento y SEO.
3. El reclutador revisa, ajusta y confirma.
4. Define el workflow del pipeline (etapas del proceso) o usa uno predefinido.
5. Envía para aprobación del hiring manager.
6. El hiring manager aprueba.
7. El reclutador selecciona los canales de publicación (LinkedIn, Indeed, Glassdoor, página de carreras).
8. El sistema publica simultáneamente en todos los canales, adaptando el formato a cada uno.
9. Se confirma la publicación con enlaces y se inicia la recepción de aplicaciones.

```mermaid
sequenceDiagram
    actor R as Reclutador
    actor HM as Hiring Manager
    participant JOB as Job Service
    participant IA as Sistema de IA
    participant DB as PostgreSQL
    participant PUB as Publishing Worker
    participant LI as LinkedIn
    participant IND as Indeed
    participant GD as Glassdoor
    participant N as Notification Service

    R->>JOB: POST /jobs (título, depto, requisitos)
    JOB->>IA: Generar descripción optimizada
    IA-->>JOB: Descripción sugerida (SEO)
    JOB-->>R: Preview con descripción IA

    R->>JOB: PUT /jobs/{id} (ajustes + confirmar)
    JOB->>DB: INSERT job_position (status: pending_approval)

    JOB--)N: Notificar aprobador
    N-->>HM: Email "Vacante pendiente de aprobación"

    HM->>JOB: POST /jobs/{id}/approve
    JOB->>DB: UPDATE status = 'approved'

    R->>JOB: POST /jobs/{id}/publish (canales[])
    JOB->>DB: UPDATE status = 'published'

    par Publicación paralela
        JOB--)PUB: SQS → canal: linkedin
        PUB->>LI: POST job listing
        LI-->>PUB: external_id + URL
        PUB->>DB: INSERT job_publication
    and
        JOB--)PUB: SQS → canal: indeed
        PUB->>IND: POST job listing
        IND-->>PUB: external_id + URL
        PUB->>DB: INSERT job_publication
    and
        JOB--)PUB: SQS → canal: glassdoor
        PUB->>GD: POST job listing
        GD-->>PUB: external_id + URL
        PUB->>DB: INSERT job_publication
    end

    PUB--)N: Publicación completada
    N-->>R: Email "Vacante publicada en 3 canales"
```

---

## 5. Modelo de Datos

### 5.1 Diagrama Entidad-Relación

```mermaid
erDiagram
    COMPANY {
        UUID id PK
        VARCHAR name
        VARCHAR slug UK
        VARCHAR industry
        VARCHAR subscription_plan
        BOOLEAN gdpr_enabled
        TIMESTAMP created_at
    }

    USER {
        UUID id PK
        UUID company_id FK
        VARCHAR email UK
        VARCHAR first_name
        VARCHAR last_name
        UUID role_id FK
        BOOLEAN mfa_enabled
        BOOLEAN is_active
    }

    ROLE {
        UUID id PK
        UUID company_id FK
        VARCHAR name
        BOOLEAN is_system_role
    }

    DEPARTMENT {
        UUID id PK
        UUID company_id FK
        VARCHAR name
        UUID parent_department_id FK
    }

    JOB_POSITION {
        UUID id PK
        UUID company_id FK
        UUID department_id FK
        UUID recruiter_id FK
        UUID hiring_manager_id FK
        UUID workflow_id FK
        VARCHAR title
        TEXT description
        VARCHAR contract_type
        VARCHAR seniority_level
        DECIMAL salary_min
        DECIMAL salary_max
        VARCHAR status
        INTEGER headcount
        TIMESTAMP published_at
    }

    CANDIDATE {
        UUID id PK
        VARCHAR email UK
        VARCHAR first_name
        VARCHAR last_name
        VARCHAR phone
        VARCHAR linkedin_url
        VARCHAR current_title
        VARCHAR current_company
        DECIMAL years_of_experience
        VARCHAR source
        BOOLEAN is_in_talent_pool
    }

    APPLICATION {
        UUID id PK
        UUID candidate_id FK
        UUID job_position_id FK
        UUID current_stage_id FK
        DECIMAL ai_score
        VARCHAR ai_label
        VARCHAR status
        VARCHAR source_channel
        TIMESTAMP applied_at
    }

    PIPELINE_STAGE {
        UUID id PK
        UUID workflow_id FK
        VARCHAR name
        INTEGER stage_order
        VARCHAR stage_type
        BOOLEAN is_terminal
        INTEGER sla_days
    }

    CANDIDATE_SKILL {
        UUID id PK
        UUID candidate_id FK
        VARCHAR skill_name
        VARCHAR proficiency_level
        DECIMAL years_of_experience
    }

    CANDIDATE_DOCUMENT {
        UUID id PK
        UUID candidate_id FK
        VARCHAR document_type
        VARCHAR file_url
        JSONB parsed_content
        BOOLEAN is_primary_cv
    }

    SCREENING_RESULT {
        UUID id PK
        UUID application_id FK
        DECIMAL overall_score
        DECIMAL skills_score
        DECIMAL experience_score
        DECIMAL education_score
        VARCHAR model_version
        BOOLEAN was_overridden
    }

    INTERVIEW {
        UUID id PK
        UUID application_id FK
        UUID scorecard_id FK
        UUID organized_by_id FK
        VARCHAR interview_type
        TIMESTAMP scheduled_at
        INTEGER duration_minutes
        VARCHAR meeting_url
        VARCHAR status
    }

    INTERVIEW_FEEDBACK {
        UUID id PK
        UUID interview_id FK
        UUID interviewer_id FK
        INTEGER overall_rating
        VARCHAR recommendation
        JSONB criterion_scores
        TEXT strengths
        TEXT concerns
    }

    OFFER {
        UUID id PK
        UUID application_id FK
        UUID created_by_id FK
        DECIMAL salary
        VARCHAR currency
        DATE start_date
        VARCHAR status
        TIMESTAMP sent_at
        VARCHAR signature_url
    }

    JOB_PUBLICATION {
        UUID id PK
        UUID job_position_id FK
        UUID channel_id FK
        VARCHAR external_id
        VARCHAR external_url
        VARCHAR status
    }

    COMMUNICATION_LOG {
        UUID id PK
        UUID candidate_id FK
        UUID application_id FK
        VARCHAR channel
        VARCHAR subject
        TEXT body
        VARCHAR status
        TIMESTAMP sent_at
    }

    AUDIT_LOG {
        UUID id PK
        UUID company_id FK
        UUID user_id FK
        VARCHAR action
        VARCHAR entity_type
        UUID entity_id
        JSONB old_values
        JSONB new_values
        TIMESTAMP created_at
    }

    COMPANY ||--o{ USER : "emplea"
    COMPANY ||--o{ DEPARTMENT : "organiza"
    COMPANY ||--o{ JOB_POSITION : "tiene"
    USER }o--|| ROLE : "tiene"
    DEPARTMENT ||--o{ JOB_POSITION : "solicita"
    JOB_POSITION ||--o{ APPLICATION : "recibe"
    JOB_POSITION ||--o{ PIPELINE_STAGE : "define"
    JOB_POSITION ||--o{ JOB_PUBLICATION : "publicada en"
    CANDIDATE ||--o{ APPLICATION : "aplica"
    CANDIDATE ||--o{ CANDIDATE_SKILL : "posee"
    CANDIDATE ||--o{ CANDIDATE_DOCUMENT : "adjunta"
    CANDIDATE ||--o{ COMMUNICATION_LOG : "recibe"
    APPLICATION }o--|| PIPELINE_STAGE : "está en"
    APPLICATION ||--o| SCREENING_RESULT : "evaluada por IA"
    APPLICATION ||--o{ INTERVIEW : "tiene"
    APPLICATION ||--o| OFFER : "recibe"
    INTERVIEW ||--o{ INTERVIEW_FEEDBACK : "evaluada con"
    USER ||--o{ INTERVIEW_FEEDBACK : "registra"
    USER ||--o{ OFFER : "genera"
```

### 5.2 Entidades Principales — Resumen de Atributos

| Entidad | Atributos Clave | Relaciones |
|---|---|---|
| **COMPANY** | id (UUID PK), name, slug (UK), industry, subscription_plan, gdpr_enabled | 1:N → USER, DEPARTMENT, JOB_POSITION |
| **USER** | id (UUID PK), email (UK), first_name, last_name, role_id (FK), mfa_enabled, is_active | N:1 → COMPANY, ROLE. 1:N → INTERVIEW_FEEDBACK, OFFER |
| **JOB_POSITION** | id (UUID PK), title, description, contract_type, seniority_level, salary_min/max, status, headcount | N:1 → COMPANY, DEPARTMENT. 1:N → APPLICATION, PIPELINE_STAGE, JOB_PUBLICATION |
| **CANDIDATE** | id (UUID PK), email (UK), first_name, last_name, current_title, years_of_experience, is_in_talent_pool | 1:N → APPLICATION, CANDIDATE_SKILL, CANDIDATE_DOCUMENT |
| **APPLICATION** | id (UUID PK), ai_score, ai_label, status, source_channel, applied_at | N:1 → CANDIDATE, JOB_POSITION, PIPELINE_STAGE. 1:N → INTERVIEW, 1:1 → SCREENING_RESULT, OFFER |
| **INTERVIEW** | id (UUID PK), interview_type, scheduled_at, duration_minutes, status, meeting_url | N:1 → APPLICATION. 1:N → INTERVIEW_FEEDBACK |
| **SCREENING_RESULT** | id (UUID PK), overall_score, skills_score, experience_score, education_score, model_version | 1:1 → APPLICATION |
| **OFFER** | id (UUID PK), salary, currency, start_date, status, signature_url | 1:1 → APPLICATION |

---

## 6. Diseño del Sistema a Alto Nivel

### 6.1 Descripción de la Arquitectura

LTI ATS utiliza una **arquitectura de microservicios cloud-native** desplegada en **AWS**, diseñada para alta disponibilidad, escalabilidad automática y procesamiento asíncrono de tareas intensivas (parsing de CVs, scoring con IA).

**Principios de diseño:**

- **Microservicios por dominio:** Cada bounded context del negocio es un servicio independiente con su propia responsabilidad, desplegable y escalable de forma autónoma.
- **Arquitectura hexagonal interna:** Cada microservicio sigue Ports & Adapters, aislando el dominio de la infraestructura.
- **Event-driven para operaciones asíncronas:** SNS (pub/sub) + SQS (colas) para desacoplar operaciones costosas (parsing, screening, publicación).
- **API Gateway centralizado:** Spring Cloud Gateway como punto único de entrada con JWT validation, rate limiting por tenant y routing.
- **Multi-tenant por discriminador:** Todos los tenants comparten infraestructura con aislamiento lógico via `company_id`.
- **Read/Write separation:** Writer (RDS Multi-AZ) para operaciones transaccionales, Read Replica para reporting y dashboards.

**Stack tecnológico:**

| Capa | Tecnología |
|---|---|
| Frontend | React 18, TypeScript, Vite |
| API Gateway | Spring Cloud Gateway (Java 21) |
| Microservicios | Spring Boot 3 (Java 21) |
| Base de datos | PostgreSQL 15 (RDS Multi-AZ) |
| Caché | Redis 7 (ElastiCache Cluster) |
| Mensajería | Amazon SNS + SQS + EventBridge |
| Storage | Amazon S3 |
| IA/ML | Amazon Textract, Comprehend, SageMaker |
| Orquestación | Amazon EKS (Kubernetes) |
| CI/CD | CodePipeline + CodeBuild + Helm |
| Observabilidad | CloudWatch, X-Ray, OpenSearch, Grafana |

### 6.2 Diagrama de Arquitectura

```mermaid
graph TB
    subgraph "Clientes"
        WEB["🖥️ SPA Web<br/>(React)"]
        PORTAL["📱 Portal Candidato<br/>(React)"]
    end

    subgraph "Edge Layer"
        CDN["CloudFront (CDN)"]
        WAF["AWS WAF"]
        ALB["Application Load Balancer"]
    end

    subgraph "API Layer"
        GW["API Gateway<br/>Spring Cloud Gateway<br/>JWT + Rate Limiting"]
    end

    subgraph "Microservicios (EKS)"
        subgraph "Core"
            S1["Job Service"]
            S2["Candidate Service"]
            S3["Application Service"]
            S4["Pipeline Service"]
        end
        subgraph "Process"
            S5["Interview Service"]
            S6["Evaluation Service"]
            S7["Offer Service"]
            S8["Communication Service"]
        end
        subgraph "Platform"
            S9["Auth Service"]
            S10["Notification Service"]
            S11["Audit Service"]
            S12["Reporting Service"]
        end
        subgraph "Workers (KEDA autoscale)"
            W1["CV Parsing Worker"]
            W2["AI Screening Worker"]
            W3["Publishing Worker"]
        end
    end

    subgraph "Mensajería Async"
        SNS["SNS<br/>Event Bus"]
        SQS["SQS<br/>Task Queues"]
        EB["EventBridge<br/>Scheduler"]
    end

    subgraph "Data Layer"
        DB_W[("PostgreSQL<br/>Writer")]
        DB_R[("PostgreSQL<br/>Read Replica")]
        REDIS[("Redis<br/>Cache")]
        S3_STORE[("S3<br/>Documentos")]
        OS[("OpenSearch<br/>Logs + Search")]
    end

    subgraph "AI / ML"
        TEXTRACT["Textract<br/>(OCR)"]
        COMPREHEND["Comprehend<br/>(NLP)"]
        SAGEMAKER["SageMaker<br/>(Scoring)"]
    end

    subgraph "Externos"
        JB["Job Boards"]
        CAL["Calendar APIs"]
        SES["Amazon SES"]
        DOCUSIGN["DocuSign"]
        HRIS["HRIS"]
    end

    WEB --> CDN
    PORTAL --> CDN
    CDN --> WAF --> ALB --> GW

    GW --> S1 & S2 & S3 & S4 & S5 & S6 & S7 & S8 & S9 & S12

    S1 & S2 & S3 & S4 & S5 & S6 & S7 --> DB_W
    S12 & S4 --> DB_R
    S9 & S4 & S3 --> REDIS
    S2 & S7 --> S3_STORE
    S11 --> OS

    S1 & S3 & S5 & S7 --> SNS
    SNS --> SQS
    EB --> SQS
    SQS --> W1 & W2 & W3 & S10 & S11

    W1 --> TEXTRACT & COMPREHEND
    W2 --> SAGEMAKER
    W3 --> JB
    S5 --> CAL
    S10 --> SES
    S7 --> DOCUSIGN & HRIS
```

---

## 7. Diagrama C4

### 7.1 Nivel 1 — Contexto del Sistema

```mermaid
graph TB
    REC["👤 Reclutador<br/><i>Gestiona vacantes, pipeline,<br/>entrevistas y ofertas</i>"]
    HM["👤 Hiring Manager<br/><i>Evalúa candidatos y<br/>toma decisiones</i>"]
    CAND["👤 Candidato<br/><i>Aplica a vacantes y<br/>consulta estado</i>"]
    ADMIN["👤 Administrador<br/><i>Configura sistema<br/>y reportes</i>"]

    ATS["🏢 LTI ATS<br/><b>Applicant Tracking System</b><br/><i>Centraliza y automatiza el reclutamiento<br/>con inteligencia artificial</i>"]

    JB["🌐 Job Boards<br/><i>LinkedIn, Indeed, Glassdoor</i>"]
    CAL["📅 Calendarios<br/><i>Google Calendar, Outlook</i>"]
    IDP["🔐 Identity Provider<br/><i>Okta, Azure AD</i>"]
    EMAIL["📧 Amazon SES<br/><i>Email transaccional</i>"]
    HRIS["🏛️ HRIS<br/><i>Workday, SAP, BambooHR</i>"]
    SIGN["✍️ DocuSign<br/><i>Firma electrónica</i>"]
    AI["🤖 AWS AI Services<br/><i>Textract, Comprehend, SageMaker</i>"]

    REC -->|"HTTPS"| ATS
    HM -->|"HTTPS"| ATS
    CAND -->|"HTTPS"| ATS
    ADMIN -->|"HTTPS"| ATS

    ATS -->|"REST API"| JB
    ATS -->|"OAuth 2.0"| CAL
    ATS -->|"SAML 2.0"| IDP
    ATS -->|"AWS SDK"| EMAIL
    ATS -->|"REST API"| HRIS
    ATS -->|"REST API"| SIGN
    ATS -->|"AWS SDK"| AI
```

### 7.2 Nivel 2 — Contenedores

```mermaid
graph TB
    subgraph "Frontend"
        SPA["📱 SPA Web<br/><b>React 18</b><br/><i>S3 + CloudFront</i>"]
        PORT["📱 Portal Candidato<br/><b>React 18</b><br/><i>S3 + CloudFront</i>"]
    end

    subgraph "API"
        GW["🔀 API Gateway<br/><b>Spring Cloud Gateway</b><br/><i>EKS Pod</i>"]
    end

    subgraph "Core Services"
        JOB["📋 Job Service<br/><b>Spring Boot 3</b>"]
        CAND["👤 Candidate Service<br/><b>Spring Boot 3</b>"]
        APP["📨 Application Service<br/><b>Spring Boot 3</b>"]
        PIPE["🔄 Pipeline Service<br/><b>Spring Boot 3</b>"]
    end

    subgraph "Process Services"
        INT["🗓️ Interview Service<br/><b>Spring Boot 3</b>"]
        EVAL["📝 Evaluation Service<br/><b>Spring Boot 3</b>"]
        OFFER["📄 Offer Service<br/><b>Spring Boot 3</b>"]
        COMM["💬 Communication Svc<br/><b>Spring Boot 3</b>"]
    end

    subgraph "Platform"
        AUTH["🔐 Auth Service"]
        NOTIF["🔔 Notification Svc"]
        AUDIT["📜 Audit Service"]
        REPORT["📊 Reporting Service"]
    end

    subgraph "Workers"
        W1["🤖 CV Parsing Worker"]
        W2["🤖 AI Screening Worker"]
        W3["📤 Publishing Worker"]
    end

    subgraph "Messaging"
        SNS["📢 SNS Event Bus"]
        SQS["📬 SQS Task Queues"]
    end

    subgraph "Data"
        DB[("🐘 PostgreSQL")]
        REDIS[("⚡ Redis")]
        S3[("📦 S3")]
        OS[("🔍 OpenSearch")]
    end

    SPA & PORT -->|"HTTPS"| GW
    GW --> JOB & CAND & APP & PIPE & INT & EVAL & OFFER & COMM & AUTH & REPORT

    JOB & CAND & APP & PIPE & INT & EVAL & OFFER --> DB
    REPORT --> DB
    AUTH & PIPE & APP --> REDIS
    CAND & OFFER --> S3
    AUDIT --> OS

    APP & JOB & INT & OFFER --> SNS
    SNS --> SQS
    SQS --> W1 & W2 & W3 & NOTIF & AUDIT
```

### 7.3 Nivel 3 — Componentes del Application Service

El **Application Service** es el componente de mayor complejidad del sistema. Recibe todas las aplicaciones de candidatos, evalúa killer questions, orquesta el parsing y screening con IA, y gestiona el ciclo de vida de la aplicación a través del pipeline.

```mermaid
graph TB
    subgraph "Entrada"
        GW["API Gateway"]
        SQS_IN["SQS<br/>cv.parsed /<br/>screening.completed"]
    end

    subgraph "Application Service [Spring Boot 3 — Hexagonal Architecture]"

        subgraph "Adapters Inbound"
            CTRL["ApplicationController<br/><b>[REST Controller]</b><br/><i>POST /applications<br/>PUT /{id}/stage<br/>POST /bulk-action</i>"]
            LISTENER["SQSMessageListener<br/><b>[Message Consumer]</b><br/><i>Consume eventos async<br/>para actualizar scores</i>"]
        end

        subgraph "Use Cases (Application Layer)"
            UC1["CreateApplicationUseCase<br/><i>Valida, persiste,<br/>evalúa killer questions,<br/>publica evento</i>"]
            UC2["MoveApplicationStageUseCase<br/><i>Valida transición,<br/>registra historial,<br/>invalida caché</i>"]
            UC3["BulkActionUseCase<br/><i>Acciones masivas:<br/>rechazar, mover, contactar</i>"]
            UC4["UpdateScreeningResultUseCase<br/><i>Recibe score de IA,<br/>actualiza application</i>"]
            UC5["EvaluateKillerQuestionsUseCase<br/><i>Evalúa respuestas,<br/>auto-rechaza si eliminatoria</i>"]
        end

        subgraph "Domain"
            ENT["Application<br/><b>[Entity]</b><br/><i>id, candidateId, jobPositionId,<br/>currentStageId, aiScore, status</i>"]
            HIST["ApplicationStageHistory<br/><b>[Entity]</b>"]
            SCORE["AIScore<br/><b>[Value Object]</b><br/><i>score 0-100, label, breakdown</i>"]
            DOM["ApplicationDomainService<br/><b>[Domain Service]</b><br/><i>Reglas: validar transiciones,<br/>calcular SLA, check duplicados</i>"]
        end

        subgraph "Ports (Interfaces)"
            P1["ApplicationRepositoryPort"]
            P2["EventPublisherPort"]
            P3["PipelineStagePort"]
            P4["CandidatePort"]
            P5["CachePort"]
        end

        subgraph "Adapters Outbound"
            A1["ApplicationJpaRepository<br/><i>→ PostgreSQL</i>"]
            A2["SNSEventPublisher<br/><i>→ Amazon SNS</i>"]
            A3["PipelineStageRestClient<br/><i>→ Pipeline Service</i>"]
            A4["CandidateRestClient<br/><i>→ Candidate Service</i>"]
            A5["RedisCacheAdapter<br/><i>→ ElastiCache Redis</i>"]
        end
    end

    subgraph "Infraestructura"
        DB[("PostgreSQL")]
        SNS["Amazon SNS"]
        PIPE_SVC["Pipeline Service"]
        CAND_SVC["Candidate Service"]
        REDIS[("Redis")]
    end

    GW -->|"HTTP"| CTRL
    SQS_IN -->|"SQS"| LISTENER

    CTRL --> UC1 & UC2 & UC3
    LISTENER --> UC4

    UC1 --> DOM & UC5
    UC2 --> DOM

    DOM --> ENT & HIST
    UC4 --> SCORE

    UC1 --> P1 & P2 & P4
    UC2 --> P1 & P2 & P3 & P5
    UC3 --> P1 & P2
    UC4 --> P1

    P1 -.->|"implementa"| A1
    P2 -.->|"implementa"| A2
    P3 -.->|"implementa"| A3
    P4 -.->|"implementa"| A4
    P5 -.->|"implementa"| A5

    A1 --> DB
    A2 --> SNS
    A3 --> PIPE_SVC
    A4 --> CAND_SVC
    A5 --> REDIS
```

### 7.4 Nivel 4 — Código del CreateApplicationUseCase

```mermaid
classDiagram
    class ApplicationController {
        -CreateApplicationUseCase createUseCase
        -MoveApplicationStageUseCase moveUseCase
        +createApplication(CreateApplicationRequest) ResponseEntity
        +moveStage(UUID, MoveStageRequest) ResponseEntity
        +bulkAction(BulkActionRequest) ResponseEntity
    }

    class CreateApplicationUseCase {
        <<interface>>
        +execute(CreateApplicationCommand) ApplicationResult
    }

    class CreateApplicationUseCaseImpl {
        -ApplicationRepositoryPort applicationRepo
        -CandidatePort candidatePort
        -EventPublisherPort eventPublisher
        -EvaluateKillerQuestionsUseCase killerQuestionsUC
        -ApplicationDomainService domainService
        +execute(CreateApplicationCommand) ApplicationResult
    }

    class CreateApplicationCommand {
        +UUID jobPositionId
        +String email
        +String firstName
        +String lastName
        +UUID documentId
        +String sourceChannel
        +List killerAnswers
    }

    class ApplicationResult {
        +UUID applicationId
        +String status
        +UUID candidateId
        +LocalDateTime appliedAt
    }

    class Application {
        -UUID id
        -UUID candidateId
        -UUID jobPositionId
        -UUID currentStageId
        -BigDecimal aiScore
        -String status
        +receive() void
        +moveToStage(PipelineStage) StageHistory
        +reject(String reason) void
        +updateAIScore(AIScore) void
    }

    class ApplicationRepositoryPort {
        <<interface>>
        +save(Application) Application
        +findById(UUID) Optional
        +existsByCandidateAndJob(UUID, UUID) boolean
    }

    class EventPublisherPort {
        <<interface>>
        +publish(ApplicationReceivedEvent) void
        +publish(StageChangedEvent) void
    }

    class CandidatePort {
        <<interface>>
        +findOrCreateByEmail(String, String, String) UUID
    }

    class ApplicationJpaRepository {
        +save(Application) Application
        +findById(UUID) Optional
    }

    class SNSEventPublisher {
        -SnsClient snsClient
        +publish(ApplicationReceivedEvent) void
    }

    ApplicationController --> CreateApplicationUseCase
    CreateApplicationUseCaseImpl ..|> CreateApplicationUseCase
    CreateApplicationUseCaseImpl --> ApplicationRepositoryPort
    CreateApplicationUseCaseImpl --> CandidatePort
    CreateApplicationUseCaseImpl --> EventPublisherPort
    CreateApplicationUseCaseImpl ..> Application
    ApplicationJpaRepository ..|> ApplicationRepositoryPort
    SNSEventPublisher ..|> EventPublisherPort
```

---
