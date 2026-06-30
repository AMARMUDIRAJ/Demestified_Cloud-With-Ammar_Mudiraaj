# IT for Non-IT Learners — Cloud Computing
## Full Series ROADMAP (Phases 0–3)

*Teach the concept first (vendor-neutral), then show how all five providers do the same thing. One single ordered path for every learner.*

---

### Control panel (in effect)

| Setting | Value |
|---|---|
| MODE | ROADMAP |
| PROVIDERS | AWS · Azure · GCP · Oracle (OCI) · Alibaba |
| DEPTH | standard |
| VIDEO_LENGTH | 8–12 min |
| LANGUAGE | English |
| TONE | warm, friendly teacher; simple words; one big analogy per video |
| INCLUDE_CERTS | optional (covered in one Phase 3 video) |

**Provider order is fixed everywhere:** AWS → Azure → GCP → OCI → Alibaba.
**ID scheme:** `Phase-Domain-Item`. Foundation = `-F` (or `-F1/-F2`), providers = `-AWS/-AZ/-GCP/-OCI/-ALI`, comparison = `-CMP`.
Domain codes: NET, CPT (compute), STO (storage), DB, IAM, SEC, SVR (serverless/containers), OPS (edge/monitoring/IaC/messaging/cost).

---

### Naming updates verified June 2026 (used throughout this series)

These official names changed after the canonical map was first written. The series uses the current names and flags the old one once, so learners recognize both.

- **GCP — Cloud Functions → "Cloud Run functions."** Rebranded Aug 2024; serverless functions now live under the Cloud Run umbrella. We say "Cloud Run functions (formerly Cloud Functions)."
- **GCP — Deployment Manager retired; use "Infrastructure Manager."** Deployment Manager support ended 31 Mar 2026; the Terraform-based **Infrastructure Manager** is the successor. We teach Infrastructure Manager + Terraform.
- **Azure — CDN edge is now "Azure Front Door."** Azure CDN from Edgio retired Jan 2025; the classic Azure CDN/Front Door are on a retirement path (2027). **Azure Front Door** is the primary edge/CDN service we teach.
- **Azure — "Microsoft Entra ID" (formerly Azure AD).** Used for the IAM domain.
- **Alibaba — "SLB" is now the load-balancer family name** (CLB Classic, ALB, NLB). We teach ALB/NLB as the recommended modern choices and note CLB.

---

## PHASE 0 — Digital & Computing Literacy (pre-cloud)
*The absolute basics a non-IT person needs before the word "cloud" is ever used.*

- **P0-COMP-01** · "What's Actually Inside a Computer? CPU, RAM & Storage in Plain English" — *By the end you'll be able to explain what the brain, the desk, and the drawer of a computer each do.*
- **P0-OS-01** · "What Is an Operating System? Your Computer's Invisible Manager" — *By the end you'll be able to say what an OS does and name the big three (Windows, macOS, Linux).*
- **P0-FILE-01** · "Files, Folders & File Paths Explained for Total Beginners" — *By the end you'll be able to read a file path and explain how data is organized.*
- **P0-LINUX-01** · "Your First 10 Linux Commands (No Coding Background Needed)" — *By the end you'll be able to open a terminal and move around a computer by typing.*
- **P0-NET-01** · "How Does the Internet Actually Work? The Postal-System Guide" — *By the end you'll be able to describe what happens when you open a website.*
- **P0-NET-02** · "Client & Server Explained: Who's Really Talking When You Browse?" — *By the end you'll be able to explain the client–server model with a restaurant analogy.*
- **P0-NET-03** · "IP Addresses, DNS & Ports — The Internet's Address Book" — *By the end you'll be able to explain how `google.com` becomes a real connection.*
- **P0-VIRT-01** · "What Is a Virtual Machine? One Computer Pretending to Be Many" — *By the end you'll be able to explain virtualization — the hidden foundation of all cloud.*

**Phase 0 — 8 videos · ~80 min (1.3 hrs) at 10 min avg**

---

## PHASE 1 — Cloud Foundations (vendor-neutral)
*What "the cloud" actually is, before any provider is named.*

