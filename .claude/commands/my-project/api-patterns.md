# API Patterns Guide

Generate or review API endpoints following our standard patterns.

## API Style: [REST | GraphQL | tRPC | gRPC]

## Standard Endpoint Structure

### Request Flow
```
[CLIENT] → [MIDDLEWARE] → [HANDLER] → [SERVICE] → [REPOSITORY] → [DATABASE]
```

### Handler Template
```[LANGUAGE]
[HANDLER_TEMPLATE]
// e.g. for Go + Gin:
// func (h *Handler) GetUser(c *gin.Context) {
//     id := c.Param("id")
//     user, err := h.service.GetUser(c.Request.Context(), id)
//     if err != nil { ... }
//     c.JSON(http.StatusOK, user)
// }
```

### Response Format
```json
{
  "data": "[RESPONSE_DATA]",
  "meta": {
    "page": "[IF_PAGINATED]",
    "total": "[IF_PAGINATED]"
  },
  "error": {
    "code": "[ERROR_CODE_FORMAT]",
    "message": "[USER_FACING_MESSAGE]"
  }
}
```

### Error Codes
| HTTP Status | Usage                          |
|-------------|--------------------------------|
| 200         | Success                        |
| 201         | Created                        |
| 400         | Validation error               |
| 401         | Not authenticated              |
| 403         | Not authorized                 |
| 404         | Resource not found             |
| 409         | Conflict / duplicate           |
| 422         | Unprocessable entity           |
| 500         | Internal server error          |

### Validation
- Use [VALIDATION_LIBRARY] for input validation
- Validate at: [handler | middleware | service] layer
- Required fields: return 400 with field-level errors

### Authentication & Authorization
- Auth method: [JWT | Session | API Key | OAuth2]
- Auth middleware: [MIDDLEWARE_NAME]
- Role-based access: [RBAC_PATTERN]

### Pagination
- Style: [cursor | offset]
- Default page size: [PAGE_SIZE]
- Max page size: [MAX_PAGE_SIZE]

## Instructions

When creating a new API endpoint:
1. Create handler in [HANDLERS_DIR]
2. Create service method in [SERVICES_DIR]
3. Create repository method in [REPOS_DIR] (if DB access needed)
4. Add route in [ROUTES_FILE]
5. Add input validation using [VALIDATION_LIBRARY]
6. Add tests for handler, service, and repository layers
7. Update API documentation in [API_DOCS_LOCATION]
