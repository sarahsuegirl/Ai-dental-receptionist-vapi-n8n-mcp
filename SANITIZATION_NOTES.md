# Sanitized n8n Workflow Exports

These five files are intended for a public portfolio. They preserve node logic and connections but remove personal email addresses, Google OAuth credential references, Google Sheets document IDs, n8n workflow identifiers, the original MCP endpoint path, workflow instance metadata, and pinned test data. Workflows are marked inactive.

**These are demonstration exports, not plug-and-play production workflows.** To run them, import all five workflows into n8n, reconnect Google Sheets and Calendar credentials, select your own spreadsheet tabs and calendar, configure a fresh MCP endpoint, and reselect the referenced child workflows in the MCP Server and Book an Event nodes. Confirm the Vapi integration points to the new endpoint. The placeholder IDs are intentionally not functional.

**Privacy/security:** Never upload real patient data, access tokens, secrets, live MCP endpoint URLs, or unsanitized executions to a public repository. Audit any screenshots and README content separately. If a secret has already been committed, revoke or rotate it; deleting a file does not erase Git history.

**Known technical limitations:** Booking availability and time handling need end-to-end testing, including concurrency/race conditions, recurring events, daylight-saving transitions, and business-hour validation. The exported lookup workflow also contains a branch with no downstream output for an existing client with an upcoming appointment. This is a prototype, not a HIPAA-compliant clinical system.
