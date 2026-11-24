# Victor Okoye

Software developer working in Python, Java, and Terraform across web services, Android, and infrastructure.

Private work shows on the contribution graph. The projects below are public.

## Anyskills

Since 2018 I have been the solution architect and lead software engineer for [Anyskills](https://anyskills.co.uk) — a web and mobile marketplace that connects freelancers, artisans, and service providers with people who need work done, both locally and remotely.

I own the product end to end: architecture, backend services, the Nuxt web application, mobile shells, and the PostgreSQL data layer. The product code is private.

### Architecture

```text
Browsers / Capacitor apps
        │
        ▼
TLS / reverse proxy
        │
        ├───────────────────┬──────────────────────┐
        ▼                   ▼                      ▼
  Nuxt SPA             Django ASGI            Media SFU
  UI + Pinia           HTTP + WebSockets      live / calls
        │                   │
        │                   ├──────────┬──────────┐
        │                   ▼          ▼          ▼
        │              PostgreSQL    Redis     Kafka
        │                              │
        │                           Celery
        └────── API + WS clients ──────┘
```

- **Clients** — Nuxt web app; Capacitor for iOS / Android
- **Edge** — TLS and reverse proxy
- **Frontend** — pages, layouts, Pinia stores, API and WebSocket clients
- **Backend** — Django API, Celery workers/beat, Kafka consumers
- **Data** — PostgreSQL
- **Cache / realtime** — Redis for cache, job broker, and Channels
- **Events** — Kafka
- **Media** — mediasoup SFU; API issues join tokens; FE uses mediasoup-client

### Stack

**Backend**

| Area | Technologies |
|------|----------------|
| Language | Python |
| Framework | Django, Django Channels, ASGI (uvicorn) |
| Database | PostgreSQL |
| Cache / queues | Redis, Celery (worker + beat) |
| Events | Apache Kafka |
| Media | WebRTC SFU (mediasoup) |
| Containers / CI | Docker Compose, GitLab CI |
| Integrations | Payment providers, SMS/email, cloud object storage |

**Frontend**

| Area | Technologies |
|------|----------------|
| Framework | Nuxt (Vue 3), TypeScript |
| Rendering | SPA |
| State | Pinia |
| UI | Tailwind CSS, shadcn-nuxt |
| Realtime | WebSockets, mediasoup-client |
| Mobile | Capacitor (iOS / Android) |
| Testing | Playwright, unit tests |
| Containers / CI | Docker, Azure Pipelines, GitLab CI |

### How the FE and BE connect

- The SPA calls the backend through gateway HTTP APIs (connector / RPC-style payloads)
- Auth tokens on the client for protected requests
- WebSockets for notifications, chat, and live updates
- WebRTC media goes to the SFU using short-lived join credentials from the API

### Backend

I design and build the Django / Python platform behind Anyskills.

- Django ASGI app with domain packages and module + task dispatch
- Domain services for jobs, gigs, projects, wallets, billing, messaging, profiles, organisations, and marketplace operations
- Celery for async and scheduled work; Kafka for event-driven flows
- Channels WebSockets bridged from event consumers for chat, notifications, and collaborative workflows
- Payment webhooks and integrations for cloud media storage, search, and discovery

### Frontend

I design and build the Nuxt / Vue web application that users run every day.

- Typed Vue components, composables, and Pinia stores
- Marketplace discovery, seller and client dashboards, profiles, organisations, settings, and help
- Realtime chat, group video calling, live social surfaces, and map-based discovery
- Product modules for campaigns, collaboration and disputes, forums, events, referrals, and wallet management
- Dockerized build; Playwright for critical journeys; Capacitor for mobile

### What I own

- Full-stack features from Nuxt UI through Django APIs
- Production services, data modeling, Celery, and Kafka
- Realtime UX and WebRTC call/live client work
- Auth, payments, and integrations
- Dockerized FE/BE delivery and CI shipping
- Mentoring, reviews, and independent delivery

## Public projects

- [bulkifysms](https://github.com/contactokoyevictor/bulkifysms) — Full-stack bulk SMS platform (Spring Boot backend + Next.js frontend) for campaigns, contacts, scheduling, wallets, and delivery reporting
- [HorizonFMDutse](https://github.com/contactokoyevictor/HorizonFMDutse) — Android app for Horizon FM 100.5 Dutse: live radio streaming, background MediaPlayer service, station content, social WebViews, and listener feedback
- [TRANSCEND-CRM](https://github.com/contactokoyevictor/TRANSCEND-CRM) — Java EE CRM on TomEE: organisations, campaigns, projects & tickets, messaging, licensing, payments, Quartz jobs, and an XML rules-engine API over JPA/MySQL
- [school_managment_system](https://github.com/contactokoyevictor/school_managment_system) — Java Spring MVC school ERP: academics, students, exams, attendance, HR/payroll, fees & finance, role-based dashboards over JPA/MySQL
- [LifeStarRules](https://github.com/contactokoyevictor/LifeStarRules) — Java Drools patient-engagement platform: SMS cadence rules, BP tracker, MO/MT opt-in messaging, reminder scheduling over MySQL/JBoss
- [learning_terraform](https://github.com/contactokoyevictor/learning_terraform) — Terraform practice

## Contact

[contactokoyevictor@gmail.com](mailto:contactokoyevictor@gmail.com)