- **P1-WHATISCLOUD-01** · "What Is 'The Cloud,' Really? (It's Just Someone Else's Computer)" — *By the end you'll be able to explain the cloud with zero hype or jargon.*
- **P1-ONPREM-01** · "On-Premises vs Cloud: Owning a Car vs Calling a Taxi" — *By the end you'll be able to explain why companies move off their own servers.*
- **P1-SERVICE-01** · "IaaS, PaaS & SaaS Explained with Pizza" — *By the end you'll be able to tell the three service models apart and spot examples.*
- **P1-DEPLOY-01** · "Public, Private & Hybrid Cloud — Which Is Which?" — *By the end you'll be able to explain each deployment model and when it's used.*
- **P1-GEO-01** · "Regions & Availability Zones: How the Cloud Spans the Planet" — *By the end you'll be able to explain why location keeps your app fast and safe.*
- **P1-SHARED-01** · "The Shared Responsibility Model: Who Secures What in the Cloud?" — *By the end you'll be able to say which security jobs are yours vs the provider's.*
- **P1-ECON-01** · "Cloud Economics: CapEx vs OpEx and 'Pay Only for What You Use'" — *By the end you'll be able to explain why cloud billing differs from buying hardware.*
- **P1-MAP-01** · "The Cloud Service Map: A Bird's-Eye View Before We Dive In" — *By the end you'll be able to name the major service categories and how they fit.*



*Plus the 16 vendor-neutral **domain foundations** below — taught in Phase 1, each before its provider videos in Phase 2:*

- **P1-NET-F** · "What Is a Computer Network? The Apartment-Building Guide to the Cloud" — *By the end you'll be able to explain IP addresses, subnets, and firewalls in plain English.*
- **P1-CPT-F** · "Virtual Machines Demystified: Renting a Computer in the Sky" — *By the end you'll be able to explain what a VM is and what CPU/RAM/disk choices mean.*
- **P1-STO-F** · "Object vs Block vs File Storage — The 3 Ways the Cloud Keeps Data" — *By the end you'll be able to tell the three storage types apart and pick the right one.*
- **P1-DB-F1** · "What Is a Database? From Spreadsheets to Superpowers" — *By the end you'll be able to explain what a database is and why apps need one.*
- **P1-DB-F2** · "Relational Databases & SQL Explained (Tables, Rows & ACID)" — *By the end you'll be able to read a simple table design and explain SQL and ACID.*
- **P1-DB-F3** · "NoSQL, Semi-Structured Data & Caching Explained Simply" — *By the end you'll be able to tell relational vs NoSQL apart and know when each fits.*
- **P1-IAM-F** · "Authentication vs Authorization: Who Are You, and What Can You Do?" — *By the end you'll be able to explain users, roles, and policies — the keys to cloud security.*
- **P1-SEC-F1** · "Encryption Explained: Locking Your Data at Rest and in Transit" — *By the end you'll be able to explain encryption and what an encryption key really is.*
- **P1-SEC-F2** · "Firewalls & Security Groups: The Cloud's Bouncers Explained" — *By the end you'll be able to explain how cloud firewalls decide what traffic to allow.*
- **P1-OPS-EDGE-F** · "Load Balancers, DNS & CDNs: How Big Websites Stay Fast & Online" — *By the end you'll be able to explain how traffic gets shared, named, and cached worldwide.*
- **P1-OPS-MON-F** · "Monitoring, Metrics & Logs: How to Know If Your Cloud Is Healthy" — *By the end you'll be able to explain metrics, logs, and alerts in plain English.*
- **P1-SVR-F1** · "Containers vs Virtual Machines: What's the Difference? (Lunchbox Analogy)" — *By the end you'll be able to explain what a container is and why it beats a VM for many jobs.*
- **P1-SVR-F2** · "Serverless & Kubernetes Explained: Code Without Managing Servers" — *By the end you'll be able to explain FaaS/event-driven computing and what Kubernetes orchestrates.*
- **P1-OPS-IAC-F** · "Infrastructure as Code Explained: Build Your Cloud from a Recipe" — *By the end you'll be able to explain why teams describe infrastructure in files instead of clicking.*
- **P1-OPS-MSG-F** · "Message Queues & Events: How Cloud Apps Talk Without Crashing" — *By the end you'll be able to explain why apps use queues and events to stay reliable.*
- **P1-OPS-COST-F** · "Cloud Billing & Cost Control: How Not to Get a Surprise Bill" — *By the end you'll be able to explain pricing models and the habits that keep costs low.*


**Phase 1 — 24 videos · ~240 min (4 hrs) at 10 min avg** *(8 cloud-foundation concepts + 16 domain foundations)*

---

## PHASE 2 — Provider Implementations (category-parallel)
*For each domain: 5 provider videos (AWS → Azure → GCP → OCI → Alibaba) → 1 side-by-side comparison. The vendor-neutral Foundation for each domain is taught in Phase 1.*

