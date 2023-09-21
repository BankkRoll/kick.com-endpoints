# kick.com-endpoints

```json
{
  "url": "https://kick.com/",
  "port": null,
  "defaults": {},
  "routes": {
    "l5-swagger.default.api": {
      "GET": "documentation",
      "HEAD": "documentation"
    },
    // ... more routes in endpoints.json
  }
}
```

## Components

- `url`: Base URL for all routes
- `port`: Port number, if applicable
- `defaults`: Default parameters for routes
- `routes`: Object containing route names as keys and their details as values

### Route Details

Each route has an HTTP method (e.g., `GET`, `POST`, `HEAD`) as its key, and the corresponding URI as its value.

## How to Use

To construct a full URL for a specific route and method:

```javascript
const fullURL = \`\${kickCom.url}\${kickCom.routes['route_name']['HTTP_METHOD']}\`;
```

Replace `route_name` and `HTTP_METHOD` with the desired route name and HTTP method.

```javascript
// Example
const fullURL = \`\${kickCom.url}\${kickCom.routes['l5-swagger.default.api']['GET']}\`;
// Outputs: "https://kick.com/documentation"
```
