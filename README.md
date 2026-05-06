# Customer Data Platform (CDP)

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source Customer Data Platform that unifies customer profiles, resolves identities, and activates audiences without enterprise lock-in or per-user metering.

The Customer Data Platform (CDP) project aims to deliver a warehouse-native, AI-augmented alternative to commercial CDPs such as Segment, Tealium, and Adobe Real-Time CDP. It is built for marketing technology leads, data engineers, and growth teams who need unified customer profiles, identity resolution, and real-time activation, but who are priced out of — or locked into — incumbent platforms. The goal is to combine the data ownership of open-source tools like RudderStack and Apache Unomi with an AI layer that makes segmentation, identity resolution, and predictive scoring accessible to non-engineers.

---

## Why Customer Data Platform (CDP)?

- Commercial CDPs use Monthly Tracking User (MTU) pricing that escalates sharply at scale; Tealium, Adobe, and Salesforce enterprise deployments routinely cost $100k–$500k+/year including implementation.
- Existing open-source CDPs (RudderStack, Apache Unomi, Tracardi) are technically strong but lack AI layers and marketer-friendly UIs, leaving a clear gap between developer-grade infrastructure and accessible audience tooling.
- Identity resolution today requires data engineers to build and maintain probabilistic matching pipelines; non-engineers have no way to inspect or trust the merges.
- Audience segmentation is manual and query-based across every major platform — natural-language segment creation is absent from the category.
- Predictive models (churn, LTV, next-best-action) are bolt-on modules or require separate ML infrastructure, never continuously trained on the live profile event stream.

---

## Key Features

### Event Collection and Pipeline

- Event collection from web, mobile, and server-side sources
- Schema validation and data quality controls on ingest
- Server-side event processing for enhanced privacy
- REST API for event ingestion and querying
- Webhook support for real-time triggers

### Identity Resolution and Profiles

- Real-time identity stitching across anonymous and authenticated sessions
- Probabilistic matching with confidence scoring
- Customisable ID rules enforcing uniqueness and association logic
- Merge conflict detection and resolution
- Unified customer profile dashboard

### Segmentation and Activation

- Audience builder with query interface
- Real-time activation to marketing and analytics destinations
- Reverse ETL from data warehouse back to operational tools
- Multi-channel activation and journey orchestration
- Pre-built destination integrations across major platforms

### Privacy, Consent, and Compliance

- GDPR and CCPA consent tracking per profile
- IAB TCF 2.2 consent string propagation to ad tech destinations
- Right-to-erasure and data minimisation tooling
- Block-by-default privacy rules
- Compliance automation and audit trails

### Warehouse-Native Architecture

- Native integration with Snowflake, BigQuery, Redshift, and PostgreSQL
- Profile unification computed in the data warehouse
- Event-volume pricing rather than per-contact metering
- Self-hosted deployment for full data ownership
- API-first design for custom workflows

---

## AI-Native Advantage

Unlike incumbent CDPs that bolt AI onto rule-based cores, this project treats AI as a first-class layer. LLM-assisted identity resolution explains its merge decisions and surfaces confidence scores so non-engineers can audit and override them. Natural-language segmentation lets marketers express queries like "find customers who bought in Q4 but haven't returned" without SQL. Predictive models for churn, LTV, and next-best-action train continuously on the profile event stream rather than living as separate add-on modules.

---

## Tech Stack & Deployment

The platform targets both self-hosted and cloud deployment modes, mirroring the open-source dual-licence pattern established by RudderStack (Apache 2.0). Warehouse-native architecture builds on Snowflake, BigQuery, Redshift, and PostgreSQL. Standards alignment includes CloudEvents (CNCF) for event schema, OpenID Connect / OAuth 2.0 for identity federation, IAB TCF 2.2 for consent propagation, and ISO/IEC 27001 as an enterprise vendor qualification target. SDKs cover web, mobile, and server-side ingestion with a REST API and webhook layer for custom workflows.

---

## Market Context

The CDP market was valued at $9.72 billion in 2025 and is projected to reach $37.11 billion by 2030 at a 30.7% CAGR (MarketsandMarkets, 2025; Grand View Research, 2024). Incumbent pricing ranges from Segment's free tier through mid-market plans of $750–$5,000/month to enterprise contracts of $100k–$500k+/year for Tealium, Adobe Real-Time CDP, and Salesforce Data Cloud. Primary buyers are marketing technology leads, data engineers, VPs of Marketing/Growth, and CIOs at mid-market and enterprise companies, with particular concentration in e-commerce and regulated industries (finance, healthcare).

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
