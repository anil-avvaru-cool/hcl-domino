# HCL Domino Architecture Diagrams (Split Version)

Below are simplified, smaller diagrams to make each part easier to understand.

---

## 1. Client Access Architecture

```mermaid
flowchart LR
  NotesClient[Notes / Verse]
  WebBrowser[Web Browser]
  Mobile[Mobile Clients]

  LB[Load Balancer]
  WAF[WAF]
  WebProxy[HTTP Proxy]

  NotesClient -->|NRPC or HTTPS| Domino
  WebBrowser -->|HTTPS| LB --> WAF --> WebProxy --> Domino
  Mobile -->|REST/JSON| WebProxy --> Domino
```

---

## 2. Domino Core Server Architecture

```mermaid
flowchart LR
  DominoA[Domino Server A]
  DominoB[Domino Server B]
  ClusterFiles[NSF Databases]
  Directory[Domino Directory]
  Replicator[Replication]
  Metrics[Monitoring]

  DominoA <--> DominoB
  DominoA --> ClusterFiles
  DominoB --> ClusterFiles
  DominoA --> Directory
  DominoB --> Directory
  DominoA --> Replicator
  DominoB --> Replicator
  DominoA --> Metrics
  DominoB --> Metrics
```

---

## 3. Security and Identity Components

```mermaid
flowchart LR
  AdminP[AdminP]
  IDVault[ID Vault]
  LDAP[LDAP or AD]
  CAS[Certificate Authority]

  AdminP --> IDVault
  Domino --> LDAP
  Domino --> CAS
```

---

## 4. Integration Landscape

```mermaid
flowchart LR
  Domino[Domino App Server]
  ExternalAPI[External Systems]
  Backups[Backup and Restore]
  SIEM[SIEM Logging]

  Domino --> ExternalAPI
  Domino --> Backups
  Domino --> SIEM
```

---

