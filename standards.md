# Standards & API Reference

> Project: Fishery Management System · Generated: 2026-05-03

## Industry Standards & Specifications

### ISO Standards

**ISO/TC 234 — Fisheries and Aquaculture**
- URL: https://www.iso.org/committee/541071.html
- The ISO Technical Committee responsible for standardisation in fisheries and aquaculture, covering terminology, technical specifications, environmental monitoring, and traceability. All ISO standards listed below originate from this committee.

**ISO 12875:2011 — Traceability of Finfish Products (Captured)**
- URL: https://www.iso.org/standard/52084.html
- Specifies the information to be recorded in marine-captured finfish supply chains to establish traceability from catch through to retailers or caterers. Defines how traded fishery products must be identified and what data each business in the distribution chain must record and hold.

**ISO 12877:2011 — Traceability of Finfish Products (Farmed)**
- URL: https://www.iso.org/standard/52085.html
- The aquaculture counterpart to ISO 12875. Specifies information to be recorded in farmed finfish supply chains from breeding and farming through to retail, covering traceability of farmed finfish and their products.

**ISO 22005 — Traceability in the Feed and Food Chain**
- Provides general principles and basic requirements for designing and implementing a traceability system applicable to any organisation in the food and feed chain. Relevant when a fishery management system includes feed/input traceability for aquaculture operations.

**ISO 67.120.30 — Fish and Fishery Products Standards**
- URL: https://www.iso.org/ics/67.120.30/x/
- The ICS classification grouping all ISO standards related to fish and fishery products, including quality, safety, and labelling specifications that intersect with management and traceability requirements.

---

### W3C & IETF Standards

**RFC 7231 — Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content**
- URL: https://datatracker.ietf.org/doc/html/rfc7231
- The foundational HTTP standard governing REST API design and verb semantics. All fisheries management APIs (Global Fishing Watch, NOAA FOSS, FishSource, FishBase) are built on HTTP/1.1 or HTTP/2.

**RFC 8288 — Web Linking**
- URL: https://datatracker.ietf.org/doc/html/rfc8288
- Defines the Link header field used in hypermedia APIs. Relevant to pagination and navigation in fisheries data APIs that return large result sets (e.g., species databases, catch records).

**RFC 6749 — OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- The authorisation standard used by Global Fishing Watch, FAOSTAT, and other fisheries data APIs for secure third-party access delegation. Required for any fishery management system that connects to external government or NGO data sources.

**W3C JSON-LD 1.1**
- URL: https://www.w3.org/TR/json-ld11/
- Linked Data format adopted by the GDST Standard (v1.2) and GS1 EPCIS 2.0 for seafood traceability data exchange. JSON-LD allows fisheries data to be semantically linked across organisations without central coordination.

**GS1 EPCIS 2.0 / CBV**
- URL: https://www.gs1.org/standards/epcis
- GS1's flagship supply chain visibility standard, updated in 2022 to support JSON-LD. The GDST Standard (see below) is built directly on EPCIS 2.0 and requires it for interoperable seafood traceability. Captures the "what, when, where, why, and how" of products in the chain of custody.

**GS1 Digital Link**
- URL: https://www.gs1.org/standards/gs1-digital-link
- Communication protocol required by GDST 1.1/1.2 for computer-to-computer transfer of traceability data. Enables QR-code-based product identification that resolves to rich supply chain data.

---

### Data Model & API Specifications

**UN/CEFACT FLUX — Fisheries Language for Universal Exchange**
- URL: https://unece.org/trade/uncefact/unflux
- Brochure: https://unece.org/fileadmin/DAM/cefact/SustainableFisheriesTeamOfSpecialists/2018/FLUX-Brochure.pdf
- The UN standard message format and protocol for exchanging fisheries information between countries and organisations. Covers vessel and trip identification, fishing operations (daily catch or haul-by-haul), catch area, species and quantity, gear used, landing and sales, licensing, and inspection data. Implemented as XML messages; free, open, and global. Mandated by EU Electronic Reporting Systems (ERS) and implemented by Trackwell FiMS, FOCUS, and other systems.

**FAO CWP Data Structures — Capture Fishery Statistics**
- URL: https://www.fao.org/cwp-on-fishery-statistics/handbook
- Four standardised data structures defined by the Coordinating Working Party on Fishery Statistics: Global Capture Production, Catch, Catch & Effort, and Logbook. These define the core information model for capture fishery statistics and are harmonised with FIRMS and GRSF data frameworks.

