# HTTP Request Methods

HTTP request methods define what a client wants to do with a resource on a server. They are commonly used when building REST APIs and backend applications.

## Methods

| Method | Description | Common Use |
|---|---|---|
| GET | Retrieves data without changing the resource. | Fetch polls or user details |
| POST | Sends data to the server to create a resource or perform an operation. | Create a poll or submit a vote |
| PUT | Replaces a resource with the provided representation. | Replace poll details |
| PATCH | Updates specific fields of an existing resource. | Change a poll question |
| DELETE | Requests the removal of a resource. | Delete a poll |
| HEAD | Works like GET but returns no response body. | Check resource headers |
| OPTIONS | Returns communication options supported by a resource. | Check supported methods |
| TRACE | Returns the received request for diagnostic purposes. | Troubleshoot request handling |
| CONNECT | Establishes a tunnel to a server, commonly through a proxy. | Create an HTTPS tunnel |

## Commonly Used Methods

### GET
Used to retrieve information from an API.

Example: `GET /api/polls`

Returns a list of available polls.

### POST
Used to submit data to the server. It commonly creates resources or triggers operations.

Example: `POST /api/polls`

Creates a new poll.

### PUT
Used to replace an existing resource with a new representation. Depending on the API, it may also create a resource at a known URL.

Example: `PUT /api/polls/1`

Replaces the details of poll `1`.

### PATCH
Used to update selected fields without replacing the entire resource.

Example: `PATCH /api/polls/1`

Updates specific details of poll `1`.

### DELETE
Used to request the removal of a resource.

Example: `DELETE /api/polls/1`

Deletes poll `1`.

## Safe and Idempotent Methods

These properties describe how HTTP methods are intended to behave.

- **Safe:** The request is not intended to change the server's application state.
- **Idempotent:** Repeating the same request has the same intended effect as making it once.

| Method | Safe | Idempotent |
|---|---|---|
| GET | Yes | Yes |
| HEAD | Yes | Yes |
| OPTIONS | Yes | Yes |
| TRACE | Yes | Yes |
| POST | No | Generally no |
| PUT | No | Yes |
| PATCH | No | Not necessarily |
| DELETE | No | Yes |
| CONNECT | No | No |

## HTTP Methods in FastAPI

FastAPI provides decorators for defining API endpoints.

    from fastapi import FastAPI

    app = FastAPI()

    @app.get("/polls")
    def get_polls():
        return {"message": "Retrieve polls"}

    @app.post("/polls")
    def create_poll():
        return {"message": "Create a poll"}

    @app.put("/polls/{poll_id}")
    def replace_poll(poll_id: int):
        return {"message": f"Replace poll {poll_id}"}

    @app.patch("/polls/{poll_id}")
    def update_poll(poll_id: int):
        return {"message": f"Update poll {poll_id}"}

    @app.delete("/polls/{poll_id}")
    def delete_poll(poll_id: int):
        return {"message": f"Delete poll {poll_id}"}

## Key Points

- GET retrieves resources; POST submits data or performs operations.
- PUT replaces a resource, while PATCH updates selected fields.
- DELETE requests the removal of a resource.
- HEAD retrieves headers without a response body.
- OPTIONS identifies supported communication options.
- TRACE and CONNECT have specialized uses and are uncommon in typical application APIs.
- An HTTP method defines the intended operation, while the server determines how that operation is handled.