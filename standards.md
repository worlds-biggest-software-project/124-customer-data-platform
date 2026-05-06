# Standards & API Reference

> Project: Customer Data Platform · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

- **ISO/IEC 27001:2022 — Information security management systems** — https://www.iso.org/standard/27001 — The de-facto enterprise vendor qualification standard for SaaS. Any CDP handling customer PII at scale will be required to demonstrate ISO 27001 controls during procurement.
- **ISO/IEC 27018:2019 — Code of practice for protection of PII in public clouds acting as PII processors** — https://www.iso.org/standard/76559.html — Specifies controls for cloud-hosted CDPs that process customer PII on behalf of a controller. Highly relevant to multi-tenant CDP deployments.
- **ISO/IEC 27701:2019 — Privacy Information Management System (PIMS)** — https://www.iso.org/standard/71670.html — Extends ISO 27001 with privacy-specific controls aligned with GDPR; growing as a procurement requirement for CDPs.
- **ISO/IEC 29100:2011 — Privacy framework** — https://www.iso.org/standard/45123.html — Defines a common privacy terminology and actors (data subject, controller, processor) that map cleanly onto CDP profile/consent models.
- **ISO 8601 — Date and time representations** — https://www.iso.org/iso-8601-date-and-time-format.html — Required for event timestamps and identity-event ordering across all ingestion pipelines.
- **ISO 3166-1 (country codes) and ISO 4217 (currency codes)** — https://www.iso.org/iso-3166-country-codes.html / https://www.iso.org/iso-4217-currency-codes.html — Standard codes for normalising profile attributes (country, currency) across geographies.

### W3C & IETF Standards

- **W3C Verifiable Credentials Data Model 2.0** — https://www.w3.org/TR/vc-data-model-2.0/ — Emerging standard for portable, user-controlled identity attestations; relevant to next-gen consent and identity-resolution flows.
- **W3C JSON-LD 1.1** — https://www.w3.org/TR/json-ld11/ — Structured-data format for representing profile attributes with semantic context, used together with Schema.org.
- **W3C Tracking Preference Expression (DNT) and Global Privacy Control (GPC)** — https://www.w3.org/TR/tracking-dnt/ — Browser-side signals a CDP must honour for opt-out enforcement (CCPA/CPRA mandates GPC handling).
- **RFC 9110 — HTTP Semantics** — https://www.rfc-editor.org/rfc/rfc9110.html — Authoritative HTTP semantics that all REST-style ingestion endpoints must comply with.
- **RFC 7519 — JSON Web Token (JWT)** — https://www.rfc-editor.org/rfc/rfc7519 — Standard token format used in CDP SDK auth and source-side identity propagation.
- **RFC 7644 — System for Cross-domain Identity Management (SCIM 2.0)** — https://www.rfc-editor.org/rfc/rfc7644 — Standard protocol for syncing user/identity data between identity providers and downstream systems; relevant to identity-resolution sources.
- **RFC 8949 — Concise Binary Object Representation (CBOR)** — https://www.rfc-editor.org/rfc/rfc8949 — Compact binary encoding suited to high-volume mobile event ingestion.
- **RFC 6749 — OAuth 2.0 Authorization Framework** — https://www.rfc-editor.org/rfc/rfc6749 — Required for all server-to-server API authentication and destination-side delivery.

### Data Model & API Specifications

