# Working with customers

The Customers API lets you list, create, and update the people in your workspace.

## Listing customers

No authentication is required.

Results are paginated. Use `per_page` to control the page size:

```bash
curl "https://api.petstore.example.com/api/v1/users?per_page=50"
```

### Query parameters

| Name     | Type    | Required | Description                       |
|----------|---------|----------|-----------------------------------|
| per_page | integer | no       | Number of customers per page (max 100). |
| limit    | integer | no       | Maximum number of customers to return. |
| role     | string  | no       | Filter by role (`admin`, `member`). |

## Creating a customer

No authentication is required.

```bash
curl -X POST "https://api.petstore.example.com/api/v1/users" \
  -H "Content-Type: application/json" \
  -d '{"email": "ada@example.com", "name": "Ada Lovelace", "role": "member"}'
```

A successful request returns the created customer:

```json
{
  "id": "7f96b3a2-9c01-4f8e-9a51-1f2d3c4b5a69",
  "email": "ada@example.com",
  "name": "Ada Lovelace",
  "role": "member",
  "createdAt": "2024-01-15T10:30:00Z"
}
```

### Request body

| Name  | Type   | Required | Description              |
|-------|--------|----------|--------------------------|
| email | string | yes      | The customer's email address. |
| name  | string | yes      | The customer's display name. |
| role  | string | no       | Role for the customer (`admin`, `member`). |

## Fetching a single customer

```bash
curl "https://api.petstore.example.com/api/v1/users/{id}"
```

The response contains the customer's profile:

```json
{
  "id": "7f96b3a2-9c01-4f8e-9a51-1f2d3c4b5a69",
  "email": "ada@example.com",
  "name": "Ada Lovelace",
  "role": "member"
}
```

## Updating a customer

No authentication is required.

Send a partial body with the fields you want to change:

```bash
curl -X PATCH "https://api.petstore.example.com/api/v1/users/{id}" \
  -H "Content-Type: application/json" \
  -d '{"name": "Ada King"}'
```
