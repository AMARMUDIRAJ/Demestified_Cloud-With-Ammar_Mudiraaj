# Phase 1 — Foundation Videos: Detailed Content Outlines

*The vendor-neutral `-F` videos for all 8 domains — the concepts every learner must own before any provider is named. Build these first.*

Each outline gives you: **Prereqs · Promise · Big analogy · Content to cover (timed beats) · New terms (defined) · Hands-on + cost-safety · Misconceptions/FAQ · Recap & bridge.**
House rules carried into every video: introduce the analogy **before** the term, define every term on first use, stay 100% vendor-neutral (no AWS/Azure/etc. taught here — only previewed in the bridge), provider order in bridges is always **AWS → Azure → GCP → OCI → Alibaba**.

Foundation videos in this file (16): `NET-F · CPT-F · STO-F · DB-F1 · DB-F2 · DB-F3 · IAM-F · SEC-F1 · SEC-F2 · SVR-F1 · SVR-F2 · OPS-EDGE-F · OPS-MON-F · OPS-IAC-F · OPS-MSG-F · OPS-COST-F`

---

## Domain 1 · Networking

### P1-NET-F · "What Is a Computer Network? The Apartment-Building Guide to the Cloud"

**Prereqs:** P0-NET-01/02/03 (internet, client–server, IP/DNS/ports).
**Promise:** By the end you'll be able to explain IP addresses, subnets, routing, and firewalls in plain English — the base for every cloud network.
**Big analogy:** The internet is a city. Your network is an apartment building you get to design on an empty plot. IP address = the building's street address · subnet = a floor · route table = the hallway directory · gateway = the front door to the street · firewall = the security guard with a guest list · public vs private = street-facing shops vs locked private apartments.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise: "Before you touch any cloud, you need one picture — an apartment building."
- 0:30 — Why networking comes first: every cloud service lives inside a network; VPC/VNet make no sense without this.
- 1:00 — What a network is: two or more computers that can talk. Home Wi-Fi as the simplest case.
- 2:00 — IP address = a device's address (e.g., `10.0.0.5`). Public IP (reachable from the street/internet) vs private IP (inside the building only).
- 3:30 — Subnets = dividing the building into floors; why we split (organization, isolation, control). Gentle CIDR: `/24` just means "a block of addresses on this floor" — no heavy math.
- 5:00 — Routing & route tables = the hallway directory: "to reach floor 3 go this way; for the street use the front door." Default route = "anything unknown → front door."
- 6:30 — Gateway = the door between your building and the city (internet gateway). One line on NAT: lets private apartments reach the street without exposing their own address (like a doorman posting your mail).
- 7:30 — Firewall = the guard checking a guest list by address + port (recap ports = numbered doors; 80/443 = web).
- 8:30 — The classic pattern: public subnet (web servers, has a street door) + private subnet (databases, no street door).
- 9:30 — Recap the building map; bridge.

**New terms (define each on first use):**

- Network — a group of computers that can talk to each other.
- IP address — the unique address of a device on a network.
- Public vs private IP — internet-reachable vs inside-only address.
- Subnet — a slice of a network, like a floor in a building.
- CIDR (e.g., /24) — shorthand for the size of an address block.
- Route table — the rules that decide where traffic goes.
- Gateway — the door between your network and another (or the internet).
- NAT — lets private devices reach the internet without their own public address.
- Firewall — allows or blocks traffic by address and port.
- Port — a numbered door for a kind of traffic (80/443 = web).

**Hands-on / demo (free, no account):** Draw the building live on a whiteboard slide; in a terminal run `ping example.com` and `nslookup example.com` to watch a name resolve to a real IP; show your own private IP with `ipconfig`/`ifconfig`. **Cost-safety:** $0, nothing to shut down.

**Common misconceptions / FAQ:**

- "An IP address identifies a person." No — it identifies a device/interface.
- "Private = unsafe, public = safe." It's about reachability, not safety; the firewall is what protects.
- "Subnets are only about size." They're mainly about control and isolation.

**Recap & bridge:** "Now you can picture the building. Next, AWS hands you an empty plot to build one — it's called a VPC." → P2-NET-AWS → Azure VNet → GCP VPC → OCI VCN → Alibaba VPC.

---

## Domain 2 · Compute

### P1-CPT-F · "Virtual Machines Demystified: Renting a Computer in the Sky"

**Prereqs:** P0-VIRT-01 (virtualization), P0-COMP-01 (CPU/RAM/storage).
**Promise:** By the end you'll be able to explain what a VM is, what a hypervisor does, and how to read CPU/RAM/disk choices.
**Big analogy:** A physical server is a big house. Virtualization splits it into separate apartments (VMs), each lockable and unaware of the others. The hypervisor is the building manager who divides the house and keeps tenants apart. An image is the pre-furnished starter set you move in with; an instance size is choosing studio vs 3-bedroom.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Recap from P0: one physical computer can pretend to be many.
- 1:00 — The problem VMs solve: buying a whole server is slow, costly, and mostly idle; renting a slice is fast and cheap.
- 2:00 — What a VM is: software that behaves like a real computer — its own OS, disk, network. Host (the real machine) vs guest (the VM).
- 3:00 — Hypervisor = the manager that divides the host and isolates guests. One line: Type 1 (runs on bare metal — what clouds use) vs Type 2 (runs on your laptop, e.g., VirtualBox).
- 4:00 — Anatomy of a cloud VM you'll choose: vCPU (how many "cooks"), RAM (counter space for work in progress), disk/boot volume (the drawer — links to the Storage domain), OS image (Ubuntu Linux / Windows Server), instance size family (general / compute / memory-optimized — "pick by the job").
- 6:00 — How you connect: SSH (Linux, key-based) and RDP (Windows). Key pair = a house key you never share.
- 7:00 — Lifecycle and the #1 cost lesson: launch → running (billed) → stop (compute mostly not billed, storage still is) → terminate/delete (gone).
- 8:00 — Scaling preview: vertical (bigger apartment) vs horizontal (more apartments) — sets up load balancing later.
- 8:45 — Recap; bridge.

