# API Validation Checklist (Enhanced)

## STATUS CODE
* Correct code: 200, 201, 204 for success
* Error codes: 400, 401, 403, 404, 422
* Edge cases: 429 rate limit, 503 unavailable

## RESPONSE BODY
* Schema match: All required fields present
* Data types: String, number, boolean, array
* Null handling: Nullable fields vs missing fields
* Nested objects: Validate deep structure too
* Array length: Empty, single, paginated
* Default values: Verify defaults when omitted

## RESPONSE HEADERS
* Content-Type: application/json expected
* Cache-Control: Correct caching behavior
* Rate limit headers: X-RateLimit-Remaining
* Pagination: Link, X-Total-Count headers

## ERROR RESPONSES
* Error format: Consistent body shape; validate error body against schema
* Error messages: Helpful, not exposing internals
* Validation errors: Field-level error details
* Stack traces: Must NOT leak in production

## PERFORMANCE
* Response time: Under SLA threshold
* Payload size: Not returning extra data
* N+1 queries: List endpoints optimized

## SECURITY
* Auth required: 401 without valid token
* Authorization: 403 for wrong permissions
* Object-level authorization (IDOR): Ensure no other user's data is exposed
  * Note: IDOR stands for insecure direct object references, a type of access control 
    vulnerability that arises when an application uses user-supplied input to access objects directly
* Security headers: CORS, X-Content-Type-Options, X-Frame-Options