- **OpenAPI Specification 3.1** — https://spec.openapis.org/oas/v3.1.0 — Industry standard for describing REST APIs; should be used for the CDP control-plane and ingestion-API contracts.
- **AsyncAPI 3.0** — https://www.asyncapi.com/docs/reference/specification/v3.0.0 — The "OpenAPI for event-driven systems"; appropriate for documenting CDP event streams, webhooks, and Kafka topics.
- **CloudEvents 1.0 (CNCF)** — https://github.com/cloudevents/spec/blob/v1.0.2/cloudevents/spec.md — Vendor-neutral envelope for event metadata; increasingly adopted as the canonical event schema for CDP ingestion.
- **JSON Schema (2020-12 draft)** — https://json-schema.org/specification — Used to validate event payloads, profile attributes, and audience definitions.
- **GraphQL Specification (October 2021)** — https://spec.graphql.org/October2021/ — Common choice for CDP query APIs (profiles, audiences) because of nested-attribute traversal needs.
- **Apache Avro 1.11** — https://avro.apache.org/docs/1.11.1/specification/ — Schema-registry-friendly serialisation widely used in warehouse-native CDP pipelines (Kafka + Schema Registry).
- **Protocol Buffers (proto3)** — https://protobuf.dev/programming-guides/proto3/ — Used for high-throughput SDK-to-server event encoding (mParticle, Segment internals).
- **Schema.org / IAB Tech Lab Data Taxonomy** — https://schema.org/ , https://iabtechlab.com/standards/audience-taxonomy/ — Vocabulary for normalising profile traits and audience taxonomies across destinations.
- **Iceberg Table Spec / Delta Lake Protocol** — https://iceberg.apache.org/spec/ , https://github.com/delta-io/delta/blob/master/PROTOCOL.md — Open table formats relevant to warehouse-native CDPs that read/write profile snapshots in lakehouses.
- **dbt Semantic Layer / MetricFlow spec** — https://docs.getdbt.com/docs/build/about-metricflow — Increasingly used to express audience metrics consistently between the CDP and the warehouse.

### Security & Authentication Standards

- **OAuth 2.0 (RFC 6749) + OAuth 2.1 draft** — https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ — Modern consolidated OAuth profile; required for destination integrations.
- **OpenID Connect Core 1.0** — https://openid.net/specs/openid-connect-core-1_0.html — Identity federation layer for associating authenticated sessions with CDP profiles.
- **OWASP API Security Top 10 (2023)** — https://owasp.org/API-Security/editions/2023/en/0x00-header/ — Required threat model for CDP ingestion and query APIs.
- **OWASP ASVS 4.0.3** — https://owasp.org/www-project-application-security-verification-standard/ — Application-level verification controls for the CDP control-plane UI.
- **NIST SP 800-53 Rev. 5** — https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final — Control catalogue used for FedRAMP / public-sector CDP deployments.
- **NIST Privacy Framework 1.0** — https://www.nist.gov/privacy-framework — Reference framework for organising CDP privacy-engineering controls.
- **GDPR (Regulation EU 2016/679)** — https://eur-lex.europa.eu/eli/reg/2016/679/oj — Data minimisation, consent tracking, right-to-erasure obligations encoded into the CDP profile model.
- **CCPA / CPRA (California Civil Code §1798.100 et seq.)** — https://oag.ca.gov/privacy/ccpa — Opt-out-of-sale and deletion rights; mandates honouring GPC.
- **IAB Transparency & Consent Framework (TCF) 2.2** — https://iabeurope.eu/transparency-consent-framework/ — Standard consent-string format that the CDP must propagate to ad-tech destinations.
- **IAB Global Privacy Platform (GPP)** — https://iabtechlab.com/gpp/ — Successor framework that encodes multi-jurisdiction consent (TCF + US state signals) in a single string.

### MCP Server Specifications

- **Model Context Protocol (Anthropic)** — https://modelcontextprotocol.io/specification — Specification for exposing tool/data servers to LLM clients. Highly relevant for the AI-native angle: the CDP should ship an MCP server exposing profile lookup, audience query, and event-history tools so any LLM client can perform natural-language segmentation against the CDP.
- **MCP TypeScript and Python SDKs** — https://github.com/modelcontextprotocol — Reference implementations for building the CDP's MCP server.

## Similar Products — Developer Documentation & APIs

### Twilio Segment
- **Description:** Market-leading CDP with event collection, identity resolution, and 400+ destination integrations.
- **API Documentation:** https://segment.com/docs/api/
- **SDKs/Libraries:** https://segment.com/docs/connections/sources/ (Analytics.js, iOS, Android, Java, Python, Go, Node, Ruby, .NET)
- **Developer Guide:** https://segment.com/docs/getting-started/
- **Standards:** REST/JSON ingestion and Public API; follows the Segment Spec event taxonomy (track/identify/page/screen/group/alias).
- **Authentication:** Write-key per source; OAuth 2.0 + Personal Access Tokens for the Public API.

