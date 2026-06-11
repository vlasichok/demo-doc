# Getting started

Welcome to the Petstore Commerce API. The API is a plain JSON-over-HTTPS service
served from `https://api.petstore.example.com/api/v1`.

## Authentication

All endpoints are public; no authentication required.

## Your first request

List the users in your workspace:

```bash
curl "https://api.petstore.example.com/api/v1/users"
```

Create a user:

```bash
curl -X POST "https://api.petstore.example.com/api/v1/users" \
  -H "Content-Type: application/json" \
  -d '{"name": "Ada Lovelace", "email": "ada@example.com"}'
```

## Errors

Errors are returned as a JSON object with a single `error` string:

```json
{ "error": "User not found" }
```
