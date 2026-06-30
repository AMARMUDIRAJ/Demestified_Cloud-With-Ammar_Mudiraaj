# Start Here 👋

Welcome. This is a **single, ordered learning path** — not a pick‑your‑own playlist. If you watch in order, every video only uses ideas you've already learned.

## You need zero IT background

No programming, no networking, no prior cloud knowledge. If you can use a web browser, you can start.

## How the path is built

```
A concept (vendor-neutral)  →  AWS  →  Azure  →  GCP  →  OCI  →  Alibaba  →  Side-by-side comparison
```

You learn the **idea once** (e.g., "what a network is"), then see how each of the five clouds does that same thing. By the comparison video, you can move between clouds because you understand the concept, not just one vendor's buttons.

## The four phases

1. **Phase 0 — Digital & Computing Literacy:** the absolute basics (how a computer works, the internet, files, a little Linux, virtual machines). *Watch this even if you think you know it — it sets the vocabulary.*
2. **Phase 1 — Cloud Foundations:** what "the cloud" really is, the service/deployment models, regions, economics — **plus the 16 vendor‑neutral domain foundations** (networking, compute, storage, databases, identity, security, serverless, edge/ops/cost) that the provider videos build on.
3. **Phase 2 — Provider Implementations:** each domain across AWS → Azure → GCP → OCI → Alibaba, then a comparison.
4. **Phase 3 — Apply & Advance:** small projects, "which cloud should you learn deeply?", certification on‑ramps, and where to go next (DevOps, Data, AI).

➡️ See the complete tree in [`ROADMAP.md`](ROADMAP.md). The 16 foundations have full content outlines in [`FOUNDATION-OUTLINES.md`](FOUNDATION-OUTLINES.md).

## How to read the video IDs

Format: **`Phase-Domain-Item`**

- `P0-…`, `P1-…`, `P2-…`, `P3-…` = the phase.
- Domain codes: **NET** networking · **CPT** compute · **STO** storage · **DB** databases · **IAM** identity · **SEC** security · **SVR** serverless/containers · **OPS** edge/monitoring/IaC/messaging/cost.
- Suffix: `-F` = vendor‑neutral **F**oundation (or `-F1/-F2`), `-AWS / -AZ / -GCP / -OCI / -ALI` = provider, `-CMP` = comparison.

Example: `P1-NET-F` (networking foundation) → `P2-NET-AWS` (AWS VPC) → … → `P2-NET-CMP` (all five compared).

## Hands‑on safety (read once)

Many videos include an optional lab on a provider's **free tier**. Two rules that keep you at **₹0 / $0**:

- **Running = paying.** Stop or delete anything you spin up the moment you finish.
- **Set a budget alert on day one** (covered in the Cost foundation). Delete demo resources the same day — VMs, disks, load balancers, NAT gateways, and unused IPs can quietly bill.

## Suggested pace

| Goal | Plan |
|---|---|
| Relaxed | 2–3 videos/week → finish in ~5–6 months |
| Standard | 1 video/day → finish in ~3.5 months |
| Intensive | 1 phase/week of focused study → ~6–8 weeks |

Pick one and keep it steady. Consistency beats speed.

Ready? Open [`ROADMAP.md`](ROADMAP.md) and start with **`P0-COMP-01`**.
