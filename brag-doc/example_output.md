---
id: atlas-retrieval-platform
name: "Atlas: Unified Retrieval Platform"
date_start: 2025-01-15
date_end: 2025-09-30
org: Meridian Technologies — Search & Discovery
role: Principal Software Engineer / Tech Lead
domain: ML platform, information retrieval, serving infrastructure
keywords:
  - retrieval
  - embeddings
  - vector search
  - HNSW
  - transformer
  - Kubernetes
  - gRPC
  - feature store
  - A/B testing
status: complete
---

## One-line Summary

Designed and shipped Atlas, a unified retrieval platform consolidating three legacy search backends into a single embedding-based service, improving top-10 recall by 18% and reducing serving infrastructure cost by 41% (Source: https://meridian.internal/dashboards/atlas-q3).

## Problem, Context, & Constraints

Meridian's product search, recommendation, and autocomplete systems each ran independent retrieval stacks — separate indexes, ranking models, and serving clusters — resulting in duplicated infrastructure, inconsistent relevance, and a 6-week lead time for any retrieval feature change. A Q1 executive review identified search relevance as the top driver of user churn, with NPS scores on search dropping 12 points year-over-year (Source: https://meridian.internal/docs/q1-exec-review). The VP of Engineering mandated a unified retrieval platform by end of Q3 2025 to support a planned marketplace expansion into three new verticals.

Constraints were significant: the platform had to maintain a p99 latency budget of 45ms at 25,000 QPS across all query types, comply with GDPR right-to-deletion requirements within the vector index, operate within the existing Kubernetes footprint without additional hardware budget, and remain backward-compatible with 14 downstream consumer services during migration. The team had 4 backend engineers and 2 ML engineers, with no dedicated SRE support.

## Contributions

### Owned
- Designed the end-to-end system architecture for Atlas: a two-tower retrieval model served via approximate nearest neighbor (HNSW) with a gRPC API layer, online feature enrichment, and a unified indexing pipeline
- Implemented the core ANN serving layer in Rust, including a custom GDPR-compliant deletion mechanism that supports soft-delete with index compaction on a 24-hour cycle
- Built the offline evaluation harness comparing Atlas against all three legacy systems across 6 relevance benchmarks, enabling data-driven migration decisions
- Defined the embedding schema and versioning contract that allowed ML engineers to retrain and hot-swap models without reindexing

### Led
- Drove the migration strategy across 14 downstream services, coordinating with 4 product teams to sequence dual-write cutover windows with zero downtime
- Led the cross-functional working group (engineering, product, legal) to design the GDPR deletion approach for vector indexes, resulting in an approved compliance pattern now adopted org-wide
- Established the A/B testing framework for retrieval experiments, including guardrail metrics and automatic rollback triggers

### Contributed
- Advised the ML team on the two-tower model architecture, specifically the hard-negative mining strategy that improved offline recall@10 by 8 points over the initial baseline
- Reviewed and improved the Kubernetes resource configurations for the serving cluster, reducing pod scheduling latency during rolling deploys

## Key Decisions & Tradeoffs

- Chose HNSW over IVF-PQ for the ANN index because the query latency distribution was tighter (p99 within 45ms budget) despite 2.3x higher memory cost. Mitigated memory cost by implementing tiered storage with hot/warm partitioning based on query frequency. Would reconsider if the index exceeds 500M vectors, at which point IVF-PQ's memory profile becomes necessary.
- Built custom ANN serving in Rust instead of adopting Milvus or Weaviate. Evaluated both; neither supported the GDPR soft-delete-with-compaction requirement without forking, and vendor lock-in risk was unacceptable given Meridian's multi-cloud strategy. Tradeoff: higher initial build cost (~6 weeks) but full control over compliance and performance tuning.
- Adopted a dual-write migration pattern (legacy + Atlas in parallel) rather than a big-bang cutover. Slower rollout (8 weeks vs. 2) but eliminated downtime risk and allowed per-service A/B comparison. De-risked with automatic fallback to legacy on latency threshold breach.
- Used a shared embedding space across product search, recommendations, and autocomplete rather than domain-specific models. Sacrificed ~3% recall on autocomplete (where character-level features matter more) in exchange for a single index, single model, and unified feature pipeline — reducing operational complexity by an estimated 60%.
- Deferred real-time index updates in favor of batch reindexing on a 15-minute cycle. Real-time updates would have required a streaming pipeline and increased p99 latency by ~12ms. Acceptable tradeoff given that catalog freshness SLO was 30 minutes.

## Scope and Complexity

- 25,000 QPS at peak across product search, recommendations, and autocomplete, serving 8M monthly active users across 3 geographic regions
- 120M document vectors indexed (product catalog + user interaction embeddings), totaling ~480 GB in the HNSW index
- 6-person core team (4 backend, 2 ML) with 4 partner teams consuming the API, plus legal and compliance stakeholders
- 14 downstream services migrated, spanning 3 product domains (marketplace, discovery, seller tools)
- Operated under a hard Q3 deadline tied to marketplace vertical expansion launch

## Outcomes

### Business
- Top-10 search recall improved by 18%, contributing to a 6.2% increase in search-initiated conversions in Q3 (Source: https://meridian.internal/dashboards/atlas-q3)
- Reduced serving infrastructure cost by 41% ($1.2M annualized) by consolidating three clusters into one (Source: https://meridian.internal/docs/atlas-cost-report)

### Engineering
- Reduced retrieval feature change lead time from 6 weeks to 4 days by unifying the indexing and serving pipeline
- Achieved p99 serving latency of 32ms, well within the 45ms budget, with 99.97% availability over the first 3 months in production (Source: https://meridian.internal/dashboards/atlas-slo)
- Established a reusable GDPR deletion pattern for vector indexes, now adopted by 2 other platform teams

### ML / Model
- Two-tower retrieval model achieved recall@10 of 0.74 (up from 0.63 baseline across legacy systems), evaluated on a held-out behavioral dataset of 2M query-click pairs (Source: https://meridian.internal/docs/atlas-model-eval)
- Online A/B test showed +4.1% click-through rate and +2.8% add-to-cart rate vs. legacy, with no degradation on guardrail metrics (latency, null-result rate) (Source: https://meridian.internal/experiments/atlas-ab-final)
- Deployed model monitoring via embedding drift detection (cosine similarity distribution shift), with automated alerting — no drift incidents in first 90 days

### Adoption / Scale
- All 14 downstream services fully migrated to Atlas by end of Q3, with zero rollback incidents
- 3 new product verticals onboarded within 2 weeks of platform GA, compared to an estimated 6 weeks each on the legacy stack

## Artifacts / Evidence

* **[Atlas System Design Doc](https://meridian.internal/docs/atlas-design-v2)** - Approved architecture document covering ANN index design, serving layer, and migration strategy
* **[Q3 Retrieval Metrics Dashboard](https://meridian.internal/dashboards/atlas-q3)** - Live dashboard showing recall, latency, availability, and cost metrics
* **[GDPR Vector Deletion RFC](https://meridian.internal/docs/rfc-gdpr-vector-delete)** - Cross-org RFC establishing the soft-delete-with-compaction pattern, now org-wide standard
* **[Atlas Model Evaluation Report](https://meridian.internal/docs/atlas-model-eval)** - Offline evaluation comparing Atlas two-tower model against legacy retrieval across 6 benchmarks
* **[A/B Test Final Results](https://meridian.internal/experiments/atlas-ab-final)** - Online experiment report with CTR, add-to-cart, and guardrail metric analysis
* **[Migration Runbook](https://meridian.internal/runbooks/atlas-migration)** - Step-by-step cutover playbook used for all 14 downstream service migrations
* **[Infrastructure Cost Analysis](https://meridian.internal/docs/atlas-cost-report)** - Before/after cost breakdown supporting the $1.2M annualized savings claim

## Influence Beyond Code

- Mentored 2 mid-level engineers through the project; one promoted to Senior Engineer in the Q3 cycle, with Atlas cited as the primary evidence of system design growth (Source: recollection)
- Authored the GDPR Vector Deletion RFC that was adopted as an org-wide standard, saving an estimated 3 teams from designing their own approaches
- Delivered an internal tech talk on "Approximate Nearest Neighbors at Scale" to ~80 engineers, which became a recommended onboarding resource for the Search & Discovery org
- Designed and calibrated 2 new system design interview questions based on Atlas trade-offs, now part of the senior engineer hiring loop

## Failures / Lessons Learned

- Underestimated the complexity of GDPR-compliant deletion in HNSW indexes by ~3 weeks. Root cause: did not prototype the compaction path early enough and discovered that naive tombstoning degraded recall under high-delete workloads. Fix: implemented a background compaction process and added integration tests simulating deletion-heavy scenarios. Lesson: prototype compliance-critical paths in week 1, not after core functionality is built.
- The initial shared embedding space caused a 9% recall regression on autocomplete queries during the first A/B test. Root cause: autocomplete queries rely heavily on prefix and character-level features that the two-tower model did not capture. Fix: added a lightweight character n-gram feature to the query tower and introduced query-type-specific fine-tuning, recovering most of the gap (final delta: -3%). Lesson: evaluate shared-model approaches per query type independently before committing to a single architecture.