### Domain 1 · Networking (NET)
- **P2-NET-AWS** · "AWS VPC Explained for Absolute Beginners (No Jargon)" — *By the end you'll be able to build and understand a VPC with a public and private subnet.*
- **P2-NET-AZ** · "Azure Virtual Network (VNet) Explained for Beginners" — *By the end you'll be able to map your network knowledge onto Azure's VNet.*
- **P2-NET-GCP** · "Google Cloud VPC Explained for Beginners (Global by Default)" — *By the end you'll be able to explain how GCP's global VPC differs from the others.*
- **P2-NET-OCI** · "Oracle Cloud VCN Explained for Beginners" — *By the end you'll be able to build a basic Virtual Cloud Network in OCI.*
- **P2-NET-ALI** · "Alibaba Cloud VPC Explained for Beginners" — *By the end you'll be able to set up a basic VPC on Alibaba Cloud.*
- **P2-NET-CMP** · "Cloud Networking Side by Side: VPC vs VNet vs VPC vs VCN vs VPC" — *By the end you'll be able to translate the same network across all five clouds.*

### Domain 2 · Compute / Virtual Machines (CPT)
- **P2-CPT-AWS** · "AWS EC2 Explained: Launch Your First Cloud Server (Free Tier)" — *By the end you'll be able to launch and connect to a free-tier EC2 instance.*
- **P2-CPT-AZ** · "Azure Virtual Machines Explained for Beginners" — *By the end you'll be able to create an Azure VM and understand its sizes.*
- **P2-CPT-GCP** · "Google Compute Engine Explained for Beginners" — *By the end you'll be able to launch a VM on GCP and read machine types.*
- **P2-CPT-OCI** · "Oracle Cloud Compute Explained (Generous Always-Free VMs)" — *By the end you'll be able to launch an always-free VM on OCI.*
- **P2-CPT-ALI** · "Alibaba Cloud ECS Explained for Beginners" — *By the end you'll be able to launch an Elastic Compute Service instance.*
- **P2-CPT-CMP** · "Cloud VMs Compared: EC2 vs Azure VMs vs Compute Engine vs OCI vs ECS" — *By the end you'll be able to pick the right VM and read pricing across all five.*

### Domain 3 · Storage (STO)
- **P2-STO-AWS** · "AWS Storage Explained: S3, EBS & EFS for Beginners" — *By the end you'll be able to choose between S3, EBS, and EFS.*
- **P2-STO-AZ** · "Azure Storage Explained: Blob, Managed Disks & Azure Files" — *By the end you'll be able to map object/block/file onto Azure.*
- **P2-STO-GCP** · "Google Cloud Storage Explained: Cloud Storage, Persistent Disk & Filestore" — *By the end you'll be able to choose the right GCP storage for the job.*
- **P2-STO-OCI** · "Oracle Cloud Storage Explained: Object, Block & File Storage" — *By the end you'll be able to map the three storage types onto OCI.*
- **P2-STO-ALI** · "Alibaba Cloud Storage Explained: OSS, Cloud Disk & NAS" — *By the end you'll be able to choose between OSS, Cloud Disk, and NAS.*
- **P2-STO-CMP** · "Cloud Storage Compared: S3 vs Blob vs Cloud Storage vs OCI vs OSS" — *By the end you'll be able to translate object/block/file across all five clouds.*

### Domain 4 · Databases (DB)
- **P2-DB-AWS** · "AWS Databases Explained: RDS/Aurora, DynamoDB & ElastiCache" — *By the end you'll be able to pick the right AWS database for an app.*
- **P2-DB-AZ** · "Azure Databases Explained: Azure SQL, Cosmos DB & Cache for Redis" — *By the end you'll be able to map relational/NoSQL/cache onto Azure.*
- **P2-DB-GCP** · "Google Cloud Databases: Cloud SQL, Spanner, Firestore & Bigtable" — *By the end you'll be able to choose among GCP's database options.*
- **P2-DB-OCI** · "Oracle Cloud Databases: Autonomous Database & Base Database" — *By the end you'll be able to explain OCI's self-driving database and when to use it.*
- **P2-DB-ALI** · "Alibaba Cloud Databases: ApsaraDB RDS, Tablestore & Redis" — *By the end you'll be able to map the database types onto Alibaba Cloud.*
- **P2-DB-CMP** · "Cloud Databases Compared Across AWS, Azure, GCP, OCI & Alibaba" — *By the end you'll be able to translate relational, NoSQL, and cache across all five.*

