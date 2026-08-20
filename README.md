# GS1 (gs1)

GS1 (GS1 AISBL) is the not-for-profit, neutral standards body headquartered at Avenue Louise 523, 1050 Brussels, Belgium, that maintains the identification keys and data standards the rest of the supply chain hangs its transactions on — GTIN, GLN, SSCC, GINC and GSIN, the barcode and EPC/RFID capture standards, EPCIS and the Core Business Vocabulary for supply chain visibility events, GS1 Digital Link, and EANCOM, GS1's own subset of UN/EDIFACT. GS1 does not run a commercial logistics service; it sits underneath every party in the chain, defining the identifiers a shipper, forwarder, carrier, terminal, customs authority and last-mile network all quote at each other. Its API posture is unusually open for a standards body: the full standards library is downloadable free as PDF from ref.gs1.org with no login, EPCIS 2.0.1 ships a normative OpenAPI 3.0.3 REST binding plus JSON Schema, XSD, WSDL, SHACL and JSON-LD ontologies, and GS1 AISBL itself operates a live, unauthenticated GS1-Conformant Resolver at id.gs1.org. What is gated is the other half — issuing GS1 identifiers and querying the Verified by GS1 registry are federated to national GS1 Member Organisations and sold under paid membership or a commercial API subscription, not offered self-serve by the Global Office.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/gs1/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/gs1/refs/heads/main/apis.yml)

## Tags

- Logistics
- Supply Chain
- Belgium
- Standards
- Track and Trace
- Traceability
- Identifiers
- Barcodes
- Freight Forwarding
- Retail

## Timestamps

- **Created:** 2026-07-30
- **Modified:** 2026-07-30

## APIs

### GS1 EPCIS 2.0 REST API

The normative REST binding of the GS1 EPCIS 2.0 standard — the sector's supply chain visibility event interface, describing what happened to an object, when, where and why, using Core Business Vocabulary terms. GS1 publishes the contract (OpenAPI 3.0.3, 29 paths) rather than hosting a repository: capture (POST /capture), query (GET /events plus resource-scoped views by epc, bizStep, bizLocation, readPoint, disposition and eventType), named queries (POST /queries), and mandatory webhook subscriptions (POST /queries/{queryName}/subscriptions) where the client supplies a `dest` callback URL and a signatureToken the server echoes back in a GS1-Signature header. Implementers host their own base URL; the specification declares no `servers` block.

- **Human URL:** [https://ref.gs1.org/standards/epcis/](https://ref.gs1.org/standards/epcis/)

#### Tags

- EPCIS
- Supply Chain Visibility
- Track and Trace
- Traceability
- Events
- Standards

#### Properties

- [OpenAPI](openapi/gs1-epcis-2-0-1-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/gs1-epcis-2-0-1.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gs1-epcis-2-0-1.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/gs1-epcis-json-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/gs1-epcis-query-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Specification](https://ref.gs1.org/standards/epcis/2.0.1/)
- [Documentation](https://www.gs1.org/standards/epcis)
- [Artefacts](https://ref.gs1.org/standards/epcis/artefacts)
- [Vocabulary](https://ref.gs1.org/cbv/)
- [Source Code](https://github.com/gs1/EPCIS)

### GS1 Digital Link Resolver (id.gs1.org)

GS1 AISBL's own live, unauthenticated GS1-Conformant Resolver, implementing the GS1-Conformant Resolver Standard 1.2.0. It takes a GS1 Digital Link URI built from a GS1 identification key and returns either a 303 redirect to the brand owner's target resource or, on request, an RFC 9264 linkset enumerating every registered link type for that key. The resolver description document at /.well-known/gs1resolver declares the supported primary keys — 00 (SSCC), 01 (GTIN), 253 (GDTI), 255 (GCN), 401 (GINC), 402 (GSIN), 414/415/417 (GLN), 8003 (GRAI), 8004 (GIAI), 8006 (ITIP), 8010 (CPID), 8013 (GMN) and 8017/8018 (GSRN) — which includes the consignment and shipment keys logistics parties actually quote. No key, no signup and no contract is required to call it.

- **Human URL:** [https://ref.gs1.org/standards/resolver/](https://ref.gs1.org/standards/resolver/)
- **Base URL:** `https://id.gs1.org`

#### Tags

- GS1 Digital Link
- Resolver
- Identifiers
- Linked Data
- Track and Trace
- Standards

#### Properties

- [Specification](https://ref.gs1.org/standards/resolver/1.2.0/)
- [JSON Schema](json-schema/gs1-resolver-linkset-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/gs1-resolver-description-file-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Well Known](well-known/gs1-resolver-description.json)
- [JSON-LD](json-ld/gs1-resolver-linkset-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](json-ld/gs1-web-vocabulary-linktypes.json)
- [Documentation](https://www.gs1.org/standards/gs1-digital-link)
- [Artefacts](https://ref.gs1.org/standards/resolver/artefacts)
- [Test Suite](https://ref.gs1.org/test-suites/resolver/)
- [Source Code](https://github.com/gs1/GS1_DigitalLink_Resolver_CE)
- [Postman Collection](collections/gs1-epcis-2-0-1.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/gs1-epcis-2-0-1.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Issue Tracker](https://github.com/gs1/EPCIS/issues)
- [Code Of Conduct](https://github.com/gs1/EPCIS/blob/master/CODE_OF_CONDUCT.md)
- [Website](https://www.gs1.org/)
- [Documentation](https://ref.gs1.org/)
- [Specifications Repository](https://ref.gs1.org/standards/)
- [GitHub Organization](https://github.com/gs1)
- [Vocabulary](https://ref.gs1.org/voc/)
- [Governance](https://www.gs1.org/standards/development-work-groups)
- [Standard](https://ref.gs1.org/standards/genspecs/)
- [Standard](https://ref.gs1.org/standards/digital-link/uri-syntax/)
- [Standard](https://ref.gs1.org/standards/cbv/)
- [Standard](https://ref.gs1.org/standards/eancom/)
- [Standard](https://ref.gs1.org/standards/edi-business-terms/)
- [Standard](https://ref.gs1.org/standards/logistics-interoperability/)
- [Standard](https://ref.gs1.org/standards/tds/)
- [Standard](https://ref.gs1.org/standards/gdm/)
- [Tools](https://ref.gs1.org/tools/gs1-barcode-syntax-resource/)
- [Registry](https://www.gs1.org/services/verified-by-gs1)
- [Industry](https://www.gs1.org/industries/transport-and-logistics)
- [LinkedIn](https://www.linkedin.com/company/gs1)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
