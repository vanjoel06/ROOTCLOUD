# ROOTCLOUD — Architecture

## 1. Overview

ROOTCLOUD is being designed as a modular private cloud platform based primarily on open-source technologies.

The initial architecture focuses on four fundamental layers:

1. Network and security
2. Virtualization and infrastructure
3. Cloud services
4. Storage

The architecture is currently at the prototype stage and may evolve as testing progresses.

---

## 2. High-Level Architecture

```text
                         INTERNET
                            │
                            ▼
                    ┌───────────────┐
                    │    OPNsense   │
                    │               │
                    │ Firewall      │
                    │ VPN           │
                    │ Routing       │
                    │ Network Sec.  │
                    └───────┬───────┘
                            │
                     Internal Network
                            │
             ┌──────────────┴──────────────┐
             │                             │
             ▼                             ▼
      ┌───────────────┐             ┌───────────────┐
      │   Nextcloud   │             │     MinIO     │
      │               │             │               │
      │ File storage  │             │ Object        │
      │ Collaboration │             │ storage       │
      │ User access   │             │ S3-compatible │
      └───────┬───────┘             └───────┬───────┘
              │                             │
              └──────────────┬──────────────┘
                             │
                             ▼
                     ┌───────────────┐
                     │    Proxmox    │
                     │               │
                     │ Virtualization│
                     │ Infrastructure│
                     └───────────────┘
```

---

## 3. Network and Security Layer

### OPNsense

OPNsense is intended to provide the initial network security layer.

Potential responsibilities include:

* Firewalling
* Routing
* Network segmentation
* VPN
* Access control
* Traffic filtering
* Network monitoring

The final network architecture will depend on the deployment environment.

---

## 4. Virtualization Layer

### Proxmox VE

Proxmox VE provides the virtualization foundation for the prototype.

It allows ROOTCLOUD services to be isolated into dedicated virtual machines or containers.

For example:

```text
Proxmox
│
├── VM — OPNsense
│
├── VM — Nextcloud
│
├── VM — MinIO
│
├── VM — Monitoring
│
└── VM — Future Services
```

The exact allocation of resources will depend on the available hardware.

---

## 5. Cloud Services Layer

### Nextcloud

Nextcloud is being evaluated as the primary user-facing cloud platform.

Potential functions include:

* File storage
* File synchronization
* File sharing
* User management
* Collaborative work
* Remote access

---

## 6. Object Storage Layer

### MinIO

MinIO provides an S3-compatible object-storage interface.

It may be used for:

* Application data
* Object storage
* Backup repositories
* Future cloud services
* S3-compatible applications

The final role of MinIO within ROOTCLOUD is still being evaluated.

---

## 7. Storage Architecture

Storage is a critical component of ROOTCLOUD.

The project will investigate:

* Local storage
* Redundant storage
* Backup storage
* Object storage
* Data replication
* Recovery mechanisms

A production deployment should avoid relying on a single physical disk or single point of failure.

---

## 8. Backup and Recovery

Backup is considered a separate function from primary storage.

The architecture will progressively evaluate:

```text
Primary Data
     │
     ├──────────────► Local Backup
     │
     └──────────────► Secondary / Remote Backup
```

Future work will define:

* Backup frequency
* Retention policies
* Recovery Point Objectives (RPO)
* Recovery Time Objectives (RTO)
* Backup encryption
* Restore testing

---

## 9. Security Architecture

Security will be integrated throughout the platform rather than treated as a separate component.

Areas under consideration include:

* Least privilege
* Identity and access management
* Strong authentication
* Network segmentation
* Encryption
* Secure remote access
* Logging
* Monitoring
* Vulnerability management
* Backup protection
* Incident detection

---

## 10. Availability and Resilience

The prototype will initially focus on functionality before implementing advanced high-availability mechanisms.

Future studies may include:

* Redundant network connectivity
* Redundant storage
* Service redundancy
* Virtual machine replication
* High-availability clusters
* Backup infrastructure
* Disaster recovery

The objective is to progressively identify and reduce critical single points of failure.

---

## 11. ROOTBOX Integration

ROOTBOX is envisioned as an edge/continuity component complementary to the central ROOTCLOUD infrastructure.

A possible future architecture is:

```text
                 ROOTCLOUD
              Central Platform
                     │
              Internet / VPN
                     │
                     ▼
                  ROOTBOX
               Local / Edge
                     │
          ┌──────────┴──────────┐
          │                     │
       Local Data          Local Services
          │                     │
          └──────────┬──────────┘
                     │
              Synchronization
                     │
                     ▼
                 ROOTCLOUD
```

This architecture remains conceptual and requires further experimentation.

---

## 12. Future Architecture

As the project matures, ROOTCLOUD may evolve toward a more modular cloud platform providing:

```text
                    ROOTCLOUD
                        │
        ┌───────────────┼────────────────┐
        │               │                │
       SaaS            PaaS             IaaS
        │               │                │
 Applications      Development       Infrastructure
   Services          Services          Services
```

Potential technologies such as OpenStack or other orchestration platforms may be evaluated when justified by the project's requirements.

---

## 13. Design Principles

ROOTCLOUD follows several initial principles:

### Security by design

Security should be considered during architecture and implementation rather than added afterward.

### Open-source first

Open-source technologies are preferred when they provide appropriate functionality, security and maintainability.

### Modularity

Components should be replaceable without redesigning the entire platform.

### Sovereignty

Organizations should retain control over their infrastructure and data.

### Resilience

The architecture should progressively reduce critical single points of failure.

### Cost awareness

The platform should consider the financial and technical constraints of its target users.