### Domain 5 · Identity & Access (IAM)
- **P2-IAM-AWS** · "AWS IAM Explained for Beginners (Users, Roles & Policies)" — *By the end you'll be able to create a safe IAM user instead of using root.*
- **P2-IAM-AZ** · "Microsoft Entra ID & RBAC Explained for Beginners (formerly Azure AD)" — *By the end you'll be able to understand Azure identities and role-based access.*
- **P2-IAM-GCP** · "Google Cloud IAM Explained for Beginners" — *By the end you'll be able to grant least-privilege access in GCP.*
- **P2-IAM-OCI** · "Oracle Cloud IAM Explained: Compartments, Users & Policies" — *By the end you'll be able to understand OCI's unique compartment model.*
- **P2-IAM-ALI** · "Alibaba Cloud RAM Explained for Beginners" — *By the end you'll be able to manage users and permissions with RAM.*
- **P2-IAM-CMP** · "Cloud IAM Compared: AWS vs Entra ID vs GCP vs OCI vs Alibaba RAM" — *By the end you'll be able to translate identity and access across all five clouds.*

### Domain 6 · Security & Encryption (SEC)
- **P2-SEC-AWS** · "AWS Security: KMS, Security Groups & NACLs Explained" — *By the end you'll be able to encrypt with KMS and lock down traffic with security groups.*
- **P2-SEC-AZ** · "Azure Security: Key Vault & Network Security Groups Explained" — *By the end you'll be able to protect keys and network traffic in Azure.*
- **P2-SEC-GCP** · "Google Cloud Security: Cloud KMS & Firewall Rules Explained" — *By the end you'll be able to manage keys and firewall rules in GCP.*
- **P2-SEC-OCI** · "Oracle Cloud Security: OCI Vault & Security Lists Explained" — *By the end you'll be able to secure keys and traffic in OCI.*
- **P2-SEC-ALI** · "Alibaba Cloud Security: KMS & Security Groups Explained" — *By the end you'll be able to protect keys and network traffic on Alibaba Cloud.*
- **P2-SEC-CMP** · "Cloud Security & Encryption Compared Across All Five Clouds" — *By the end you'll be able to translate key management and network security across providers.*

### Domain 7 · Serverless & Containers (SVR)
- **P2-SVR-AWS** · "AWS Serverless & Containers: Lambda, ECS & EKS Explained" — *By the end you'll be able to know when to use Lambda vs containers on AWS.*
- **P2-SVR-AZ** · "Azure Functions & AKS Explained for Beginners" — *By the end you'll be able to run serverless code and containers on Azure.*
- **P2-SVR-GCP** · "Google Cloud Run, Cloud Run Functions & GKE Explained" — *By the end you'll be able to run serverless and Kubernetes workloads on GCP.*
- **P2-SVR-OCI** · "Oracle Cloud Functions & OKE Explained for Beginners" — *By the end you'll be able to run serverless functions and Kubernetes on OCI.*
- **P2-SVR-ALI** · "Alibaba Function Compute & ACK Explained for Beginners" — *By the end you'll be able to run serverless and Kubernetes on Alibaba Cloud.*
- **P2-SVR-CMP** · "Serverless & Kubernetes Compared Across AWS, Azure, GCP, OCI & Alibaba" — *By the end you'll be able to translate Functions and managed Kubernetes across all five.*

### Domain 8 · Edge, Operations & Cost (OPS)
*The "make it fast, watch it, automate it, connect it, and pay smart" domain — split into five short tracks.*

**8a · Edge networking (OPS-EDGE) — Load Balancing, DNS, CDN**
- **P2-OPS-EDGE-AWS** · "AWS Edge: ELB, Route 53 & CloudFront Explained" — *By the end you'll be able to distribute traffic, route DNS, and cache content on AWS.*
- **P2-OPS-EDGE-AZ** · "Azure Edge: Load Balancer, Azure DNS & Front Door Explained" — *By the end you'll be able to balance traffic and deliver content fast on Azure.*
- **P2-OPS-EDGE-GCP** · "Google Cloud Load Balancing, Cloud DNS & Cloud CDN Explained" — *By the end you'll be able to serve global traffic with GCP's edge services.*
- **P2-OPS-EDGE-OCI** · "Oracle Cloud Load Balancer, DNS & CDN Explained" — *By the end you'll be able to balance and route traffic on OCI.*
- **P2-OPS-EDGE-ALI** · "Alibaba Cloud ALB/NLB, DNS & CDN Explained" — *By the end you'll be able to distribute and accelerate traffic on Alibaba Cloud.*
- **P2-OPS-EDGE-CMP** · "Cloud Load Balancing, DNS & CDN Compared Across All Five Clouds" — *By the end you'll be able to translate edge networking across providers.*

