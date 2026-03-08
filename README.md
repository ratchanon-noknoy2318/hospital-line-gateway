# LINE Digital Health Gateway (KPPMCH)

**Integrated Service Orchestration | 8-Grid High-Availability Interface | Nurse-Validated**

An enterprise-grade LINE Official Account (OA) framework designed as the "Digital Front Desk" for Kamphaeng Phet Municipal Community Hospital. This gateway orchestrates multiple clinical services into a single, user-centric mobile interface, ensuring 24/7 healthcare accessibility.

---

## 1. System Architecture & Service Flow

The system acts as a centralized middleware connecting citizens directly to hospital services via a structured rich-menu interface.

### 🔄 Service Orchestration Diagram
```mermaid
graph TD
    subgraph Client_Layer [User Interface]
        User[Patient / User] -->|HTTPS/JSON| LINE[LINE Messaging Platform]
    end

    subgraph Orchestration_Layer [Serverless Logic - Node.js/GAS]
        LINE -->|Webhook Event| Gateway{Digital Health Gateway}
        Gateway -->|Route| Tele[Telemedicine: Next.js + Vercel]
        Gateway -->|Query| FAQ[Knowledge Base: Google Apps Script]
        Gateway -->|Fetch| Trad[Static Content Service]
        Gateway -->|Stream| News[Municipal News Feed API]
    end

    subgraph Data_Layer [Persistence & Storage]
        Tele -->|ACID Transaction| DB[(Patient Database)]
        FAQ -->|Lookup| Sheet[(Cloud Knowledge Base)]
    end