### RudderStack
- **Description:** Open-source warehouse-native CDP with 200+ integrations and self-hosting option.
- **API Documentation:** https://www.rudderstack.com/docs/api/
- **SDKs/Libraries:** https://github.com/rudderlabs (JavaScript, iOS, Android, React Native, Flutter, Unity, Java, Python, Go, Node, Ruby, .NET, PHP)
- **Developer Guide:** https://www.rudderstack.com/docs/
- **Standards:** Segment-compatible event spec; REST + HTTP API; OpenAPI-described control plane.
- **Authentication:** Write-key per source; Personal Access Tokens for control-plane API.

### mParticle
- **Description:** Mobile-first CDP focused on identity resolution and data quality for app-driven businesses.
- **API Documentation:** https://docs.mparticle.com/developers/
- **SDKs/Libraries:** https://github.com/mParticle (iOS, Android, Web, React Native, Cordova, Xamarin, Unity, Java, Python, Node, Go)
- **Developer Guide:** https://docs.mparticle.com/developers/quickstart/
- **Standards:** REST/JSON; Events API v2; Profile API; Bulk API; OpenAPI-described.
- **Authentication:** API key + secret per workspace (HTTP Basic); OAuth 2.0 for platform APIs.

### Tealium AudienceStream / EventStream
- **Description:** Enterprise CDP suite combining tag management, event streaming, ML predictions, and consent management.
- **API Documentation:** https://docs.tealium.com/server-side/
- **SDKs/Libraries:** https://docs.tealium.com/platforms/ (Web utag.js, iOS, Android, Roku, Unity, React Native)
- **Developer Guide:** https://docs.tealium.com/getting-started/
- **Standards:** REST/JSON HTTP API; Universal Data Object (UDO) schema.
- **Authentication:** API key + bearer tokens; SAML SSO for console.

### Salesforce Data Cloud
- **Description:** Salesforce-native CDP unifying customer profiles across Marketing Cloud, Sales Cloud, and Service Cloud.
- **API Documentation:** https://developer.salesforce.com/docs/data/data-cloud-int/guide/api.html
- **SDKs/Libraries:** Salesforce Mobile SDK (iOS/Android), Web SDK; standard Salesforce REST/SOAP/Bulk APIs.
- **Developer Guide:** https://developer.salesforce.com/docs/data/data-cloud-dev/guide/dc-developer-guide.html
- **Standards:** REST/JSON; Salesforce Object Query Language (SOQL); Bulk API 2.0.
- **Authentication:** OAuth 2.0 (JWT bearer, web server, user-agent flows).

### Adobe Experience Platform / Real-Time CDP
- **Description:** Adobe's enterprise CDP within Experience Cloud, with profile unification and edge activation.
- **API Documentation:** https://developer.adobe.com/experience-platform-apis/
- **SDKs/Libraries:** Adobe Experience Platform Mobile SDK, Web SDK (alloy.js); https://github.com/adobe/aep-sdks
- **Developer Guide:** https://experienceleague.adobe.com/en/docs/experience-platform/landing/home
- **Standards:** Experience Data Model (XDM) — Adobe's open schema based on JSON Schema; REST/JSON.
- **Authentication:** OAuth 2.0 server-to-server (JWT deprecated in favour of OAuth S2S).

### BlueConic
- **Description:** Marketer-focused profile-based CDP with strong consent and lifecycle orchestration.
- **API Documentation:** https://support.blueconic.com/hc/en-us/categories/360002214199-REST-API
- **SDKs/Libraries:** JavaScript front-end SDK; mobile SDKs (iOS/Android).
- **Developer Guide:** https://support.blueconic.com/hc/en-us/categories/360001633019-Developers
- **Standards:** REST/JSON.
- **Authentication:** OAuth 2.0; API tokens.

### Hightouch (Composable CDP / Reverse ETL)
- **Description:** Warehouse-native activation layer that turns the data warehouse into the CDP system of record.
- **API Documentation:** https://hightouch.com/docs/api-reference/introduction
- **SDKs/Libraries:** Events SDKs for Web, iOS, Android, Node, Python, Go; https://github.com/hightouchio
- **Developer Guide:** https://hightouch.com/docs/
- **Standards:** REST/JSON; OpenAPI 3.x described.
- **Authentication:** Bearer API tokens (workspace-scoped); OAuth 2.0 for partner apps.