**8b · Monitoring & logging (OPS-MON)**
- **P2-OPS-MON-AWS** · "AWS CloudWatch Explained for Beginners" — *By the end you'll be able to read metrics, view logs, and set an alarm in CloudWatch.*
- **P2-OPS-MON-AZ** · "Azure Monitor Explained for Beginners" — *By the end you'll be able to track health and set alerts with Azure Monitor.*
- **P2-OPS-MON-GCP** · "Google Cloud Monitoring & Logging (Operations Suite) Explained" — *By the end you'll be able to monitor and log workloads in GCP.*
- **P2-OPS-MON-OCI** · "Oracle Cloud Monitoring & Logging Explained" — *By the end you'll be able to watch metrics and logs in OCI.*
- **P2-OPS-MON-ALI** · "Alibaba CloudMonitor Explained for Beginners" — *By the end you'll be able to monitor resources and set alerts on Alibaba Cloud.*
- **P2-OPS-MON-CMP** · "Cloud Monitoring Compared: CloudWatch vs Azure Monitor vs the Rest" — *By the end you'll be able to translate monitoring and logging across all five clouds.*

**8c · Infrastructure as Code (OPS-IAC)**
- **P2-OPS-IAC-AWS** · "AWS CloudFormation Explained for Beginners" — *By the end you'll be able to deploy AWS resources from a template.*
- **P2-OPS-IAC-AZ** · "Azure ARM Templates & Bicep Explained for Beginners" — *By the end you'll be able to deploy Azure resources as code.*
- **P2-OPS-IAC-GCP** · "Google Cloud Infrastructure Manager & Terraform Explained" — *By the end you'll be able to provision GCP with Terraform-based IaC.*
- **P2-OPS-IAC-OCI** · "Oracle Cloud Resource Manager (Terraform) Explained" — *By the end you'll be able to deploy OCI resources as code.*
- **P2-OPS-IAC-ALI** · "Alibaba Cloud ROS (Resource Orchestration Service) Explained" — *By the end you'll be able to deploy Alibaba resources from a template.*
- **P2-OPS-IAC-CMP** · "Infrastructure as Code Compared + Why Terraform Is the Portable Choice" — *By the end you'll be able to translate IaC across clouds and see why Terraform travels everywhere.*

**8d · Messaging & queues (OPS-MSG)**
- **P2-OPS-MSG-AWS** · "AWS SQS & SNS Explained for Beginners" — *By the end you'll be able to decouple apps with queues and notifications on AWS.*
- **P2-OPS-MSG-AZ** · "Azure Service Bus & Event Grid Explained for Beginners" — *By the end you'll be able to connect apps with messaging on Azure.*
- **P2-OPS-MSG-GCP** · "Google Cloud Pub/Sub Explained for Beginners" — *By the end you'll be able to send and receive events at scale with Pub/Sub.*
- **P2-OPS-MSG-OCI** · "Oracle Cloud Queue & Streaming Explained for Beginners" — *By the end you'll be able to pass messages and streams in OCI.*
- **P2-OPS-MSG-ALI** · "Alibaba Cloud MNS & MQ Explained for Beginners" — *By the end you'll be able to decouple apps with Alibaba messaging.*
- **P2-OPS-MSG-CMP** · "Cloud Messaging Compared Across AWS, Azure, GCP, OCI & Alibaba" — *By the end you'll be able to translate queues and events across all five clouds.*

**8e · Cost & billing (OPS-COST)**
- **P2-OPS-COST-AWS** · "AWS Billing & Cost Explorer Explained (Set a Budget Alert)" — *By the end you'll be able to read your AWS bill and set a budget alarm.*
- **P2-OPS-COST-AZ** · "Azure Cost Management Explained for Beginners" — *By the end you'll be able to track and cap spending in Azure.*
- **P2-OPS-COST-GCP** · "Google Cloud Billing & Budgets Explained for Beginners" — *By the end you'll be able to monitor and control GCP spend.*
- **P2-OPS-COST-OCI** · "Oracle Cloud Cost Analysis & Budgets Explained" — *By the end you'll be able to track spending and set budgets in OCI.*
- **P2-OPS-COST-ALI** · "Alibaba Cloud Billing Management Explained for Beginners" — *By the end you'll be able to monitor and control Alibaba Cloud costs.*
- **P2-OPS-COST-CMP** · "Cloud Cost Tools Compared + Universal Money-Saving Habits" — *By the end you'll be able to translate cost tools and apply savings tactics on any cloud.*

