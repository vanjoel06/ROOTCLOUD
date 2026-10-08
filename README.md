# ROOTCLOUD

### Your data. Your control.

**ROOTCLOUD** is an open-source project focused on building a secure and sovereign cloud platform for organizations in Cameroon and Africa.

The project aims to provide organizations with greater control over their data and infrastructure through locally manageable cloud services for **storage, remote access, backup, collaboration and infrastructure management**.

> **Status:** 🚧 In active development / prototype stage

---

## 🌍 Vision

Organizations increasingly depend on cloud services to store and access critical data. However, reliance on external infrastructure can create challenges related to **data sovereignty, cost, availability, security and operational control**.

ROOTCLOUD explores an alternative approach:

> **Build cloud infrastructure that organizations can operate, secure and control themselves.**

The project is initially designed with **SMEs** in mind, with a longer-term vision extending to universities, institutions and public-sector organizations.

---

## 🎯 Objectives

ROOTCLOUD aims to provide:

* 🔐 Secure data storage
* ☁️ Private and sovereign cloud services
* 📁 File sharing and collaboration
* 💾 Automated backup and data protection
* 🌐 Secure remote access
* 👥 User and access management
* 🛡️ Infrastructure security
* 📊 Monitoring and administration
* 🚀 A foundation for future SaaS, PaaS and IaaS services

The objective is not simply to reproduce existing public-cloud services, but to explore an infrastructure model adapted to the **technical, financial and operational realities of African organizations**.

---

## 🏗️ Architecture

The current architecture is being explored using open-source technologies.

```text
                         ┌─────────────────────┐
                         │       USERS         │
                         │  Web / Desktop      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      OPNsense       │
                         │ Firewall / Network   │
                         │ Security / VPN       │
                         └──────────┬──────────┘
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
                    ▼                               ▼
          ┌─────────────────┐             ┌─────────────────┐
          │    Nextcloud    │             │      MinIO      │
          │ File / Collab.  │             │ Object Storage  │
          └────────┬────────┘             └────────┬────────┘
                   │                               │
                   └───────────────┬───────────────┘
                                   │
                                   ▼
                         ┌─────────────────────┐
                         │      Proxmox        │
                         │ Virtualization      │
                         │ Infrastructure      │
                         └─────────────────────┘
```

This architecture is currently a **prototype and experimentation environment**. Components and design decisions may evolve as the project progresses.

---

## 🧩 Technology Stack

The project currently explores the following technologies:

| Component                   | Technology                 |
| --------------------------- | -------------------------- |
| Virtualization              | Proxmox VE                 |
| Cloud / Collaboration       | Nextcloud                  |
| Object Storage              | MinIO                      |
| Firewall / Network Security | OPNsense                   |
| Operating Systems           | Linux                      |
| Infrastructure              | Virtual Machines / Servers |
| Future orchestration        | To be evaluated            |
| Future cloud services       | SaaS / PaaS / IaaS         |

The project prioritizes **open-source technologies** whenever technically and economically appropriate.

---

## 🗄️ Core Services

### Storage

ROOTCLOUD aims to provide centralized storage for organizational data while maintaining control over the underlying infrastructure.

### Backup

The platform is designed to incorporate reliable backup mechanisms to protect organizational data against:

* accidental deletion;
* hardware failure;
* ransomware;
* service interruption;
* other operational incidents.

### Remote Access

Users should be able to securely access their resources remotely without exposing internal infrastructure unnecessarily.

### Collaboration

Nextcloud provides the foundation for collaborative file management and sharing.

### Object Storage

MinIO is being evaluated as an S3-compatible object-storage layer for applications and future cloud services.

---

## 🔐 Security

Security is a fundamental part of the ROOTCLOUD architecture.

The project explores:

* network segmentation;
* firewalling;
* secure remote access;
* identity and access management;
* least-privilege principles;
* backup protection;
* infrastructure monitoring;
* logging;
* secure configuration;
* resilience and availability.

Security mechanisms will evolve as the platform moves from prototype to production-oriented architecture.

---

## 📦 ROOTBOX

**ROOTBOX** is a complementary concept within the ROOTCLOUD ecosystem.

It explores an edge/offline continuity approach designed to maintain access to selected services or data when connectivity to the central infrastructure is temporarily unavailable.

The relationship can be represented as:

```text
                  ROOTCLOUD
              Central Cloud Platform
                       │
                       │
                ┌──────┴──────┐
                │             │
             Storage       Services
                │             │
                └──────┬──────┘
                       │
                    ROOTBOX
                 Edge / Local
              Continuity Layer
```

ROOTBOX is currently a concept under development and is not yet presented as a production-ready component.

---

## 🤖 Future AI Integration

ROOTCLOUD may integrate AI capabilities to assist administrators and users with cloud operations.

Potential use cases include:

* infrastructure assistance;
* troubleshooting;
* documentation generation;
* log and event analysis;
* security-event assistance;
* configuration guidance;
* user support;
* operational automation.

AI integration will be evaluated progressively according to **security, privacy, cost and operational requirements**.

---

## 🗺️ Roadmap

### Phase 1 — Foundation

* [x] Define ROOTCLOUD vision
* [x] Define initial architecture
* [x] Identify core technologies
* [ ] Build initial prototype
* [ ] Document deployment process

### Phase 2 — Core Cloud

* [ ] Deploy Nextcloud
* [ ] Integrate MinIO
* [ ] Configure OPNsense
* [ ] Implement secure remote access
* [ ] Implement user/access management
* [ ] Implement backup strategy

### Phase 3 — Security & Resilience

* [ ] Network segmentation
* [ ] Centralized logging
* [ ] Monitoring
* [ ] Security hardening
* [ ] Backup and recovery testing
* [ ] High-availability architecture study

### Phase 4 — ROOTBOX

* [ ] Define edge architecture
* [ ] Prototype local/offline services
* [ ] Synchronization mechanisms
* [ ] Connectivity recovery mechanisms

### Phase 5 — Cloud Platform Evolution

* [ ] SaaS services
* [ ] PaaS capabilities
* [ ] IaaS experimentation
* [ ] API ecosystem
* [ ] AI-assisted administration

---

## 📚 Documentation

Documentation will progressively be added to this repository.

Planned documentation:

* [Architecture](docs/architecture.md)
* [Vision](docs/vision.md)
* [Roadmap](docs/roadmap.md)
* Deployment guides
* Security documentation
* Infrastructure documentation

---

## 🚧 Project Status

ROOTCLOUD is currently an **early-stage project / prototype**.

The architecture, technologies and features are actively being evaluated and may change as development progresses.

The project is intended to evolve from an experimental infrastructure into a more complete cloud platform through iterative development and testing.

---

## 🤝 Contributing

ROOTCLOUD is intended to explore open-source approaches to cloud infrastructure and sovereignty.

Contributions, technical discussions, ideas and experimentation are welcome.

Before contributing, please review the project documentation and roadmap.

---

## 📜 License

ROOTCLOUD is intended to use an open-source license.

The final licensing model will be defined as the project architecture and contribution model mature.

---

## 👤 Project

**ROOTCLOUD**

> **Your data. Your control.**

Developed as an open-source exploration of secure and sovereign cloud infrastructure for organizations in Cameroon and Africa.
