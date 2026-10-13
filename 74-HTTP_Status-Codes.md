# HTTP Status Codes

HTTP status codes indicate the result of an HTTP request between a client and a server.

## 1. Categories of HTTP Status Codes

| Category | Meaning |
|---|---|
| 1xx | Informational |
| 2xx | Success |
| 3xx | Redirection |
| 4xx | Client Error |
| 5xx | Server Error |

## 2. 2xx — Success

| Code | Name | Meaning |
|---|---|---|
| 200 | OK | Request successful. |
| 201 | Created | Resource successfully created. |
| 202 | Accepted | Request accepted for processing. |
| 204 | No Content | Request successful; no response body. |

## 3. 3xx — Redirection

| Code | Name | Meaning |
|---|---|---|
| 301 | Moved Permanently | Resource permanently moved to another URL. |
| 302 | Found | Temporary redirection. |
| 304 | Not Modified | Resource has not changed; cached version can be used. |

## 4. 4xx — Client Errors

| Code | Name | Meaning |
|---|---|---|
| 400 | Bad Request | Invalid or malformed request. |
| 401 | Unauthorized | Authentication is missing or invalid. |
| 403 | Forbidden | Client lacks permission. |
| 404 | Not Found | Resource not found. |
| 405 | Method Not Allowed | HTTP method not supported for the endpoint. |
| 409 | Conflict | Request conflicts with the current resource state. |
| 410 | Gone | Resource is permanently unavailable. |
| 415 | Unsupported Media Type | Request content type is unsupported. |
| 422 | Unprocessable Content | Request data fails validation or cannot be processed. |
| 429 | Too Many Requests | Too many requests sent within a period. |

## 5. 5xx — Server Errors

| Code | Name | Meaning |
|---|---|---|
| 500 | Internal Server Error | Unexpected server-side error. |
| 501 | Not Implemented | Server does not support the requested functionality. |
| 502 | Bad Gateway | Upstream server returned an invalid response. |
| 503 | Service Unavailable | Server is temporarily unavailable. |
| 504 | Gateway Timeout | Upstream server did not respond in time. |

## 6. Important Differences

| Status Code | Difference |
|---|---|
| 400 | Request is invalid. |
| 401 | Authentication is missing or invalid. |
| 403 | Access is forbidden. |
| 404 | Resource cannot be found. |
| 405 | HTTP method is not allowed. |
| 409 | Request conflicts with the current state. |
| 422 | Request data fails validation. |
| 500 | Unexpected server error. |
| 502 | Invalid response from an upstream server. |
| 503 | Service is temporarily unavailable. |
| 504 | Upstream response timed out. |

## 7. HTTP Status Codes in FastAPI

FastAPI returns `200 OK` by default for successful requests unless another status code is specified.

| Status Code | FastAPI Usage |
|---|---|
| 200 | Successful GET request. |
| 201 | Successfully created a resource. |
| 204 | Successful request without a response body. |
| 400 | Invalid request. |
| 401 | Authentication error. |
| 403 | Permission denied. |
| 404 | Resource not found. |
| 422 | Request validation error. |
| 500 | Internal server error. |

Use `status_code` to specify a response status and `HTTPException` to return an HTTP error.

## Conclusion

HTTP status codes help clients understand whether a request succeeded, requires redirection, failed because of client input, or encountered a server error.