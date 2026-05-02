# Customer Data Platform — Feature & Functionality Survey

> Candidate #124 · Researched: 2026-05-02

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Segment (Twilio) | Commercial SaaS | Proprietary; Free (1k MTUs)–Business custom pricing | https://segment.com/customer-data-platform/ |
| RudderStack | Open Source | Apache 2.0; free self-hosted or cloud from $750/mo | https://www.rudderstack.com/ |
| Tealium AudienceStream | Commercial SaaS | Proprietary; custom enterprise pricing | https://tealium.com/products/audiencestream-cdp/ |

## Feature Analysis by Solution

### Segment (Twilio)

**Core features**
- Event collection across web, mobile, server, and third-party sources
- Identity Graph: real-time identity stitching merging anonymous and authenticated IDs
- Customisable ID Rules enforcing uniqueness and association logic
- Merge Protection: automatic detection and resolution of identity conflicts
- Unify: real-time profile generation and segmentation
- Engage: audience building and journey orchestration
- 400+ destination integrations for reverse ETL and activation
- Warehouse-native options: sync to Snowflake, BigQuery, Redshift
- Privacy and consent controls with GDPR/CCPA compliance
- Data classification and encryption

**Differentiating features**
- Largest integration ecosystem in category (400+)
- Warehouse-native options for data-mature organisations
- Real-time identity graph with online/offline support
- Anonymous identity stitching (session merge)
- Reliable profile sync with minimal latency
- Developer-friendly API and documentation
- Reverse ETL for activation from warehouse

**UX patterns**
- Dashboard showing identity graph structure and confidence
- Audience builder with SQL or visual query interface
- Event flow visualisation showing data pipeline status
- Integration marketplace with pre-built connectors

**Integration points**
- 400+ destination integrations
- Warehouse native: Snowflake, BigQuery, Redshift
- REST API for custom workflows
- Webhook support for real-time activation
- OAuth with major platforms (Google, Salesforce, HubSpot)

**Known gaps**
- MTU (Monthly Tracking User) pricing escalates sharply; cost prohibitive at scale
- Pricing opacity; enterprise quotes required
- Limited open-source transparency
- AI-powered audience segmentation limited
- Predictive scoring requires third-party ML models

**Licence / IP notes**
- Proprietary SaaS; owned by Twilio (acquired for $3.2B in 2020)
- Customer data on Twilio servers
- No self-hosting option

### RudderStack

**Core features**
- Open-source, warehouse-native event collection SDK
- Profiles: real-time customer profile unification in data warehouse
- Identity resolution with probabilistic matching
- 200+ integration destinations
- Event pipeline with schema validation and data quality controls
- Server-side event processing for enhanced privacy
- Reverse ETL for syncing warehouse back to tools
- Data warehouse integrations: Snowflake, BigQuery, Redshift, Postgres
- Free self-hosted deployment
- Cloud option with transparent event-volume pricing ($750/mo base)

**Differentiating features**
- Full data ownership via self-hosted deployment
- Warehouse-native architecture eliminates data silos
- No per-contact or per-user metering; pricing based on event volume
- Developer-friendly with full source code transparency
- Actively maintained open-source community
- Scalable to enterprise event volumes
- API-first design for custom workflows

**UX patterns**
- CLI and SDKs for integration
- Event explorer for debugging data pipeline
- Warehouse-native segment builder with SQL
- API-first identity resolution
- Dashboard showing data pipeline health and volume

**Integration points**
- 200+ destination integrations
- Warehouse native: Snowflake, BigQuery, Redshift, PostgreSQL
- REST API for event ingestion and querying
- Webhook support for real-time activation
- Support for custom event sources via SDKs

**Known gaps**
- Requires engineering resources for self-hosted deployment
- Marketer-friendly UI limited; requires SQL knowledge
- Smaller integration ecosystem than Segment (200 vs 400+)
- AI-powered features not built-in; require external models
- No out-of-the-box predictive scoring or churn models

**Licence / IP notes**
- Apache 2.0 licence; full source code on GitHub
- Self-hosted grants complete data ownership
- No restrictions on commercial use or derivative works
- Community-driven support; commercial support available

### Tealium AudienceStream

**Core features**
- Real-time identity resolution and stitching
- 1,300+ integration ecosystem
- Event collection and orchestration
- Customer segmentation and audience building
- Real-time activation across channels
- Built-in consent and preference management
- GDPR/CCPA compliance automation
- Block-by-default privacy rules
- Real-time, cloud-first, and hybrid architecture support
- AI and agent context feeding with real-time, consented signals

