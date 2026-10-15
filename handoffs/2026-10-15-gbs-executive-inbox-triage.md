# GBS Executive Inbox Triage — 2026-10-15 Handoff

## Status — STOP HERE 2026-10-15
Workflow **GBS - Executive Inbox Triage & Morning Briefing** ID `PBA116osbnKrkuDM`, https://garagebaggerstereo.app.n8n.cloud/workflow/PBA116osbnKrkuDM. **Inactive; 24 nodes.** Do not rename thread. Separate 77-node vendor invoice fulfillment workflow untouched.
## Completed
- Supabase `public.gbs_email_triage_ledger` with unique (mailbox,message_id), RLS enabled, restricted anon/authenticated grants; atomic claim and briefing indexes.
- n8n paths: 15-minute Outlook poll → vendor protection → Node 5 Normalize → Node 7 atomic claim → Node 7A unpack → Node 8 structured LLM classification → Node 9 validation → Node 9A strict draft gate → Node 10 LLM draft → Node 10A HTML header sanitizer → Node 11A createReply → Node 11B capture ID → Node 11C PATCH → Node 13 ledger update. 6:30 AM America/New_York trigger → Node 14 SQL → Node 15 HTML digest → Node 15B Outlook email.
- Synthetic executions #584 category routing, #585 malformed JSON, #602 All Clear digest, #605 flattened payload passed. Direct Supabase test `TEST-MSG-001` first insert 1 row, duplicate 0 rows; test row deleted afterward.
## Safe state and blocker
- Workflow INACTIVE; Graph draft POST Node 11A DISABLED; draft PATCH Node 11C DISABLED; ledger finalize Node 13 DISABLED; briefing send Node 15B DISABLED. No customer replies auto-sent.
- Marketing mailbox read via connected Outlook shared-mailbox lookup returned HTTP 404 `ErrorItemNotFound / Default folder AllItems not found`. No live Graph createReply/PATCH execution or draft verification yet. Mail.ReadWrite and exact mapping of n8n OAuth credential `IXAGiP3gCiK4ZR6t` to marketing mailbox not verified.
- Node 15B configured solely for `marketing@garagebaggerstereo.com`, still disabled.
## Important unresolved
- Test Node 7 through actual n8n Postgres credential, including query-parameter array serialization and duplicate stop behavior (database itself verified separately).
- Resolve mailbox identities; Node 5 truncates bodyText to 20k; review vendor early-drop vs ledger accounting; require safe HTML allowlist.
- Live Graph isolated internal message test only after verifying mailbox scope; check POST/PATCH, read-back, no sends; disable nodes again. Then validate ledger draft_id and DRAFT_CREATED.
- Final briefing delivery verification and pilot review before activation. 24-node graph exceeds original 15 target; safety more important than count.
## Next step
Verify read-only identity and Graph Mail.ReadWrite access to `marketing@garagebaggerstereo.com`, locate a dedicated internal test message (never use a real customer/vendor message), then single-item Graph draft test. No production turn-on until confirmed.
