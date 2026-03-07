# LINE Digital Health Gateway (KPPMCH)

**Integrated Service Orchestration | 8-Grid High-Availability Interface | Nurse-Validated**

An enterprise-grade LINE Official Account (OA) framework designed as the "Digital Front Desk" for Kamphaeng Phet Municipal Community Hospital. This gateway orchestrates multiple clinical services into a single, user-centric mobile interface, ensuring 24/7 healthcare accessibility.

---

## 1. System Architecture & Service Flow

The system acts as a centralized middleware connecting citizens directly to hospital services via a structured rich-menu interface.

### 🔄 Service Orchestration Diagram
```mermaid
graph TD
    A[Patient/User] -->|LINE Interface| B{Digital Gateway}
    B -->|Keyword Trigger| C[Telemedicine Session]
    B -->|API Request| D[Clinical FAQ Knowledge Base]
    B -->|Navigation| E[Traditional Medicine Info]
    B -->|Webhook| F[Municipal News Feed]
