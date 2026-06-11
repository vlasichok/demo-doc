# Working with users

The Users API lets you list, create, and update the people in your workspace.

> **Authentication:** No authentication is required for any Users API endpoint.

## Listing users

No authentication is required.

Results are paginated. Use `pageSize` to control the page size:

```bash
curl "https://api.petstore.example.com/api/v1/users?pageSize=50"
```

### Query parameters

| Name     | Type    | Required | Description                       |
|----------|---------|----------|-----------------------------------|
| pageSize | integer | no       | Number of users per page (max 100). |
| limit    | integer | no       | Maximum number of users to return. |
| role     | string  | no       | Filter by role (`admin`, `member`). |

## Fetching a single user

No authentication is required.

```bash
curl "https://api.petstore.example.com/api/v1/users/{id}"
```

The response contains the user's profile:

```json
{
  "id": "7f96b3a2-9c01-4f8e-9a51-1f2d3c4b5a69",
  "email": "ada@example.com",
  "name": "Ada Lovelace",
  "role": "member",
  "createdAt": "2024-01-15T10:30:00.000Z"
}
```

## Updating a user

No authentication is required.

Send a partial body with the fields you want to change:

```bash
curl -X PATCH "https://api.petstore.example.com/api/v1/users/{id}" \
  -H "Content-Type: application/json" \
  -d '{"name": "Ada King"}'
```