**OpenAPI Specification 3.1**
- URL: https://spec.openapis.org/oas/latest.html
- The standard for describing REST APIs. NOAA's NEMIS API is documented in OpenAPI v3 format. Any new fishery management system exposing a REST API should publish an OpenAPI 3.1 specification for developer adoption.

**GDST Technical Standard 1.2 (Global Dialogue on Seafood Traceability)**
- URL: https://thegdst.org/resources/standard/
- Developer Docs: https://developer.thegdst.org
- Extends GS1 EPCIS 2.0 with seafood-specific Critical Tracking Events (CTEs) and Key Data Elements (KDEs) covering fishing, aquaculture, processing, cold storage, and retail. Transitioned to JSON-LD in v1.2 to align with EPCIS 2.0. Provides open-source implementation libraries (Open Traceability project).

**GS1 Foundation for Fish, Seafood, and Aquaculture Traceability Guideline**
- URL: https://www.gs1.org/sites/default/files/docs/traceability/GS1_Foundation_for_Fish_Seafood_Aquaculture_Traceability_Guideline.pdf
- The GS1 implementation guide for applying EPCIS and GS1 standards to seafood supply chains, covering identification, capture, share, and use of traceability data at each supply chain step.

---

### Security & Authentication Standards

**OAuth 2.0 (RFC 6749) — Application to Fisheries APIs**
- Global Fishing Watch, FAOSTAT, and MSC APIs all use bearer-token or OAuth 2.0 based authentication. Fishery management systems integrating with government or NGO data sources must implement OAuth 2.0 flows. JWT tokens (FAOSTAT) expire after 60 minutes; client credential flows are common for server-to-server integrations.

**GDPR — Regulation (EU) 2016/679**
- URL: https://gdpr-info.eu/
- Applies to fishery management systems operating in the EU or handling data about EU nationals. Vessel operator and fisher personal data must comply with GDPR data minimisation principles. The GDST Technical Standard explicitly recommends collecting organisational rather than personal data to minimise GDPR exposure in traceability systems.

**EU Fisheries Control Regulation (EC) No 1224/2009 (amended by EU 2023/2842)**
- URL: https://eur-lex.europa.eu/EN/legal-content/summary/the-eu-s-fisheries-control-system.html
- The primary EU regulatory framework for fisheries control, inspection, and enforcement. Mandates electronic logbooks (ERS) for all EU vessels over 12 m (and from 2028, all vessels). Defines data reporting requirements for catches, landings, transshipments, and quota exhaustion thresholds. Requires Remote Electronic Monitoring (REM/CCTV) for high-risk vessels over 18 m from mandate date.

**AIS — Automatic Identification System (ITU-R M.1371)**
- The maritime transponder standard used by vessels to broadcast position, identity, and navigational data. Provides open (unencrypted) vessel tracking data used by Global Fishing Watch and other monitoring platforms. Distinguished from VMS (closed, encrypted, government-only) by its public accessibility.

**VMS — Vessel Monitoring System Standards (FAO/RFMO)**
- URL: https://www.fao.org/gfcm/activities/compliance/vessel-monitoring/en/
- The closed, encrypted vessel position reporting system mandated by FAO and regional fisheries management organisations (RFMOs) for larger commercial fishing vessels. VMS is the only reporting system recognised by FAO for global fisheries monitoring. Data is transmitted only to national fisheries authorities and shared via FLUX network with RFMOs and coastal states.

---

### MCP Server Specifications

Model Context Protocol (MCP) is not currently implemented in the fisheries management domain's major platforms. However, an AI-native fishery management system could expose MCP-compliant tools for vessel lookups, quota checks, species identification, and FLUX message generation, enabling integration with AI agent frameworks (Claude, GPT-4, etc.) for analyst and compliance officer workflows.

---

## Similar Products — Developer Documentation & APIs

### Global Fishing Watch API
- **Description:** Open API platform providing AIS-based fishing vessel tracking, apparent fishing effort, vessel identity, port visits, fishing events, and marine area compliance. Used by researchers, governments, and NGOs worldwide for IUU fishing detection and ocean monitoring.
- **API Documentation:** https://globalfishingwatch.org/our-apis/documentation
- **Interactive Docs:** https://api-doc.globalfishingwatch.org/
- **SDKs/Libraries:**
  - R package (gfwr): https://github.com/GlobalFishingWatch/gfwr
  - Python client: https://github.com/GlobalFishingWatch/gfw-api-python-client
  - Postman collection available for download via documentation portal
