# System Design at Scale — 120 Days

> **By [Eknatha Reddy Puli](https://github.com/eknatha) · EknathaLabs**  
> Real-world system design. Engineering trade-offs. Failure scenarios. Capacity math. Kubernetes at scale. Built in public.

---

## What This Is

This is not a diagram collection.

Most system design content stops at boxes and arrows. This series goes further — into the trade-offs that get made at 3am when a service is degrading, the capacity math that happens before a product launch, the failure modes that only reveal themselves at scale, and how Kubernetes actually behaves when the cluster is under pressure.

120 days. One topic per day. Every entry written from an engineer's perspective.

---

## Structure

```
system-design-at-scale-120-days/
│
├── 00-foundations/               # Days 01–10:  Core concepts before scale
├── 01-scalability/               # Days 11–20:  Scaling patterns & anti-patterns
├── 02-reliability/               # Days 21–30:  Failure scenarios, resilience design
├── 03-data-at-scale/             # Days 31–40:  Storage, replication, consistency
├── 04-networking-and-traffic/    # Days 41–50:  Load balancing, CDN, DNS at scale
├── 05-capacity-planning/         # Days 51–60:  Back-of-envelope math, resource modeling
├── 06-observability/             # Days 61–70:  Metrics, tracing, alerting philosophy
├── 07-engineering-trade-offs/    # Days 71–80:  The decisions behind the decisions
├── 08-case-studies/              # Days 81–95:  Real-world system breakdowns
├── 09-kubernetes-at-scale/       # Days 96–115: Kubernetes internals, failure, security, ops
├── 10-interview-ready/           # Days 116–120: Synthesis, walkthroughs, practice
│
├── templates/
│   ├── daily-entry.md            # Template for each day's entry
│   ├── case-study.md             # Template for case study entries
│   └── capacity-worksheet.md    # Template for capacity planning exercises
│
└── README.md
```

---

## What Each Entry Covers

Every day's entry follows a consistent structure:

```
# Day XX: [Topic]

## The Problem at Scale
What breaks, degrades, or becomes expensive as you grow.

## Core Concept
The mechanism, pattern, or principle — explained without hand-waving.

## Engineering Trade-offs
What you gain, what you give up, and when to choose differently.

## Failure Scenarios
How this goes wrong. Real failure modes, not just "what if the server dies."

## Capacity Signals
Numbers to know. Rules of thumb. Back-of-envelope estimates.

## Real-World Signal
How this manifests in production systems — at companies, at scale.

## Key Takeaway
One sentence. What an engineer should carry forward.
```

---

## Series Breakdown

### 🔷 Foundations (Days 01–10)
Core mental models before you touch scale.

| Day | Topic |
|-----|-------|
| 01 | Latency vs Throughput — the number every decision rides on |
| 02 | Horizontal vs Vertical Scaling — when each one breaks |
| 03 | CAP Theorem — what it actually means in practice |
| 04 | Consistency Models — eventual, strong, causal |
| 05 | The Fallacies of Distributed Computing |
| 06 | Back-of-Envelope Math — how to estimate like a senior engineer |
| 07 | Stateless vs Stateful Services |
| 08 | Synchronous vs Asynchronous Communication |
| 09 | The Cost of a Network Call |
| 10 | SLOs, SLIs, and Error Budgets |

---

### ⚡ Scalability (Days 11–20)
Patterns that work, anti-patterns that look like they work.

| Day | Topic |
|-----|-------|
| 11 | Load Balancing — algorithms and failure modes |
| 12 | Caching — layers, invalidation, stampede |
| 13 | Database Sharding — keys, hotspots, rebalancing |
| 14 | Read Replicas — lag, failover, consistency traps |
| 15 | Rate Limiting — algorithms, distributed enforcement |
| 16 | Queue-Based Load Leveling |
| 17 | Fan-out vs Fan-in Architectures |
| 18 | Write-Heavy Systems — patterns and pitfalls |
| 19 | Read-Heavy Systems — CDN, caching hierarchies |
| 20 | The Thundering Herd Problem |

---

### 🔴 Reliability & Failure Scenarios (Days 21–30)
Systems fail. Design for it.

| Day | Topic |
|-----|-------|
| 21 | Circuit Breakers — when to open, when to close |
| 22 | Retry Storms — why naive retries make outages worse |
| 23 | Cascading Failures — how one service takes down ten |
| 24 | Bulkhead Pattern — isolating failure blast radius |
| 25 | Graceful Degradation vs Total Failure |
| 26 | Chaos Engineering — intentional failure as discipline |
| 27 | Split Brain Scenarios in Distributed Systems |
| 28 | Clock Skew and Distributed Consensus |
| 29 | Hot Standby vs Warm Standby vs Cold Standby |
| 30 | Building a Post-Mortem Culture |

---

### 🗄️ Data at Scale (Days 31–40)
Where most systems hit their ceiling.

| Day | Topic |
|-----|-------|
| 31 | When Relational Databases Stop Scaling |
| 32 | NoSQL Trade-offs — not a silver bullet |
| 33 | Time-Series Data — storage and query patterns |
| 34 | Data Replication — sync vs async, lag implications |
| 35 | Write-Ahead Log (WAL) — the backbone of durability |
| 36 | Consistent Hashing — virtual nodes, rebalancing |
| 37 | Event Sourcing vs CRUD — when history matters |
| 38 | CQRS — separating read and write models |
| 39 | Blob Storage at Scale — object stores, access patterns |
| 40 | Database Connection Pooling — the silent bottleneck |

---

### 🌐 Networking & Traffic (Days 41–50)
Traffic is not just bandwidth — it's behavior.

| Day | Topic |
|-----|-------|
| 41 | DNS at Scale — TTLs, anycast, failover |
| 42 | CDN Internals — edge caching, cache miss cost |
| 43 | TCP vs UDP — choosing at the application layer |
| 44 | HTTP/2 and HTTP/3 — what changes at scale |
| 45 | WebSockets and Long Polling — real-time trade-offs |
| 46 | Service Mesh — sidecar overhead vs observability |
| 47 | API Gateway — not just a proxy |
| 48 | Traffic Shaping and Throttling |
| 49 | BGP, Anycast, and Global Load Balancing |
| 50 | Network Partitions — designing for them, not ignoring them |

---

### 📐 Capacity Planning (Days 51–60)
Math-driven decisions before the incident.

| Day | Topic |
|-----|-------|
| 51 | Capacity Planning Fundamentals — the mental model |
| 52 | Estimating Storage Growth |
| 53 | Estimating QPS and Traffic Peaks |
| 54 | CPU and Memory Sizing Heuristics |
| 55 | Database Capacity — IOPS, connections, row growth |
| 56 | Cache Hit Rate Math — sizing for efficiency |
| 57 | Queue Depth and Lag Modeling |
| 58 | Bandwidth Cost Estimation |
| 59 | Capacity for High-Availability Configurations |
| 60 | Runway Planning — when to scale before you must |

---

### 🔭 Observability (Days 61–70)
You can't fix what you can't see.

| Day | Topic |
|-----|-------|
| 61 | The Three Pillars — Metrics, Logs, Traces |
| 62 | Designing Meaningful Metrics |
| 63 | Distributed Tracing — propagation, sampling |
| 64 | Log Aggregation at Scale |
| 65 | Alerting Philosophy — signal vs noise |
| 66 | SLO-Based Alerting |
| 67 | Dashboards That Actually Help During Incidents |
| 68 | On-Call Design — reducing alert fatigue |
| 69 | Synthetic Monitoring and Health Checks |
| 70 | Observability in Kubernetes Environments |

---

### ⚖️ Engineering Trade-offs (Days 71–80)
The decisions behind the decisions.

| Day | Topic |
|-----|-------|
| 71 | Consistency vs Availability — choosing in context |
| 72 | Latency vs Durability |
| 73 | Monolith vs Microservices — the honest version |
| 74 | SQL vs NoSQL — a trade-off framework, not a debate |
| 75 | Push vs Pull Architectures |
| 76 | Synchronous vs Event-Driven — where each breaks |
| 77 | Build vs Buy vs OSS |
| 78 | Strong Typing vs Schema Flexibility in APIs |
| 79 | Multi-Region vs Single-Region — cost, complexity, need |
| 80 | Technical Debt as a System Design Variable |

---

### 🏢 Case Studies (Days 81–95)
Real systems. Real decisions. Real failures.

| Day | System | Angle |
|-----|--------|-------|
| 81 | Twitter/X | Fan-out on write vs read — the timeline problem |
| 82 | YouTube | Video ingestion and adaptive streaming at scale |
| 83 | Slack | Message delivery guarantees and ordering |
| 84 | Uber | Geospatial indexing and dispatch at scale |
| 85 | Netflix | Chaos Engineering origin and resilience model |
| 86 | WhatsApp | 2 million connections per server — how |
| 87 | GitHub | Git hosting at scale — object storage, LFS |
| 88 | Cloudflare | Anycast routing and DDoS mitigation |
| 89 | Stripe | Idempotency, payment reliability, ledger design |
| 90 | Discord | Moving from MongoDB to Cassandra |
| 91 | Dropbox | Deduplication, sync protocol, delta compression |
| 92 | Reddit | Hot content serving and vote counters |
| 93 | Amazon S3 | Durability math and storage internals |
| 94 | Zoom | 300ms latency budget and media routing |
| 95 | A Fictional Startup | Scaling from 0 to 10M users — every decision |

---

---

### ☸️ Kubernetes at Scale (Days 96–115)
Not how to pass the CKA. How Kubernetes behaves under real production pressure.

#### 🔩 Internals & Architecture (Days 96–101)

| Day | Topic |
|-----|-------|
| 96  | Kubernetes Control Plane Internals — what etcd, API server, scheduler actually do |
| 97  | The Kubelet — how it drives node state and what happens when it fails |
| 98  | etcd at Scale — why it's the cluster's single point of truth and its limits |
| 99  | Kubernetes Networking Model — CNI plugins, Pod-to-Pod, Service routing |
| 100 | kube-proxy vs eBPF — how traffic actually reaches your Pod |
| 101 | Kubernetes Scheduling — predicates, priorities, and why pods get stuck |

#### ⚡ Scaling & Resource Management (Days 102–106)

| Day | Topic |
|-----|-------|
| 102 | HPA Deep Dive — custom metrics, stabilization windows, flapping |
| 103 | VPA vs HPA — when vertical scaling makes sense in Kubernetes |
| 104 | Cluster Autoscaler — node provisioning lag and its real-world impact |
| 105 | Resource Requests vs Limits — the QoS classes that determine eviction order |
| 106 | Node Pressure and Pod Eviction — OOMKilled, DiskPressure, and what triggers what |

#### 🔴 Failure Scenarios & Reliability (Days 107–110)

| Day | Topic |
|-----|-------|
| 107 | Kubernetes Failure Modes — what actually breaks and in what order |
| 108 | CrashLoopBackOff, ImagePullBackOff, Pending — root causes behind the status |
| 109 | Control Plane HA — multi-master setup, etcd quorum, split brain |
| 110 | Pod Disruption Budgets — rolling updates that don't take down your service |

#### 🔐 Security at Scale (Days 111–113) *(CKS territory)*

| Day | Topic |
|-----|-------|
| 111 | RBAC in Production — least privilege, common misconfigurations, audit logs |
| 112 | Pod Security — SecurityContext, seccomp, AppArmor, privileged containers |
| 113 | Supply Chain Security — image signing, admission controllers, OPA/Gatekeeper |

#### 🔭 Kubernetes Observability & Ops (Days 114–115)

| Day | Topic |
|-----|-------|
| 114 | Kubernetes-Native Observability — events, metrics-server, Prometheus operator |
| 115 | Multi-Cluster and Multi-Tenant Kubernetes — federation, namespace isolation, cost attribution |

---

### 🎯 Interview-Ready Synthesis (Days 116–120)

| Day | Topic |
|-----|-------|
| 116 | How to Walk Through a System Design Problem |
| 117 | Scoping, Assumptions, and Estimation in Interviews |
| 118 | 5 Common Systems — Full Walkthroughs |
| 119 | Red Flags That Kill Candidates (And How to Avoid Them) |
| 120 | The Mental Model Stack — Everything in One Page |


---

## How to Follow Along

- ⭐ Star the repo to get updates
- Watch for new entries daily (or close to it)
- Cross-references between entries are intentional — systems thinking requires connecting concepts

---

## About

Built by **Eknatha Reddy Puli** .

- 🔗 GitHub: [@eknatha](https://github.com/eknatha)
- 💼 LinkedIn: [eknathareddyp](https://linkedin.com/in/eknathareddyp)
- 🌐 Blog: [blog.eknathalabs.com](https://blog.eknathalabs.com)
- 🧪 Website: [eknathalabs.com](https://eknathalabs.com)

Part of the **EknathaLabs** ecosystem — building in public.

---

> *"Scale is not a feature. It's a consequence of design decisions made long before the traffic arrived."*

---

**120 days. No filler. Engineer-first.**
