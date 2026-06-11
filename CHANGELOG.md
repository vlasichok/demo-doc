# Changelog

Historical record — entries describe the API as it was at release time.

## 1.4.0

- Added `DELETE /users/{userId}` for workspace cleanup.
- Documented the `per_page` query parameter on `GET /users`.

## 1.2.0

- Orders can now be filtered by `status` (`pending`, `paid`, `shipped`, `cancelled`).
- All endpoints remain public while the auth rollout is in beta.

## 1.0.0

- Initial public release: users, orders, login.
