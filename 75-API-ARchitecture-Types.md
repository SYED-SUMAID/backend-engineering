# API Architecture Types

API architecture defines how applications communicate and exchange data.

## 1. REST API
**Full Form:** Representational State Transfer

REST uses HTTP methods to interact with resources.

- Commonly uses JSON.
- Supports GET, POST, PUT, and DELETE.
- Uses stateless communication.

**Example:** Web applications and CRUD APIs.

## 2. SOAP API
**Full Form:** Simple Object Access Protocol

SOAP is a protocol for exchanging structured messages between applications.

- Uses XML messages.
- Follows strict communication standards.
- Common in enterprise systems.

**Example:** Banking and financial services.

## 3. GraphQL API
**Full Form:** Graph Query Language

GraphQL allows clients to request exactly the data they need.

- Uses a defined schema.
- Supports queries and mutations.
- Reduces unnecessary data retrieval.

**Example:** Fetching a user's name and email without retrieving their entire profile.

## 4. WebSocket API
**Full Form:** WebSocket has no official full form.

WebSocket provides continuous, two-way communication between clients and servers.

- Supports real-time data exchange.
- Allows both sides to send messages.
- Maintains a persistent connection.

**Example:** Chat applications and live notifications.

## 5. gRPC
**Full Form:** gRPC Remote Procedure Calls

gRPC is a high-performance framework for communication between services.

- Commonly uses Protocol Buffers.
- Typically communicates over HTTP/2.
- Supports efficient service-to-service communication.

**Example:** Communication between backend microservices.

## Comparison

| Type | Full Form | Common Use |
|---|---|---|
| REST | Representational State Transfer | Web APIs |
| SOAP | Simple Object Access Protocol | Enterprise systems |
| GraphQL | Graph Query Language | Flexible data queries |
| WebSocket | No official full form | Real-time communication |
| gRPC | gRPC Remote Procedure Calls | Microservices |

## Key Takeaway

Each approach serves a different purpose. Choose based on your application's requirements and communication needs.