- **Developer Guide:** https://globalfishingwatch.github.io/gfwr/
- **Standards:** REST/JSON, HTTPS, resource-oriented URLs
- **Authentication:** Bearer token (API key)
- **Key Endpoints:** Vessel API (vessel search/identity), Events API (fishing events, port visits, loitering, encounters), 4Wings API (fishing effort map tiles), Insights API (IUU risk assessment), Datasets API (offshore infrastructure)

---

### NOAA Fisheries One Stop Shop (FOSS) API
- **Description:** NOAA's public commercial and recreational fisheries data platform covering catch, haul, and environmental survey data collected by NOAA scientific surveys. Final validated data published soon after surveys complete.
- **API Documentation:** https://www.fisheries.noaa.gov/foss/f?p=215:35
- **Standards:** OpenAPI v3 (NEMIS endpoint), REST/JSON
- **Authentication:** Public access (no auth required for most endpoints); web service layer available for government partners
- **Notes:** Landings data accessible via web interface but machine-to-machine API access is limited; NEMIS (Northeast Fisheries Science Center) provides a fully documented OpenAPI 3.0 specification. Stock SMART provides stock assessment data downloads.
- **NEMIS API Docs:** https://apps-nefsc.fisheries.noaa.gov/NEMIS/index.php/docs/readme

---

### FishSource API (Sustainable Fisheries Partnership)
- **Description:** Sustainability assessment database for commercial fisheries worldwide, scoring stock status, management effectiveness, and environmental/biodiversity impact. Used by seafood buyers for due diligence.
- **API Documentation:** https://www.fishsource.org/apipie/v4.html (v4), https://www.fishsource.org/apipie/v5/stock/show.html (v5)
- **Standards:** REST/JSON
- **Authentication:** Not publicly documented; contact SFP for API access
- **Key Resources:** Fisheries, Management Units, Stocks — returns assessment scores and supporting narratives in JSON

---

