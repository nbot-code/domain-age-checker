---
name: domain-age-checker
description: Look up a domain's registration date, expiration date, age, and days until expiration. Use when a user asks how old a site or domain is, when a domain was registered, when it expires, whether it looks established, or whether a URL/domain looks credible based on age.
---

# Domain Age Checker

Use this skill to check domain age and registration details through the Domain Age Checker API.

## Endpoint

```text
GET https://api-dac.nader.io?domain={domain}
```

## Input

- Accept a bare domain like `google.com` or a full URL like `https://google.com/some/path`.
- Extract and normalize the domain before calling the API.
- Always send the cleaned domain in the `domain` query parameter.

## Example request

```text
GET https://api-dac.nader.io?domain=google.com
```

## Example response

```json
{
  "domain": "google.com",
  "created": "September 15, 1997",
  "expires": "September 14, 2028",
  "age": "28 years, 5 months",
  "daysLeft": 920
}
```

## Workflow

1. Extract the domain from the user's input.
2. Call the API endpoint.
3. Read `created`, `expires`, `age`, and `daysLeft` from the response.
4. Summarize the result naturally.
5. If the user is evaluating trust or legitimacy, present domain age as one signal rather than proof.

## Error handling

- `400`: Missing domain parameter.
- `404`: Domain not found or no registration data available.
- `429`: Rate limit exceeded.

If the API returns an error, explain it plainly and ask for a different domain only when needed.

## Link

- Web app: https://dac.nader.io/
