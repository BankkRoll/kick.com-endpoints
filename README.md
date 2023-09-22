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

## How to Use the JSON Data

## Reading the JSON Data

### Python

```python
import json

# Read the JSON file
with open('kick_com_routes.json', 'r') as f:
    kick_com_data = json.load(f)

# Example: Print out the loaded data
print(kick_com_data)
```

### JavaScript (Node.js)

```javascript
const fs = require('fs');

// Read the JSON file
const kickComData = JSON.parse(fs.readFileSync('kick_com_routes.json', 'utf-8'));

// Example: Print out the loaded data
console.log(kickComData);
```

## Constructing a Full URL

### Python

Here's a full example in Python that includes reading the JSON file:

```python
import json

# Read the JSON file
with open('kick_com_routes.json', 'r') as f:
    kick_com_data = json.load(f)

# Get the base URL and route URI
base_url = kick_com_data['url']
route_uri = kick_com_data['routes']['l5-swagger.default.api']['GET']

# Construct the full URL
full_url = f"{base_url}{route_uri}"

# Output: "https://kick.com/documentation"
print(full_url)
```

### JavaScript (Node.js)

Here's a full example in JavaScript that includes reading the JSON file:

```javascript
const fs = require('fs');

// Read the JSON file
const kickComData = JSON.parse(fs.readFileSync('kick_com_routes.json', 'utf-8'));

// Get the base URL and route URI
const baseUrl = kickComData.url;
const routeUri = kickComData.routes['l5-swagger.default.api'].GET;

// Construct the full URL
const fullUrl = `${baseUrl}${routeUri}`;

// Output: "https://kick.com/documentation"
console.log(fullUrl);
```