### FishBase / SeaLifeBase API
- **Description:** Global reference database for over 30,000 fish species covering biology, ecology, morphology, distribution, and more. Maintained by rOpenSci as an open REST API backed by Amazon S3-compatible storage.
- **API Documentation:** https://ropensci.github.io/fishbaseapidocs/
- **Apiary Docs:** https://fishbaseapi.docs.apiary.io/
- **GitHub:** https://github.com/ropensci/fishbaseapi
- **SDKs/Libraries:**
  - R: rfishbase package (https://docs.ropensci.org/rfishbase/)
  - Python: via S3 API (boto3, Apache Arrow)
- **Standards:** REST (GET/HEAD only), AWS S3 API v4 compatible, versioned via Accept header
- **Authentication:** Public (no auth required)
- **Endpoints:** https://fishbase.ropensci.org/fishbase (FishBase), https://fishbase.ropensci.org/sealifebase (SeaLifeBase)

---

### FAOSTAT API
- **Description:** FAO's global food and agriculture statistics platform covering fisheries production, trade, and sustainability indicators for 245+ countries from 1961 to present. Used as a source for global catch trend data in fisheries management research.
- **API Documentation:** https://www.fao.org/statistics/highlights-archive/highlights-detail/faostat-launches-a-new-api-developer-portal-to-make-data-access-easier/en
- **GitHub:** https://github.com/FAOSTAT/faostat-api
- **SDKs/Libraries:**
  - Python: faostat package (https://pypi.org/project/faostat/)
  - R: FAOSTAT package (https://rdrr.io/cran/FAOSTAT/api/)
- **Standards:** REST/JSON, JWT authentication
- **Authentication:** JWT bearer token (expires 60 min); requires account on FAOSTAT Developer Portal

---

### MSC Data Validation API (Marine Stewardship Council)
- **Description:** API enabling automated validation of whether a fishery, supply chain company, or consumer product holds a valid MSC sustainability certificate. Eliminates manual searches in Track a Fishery and Find a Supplier databases.
- **API Documentation:** https://www.msc.org/for-business/msc-data-validation-api
- **Explainer PDF:** https://www.msc.org/docs/default-source/default-document-library/for-business/msc-data-validation-api-explainer.pdf
- **Standards:** REST/JSON
- **Authentication:** MSC Ecolabel License Agreement holders receive API access as part of annual fee
- **Use Cases:** Traceability systems vetting certified status of fisheries; supply chain due diligence; consumer product certification verification

---

### AKVA Group FishTalk / AKVA Ecosystem APIs
- **Description:** Cloud-based aquaculture production management platform with APIs for biological and financial planning. AKVA ecosystem APIs allow data to flow between business systems and external applications.
- **API Documentation:** https://www.akvagroup.com/akvafusion/akva-ecosystem/ (commercial access required)
- **Standards:** REST/JSON (inferred from cloud-based open platform positioning)
- **Authentication:** Commercial agreement required
- **Key APIs:**
  - Organization API: company structure, production units, site coordinates, capacity
  - Batch API: stock data on farmed and cleaner fish, lifecycle events
  - Feed API: feeding amounts, feed types, daily profiles
  - Environment API: nitrogen, oxygen, salinity, temperature readings
  - Lice API: sea lice sampling data and active lice stages

---

### ICES DATRAS Web Services
- **Description:** International Council for the Exploration of the Sea trawl survey database providing bottom trawl survey data for stock assessment across the Baltic Sea, North Sea, Celtic Sea, Bay of Biscay, and Eastern Atlantic. Data includes catch-per-unit-effort (CPUE) indices used directly in stock assessments.
- **API Documentation / Web Services:** https://datras.ices.dk/WebServices/Webservices.aspx
- **SDKs/Libraries:**
  - R: icesDatras package (https://ices-tools-prod.r-universe.dev/icesDatras)
- **Standards:** SOAP/REST web services, standardised data exchange formats
- **Authentication:** Public access for validated datasets
- **Data Products:** HH (haul data), HL (length data), CA (age data), CPUE per age/length, age-length keys, survey indices

---

### OpenFisheries API
- **Description:** Open platform consolidating global fisheries landings datasets from FAO and national sources, designed for data science and analytics use cases. Lightweight REST API returning JSON.
- **API Documentation / GitHub:** https://github.com/OpenFisheries/api.openfisheries.org
- **Website:** https://www.openfisheries.org/
- **Standards:** REST/JSON (GET requests)
- **Authentication:** Public (no auth required)
- **Key Endpoints:**
  - Global landings: `http://openfisheries.org/api/landings.json`
  - Country-level data: `api/landings/countries.json`

---

### GDST Developer Portal (Global Dialogue on Seafood Traceability)
- **Description:** Developer documentation for implementing interoperable seafood traceability using GDST 1.2, which extends GS1 EPCIS 2.0 with seafood-specific Critical Tracking Events and Key Data Elements.
- **API Documentation:** https://developer.thegdst.org
- **Standards:** GS1 EPCIS 2.0, GS1 Digital Link, JSON-LD 1.1, HTTP
- **Authentication:** Per implementation (typically OAuth 2.0 or API key for partner exchanges)
- **Open Source Libraries:** Open Traceability (designed to facilitate GDST implementation)
- **Key Concepts:** Trace-backs, master data, first-mile capability testing, GDPR-aligned data minimisation

---

## Notes

**FLUX vs. AIS vs. VMS:**
These three data exchange mechanisms operate in parallel in fisheries management. VMS is mandatory for larger commercial vessels and sends encrypted position data to government authorities; AIS is an open broadcast used for maritime safety and publicly accessible (used by Global Fishing Watch); FLUX is the UN/CEFACT standard for exchanging structured fisheries activity data (logbooks, catch reports, inspections) between national systems and RFMOs. A comprehensive fishery management system should ideally support all three.

**Evolving EU Regulatory Landscape:**
EU Regulation 2023/2842 (amending 1224/2009) significantly expands ERS obligations from 2028 (all vessel sizes) and mandates Remote Electronic Monitoring for high-risk vessels. Any fishery management system targeting EU markets should design its data models around FLUX compliance and anticipate mandatory CCTV/sensor integration.

**Data Format Transition:**
The fisheries data domain is actively transitioning from XML (FLUX messages, EPCIS 1.x) toward JSON/JSON-LD (EPCIS 2.0, GDST 1.2, FishBase API). New systems should default to JSON-LD for traceability data exchange while maintaining XML compatibility for legacy government FLUX integrations.

**Open Source Foundations:**
FOCUS (https://www.focus.fish/) provides open-source, FLUX-compliant components (UnionVMS, e-sales notes, e-log viewer) under open licences that a new project could build upon or integrate with, avoiding re-implementation of core regulatory compliance infrastructure.
