# Getting started

Welcome to the Petstore Commerce API. The API is a plain JSON-over-HTTPS service
served from `https://api.petstore.example.com/api/v1`.

## Authentication

Authentication requirements vary by endpoint:

- **No authentication required:** `GET /api/v1/users`, `POST /api/v1/users`, `GET /api/v1/users/:id`, `PATCH /api/v1/users/:id`, `POST /api/v1/auth/login`
- **Bearer token required** (pass `Authorization: Bearer <token>` header): `GET /api/v1/orders`, `POST /api/v1/orders`, `GET /api/v1/orders/:orderId/items`

## Your first request

List the customers in your workspace:

```bash
curl "https://api.petstore.example.com/api/v1/users"
```

Create a customer:

```bash
curl -X POST "https://api.petstore.example.com/api/v1/users" \
  -H "Content-Type: application/json" \
  -d '{"name": "Ada Lovelace", "email": "ada@example.com"}'
```

The server responds with `201 Created` and the new user object:

```json
{
  "id": "usr_01",
  "name": "Ada Lovelace",
  "email": "ada@example.com"
}
```

## Errors

Errors are returned as a JSON object with a single `error` string:

```json
{ "error": "User not found" }
```
