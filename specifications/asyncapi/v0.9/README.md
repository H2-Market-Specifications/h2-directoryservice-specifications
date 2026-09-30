# Directory Service AsyncAPI

[AsyncAPI YAML](asyncapi-directory-websocket.yaml) — AsyncAPI 3.0.0, contract version 1.0.0, document bundle v0.9.

The description covers the directory service WebSocket channel and its client and server messages. Operations use the directory service's perspective:

| Operation | Direction |
|---|---|
| `receiveClientMessages` | Client → directory service |
| `sendServerMessages` | Directory service → client |

The description references the [local message and DirectoryRecord schemas](../../schemas/v0.9/). Keep the repository directory layout when using AsyncAPI tooling and configure schema identifier resolution as described in the schema README.

Notifications are delivered at most once, without resume. The API description requires resynchronization through the synchronous HTTP API after each connection is established.

Related: [OpenAPI](../../openapi/v0.9/), [DirectoryRecord PDF](../../../docs/directory-record/v0.9/) and [WebSocket/JWS documentation](https://github.com/H2-Market-Specifications/h2-api-guidelines).

[Repository overview](../../../README.md)
