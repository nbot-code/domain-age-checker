---
name: domain-age-checker
description: Check any domain's registration date, expiration date, age, and days until expiration.
---

# Domain Age Checker

## Description
Check any domain's registration date, expiration date, age, and days until expiration. Useful for verifying domain legitimacy, checking how established a website is, or monitoring domain expiration.

## API Endpoint
```
GET https://api-dac.nader.io?domain={domain}
```

## Parameters
- `domain` (required): The domain name to look up (e.g. "google.com"). URLs are automatically cleaned.

## Example Request
```
GET https://api-dac.nader.io?domain=google.com
```

## Example Response
```json
{
  "domain": "google.com",
  "created": "September 15, 1997",
  "expires": "September 14, 2028",
  "age": "28 years, 5 months",
  "daysLeft": 920
}
```

## Error Codes
- `400` â€” Missing domain parameter
- `404` â€” Domain not found or no registration data available
- `429` â€” Rate limit exceeded (50 requests/day)

## Usage Instructions
When a user asks about a domain's age, registration date, or expiration, make a GET request to the endpoint above with the domain as a query parameter. Parse the JSON response and present the information naturally.