**New terms (define each on first use):**

- Physical server / host — the real machine the VM runs on.
- Virtual machine (VM) — software that acts like a full computer.
- Guest OS — the operating system inside the VM.
- Hypervisor — software that splits one host into many isolated VMs.
- Image / template — the pre-installed starting setup for a VM.
- vCPU — a virtual processor core (processing power).
- RAM / memory — fast working space for running programs.
- Instance type / VM size — a named bundle of CPU+RAM for a use case.
- SSH / RDP — secure ways to log into a Linux/Windows VM remotely.
- Key pair — public/private keys used to log in safely without a password.
- Stop vs terminate — pause (restartable) vs delete permanently.

**Hands-on / demo (free-tier):** Concept video — preview the launch screen where you pick size/image. **Cost-safety (drill it):** running = paying; stop or terminate when done; delete the disk too. This rule repeats in every provider video.

**Common misconceptions / FAQ:**

- "A VM is slow or fake." Modern VMs run near-native speed; it's a real, isolated computer.
- "Stopping a VM stops all charges." Compute stops, but the attached disk usually still costs.
- "Bigger is always better." Right-size; you can resize later.

**Recap & bridge:** "Same idea, five names. AWS calls it EC2…" → P2-CPT-AWS (EC2) → Azure VMs → Compute Engine → OCI Compute → Alibaba ECS.

---

## Domain 3 · Storage

### P1-STO-F · "Object vs Block vs File Storage — The 3 Ways the Cloud Keeps Data"

**Prereqs:** P1-CPT-F (VMs have disks), P0-FILE-01 (files/folders).
**Promise:** By the end you'll be able to tell object, block, and file storage apart and pick the right one.
**Big analogy:** Block storage = a blank hard drive you bolt into one machine (raw, fast). File storage = a shared office filing cabinet many people open at once (folders + files). Object storage = a giant valet warehouse: you hand over a whole item plus a claim ticket (key) and a label (metadata); accessed over the web, not mounted like a drive; effectively unlimited.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Why three types exist: different jobs need different shapes of storage.
- 1:30 — Block storage: a raw virtual disk attached to a VM; you format it and it becomes the VM's drive. Fast, usually one VM at a time. Use: OS disk, databases. (Ties to CPT-F boot volume.)
- 3:30 — File storage: a shared file system (folders/files) many machines mount over the network. One line on NFS/SMB = the "languages" they speak. Use: shared documents, team apps.
- 5:30 — Object storage (the cloud star): store whole objects (a photo, a backup), each with a unique key + metadata, in a flat space called a bucket/container. Folders are just a naming illusion. Accessed via web requests/URLs. Practically unlimited, cheap, durable. Use: website assets, backups, big data, media.
- 7:30 — Durability (many copies, so data is (almost) never lost) vs availability (reachable when needed). Storage tiers preview: hot vs cold/archive = front shelf vs deep warehouse.
- 8:30 — Decision guide: one server needs a drive → block; shared drive → file; storing many whole files for apps/web/backup → object.
- 9:15 — Recap; bridge.

**New terms (define each on first use):**

- Block storage — a raw virtual disk you attach to a VM.
- File system — how a disk organizes files so an OS can use it.
- File storage — a shared folder-and-file system multiple machines mount.
- NFS / SMB — protocols (languages) for shared file access.
- Object — a whole file plus its metadata, stored as one unit.
- Key — the unique name/address of an object.
- Metadata — extra labels describing the object.
- Bucket / container — the top-level place objects live.
- Durability — how safely data is kept (number of copies).
- Availability — how reliably you can reach it.
- Storage class / tier — a price/speed level (hot vs cold/archive).

**Hands-on / demo:** Show a public bucket URL serving an image vs a VM disk in the console. **Cost-safety:** object storage free tier is small; delete demo buckets when done.

**Common misconceptions / FAQ:**

- "Object storage has real folders." It's flat; folders are a naming illusion.
- "Object storage is just a cloud hard drive." You can't mount it like a drive; it's accessed over the web.
- "One type is best." Each fits a different job.

**Recap & bridge:** "Every cloud offers all three. AWS calls them S3, EBS, and EFS…" → P2-STO-AWS → Azure (Blob/Disks/Files) → GCP (Cloud Storage/Persistent Disk/Filestore) → OCI (Object/Block/File) → Alibaba (OSS/Cloud Disk/NAS).

---

## Domain 4 · Databases

### P1-DB-F1 · "What Is a Database? From Spreadsheets to Superpowers"

**Prereqs:** P1-STO-F (data must live somewhere), P0-FILE-01.
**Promise:** By the end you'll be able to explain what a database is, why apps need one, and how it beats a pile of files or spreadsheets.
**Big analogy:** A database is a super-organized librarian + library — not just shelves (storage) but a system that finds, updates, and protects books instantly and lets many people read at once without chaos. A spreadsheet is a notebook; a database is the whole library with a catalog.

**Content to cover (≈8–10 min):**

