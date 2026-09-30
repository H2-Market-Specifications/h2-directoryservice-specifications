# Directory Service JSON Schemas

The schemas use JSON Schema Draft 2020-12 and are expressed in YAML.

| File | Definitions |
|---|---|
| [directory-record.schema.yaml](directory-record.schema.yaml) | `DirectoryRecord`, `DirectoryRecordWrite`, `ManualOverrideRequest` and `DirectoryRecordDeletionResult`. |
| [ws-client-message.schema.yaml](ws-client-message.schema.yaml) | `subscribe`, `unsubscribe`, `availabilityStart`, `availabilityHeartbeat` and `availabilityStop`. |
| [ws-server-message.schema.yaml](ws-server-message.schema.yaml) | Acknowledgements, notifications, errors and a branch for unknown future server message types. |

## Validation

Parse the YAML and use a JSON Schema Draft 2020-12 validator. Select the appropriate root schema or named definition for the object being validated.

Register the schemas in a local or controlled resolver using their declared identifiers:

| Identifier | Local file |
|---|---|
| `urn:h2:directory:record:v1` | `directory-record.schema.yaml` |
| `urn:h2:directory:ws:client-message:v1` | `ws-client-message.schema.yaml` |
| `urn:h2:directory:ws:server-message:v1` | `ws-server-message.schema.yaml` |

The server message schema references `urn:h2:directory:record:v1#/$defs/DirectoryRecord`. Resolve it to the local DirectoryRecord schema. The PDF requires controlled artifact resolution; schemas must not be fetched from uncontrolled sources at runtime.

Enable format checking where supported. Schema validation does not verify signatures or enforce all server-side processing rules; consult the [DirectoryRecord PDF](../../../docs/directory-record/v0.9/) and the [JWS/WebSocket documentation](https://github.com/H2-Market-Specifications/h2-api-guidelines).

## Source of WebSocket Schemas

The client and server schemas are unchanged copies from [h2-api-guidelines, commit 62f9da2accfa15176f778c92354b7172a83b9ec4](https://github.com/H2-Market-Specifications/h2-api-guidelines/tree/62f9da2accfa15176f778c92354b7172a83b9ec4/specifications/websocket/v0.9), included with the DirectoryRecord schema to provide a complete local bundle.

[Repository overview](../../../README.md)
