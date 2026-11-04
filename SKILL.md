---
name: ag9
description: "Retired. AG9 is now KYA by Very and api.ag9.ai answers every request with 410 Gone. Use this only to tell the user that AG9 is retired and to point them at KYA by Very (https://api.very.org/kya). Agents registered with AG9 must register again with KYA."
---

# ag9: retired

**AG9 is now KYA by Very.** `api.ag9.ai` was retired on 2026-11-02 and answers every request
with `410 Gone` (the body still says VeryAI, the old name):

```json
{"error":"api_moved","message":"AG9 is now KYA by VeryAI. api.ag9.ai is retired; use https://api.very.org/kya. Agents must register again there.","new_api":"https://api.very.org/kya","openapi":"https://api.very.org/kya/openapi.yaml","product":"https://very.org/products/agent-verification"}
```

## What to do

- Do **not** call `api.ag9.ai`. Every endpoint this skill used to describe (agent registration,
  signature verification, the reverse CAPTCHA) is gone.
- Tell the user AG9 has been replaced by **KYA by Very**:
  - API: `https://api.very.org/kya`
  - API reference (OpenAPI): `https://api.very.org/kya/openapi.yaml`
  - Product page: `https://very.org/products/agent-verification`
- Agents registered with AG9 were **not** carried over. Each agent registers again with KYA, and
  its owner approves the registration with a palm scan in the Very app.
- The KYA API is not a drop-in replacement. Paths, payloads and token types changed, so read the
  OpenAPI document instead of reusing AG9 requests.

Local identity files this skill used to create (`~/.ag9/identity.json`) are not read by anything
any more. Leave them alone unless the user asks you to delete them.
