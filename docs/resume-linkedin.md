# AI Dental Receptionist — Resume, LinkedIn & Portfolio Copy

**Project:** AI Dental Receptionist — Voice AI Workflow Automation  
**Repository:** https://github.com/sarahsuegirl/Ai-dental-receptionist-vapi-n8n-mcp  
**Technologies:** Vapi, n8n, Model Context Protocol (MCP), JavaScript, Google Sheets, Google Calendar, workflow orchestration, API integration

> These descriptions reflect the exported workflows. They do not claim HIPAA compliance, production deployment, measured time savings, or guaranteed protection against simultaneous booking conflicts.

## 1. Resume — recommended version

**AI Dental Receptionist | Voice AI & Workflow Automation Project**  
*Vapi · n8n · MCP · JavaScript · Google Sheets · Google Calendar*

- Designed a modular voice AI receptionist prototype connecting Vapi to four n8n workflow tools through an MCP server for client lookup, registration, availability checks, and appointment booking.
- Implemented Google Sheets CRM lookup and new-client registration workflows, with conditional paths for existing clients and appointment-log queries.
- Built JavaScript appointment validation for timezone-aware ISO timestamps, 60-minute slots, weekday business hours, and configurable calendar-search buffers.
- Orchestrated Google Calendar availability checks and a booking workflow that rechecks availability before event creation, returning structured confirmation or busy-slot responses.
- Documented architecture, testing scenarios, deployment dependencies, and remaining concurrency and privacy considerations in a public GitHub portfolio.

## 2. Resume — compact two-bullet version

**AI Dental Receptionist — Vapi, n8n, MCP, JavaScript, Google Calendar/Sheets**

- Developed a voice AI automation prototype with MCP-connected n8n tools for CRM lookup, patient registration, calendar availability, and conditional appointment booking.
- Implemented timezone-aware appointment validation, one-hour scheduling rules, calendar conflict checks, and structured booking responses; documented the architecture and limitations on GitHub.

## 3. LinkedIn Projects section

**Project name:** AI Dental Receptionist | Voice AI, MCP & n8n Automation

**Description:**

Designed and implemented an AI receptionist prototype that connects Vapi voice conversations to operational workflows using n8n and the Model Context Protocol (MCP). The system exposes four tools for client lookup, new-client registration, appointment availability checks, and conditional booking. Google Sheets serves as a demo CRM, while Google Calendar handles scheduling and event creation.

The availability workflow includes JavaScript validation for timezone-aware ISO dates, one-hour appointments, weekday clinic hours, and scheduling buffers. The booking workflow performs an additional availability check before attempting to create an event. I also documented test cases and engineering improvements needed for production, including atomic concurrency control, robust error handling, and privacy safeguards.

**Skills:** Agentic AI · Voice AI · Workflow Automation · n8n · MCP · Vapi · JavaScript · Google Calendar API · Google Sheets · Systems Integration

**Project URL:** https://github.com/sarahsuegirl/Ai-dental-receptionist-vapi-n8n-mcp

## 4. LinkedIn Featured item

**Title:** AI Dental Receptionist — Vapi + n8n MCP Automation

**Caption:** Voice AI receptionist prototype connecting patient CRM workflows and appointment scheduling through four MCP-exposed n8n tools. Includes calendar validation, conditional booking, sanitized JSON workflows, and architecture documentation.

**Link:** https://github.com/sarahsuegirl/Ai-dental-receptionist-vapi-n8n-mcp

## 5. LinkedIn post — professional launch draft

I built an **AI Dental Receptionist** prototype to explore how conversational AI can connect to real business workflows.

Using **Vapi, n8n, MCP, JavaScript, Google Sheets, and Google Calendar**, I designed a modular system with tools for client lookup, new-client registration, appointment availability, and conditional booking.

One of the key challenges was moving beyond a simple calendar lookup. The availability workflow validates timezone-aware dates, enforces one-hour appointments and weekday clinic hours, and checks for events within a scheduling buffer. The booking workflow then rechecks availability before attempting event creation.

The project also reinforced an important engineering distinction: checking availability before booking helps reduce conflicts, but production-grade simultaneous booking protection requires atomic reservations or another concurrency-safe design.

I've published sanitized workflow exports and technical documentation so others can explore the architecture and implementation.

**GitHub:** https://github.com/sarahsuegirl/Ai-dental-receptionist-vapi-n8n-mcp

#VoiceAI #AgenticAI #n8n #MCP #Automation #JavaScript #AIEngineering

## 6. Interview pitch — 30 seconds

“I built an AI Dental Receptionist prototype using Vapi, n8n, and MCP. It exposes four tools for patient lookup, registration, appointment availability, and booking, with Google Sheets as a demo CRM and Google Calendar for scheduling. I wrote JavaScript validation for one-hour appointments, New York business hours, timezone-aware timestamps, and scheduling buffers. The booking workflow rechecks availability before event creation. I also identified what needs to change for production, particularly atomic concurrency protection and privacy controls.”

## 7. Claims to avoid unless separately verified

- “Deployed to a real dental clinic”
- “HIPAA-compliant”
- “Guaranteed no double bookings”
- “Handles five simultaneous calls” (this was a separate design target, not a tested result of these exports)
- “Reduced administrative costs by X%” or “saved Y hours” without measured data
- “Fully integrated end-to-end” if only individual workflow nodes were tested or pinned output was used

**Recommended positioning:** Demonstrated architecture and working workflow components; integration testing and production hardening remain ongoing.
