# AI Dental Receptionist — Interview Demo Script

**Recommended length:** 4–6 minutes  
**Audience:** AI Solutions Analyst, automation engineer, or applied AI hiring team  
**Demo assets:** Vapi test assistant, n8n workflow canvas, sanitized GitHub repository, dedicated Google Sheets demo CRM, dedicated Google Calendar test calendar.

> **Before recording:** Use fictional names, fake emails, and a test calendar. Confirm which live integrations work. Never describe pinned/mock output as a real Calendar booking. If a live step fails, show the relevant workflow configuration and describe it as an implemented prototype path rather than a successful end-to-end demonstration.

## 0:00–0:35 — Introduction

**Say:**

“Hi, I'm presenting an AI Dental Receptionist prototype built with Vapi, n8n, the Model Context Protocol, Google Sheets, Google Calendar, and JavaScript. The goal is to connect a conversational AI receptionist to actual business workflows—not just answer questions, but look up patients, register new clients, check appointment availability, and request bookings.”

**Show:** GitHub README title and high-level architecture diagram.

## 0:35–1:15 — Architecture and tools

**Say:**

“Vapi handles the voice conversation. An n8n MCP Server Trigger exposes four workflow tools: patient lookup, new-patient registration, availability checking, and appointment booking. The tools are implemented as separate n8n subworkflows so the integration is modular and easier to test.”

**Show:** `Vapi MCP Server` workflow and its four Call Workflow Tool nodes, then the `workflows/` folder in GitHub.

## 1:15–2:00 — Patient lookup and registration

**Say:**

“When a caller provides an email, the lookup workflow searches a Google Sheets client table. For an existing client, it can also check the appointment log. If no client record is found, the assistant can collect the caller's name, email, and phone number and invoke the create-client workflow to append a new row.”

**Optional live prompt:** “Can you check whether alex.demo@example.com is already registered?”

**Show:** `Client Lookup` node, branches for existing/new clients, and `Append row in sheet` node. Show only synthetic CRM rows.

**Evidence rule:** If the test call does not complete, say “This is the workflow path designed for registration,” not “The patient was successfully registered.”

## 2:00–3:10 — Availability validation

**Say:**

“Availability checking is more than a calendar search. A JavaScript node validates explicit timezone offsets, rejects past dates, requires an exactly one-hour appointment, and enforces weekday clinic hours in New York. The workflow also searches one hour before and after the requested appointment to enforce a scheduling buffer. A Calendar query checks existing events, and an If node returns either ‘is available’ or ‘is busy.’”

**Show:** `check availability` canvas → `Code in JavaScript` → `Get many events` → `If` → `Busy` / `Available`.

**Demo tests:**

1. **Busy slot:** Choose a future weekday appointment that overlaps a synthetic calendar event or its buffer. Expected: `is busy`.
2. **Free slot:** Choose a future weekday appointment without events in the buffered interval. Expected: `is available`.
3. **Invalid slot:** Try a weekend or a 30-minute request. Expected: validation error; no booking.

**Note:** Pick dates at recording time; do not reuse old hardcoded 2026 dates after they pass. Use a calendar with known test events.

## 3:10–4:05 — Booking with recheck

**Say:**

“The booking workflow calls the availability workflow again immediately before creating a Google Calendar event. If the slot is busy, it returns a rejection status. If the slot is available and Google Calendar successfully creates the event, the workflow returns a confirmation containing the event ID and appointment times.”

**Show:** `Book an event` → `Call 'check availability'` → `If` → `Booking Unavailable` or `Create an event` → `Booking Confirmed`.

**Important:** Only show `booking_confirmed` as a live success if the Google Calendar **Create an event** node actually executed and the new event is visible in the test calendar. A pinned `test_event_123` JSON example is mock data, not proof of a real booking.

## 4:05–4:45 — Engineering judgment and limitations

**Say:**

“One design choice was to separate availability checking from booking while still rechecking at booking time. That catches many common conflicts, but it does not provide atomic concurrency control. Two callers could potentially pass the check simultaneously. For production, I would integrate an atomic booking or slot-hold mechanism, add structured error handling and human escalation, and complete security and compliance review before processing real patient data.”

**Show:** `docs/architecture.md` → Known limitations and engineering roadmap.

## 4:45–5:15 — Close

**Say:**

“This project demonstrates how I design and connect AI agents to operational systems: defining tool contracts, orchestrating n8n workflows, validating business rules in JavaScript, integrating APIs, and testing success and failure paths. The repository includes sanitized workflow exports, the architecture, and implementation notes.”

**Show:** GitHub repository structure and README.

## Recording checklist

- [ ] Use only fictional patient names, emails, and phone numbers.
- [ ] Confirm Vapi and MCP connectivity before recording.
- [ ] Verify that the test Google Calendar and test Google Sheets are selected.
- [ ] Unpin test data or clearly label mock results.
- [ ] Demonstrate at least one busy-slot branch and one available-slot branch.
- [ ] If showing a booking confirmation, verify the actual event in Calendar.
- [ ] Do not show API keys, OAuth settings, private MCP endpoints, or sensitive logs.
- [ ] Show the GitHub repository URL and docs at the end.

## Suggested Loom title and description

**Title:** AI Dental Receptionist | Vapi + n8n MCP + Google Sheets + Google Calendar

**Description:** Walkthrough of a voice AI receptionist prototype integrating patient lookup, client registration, appointment validation, calendar availability, and conditional booking. Includes workflow architecture, business rules, and current production-readiness limitations.
