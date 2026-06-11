# Working with users

The Users API lets you list, create, and update the people in your workspace.

## Listing users

Results are paginated. Use `per_page` to control the page size:

```bash
curl "https://api.petstore.example.com/api/v1/users?per_page=50"
```

### Query parameters

| Name     | Type    | Required | Description                       |
|----------|---------|----------|-----------------------------------|
| per_page | integer | no       | Number of users per page (max 100). |
| limit    | string  | no       | Maximum number of users to return. |
| role     | string  | no       | Filter by role (`admin`, `member`). |

## Fetching a single user

```bash
curl "https://api.petstore.example.com/api/v1/users/{userId}"
```

The response contains the user's profile:

```json
{
  "id": "7f96b3a2-9c01-4f8e-9a51-1f2d3c4b5a69",
  "email": "ada@example.com",
  "name": "Ada Lovelace",
  "role": "member"
}
```

## Updating a user

Send a partial body with the fields you want to change:

```bash
curl -X PATCH "https://api.petstore.example.com/api/v1/users/{userId}" \
  -H "Content-Type: application/json" \
  -d '{"name": "Ada King"}'
```