### Census (Composable CDP / Reverse ETL)
- **Description:** Reverse-ETL platform that syncs warehouse data to SaaS destinations as a composable-CDP alternative.
- **API Documentation:** https://docs.getcensus.com/basics/api
- **SDKs/Libraries:** REST clients; Embedded SDK for white-label deployments.
- **Developer Guide:** https://docs.getcensus.com/
- **Standards:** REST/JSON; OpenAPI described.
- **Authentication:** Bearer API tokens.

### Apache Unomi (Open Source)
- **Description:** Apache-licensed CDP with GDPR-first design, ElasticSearch-backed, focused on real-time personalisation.
- **API Documentation:** https://unomi.apache.org/rest-api-doc/
- **SDKs/Libraries:** Java client; HTTP clients in any language; CXS reference implementation.
- **Developer Guide:** https://unomi.apache.org/manual/latest/
- **Standards:** OASIS Context Server (CXS) draft specification — https://wiki.oasis-open.org/customercontextserver/ — the only formal open standard for CDP semantics; REST/JSON.
- **Authentication:** HTTP Basic; can be fronted by OAuth/OIDC reverse proxy.

### Tracardi (Open Source)
- **Description:** Modern Python-based open-source CDP with real-time segmentation and visual workflow automation.
- **API Documentation:** https://docs.tracardi.com/development/api/
- **SDKs/Libraries:** REST clients; JavaScript tracker; bring-your-own.
- **Developer Guide:** https://docs.tracardi.com/
- **Standards:** REST/JSON; OpenAPI described (FastAPI-generated).
- **Authentication:** OAuth 2.0 password/bearer flow.

### Jitsu (Open Source)
- **Description:** Open-source data-collection / event-streaming platform often used as a Segment alternative.
- **API Documentation:** https://docs.jitsu.com/api
- **SDKs/Libraries:** https://github.com/jitsucom (JavaScript, Node, Python, Go, iOS, Android)
- **Developer Guide:** https://docs.jitsu.com/
- **Standards:** Segment-compatible event spec; REST/JSON.
- **Authentication:** Write-key per source; bearer tokens for management API.

## Notes

- **Formal CDP semantic standards are weak.** The OASIS Context Server (CXS) specification — implemented by Apache Unomi — is the only open standard that defines a CDP-specific data model. Most other vendors maintain proprietary event taxonomies (Segment Spec, Adobe XDM, Tealium UDO, mParticle Schema). An AI-native open-source CDP has an opportunity to converge on CloudEvents + JSON-LD + Schema.org rather than invent a new proprietary taxonomy.
- **AsyncAPI is under-adopted in the CDP space.** Despite event streams being the core abstraction, very few CDPs publish AsyncAPI documents for their webhooks/destinations. Shipping AsyncAPI specs would be a developer-experience differentiator.
- **MCP is the natural surface for the AI-native angle.** Exposing profile lookup, audience query, and event-history as MCP tools allows any LLM client (Claude, ChatGPT desktop, Cursor, etc.) to perform natural-language segmentation without bespoke integrations — directly addressing the "AI-Native Opportunity" identified in research.md.
- **Consent encoding is consolidating on IAB GPP.** New CDPs should target GPP rather than legacy TCF 2.2 alone, since GPP encodes both EU TCF and US state signals (CCPA/CPRA, Colorado, Virginia, etc.) in a single portable string.
- **Warehouse-native CDPs are aligning on Iceberg/Delta.** Profile snapshots and audience materialisations increasingly live in open table formats; supporting Iceberg/Delta as first-class storage targets is becoming table stakes for the composable-CDP segment.
- **Gap: no widely-adopted open standard for identity-resolution graphs.** Each CDP exposes its own identity-graph API. This is an opportunity area — a JSON-LD-based identity-graph schema, possibly aligned with W3C VC, could become a meaningful open contribution.