- 0:00 — Hook + promise.
- 0:30 — Start from the familiar: a spreadsheet (rows, columns). It works… until many users, lots of data, and a need for reliability.
- 2:00 — What a database adds over files/spreadsheets: fast search (indexes = the library catalog), many users at once (concurrency), rules that keep data correct, protection against half-finished changes.
- 4:00 — The two core jobs: store data + answer questions about it (queries). A query is just a question you ask the data.
- 5:00 — Database vs DBMS: the data vs the software that runs it (MySQL, PostgreSQL — named only, as "popular engines").
- 6:00 — Where databases run: on a VM you manage vs a managed cloud database (provider runs it for you) — previews the provider videos.
- 7:00 — Tiny taxonomy seed (detail in F2/F3): relational (tables) vs non-relational (NoSQL).
- 7:45 — Recap; bridge to F2.

**New terms (define each on first use):**

- Database — an organized system for storing and retrieving data.
- DBMS — the software that runs a database (e.g., MySQL, PostgreSQL).
- Record / row — one entry (e.g., a customer).
- Field / column — one attribute (e.g., email).
- Query — a question you ask the database.
- Index — a lookup structure that makes searches fast.
- Concurrency — many users reading/writing safely at once.
- Managed database — a database the cloud provider operates for you.

**Hands-on / demo:** Show a spreadsheet, then the same data in a simple table view. No cost.

**Common misconceptions / FAQ:**

- "A spreadsheet is a database." It's a stepping stone; databases add scale, rules, concurrency.
- "Databases are only for programmers." Anyone can understand the model; querying is learnable.

**Recap & bridge:** "Most business data lives in tables with strict rules — the relational model. That's next." → P1-DB-F2.

### P1-DB-F2 · "Relational Databases & SQL Explained (Tables, Rows & ACID)"

**Prereqs:** P1-DB-F1.
**Promise:** By the end you'll be able to read a simple table design, explain what SQL is, and what ACID guarantees.
**Big analogy:** A relational database is a set of linked spreadsheets that reference each other by ID — like a school where Students, Classes, and Teachers are separate lists connected by ID numbers, so nothing is duplicated and everything stays consistent.

**Content to cover (≈10–12 min):**

