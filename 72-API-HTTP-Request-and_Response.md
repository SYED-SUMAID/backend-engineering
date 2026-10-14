# HTTP Requests and Responses

HTTP defines how clients and servers communicate. A client sends an HTTP request, and the server processes it and returns an HTTP response.

## 1. HTTP Request

An HTTP request is a message sent by a client to a server to retrieve data or perform an operation.

### Components

| Component | Description | Example |
|---|---|---|
| Method | Defines the intended action | `GET`, `POST` |
| URL | Identifies the target resource | `/api/polls` |
| Headers | Provide additional information | `Content-Type: application/json` |
| Path Parameters | Identify a specific resource | `/api/polls/1` |
| Query Parameters | Filter or modify a data lookup | `/api/polls?limit=10` |
| Body | Contains data sent to the server | JSON payload |

### Example Request

    POST /api/polls HTTP/1.1
    Host: localhost:8000
    Content-Type: application/json

    {
        "question": "Which technology do you prefer?"
    }

The request uses `POST` to submit data to the `/api/polls` endpoint.

## 2. HTTP Response

An HTTP response is the message a server sends back after processing a request.

### Components

| Component | Description | Example |
|---|---|---|
| Status Code | Indicates the request outcome | `200 OK` |
| Headers | Provide response metadata | `Content-Type: application/json` |
| Body | Contains the returned data, if any | JSON response |

### Example Response

    HTTP/1.1 201 Created
    Content-Type: application/json

    {
        "id": 1,
        "question": "Which technology do you prefer?"
    }

The server returns `201 Created` to indicate that the poll was successfully created.

## 3. Request and Response Headers

Headers carry metadata about a request or response.

| Header | Purpose |
|---|---|
| `Content-Type` | Specifies the media type of the message body |
| `Accept` | Indicates the response formats the client can accept |
| `Authorization` | Carries authentication credentials |
| `Cache-Control` | Defines caching instructions |
| `User-Agent` | Identifies the client software |

### Example

    Content-Type: application/json
    Accept: application/json

`Content-Type` describes the data being sent, while `Accept` describes the response formats the client can handle.

## 4. Request Body and JSON

A request body carries data to the server. APIs commonly use JSON to exchange structured data.

### Example JSON Body

    {
        "question": "Choose your preferred framework",
        "options": ["FastAPI", "Django", "Flask"]
    }

A server can validate this data before processing it.

Request bodies are commonly used with `POST`, `PUT`, and `PATCH`. Whether a method uses a body depends on the API design and HTTP semantics.

## 5. Path and Query Parameters

### Path Parameters

Path parameters identify a specific resource.

Example:

    GET /api/polls/5

Here, `5` identifies the poll.

### Query Parameters

Query parameters provide additional instructions, such as filtering, sorting, or pagination.

Example:

    GET /api/polls?limit=10&offset=0

Here, `limit` specifies the maximum number of results, while `offset` specifies where the results begin.

## 6. HTTP Status Codes

Status codes indicate the outcome of a request.

| Code | Meaning | Common Use |
|---|---|---|
| `200` | OK | Request completed successfully |
| `201` | Created | Resource created successfully |
| `204` | No Content | Successful response without a body |
| `400` | Bad Request | Invalid request |
| `401` | Unauthorized | Authentication is required or invalid |
| `403` | Forbidden | Access is not permitted |
| `404` | Not Found | Resource does not exist |
| `405` | Method Not Allowed | HTTP method is unsupported for the resource |
| `409` | Conflict | Request conflicts with the current resource state |
| `422` | Unprocessable Content | Request content failed validation |
| `429` | Too Many Requests | Rate limit exceeded |
| `500` | Internal Server Error | Unexpected server-side failure |
| `503` | Service Unavailable | Server is temporarily unable to handle the request |

## 7. HTTP Requests in FastAPI

FastAPI uses route decorators to define endpoints and automatically converts returned dictionaries and lists into JSON responses.

    from fastapi import FastAPI

    app = FastAPI()

    @app.get("/api/polls")
    def get_polls():
        return {
            "polls": [
                {"id": 1, "question": "Learn FastAPI?"},
                {"id": 2, "question": "Learn Docker?"}
            ]
        }

    @app.post("/api/polls")
    def create_poll(data: dict):
        return {
            "message": "Poll received",
            "poll": data
        }

### Example POST Request

Send a `POST` request to `/api/polls` with this JSON body:

    {
        "question": "Which technology should we learn?"
    }

FastAPI receives the body through the `data` parameter and returns a JSON response.

For production applications, use Pydantic models instead of unrestricted dictionaries to validate request data.

## 8. Request and Response Flow

1. The client sends an HTTP request.
2. The server receives the request at the appropriate endpoint.
3. The backend validates and processes the input.
4. The server performs any required operations, such as database queries.
5. The server returns an HTTP response containing a status code, headers, and optionally a body.
6. The client processes the response.

## Key Points

- Requests travel from the client to the server; responses travel back to the client.
- HTTP methods define the intended operation.
- Headers provide metadata about messages.
- Request bodies commonly carry JSON data.
- Path parameters identify resources; query parameters help filter or configure requests.
- Status codes communicate the outcome of a request.
- FastAPI supports JSON responses and request validation.