**Phase 2 — 72 videos · ~720 min (12 hrs) at 10 min avg**
*(12 domains × 6 = 72; each domain = 5 providers + 1 comparison)*

---

## PHASE 3 — Apply & Advance

- **P3-PROJECT-01** · "Mini-Project: Host Your First Website on the Cloud (Same Site, 2 Clouds)" — *By the end you'll be able to deploy a static website and compare two providers.*
- **P3-PROJECT-02** · "Mini-Project: A Database-Backed App on the Cloud" — *By the end you'll be able to connect a small app to a managed database.*
- **P3-PROJECT-03** · "Mini-Project: Your First Serverless Function (Trigger to Result)" — *By the end you'll be able to build and trigger a serverless function end to end.*
- **P3-GUIDE-01** · "Which Cloud Should You Learn Deeply? An Honest Beginner's Guide" — *By the end you'll be able to choose a primary cloud based on goals, jobs, and region.*
- **P3-CERT-01** · "Cloud Certifications Decoded: AWS CCP, AZ-900, GCP Digital Leader, OCI Foundations & Alibaba ACA" — *By the end you'll be able to pick your first certification and know how to start.*
- **P3-NEXT-01** · "Where to Go Next: DevOps, Data & AI Career Paths from Cloud" — *By the end you'll be able to map your next learning path after the fundamentals.*

**Phase 3 — 6 videos · ~60 min (1 hr) at 10 min avg**

---

## Series totals

| Phase | Videos | Est. runtime (10 min avg) |
|---|---|---|
| Phase 0 — Digital & Computing Literacy | 8 | ~1.3 hrs |
| Phase 1 — Cloud + domain foundations | 24 | ~4.0 hrs |
| Phase 2 — Provider implementations (12 domains) | 72 | ~12.0 hrs |
| Phase 3 — Apply & Advance | 6 | ~1.0 hr |
| **Total** | **110** | **~18.3 hrs** (range 14.7–22 hrs at 8–12 min) |

---

## How this roadmap honors the non-negotiable principles

- **P1 Non-IT first** — Phase 0 teaches computer/internet/VM basics before "cloud" is mentioned; every Foundation video introduces an analogy before any term.
- **P2 One single spine** — strictly ordered; no "pick your provider" until Phase 3's "which cloud?" guide.
- **P3 Foundation before vendor** — every concept gets a vendor-neutral Foundation in Phase 1 before any provider builds on it (e.g., `P1-NET-F` before `P2-NET-AWS`; `P1-CPT-F` before EC2; `P1-DB-F1/F2/F3` before any managed DB).
- **P4 Category-parallel** — each Phase 2 domain runs AWS → Azure → GCP → OCI → Alibaba → Comparison (after its Phase 1 Foundation), always in that order.
- **P5 Standalone yet sequential** — each provider video recaps its Foundation ("remember subnets from P1-NET-F?") and assumes only earlier spine videos.
- **P6 Hands-on & free-tier safe** — provider videos use free-tier/always-free labs; every lab gets a cost-safety note in its full template.
- **P7 Retention-engineered** — titles pair curiosity with a searchable keyword; promises are concrete and testable.
- **P8 Portable mindset** — comparison videos frame differences as "same idea, different name/button."

---

## Next actions (change the MODE in the control panel)

- `PHASE:0` (or 1/2/3) → expand every video in a phase via the per-video template.
- `DOMAIN:Networking` (or Compute/Storage/Databases/IAM/Security/Serverless/OPS) → full templates for that domain's 5 providers + comparison (its Foundation lives in Phase 1).
- `VIDEO:P2-NET-AWS` → one complete per-video template.
- `SCRIPT:P1-NET-F` → full word-for-word narration with on-screen-text cues.
- `SEO:P2-NET-AWS` → the SEO pack only.
- `THUMBNAIL:P2-NET-AWS` → 3 thumbnail concepts.

*Recommended production order: shoot Phase 0 + Phase 1 first (they unlock everything), then run Phase 2 domain by domain in spine order.*
