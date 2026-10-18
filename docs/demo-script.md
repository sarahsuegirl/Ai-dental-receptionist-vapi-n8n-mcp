# 2–3 minute interview demo script

**0:00–0:25 — Problem:** “Dental offices handle repetitive intake and scheduling calls. I built a voice-AI prototype to orchestrate those tasks using Vapi, n8n, and MCP.”

**0:25–0:55 — Architecture:** Show the diagram and explain the Vapi → MCP → n8n → Sheets/Calendar flow.

**0:55–1:45 — Working feature:** Run a call using a **synthetic** email and show the matching n8n patient lookup execution.

**1:45–2:20 — Calendar:** Show the availability workflow, then state clearly: “I found a date parsing issue in testing, so I'm adding server-side validation and buffer rules before enabling reliable booking.”

**2:20–2:45 — Engineering judgment:** Describe privacy sanitization, tool response normalization, idempotency, and authentication as next steps.

**Recording checklist:** Hide browser account identity, credentials, tokens, personal email addresses, calendar event descriptions, and MCP URLs. Do not show real patient data.