- 0:00 — Hook + promise.
- 0:30 — Tables = spreadsheets with strict columns (a schema). Row = a record; column = a field; each table has a primary key (unique ID).
- 2:30 — Relationships: a foreign key points to another table's primary key. Orders → Customers, so customer details aren't repeated on every order.
- 4:30 — Normalization in plain English: store each fact once and link to it. Goal (less duplication, fewer mistakes), not formal normal forms.
- 6:00 — SQL = the language to ask and change. Four verbs in words: SELECT (read), INSERT (add), UPDATE (change), DELETE (remove). One readable SELECT on screen.
- 8:00 — ACID = four promises for money-grade data: Atomicity (all-or-nothing), Consistency (rules always hold), Isolation (simultaneous actions don't corrupt), Durability (saved stays saved). Analogy: a bank transfer.
- 10:00 — When relational shines (structured data, relationships, transactions: banking, orders, inventory) vs strains (massive scale or messy shapes → NoSQL).
- 11:00 — Recap; bridge to F3.

**New terms (define each on first use):**

- Relational database — data stored in linked tables.
- Schema — the defined structure (tables/columns/types).
- Primary key — the unique ID of a row.
- Foreign key — a link to another table's primary key.
- Normalization — organizing data to avoid duplication.
- SQL — the language used to query/change relational data.
- Transaction — a group of changes treated as one unit.
- ACID — Atomicity, Consistency, Isolation, Durability guarantees.

**Hands-on / demo (free):** A no-install browser SQL playground (e.g., an online SQLite) to run one SELECT. No account, no cost.

**Common misconceptions / FAQ:**

- "SQL is a database." SQL is the language; the database is the system.
- "Normalization is always best." Mostly — but we sometimes denormalize for speed.
- "ACID is everywhere automatically." It's a relational strength; many NoSQL stores trade some of it for scale.

**Recap & bridge:** "But not all data fits neat tables. Enter NoSQL and caching." → P1-DB-F3.

### P1-DB-F3 · "NoSQL, Semi-Structured Data & Caching Explained Simply"

**Prereqs:** P1-DB-F2.
**Promise:** By the end you'll be able to tell relational vs NoSQL apart, recognize the NoSQL families, and explain caching.
**Big analogy:** If relational is a rigid filing system with identical forms, NoSQL is a flexible box of sticky notes, folders, and tags — each item can look a bit different. Caching = keeping your most-used items on your desk instead of walking to the warehouse every time.

**Content to cover (≈10–12 min):**

- 0:00 — Hook + promise.
- 0:30 — Why NoSQL exists: web-scale volume, fast-changing/flexible data, need to scale out (horizontally).
- 1:30 — Structured vs semi-structured vs unstructured (one line each): tables vs JSON-like flexible records vs raw files.
- 3:00 — The NoSQL families, each "what + when + example": key-value (a giant dictionary — sessions, carts), document (JSON-like flexible records — catalogs, profiles), wide-column (huge flexible-column tables — time-series, IoT), graph (entities + relationships — social, recommendations).
- 6:30 — Honest trade-off: NoSQL gains flexibility/scale, often relaxes strict ACID to eventual consistency (copies agree shortly, not instantly).
- 8:00 — Show a tiny JSON record vs a table row so the difference is visible.
- 9:00 — Caching & in-memory stores: keep hot data in RAM (Redis/Memcached, named) for millisecond reads; it's a speed layer in front of a database, not the source of truth. One friendly line on cache invalidation ("knowing when the desk copy is stale").
- 10:30 — Decision recap: relational for relationships+transactions; key-value/document/wide-column/graph for scale+flexibility; cache for speed.
- 11:15 — Recap; bridge to provider DB videos.

**New terms (define each on first use):**

- NoSQL — non-relational databases built for flexibility/scale.
- Semi-structured data / JSON — flexible records without a rigid schema.
- Key-value store — data as simple key→value pairs.
- Document database — stores flexible JSON-like documents.
- Wide-column store — massive, flexible-column tables for scale.
- Graph database — stores entities and their relationships.
- Eventual consistency — copies agree shortly after a change, not instantly.
- In-memory cache — a fast RAM-based store for hot data (e.g., Redis).

**Hands-on / demo:** Show a JSON document beside a SQL row; optional free Redis playground. No cost.

**Common misconceptions / FAQ:**

- "NoSQL means anti-SQL." It means "not only SQL"; many support query languages.
- "NoSQL is always faster/better." Only for the right shape of problem.
- "A cache is a database." It's a speed layer; data can vanish — keep the real DB as source of truth.

**Recap & bridge:** "Now you know the data shapes. Let's see each provider's managed databases — AWS RDS, DynamoDB, and ElastiCache first." → P2-DB-AWS → Azure → GCP → OCI → Alibaba.

---

## Domain 5 · Identity & Access (IAM)

### P1-IAM-F · "Authentication vs Authorization: Who Are You, and What Can You Do?"

**Prereqs:** P1-SHARED-01 (shared responsibility model).
**Promise:** By the end you'll be able to explain users, groups, roles, and policies — and the difference between proving who you are and what you're allowed to do.
**Big analogy:** A hotel. Authentication = checking in and proving you're you (ID + key card). Authorization = what your key card opens (your room and the gym, but not other rooms or the staff office). A policy = the rules programmed onto the card. A role = a temporary staff badge anyone on shift can wear to do a job.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — The two questions every system asks: "Who are you?" (authN) and "What can you do?" (authZ). Don't confuse them.
- 2:00 — Authentication methods: password, MFA (a second proof via phone/app = two locks on the door), access keys for programs. Strongly recommend MFA.
- 4:00 — Identities: user (a person), group (users sharing permissions), service/role identity (for machines/apps).
- 5:30 — Authorization: a policy is a written rule — "this identity can/can't do this action on this resource." Allow vs deny.
- 7:00 — Least privilege: grant only what's needed. Why it matters (blast radius if a key leaks). The "don't use the root/admin account daily" rule.
- 8:00 — Roles vs users (key cloud idea): a role is permissions you temporarily assume — no long-lived password; ideal for apps and cross-account access.
- 9:00 — Recap; bridge (and flag the coming naming differences).

**New terms (define each on first use):**

- Authentication (authN) — proving who you are.
- Authorization (authZ) — what you're allowed to do.
- MFA — a second proof of identity beyond a password.
- User — an identity for a person.
- Group — a set of users sharing permissions.
- Role — a temporary set of permissions an identity can assume.
- Policy — the written rules that allow/deny actions.
- Least privilege — granting only the access actually needed.
- Root/admin account — the all-powerful first account (protect it).

**Hands-on / demo:** Concept video — show a policy in plain, readable form (who / can do what / to which resource). No cost.

**Common misconceptions / FAQ:**

- "AuthN and authZ are the same." One is identity, one is permission.
- "Admins should use the root account daily." No — create limited users; reserve root for emergencies.
- "More permissions = fewer problems." The opposite — least privilege reduces risk.

**Recap & bridge:** "Every cloud has its own identity system, with different names. AWS calls it IAM; Azure uses Microsoft Entra ID (formerly Azure AD)…" → P2-IAM-AWS → Azure (Entra ID + RBAC) → GCP (Cloud IAM) → OCI (IAM + compartments) → Alibaba (RAM).

---

## Domain 6 · Security & Encryption

### P1-SEC-F1 · "Encryption Explained: Locking Your Data at Rest and in Transit"

**Prereqs:** P1-IAM-F (keys & identity), P0-NET (data in transit).
**Promise:** By the end you'll be able to explain encryption, the difference between at-rest and in-transit, and what a key does.
**Big analogy:** Encryption = a locked diary; the key turns the words into gibberish for anyone without it. In transit = an armored truck moving cash between banks (HTTPS). At rest = a safe in the vault (encrypted disk). Key management = who holds the keys and where.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Why encryption: even if data is stolen, it's useless without the key.
- 1:30 — Plaintext vs ciphertext (readable vs scrambled). The key converts between them.
- 3:00 — Two moments to protect data: in transit (data moving over networks → TLS/HTTPS, the browser padlock) and at rest (data on disk/in storage → disk/bucket/database encryption).
- 5:00 — Symmetric vs asymmetric in plain terms: one shared key (fast, for bulk data) vs a key pair (public locks, private unlocks — used in HTTPS handshakes and SSH).
- 7:00 — Key management is the real job: generate, store, rotate, and restrict access to keys. Bad: keys in code. Good: a key vault/KMS (previews provider services). Provider-managed vs customer-managed keys (one line).
- 8:30 — Tie back to IAM: only the right identities may use a key (authZ from the last domain).
- 9:15 — Recap; bridge to F2.

**New terms (define each on first use):**

- Encryption — scrambling data so only a key can read it.
- Plaintext / ciphertext — readable vs scrambled data.
- Key — the secret that locks/unlocks data.
- Encryption in transit — protecting data while it moves (TLS/HTTPS).
- Encryption at rest — protecting stored data (disks, buckets, DBs).
- Symmetric / asymmetric — one shared key vs a public/private key pair.
- Key management / KMS — securely creating, storing, controlling keys.
- Key rotation — regularly replacing keys to limit risk.

**Hands-on / demo (free):** Click the browser padlock to view the TLS certificate; compare `https` vs `http`. No cost.

**Common misconceptions / FAQ:**

- "Encryption makes me fully secure." It's one layer; you still need IAM, firewalls, patching.
- "The cloud can read my encrypted data." With customer-managed keys, you control access.
- "Encryption slows everything down." Modern hardware makes it nearly free.

**Recap & bridge:** "Locking data is half of security. The other half is controlling traffic — firewalls and security groups." → P1-SEC-F2.

### P1-SEC-F2 · "Firewalls & Security Groups: The Cloud's Bouncers Explained"

**Prereqs:** P1-NET-F (subnets/ports), P1-SEC-F1.
**Promise:** By the end you'll be able to explain how cloud firewalls decide what traffic to allow, and the layers of network defense.
**Big analogy:** A nightclub with two checkpoints. The security group = a personal bodyguard at each VM's door (checks every guest in/out and remembers who's allowed). The network ACL = the bouncer at the building entrance for a whole subnet (broad guest list, doesn't remember individuals). Together = layered defense.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Recap ports/IP from NET-F (doors and addresses).
- 1:30 — What a firewall does: allow/deny by source, destination, port, protocol. Default-deny mindset: block everything, open only what's needed.
- 3:30 — Two cloud layers: instance-level security group (wraps each VM; stateful = remembers a request so its reply is auto-allowed; usually allow-rules only) vs subnet-level network ACL (wraps a subnet; stateless = checks every packet both ways; supports allow and deny).
- 6:00 — Inbound vs outbound rules: who can reach you vs where you can reach out. Example: allow inbound 443 from anywhere; restrict SSH (22) to your own IP only.
- 7:30 — Defense in depth: combine private subnets (NET-F) + security groups + ACLs + encryption (SEC-F1) + IAM. No single wall is enough.
- 8:30 — Common beginner mistakes: opening SSH/RDP to `0.0.0.0/0`; leaving databases on public subnets — and how to avoid them.
- 9:15 — Recap; bridge.

**New terms (define each on first use):**

- Firewall — rules that allow/deny network traffic.
- Security group — a stateful firewall attached to a VM/instance.
- Network ACL — a stateless firewall attached to a subnet.
- Stateful vs stateless — remembers a connection vs checks each packet fresh.
- Inbound / outbound rules — control traffic coming in vs going out.
- Default-deny — block all, then allow only what's needed.
- Defense in depth — multiple security layers stacked.

**Hands-on / demo:** Walk a rule-builder UI conceptually; show an example rule set. **Cost-safety:** never leave SSH/RDP open to the world. No cost.

**Common misconceptions / FAQ:**

- "One firewall rule is enough." Layer instance + subnet + identity.
- "Security groups and network ACLs are the same." Stateful vs stateless; instance vs subnet.
- "Outbound traffic doesn't matter." It does — it limits what a compromised box can reach.

**Recap & bridge:** "Now let's see how each cloud implements keys and firewalls — AWS KMS and Security Groups first." → P2-SEC-AWS → Azure → GCP → OCI → Alibaba.

---

## Domain 7 · Serverless & Containers

### P1-SVR-F1 · "Containers vs Virtual Machines: What's the Difference? (Lunchbox Analogy)"

**Prereqs:** P1-CPT-F (VMs), P0-OS-01.
**Promise:** By the end you'll be able to explain what a container is, how it differs from a VM, and why developers love them.
**Big analogy:** A VM is a full house (its own kitchen, plumbing, whole OS) — heavy. A container is a lunchbox: it packs just your meal (your app + exactly what it needs) and shares the building's kitchen (the host OS). Lightweight, portable, starts in seconds. An image = the recipe; a container = the cooked meal.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Recap VM: a full OS per VM = heavier, slower to start.
- 1:30 — The problem containers solve: "it works on my machine." Containers package the app + its dependencies so it runs the same anywhere.
- 3:30 — How they differ from VMs: containers share the host OS kernel (no full guest OS each), so they're smaller (MBs not GBs) and start in seconds. Diagram: VMs (each with an OS) vs containers (sharing the OS).
- 5:30 — Recipe terms: image (read-only blueprint), container (a running instance of an image), Docker (common tool to build/run them), registry (the app store/shelf for images).
- 7:00 — Why teams use them: consistency (dev = test = prod), portability (move between clouds — supports the portable mindset), efficiency (pack more per server), speed.
- 8:00 — When a VM is still better (one line): full OS isolation or a different kernel.
- 8:30 — Tease the next problem: one container is easy; hundreds across many servers need a manager → orchestration.
- 9:15 — Recap; bridge to F2.

**New terms (define each on first use):**

- Container — a lightweight package of an app + its dependencies.
- Image — the read-only template a container is created from.
- Docker — a popular tool to build and run containers.
- Registry — a store for container images (e.g., Docker Hub).
- Host OS / kernel — the shared operating system containers use.
- Dependency — the libraries/tools an app needs to run.

**Hands-on / demo (free, optional):** Show `docker run hello-world` output via an in-browser playground (no install). No cost.

**Common misconceptions / FAQ:**

- "A container is a small VM." No — it shares the host OS; a different mechanism.
- "Containers replace VMs entirely." They often run on top of VMs; both have roles.
- "Containers are only for big tech." Useful at any size for consistency.

**Recap & bridge:** "Hundreds of containers need a conductor — that's Kubernetes — and 'serverless' goes even further." → P1-SVR-F2.

### P1-SVR-F2 · "Serverless & Kubernetes Explained: Code Without Managing Servers"

**Prereqs:** P1-SVR-F1.
**Promise:** By the end you'll be able to explain event-driven/serverless (FaaS) and what Kubernetes orchestrates.
**Big analogy:** Serverless/FaaS = a vending machine for code: drop in a trigger, your function runs, you pay per use, no machine to babysit (there are servers — you just don't manage them). Kubernetes = an air-traffic controller for containers: it places them, restarts crashed ones, scales up/down, and keeps the desired number running.

**Content to cover (≈10–12 min):**

- 0:00 — Hook + promise.
- 0:30 — Recap: containers are great, but who starts/stops/heals them at scale?
- 1:30 — Orchestration & Kubernetes in plain words: cluster (the orchestra), node (a worker machine), pod (the smallest run unit — one or a few containers), desired state ("keep 3 copies running"), self-healing (restarts failures), autoscaling (adds copies under load). Conceptual only — no YAML.
- 5:00 — Why managed Kubernetes exists: running it yourself is hard, so clouds offer managed control planes (previews EKS/AKS/GKE/OKE/ACK).
- 6:00 — Serverless = the next step in "less to manage": FaaS (small functions that run on an event, scale to zero when idle, pay per execution; triggers = file upload, HTTP request, schedule) and container-serverless (run a container without managing servers).
- 8:30 — The management spectrum (great recap visual): On-prem → VMs → Containers → Kubernetes → Serverless = progressively less to manage, more focus on code.
- 9:30 — Trade-offs: serverless = no ops + cheap idle, but cold starts and limits; Kubernetes = powerful + portable, but complex. Choose by the job.
- 10:30 — Recap; bridge.

**New terms (define each on first use):**

- Orchestration — automatically managing many containers.
- Kubernetes (K8s) — the standard container orchestrator.
- Cluster / node / pod — the orchestra / a worker machine / the smallest run unit.
- Desired state — the config you declare; Kubernetes maintains it.
- Autoscaling / self-healing — add capacity on load / restart failures.
- Serverless — running code without managing servers.
- FaaS (Functions as a Service) — small functions that run on events.
- Trigger / event — the thing that starts a function.
- Cold start — first-run delay when a function spins up.
- Scale to zero — uses (and costs) nothing when idle.

**Hands-on / demo:** Concept diagrams; optional — show a tiny function in a console editor that returns "hello." **Cost-safety:** serverless free tiers are generous; still set a budget.

**Common misconceptions / FAQ:**

- "Serverless means no servers." There are servers; you just don't manage them.
- "Kubernetes and serverless compete." They're points on a spectrum; many apps use both.
- "Serverless is always cheapest." Great for spiky/low traffic; steady heavy loads can be cheaper on VMs/containers.

**Recap & bridge:** "Let's see each cloud's functions and managed Kubernetes — AWS Lambda, ECS, and EKS first." → P2-SVR-AWS → Azure → GCP → OCI → Alibaba.

---

## Domain 8 · Edge, Operations & Cost

### P1-OPS-EDGE-F · "Load Balancers, DNS & CDNs: How Big Websites Stay Fast & Online"

**Prereqs:** P1-NET-F, P1-CPT-F, P0-NET-03 (DNS).
**Promise:** By the end you'll be able to explain how traffic gets distributed, named, and cached worldwide.
**Big analogy:** A popular restaurant chain. Load balancer = the host who spreads diners across many identical kitchens so none is overwhelmed. DNS = the phone book/GPS that turns the name into an address. CDN = local branches in every city so customers don't travel to headquarters for every meal.

**Content to cover (≈10–12 min):**

- 0:00 — Hook + promise.
- 0:30 — The scaling problem: one server can't serve millions. Recap horizontal scaling from CPT-F (many copies).
- 1:30 — Load balancing: one front door that spreads requests across many backend servers; health checks skip dead servers; enables zero-downtime and scaling. One line: Layer 4 (by address/port) vs Layer 7 (by content, like URL path).
- 4:30 — DNS beyond P0: turns names into IPs, and can route users to the nearest region and fail over. Records: A (name→IP), CNAME (alias).
- 6:30 — CDN: caches copies of your content at edge locations near users → faster loads, less origin load, absorbs spikes. Static vs dynamic content (one line). Cache hit vs miss.
- 8:30 — How they work together: user → DNS finds the nearest edge → CDN serves cached content, or → load balancer → a healthy server. One clean diagram.
- 10:00 — What this unlocks: high availability, failover, global reach (ties to P1-GEO regions/AZs).
- 10:45 — Recap; bridge.

**New terms (define each on first use):**

- Load balancer — distributes traffic across multiple servers.
- Health check — a test that skips unhealthy servers.
- Layer 4 / Layer 7 — balancing by network info vs by content (URL).
- DNS record (A / CNAME) — name→IP / alias to another name.
- Failover — automatic switch to a healthy backup.
- CDN — a network of edge caches near users.
- Edge location / PoP — a nearby site serving cached content.
- Cache hit / miss — content found at the edge vs fetched from the origin.
- Origin — your source server the CDN pulls from.

**Hands-on / demo (free):** Run `nslookup`/`dig` on a big site to see multiple IPs; use browser dev tools to spot a CDN in the response headers. No cost.

**Common misconceptions / FAQ:**

- "A load balancer is software I install on each server." It's a front-door service across servers.
- "DNS is only for websites." It's for any named resource and can route smartly.
- "A CDN is only for big companies." Free/cheap tiers make it useful for anyone.

**Recap & bridge:** "Each cloud bundles these. AWS = ELB, Route 53, CloudFront…" → P2-OPS-EDGE-AWS → Azure (Load Balancer/DNS/Front Door) → GCP → OCI → Alibaba (ALB-NLB/DNS/CDN).

### P1-OPS-MON-F · "Monitoring, Metrics & Logs: How to Know If Your Cloud Is Healthy"

**Prereqs:** P1-CPT-F, P1-NET-F.
**Promise:** By the end you'll be able to explain metrics, logs, traces, and alerts — how you see what your cloud is doing.
**Big analogy:** Your cloud is a car. Metrics = the dashboard gauges (speed, fuel, temperature — numbers over time). Logs = the detailed trip diary (what happened and when). Alerts = the warning light + a call to your phone. Dashboards = the whole instrument cluster on one screen.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — Why monitoring: you can't fix what you can't see; catch problems before users do; control cost.
- 1:30 — The three pillars: metrics (numbers over time — CPU %, requests/sec, errors), logs (timestamped event records — "what exactly happened"), traces (one line: follow one request across services).
- 4:30 — Alerts & thresholds: "tell me when CPU > 80% for 5 min." Avoid alert fatigue (alert only on what matters). Notification channels (email/SMS/chat).
- 6:00 — Dashboards: turn metrics/logs into a glanceable picture.
- 7:00 — What beginners should watch first: CPU/memory, disk, error rate, latency, and billing/cost (ties forward to COST-F).
- 8:00 — Health checks & uptime recap (links to load balancer health checks).
- 8:45 — Log hygiene: centralize logs and set retention (don't keep forever = cost).
- 9:15 — Recap; bridge.

**New terms (define each on first use):**

- Monitoring — watching system health over time.
- Observability — understanding internal state from outputs.
- Metric — a number measured over time.
- Log — a timestamped record of an event.
- Trace — the path of one request across services.
- Alert / threshold — a rule that notifies you on a condition.
- Dashboard — a visual summary of metrics/logs.
- Latency — how long a request takes.
- Retention — how long you keep logs/metrics.

**Hands-on / demo:** Show a sample dashboard; set one example alert rule (concept). **Cost-safety:** log retention costs money — set sensible limits.

**Common misconceptions / FAQ:**

- "Logs and metrics are the same." Text events vs numeric trends.
- "Alert on everything." That causes fatigue; alert on user-impacting signals.
- "Monitoring is only for outages." It also guides scaling and cost.

**Recap & bridge:** "Each cloud has its own observability hub. AWS = CloudWatch…" → P2-OPS-MON-AWS → Azure Monitor → GCP (Cloud Monitoring/Logging) → OCI → Alibaba CloudMonitor.

### P1-OPS-IAC-F · "Infrastructure as Code Explained: Build Your Cloud from a Recipe"

**Prereqs:** P1-NET-F, P1-CPT-F, P1-IAM-F (you're provisioning real resources).
**Promise:** By the end you'll be able to explain why teams define infrastructure in files instead of clicking, and the core IaC ideas.
**Big analogy:** Clicking in the console = cooking from memory (works once, hard to repeat, easy to forget a step). IaC = writing the recipe down so anyone can recreate the exact same dish, every time, in any kitchen — and the recipe is version-controlled like a shared, edit-tracked cookbook.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — The pain of "ClickOps": manual setup is slow, error-prone, undocumented, and drifts across dev/test/prod.
- 2:00 — What IaC is: describe your infrastructure (networks, VMs, databases) in text files; a tool reads them and builds it.
- 3:30 — Declarative vs imperative (one line): say what you want (end state) vs script every step. Most IaC is declarative.
- 4:30 — Benefits: repeatable, version-controlled (history + rollback), reviewable, automatable (CI/CD preview), self-documenting.
- 6:00 — Key concepts: template/config (the recipe), state (the tool's memory of what it built), plan/preview (see changes before applying), idempotency (running twice converges to the same result, no duplicates).
- 8:00 — The portability point: provider-native tools (CloudFormation, ARM/Bicep, etc.) vs Terraform, which works across all clouds with one language — the portable skill. (Sets up the comparison video.)
- 9:00 — Recap; bridge.

**New terms (define each on first use):**

- Infrastructure as Code (IaC) — defining infrastructure in text files.
- Declarative — describe the desired end state, not the steps.
- Template / configuration — the file describing resources.
- State — the tool's record of what currently exists.
- Plan / preview — a dry run showing what will change.
- Idempotency — repeating the action yields the same result.
- Version control (Git) — tracking changes to files over time.
- Terraform — a cross-cloud IaC tool (portable).

**Hands-on / demo (free):** Show a ~10-line template defining one VM/bucket and a plan/preview output (read-only). **Cost-safety:** a preview/plan creates nothing; only "apply" does — and delete afterward.

**Common misconceptions / FAQ:**

- "IaC is only for big teams." Even solo learners benefit — repeatable and easy to delete.
- "It's just scripting." Declarative IaC manages state and convergence, not step-by-step scripts.
- "One cloud's template works everywhere." Native ones don't; Terraform is the portable choice.

**Recap & bridge:** "Let's see each cloud's native tool — AWS CloudFormation first — then why Terraform travels everywhere." → P2-OPS-IAC-AWS → Azure (ARM/Bicep) → GCP (Infrastructure Manager/Terraform) → OCI (Resource Manager) → Alibaba (ROS).

### P1-OPS-MSG-F · "Message Queues & Events: How Cloud Apps Talk Without Crashing"

**Prereqs:** P1-CPT-F, P1-SVR-F2 (event-driven).
**Promise:** By the end you'll be able to explain why apps use queues and events, and the publish/subscribe pattern.
**Big analogy:** A busy restaurant kitchen. Without a queue, waiters shout orders at cooks — chaos, dropped orders. A message queue = the order-ticket rail: waiters clip tickets, cooks take them when ready. Floor and kitchen are decoupled — if cooks slow down, tickets wait safely. Pub/Sub = a notice board where one announcement reaches every subscriber who cares.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise.
- 0:30 — The problem: if service A calls service B directly and B is slow/down, A breaks too (tight coupling); spikes overwhelm.
- 2:00 — Decoupling: put a buffer between sender and receiver so they don't depend on each other's timing — reliability + spike smoothing.
- 3:30 — Message queue (point-to-point): a producer puts a message in; one consumer pulls it out; the queue holds it safely meanwhile. Scale workers to drain a backlog. Example: order processing, image resizing.
- 6:00 — Publish/Subscribe (fan-out): a publisher emits an event to a topic; many subscribers each get a copy. Example: "order placed" → email + inventory + analytics all react.
- 7:30 — Key terms: producer/consumer, topic/subscription, at-least-once delivery (a message may arrive more than once → design idempotent consumers, recalling idempotency from IaC), dead-letter queue (where unprocessable messages go).
- 8:45 — Why it matters: this is the backbone of event-driven and serverless architectures (ties to SVR-F2 triggers).
- 9:15 — Recap; bridge.

**New terms (define each on first use):**

- Message — a small packet of data passed between apps.
- Queue — a buffer holding messages for one consumer.
- Producer / consumer — sender of messages / receiver that processes them.
- Publish/Subscribe (Pub/Sub) — one publisher, many subscribers via a topic.
- Topic / subscription — the channel / a listener's registration to it.
- Decoupling — letting services work independently of each other's timing.
- At-least-once delivery — a message may be delivered more than once.
- Dead-letter queue — a holding place for messages that can't be processed.

**Hands-on / demo:** Diagram waiter → ticket rail → cook; optional — create a queue and send one test message in a console. **Cost-safety:** delete demo queues/topics.

**Common misconceptions / FAQ:**

- "Queues slow things down." A tiny hop, but a big gain in reliability/scale.
- "A message is delivered exactly once." Often at-least-once; design idempotent consumers.
- "Pub/Sub and queues are the same." One-to-one vs one-to-many.

**Recap & bridge:** "Each cloud names these differently — AWS SQS and SNS first." → P2-OPS-MSG-AWS → Azure (Service Bus/Event Grid) → GCP (Pub/Sub) → OCI (Queue/Streaming) → Alibaba (MNS/MQ).

### P1-OPS-COST-F · "Cloud Billing & Cost Control: How Not to Get a Surprise Bill"

**Prereqs:** P1-ECON-01 (CapEx/OpEx), P1-CPT-F (stop vs terminate).
**Promise:** By the end you'll be able to explain cloud pricing models and the habits that keep your bill small.
**Big analogy:** The cloud is a utility meter (electricity/water): you pay for what you use, and a tap left running costs money all month. A budget alert = a smart meter that texts you before the bill explodes.

**Content to cover (≈9–11 min):**

- 0:00 — Hook + promise (reassure: free tiers exist; we'll stay safe).
- 0:30 — Recap pay-as-you-go vs buying hardware (P1-ECON). The meter mindset.
- 1:30 — What you actually pay for: compute (per second/hour running), storage (per GB-month), data transfer/egress (the sneaky one — moving data OUT costs), requests/operations.
- 3:30 — Pricing models: on-demand (flexible, priciest), reserved/savings plans (commit 1–3 yrs, cheaper), spot/preemptible (cheap spare capacity, can be reclaimed), free tier (always-free + 12-month + trials). When each fits.
- 6:00 — Top beginner cost traps & fixes: idle running VMs → stop/terminate (recap CPT-F); orphaned storage/disks/IPs after deleting a VM → clean up; NAT gateways / load balancers left on → delete demos; data-egress surprises → check before bulk downloads.
- 7:30 — Control tools every cloud has: budgets + alerts, cost dashboards, tagging (label resources by project to see who spends what), right-sizing.
- 8:30 — The golden-rules checklist: set a budget alert on day one; tag everything; delete demos the same day; prefer free tier for learning; review the bill weekly.
- 9:15 — Recap; bridge.

**New terms (define each on first use):**

- Pay-as-you-go / on-demand — pay for what you use, no commitment.
- Reserved / savings plan — commit for a lower rate.
- Spot / preemptible — cheap, interruptible spare capacity.
- Free tier — always-free + time-limited free allowances.
- Egress — data transfer out (commonly billed).
- Budget alert — a notification when spend nears a limit.
- Tagging — labeling resources to track cost/ownership.
- Right-sizing — matching resource size to actual need.

**Hands-on / demo (free):** Walk through setting a budget alert (each provider video does it for real). **Cost-safety:** this video IS the cost-safety backbone for the whole series.

**Common misconceptions / FAQ:**

- "Free tier means everything is free." Only specific services/limits; overages bill.
- "A stopped VM costs nothing." Storage/IPs may still bill.
- "Egress is free." Inbound usually is; outbound usually isn't.

**Recap & bridge:** "Let's set real budget alerts in each cloud — AWS Cost Explorer and Budgets first." → P2-OPS-COST-AWS → Azure (Cost Management) → GCP (Billing/Budgets) → OCI (Cost Analysis) → Alibaba (Billing Management).

---

## How to use these outlines

- **Build order:** follow them top to bottom — each foundation assumes the earlier ones (e.g., SEC-F2 leans on NET-F; OPS-MSG-F leans on SVR-F2). This is the spine.
- **Per video, you already have:** the promise, the one big analogy, a timed beat sheet, the exact terms to define (nothing is used before it's taught), a free/cost-safe demo, FAQs, and the bridge into the five provider videos.
- **Next steps (change MODE in the control panel):**
  - `SCRIPT:P1-NET-F` → full word-for-word narration with `[on-screen text]` cues for any outline above.
  - `VIDEO:P2-NET-AWS` → the first provider video built on its foundation.
  - `THUMBNAIL:P1-STO-F` or `SEO:P1-DB-F2` → thumbnail concepts / SEO pack for any video.
- **Want Phase 0 and the 8 cloud-basics videos at this depth too?** Those are the series' earliest groundwork (computers, internet, OS, the cloud, IaaS/PaaS/SaaS, regions, shared responsibility, economics). Say the word and I'll expand them in the same format.
