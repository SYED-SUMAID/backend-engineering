# Backend Technology Basics

Backend development handles the logic, data, and operations behind an application.

## Core Technologies

| Technology | Purpose |
|---|---|
| Python | Programming language for backend logic |
| FastAPI | Python framework for building APIs |
| SQL | Language for working with relational databases |
| PostgreSQL | Relational database management system |
| SQLite | Lightweight, file-based database |
| SQLAlchemy | Python SQL toolkit and ORM |
| Pydantic | Data validation and settings management |
| Jinja2 | Template engine for generating HTML |
| Uvicorn | ASGI server for running FastAPI |
| Git | Version control system |
| Docker | Packages applications into containers |
| Jenkins | Automates build, test, and deployment pipelines |
| Ansible | Automates configuration and server management |

## How a Backend Works

1. **Client:** Sends an HTTP request.
2. **API:** Receives the request through an endpoint.
3. **Backend logic:** Processes the request.
4. **Database:** Stores or retrieves data when needed.
5. **Response:** Returns a result, often as JSON.

## API Architecture Types

An API allows different applications or services to communicate.

| Type | Full Form | Purpose |
|---|---|---|
| REST | Representational State Transfer | Builds web APIs using HTTP |
| SOAP | Simple Object Access Protocol | Exchanges structured XML messages |
| GraphQL | Graph Query Language | Lets clients request specific data |
| WebSocket | No official full form | Enables real-time, two-way communication |
| gRPC | gRPC Remote Procedure Calls | Enables efficient communication between services |

## Important Backend Concepts

| Concept | Meaning |
|---|---|
| API | Interface for communication between software systems |
| Endpoint | URL where an API resource or operation is available |
| HTTP | Hypertext Transfer Protocol |
| JSON | JavaScript Object Notation |
| CRUD | Create, Read, Update, Delete |
| ORM | Object-Relational Mapping |
| Authentication | Verifies who a user is |
| Authorization | Determines what a user can access |
| Middleware | Processes requests or responses during their lifecycle |
| Environment Variables | Store configuration outside application code |
| Database | Stores and organizes application data |
| HTTP Status Codes | Indicate the outcome of an HTTP request |

## Common HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create or submit data |
| PUT | Replace a resource |
| PATCH | Partially update a resource |
| DELETE | Delete a resource |

## Common HTTP Status Codes

| Code | Meaning |
|---|---|
| 200 | OK |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 422 | Unprocessable Content |
| 500 | Internal Server Error |

## Key Takeaway

A backend combines application logic, APIs, databases, and supporting tools to process requests and deliver responses. Understanding these fundamentals provides a foundation for building, testing, and deploying backend applications.