**Differentiating features**
- Massive integration ecosystem (1,300+)
- Privacy-first governance with consent travelling with every event
- Enterprise-grade real-time processing
- Advanced privacy compliance (GDPR, CCPA, geo-based)
- AI-ready with consented context for agent activation
- Unified identity stitching across all channels
- Server-side processing for enhanced security

**UX patterns**
- Real-time identity dashboard
- Segment builder with privacy compliance indicators
- Consent and preference management UI
- Integration marketplace with 1,300+ options
- Event flow visualisation and debugging

**Integration points**
- 1,300+ destination integrations
- Real-time activation APIs
- Webhook support for custom triggers
- OAuth with major platforms
- Custom connector development via APIs

**Known gaps**
- Custom enterprise pricing; not transparent for SMBs
- Steep implementation and learning curve
- No open-source version or self-hosting option
- Required professional services for deployment
- Limited AI features relative to future-native platforms

**Licence / IP notes**
- Proprietary SaaS; enterprise-only deployment
- Customer data on Tealium servers
- No self-hosting option
- Significant vendor lock-in on integration ecosystem

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Event collection from web, mobile, and server sources
- Identity resolution and profile unification
- Audience segmentation and query builder
- Real-time activation to marketing/analytics tools
- Consent and privacy controls (GDPR, CCPA)
- Data quality and validation rules
- Reverse ETL for warehouse activation
- Integration with CRM and marketing tools
- Customer profile dashboard
- Export and API access

### Differentiating Features
- Warehouse-native architecture (RudderStack)
- Massive integration ecosystem (Tealium 1,300+)
- Privacy-first design with block-by-default rules
- Real-time identity stitching with probabilistic matching
- Server-side event processing for enhanced privacy
- Transparent, developer-friendly pricing (RudderStack)
- Full data ownership and no vendor lock-in (open-source)
- AI-ready context feeding for agent activation

### Underserved Areas & Opportunities
- **LLM-assisted identity resolution**: Current tools use rule-based or probabilistic matching; LLM-explained identity conflicts with confidence scores would be more accessible to non-engineers
- **Natural-language segmentation**: No platform supports "find customers who bought in Q4 but haven't returned" type natural-language queries
- **Predictive audience models**: Churn, LTV, next-best-action models are add-ons or require separate ML infrastructure; built-in, continuously trained models without manual management are absent
- **AI-native open-source CDP**: RudderStack and Unomi lack AI layers; opportunity for AI-augmented open-source platform with marketer-friendly UI
- **Privacy-first design with transparency**: Current platforms hide privacy calculations; explainable privacy decisions with audit trails are missing
- **Real-time feature engineering**: No platform automatically generates features from event streams; streaming feature stores integrated with CDPs are an opportunity
- **Customer journey simulation**: No tool simulates journey outcomes before activation; predictive experimentation capabilities are missing
- **Data clean room integration**: Emerging need for privacy-safe collaboration; built-in data clean room connectors would differentiate

## Legal & IP Summary

Commercial CDPs (Segment, Tealium) operate on proprietary SaaS with vendor lock-in. RudderStack is Apache 2.0 licensed, granting full data ownership via self-hosting. GDPR, CCPA, and CASL compliance are mandatory table-stakes; all platforms support consent tracking and right-to-erasure. IAB TCF 2.2 consent strings are required for ad tech activation. No significant IP traps exist beyond vendor lock-in on historical customer profiles and integrations.

## Recommended Feature Scope

**Must-have (MVP)**
- Event collection from web, mobile, and server sources
- Identity resolution with basic probabilistic matching
- Customer profile unification and dashboard
- Audience segmentation with query builder
- Real-time activation to 20+ destinations
- GDPR and CCPA consent tracking
- Data validation and quality rules
- REST API for custom integrations
- User and team role-based access control

**Should-have (v1.1)**
- Warehouse-native architecture (Snowflake, BigQuery, Redshift)
- 100+ pre-built destination integrations
- Advanced identity resolution with confidence scoring
- Predictive audience models (churn, LTV)
- Privacy-first design with block-by-default rules
- Reverse ETL for warehouse-to-tool activation
- Server-side event processing
- Multi-channel activation and journey orchestration
- Compliance automation and audit trails
- Webhook support for real-time triggers

**Nice-to-have (backlog)**
- LLM-explained identity resolution with confidence
- Natural-language segment creation
- AI-native feature engineering from event streams
- Real-time customer journey simulation
- Data clean room integration for privacy-safe collaboration
- Self-hosted option for data sovereignty
- Advanced privacy analytics and transparency tools
- Multi-touch attribution across all channels
- Explainable AI for segment scoring
- Customer data marketplace for monetisation
