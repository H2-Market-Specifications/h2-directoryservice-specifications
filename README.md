# H2 Directory Service Specifications v0.9

## H₂-Verzeichnisdienst: Directory Service und DirectoryRecord (Deutsch)

Dieses Repository veröffentlicht die Spezifikation des zentralen Verzeichnisdienstes für die Wasserstoffmarktkommunikation (H₂) in Deutschland. Sie beschreibt DirectoryRecords, Datenmodell und Datenhoheit sowie die synchronen HTTP-Schnittstellen und die WebSocket-Kommunikation. Enthalten sind die DirectoryRecord-Spezifikation als PDF sowie OpenAPI-, AsyncAPI- und JSON-/YAML-Schemas für Marktteilnehmer, Softwareanbieter und Entwickler. Veröffentlichte Dokument- und Bundle-Version: 0.9.

Documentation and machine-readable specifications for the central hydrogen market directory service. These materials are intended for market participants, software providers and developers implementing directory record queries, maintenance and WebSocket communication.

## Documents and Specifications

| Artifact | Purpose | File |
|---|---|---|
| DirectoryRecord specification | Data model, data ownership, synchronous operations and WebSocket integration. | [PDF v0.9](docs/directory-record/v0.9/DirectoryRecord_Spezifikation_v0.9.pdf) |
| OpenAPI 3.1.2 | Synchronous HTTP interface for querying and maintaining directory records. | [openapi-directory-service.yaml](specifications/openapi/v0.9/openapi-directory-service.yaml) |
| AsyncAPI 3.0.0 | WebSocket channel, messages and communication operations. | [asyncapi-directory-websocket.yaml](specifications/asyncapi/v0.9/asyncapi-directory-websocket.yaml) |
| DirectoryRecord schema | Record, write object, manual override request and deletion result definitions. | [directory-record.schema.yaml](specifications/schemas/v0.9/directory-record.schema.yaml) |
| WebSocket client schema | Messages from clients to the directory service. | [ws-client-message.schema.yaml](specifications/schemas/v0.9/ws-client-message.schema.yaml) |
| WebSocket server schema | Messages from the directory service to clients. | [ws-server-message.schema.yaml](specifications/schemas/v0.9/ws-server-message.schema.yaml) |

## Getting Started

Read the DirectoryRecord PDF for the data model and processing requirements. Use the OpenAPI description to implement the synchronous interface and the AsyncAPI description for WebSocket integration.

The synchronous resource is `/records/{providerId}/{apiId}/{majorVersion}` with GET, PUT, PATCH and DELETE operations. In the AsyncAPI document, operations are described from the directory service's perspective: `receive` means client to server, and `send` means server to client.

Keep the complete specification bundle together when using local tools: OpenAPI and AsyncAPI reference the YAML schemas through relative paths. The schemas use JSON Schema Draft 2020-12. See the [schema documentation](specifications/schemas/v0.9/) for URN resolution.

Server host defaults in the API descriptions are placeholders. Use the host for the intended test or production environment.

## Versions and Dependencies

The document and bundle directory version is **0.9**. The supplied PDF identifies the OpenAPI and AsyncAPI contract versions as **1.0.0**; schema identifiers use `v1`. These identifiers are retained as declared in the source artifacts.

The [API Guideline, JWS specification and WebSocket specification](https://github.com/H2-Market-Specifications/h2-api-guidelines) provide the related communication requirements. Schema validation checks data structure and values; it does not replace authorization, state processing or cryptographic signature verification.

## Repository Structure

| Directory | Contents |
|---|---|
| `docs/directory-record/v0.9/` | DirectoryRecord PDF specification. |
| `specifications/openapi/v0.9/` | Synchronous API description. |
| `specifications/asyncapi/v0.9/` | WebSocket API description. |
| `specifications/schemas/v0.9/` | DirectoryRecord and WebSocket message schemas. |

## Questions and Feedback

Open a [repository issue](https://github.com/H2-Market-Specifications/h2-directoryservice-specifications/issues) with the affected document or schema, version and section.
