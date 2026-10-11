# GBS Automation Architecture

n8n runs the workflows. Notion Project #4 retains approved status, decisions, and recovery instructions. GitHub stores sanitized versions for review and rollback. GitHub changes are **not** deployment actions.

## Customer email follow-up
- Source mailboxes: four Microsoft Outlook accounts and one Gmail account.
- Inactive sent-mail poll -> conservative inquiry classifier -> pending-review tracker.
- Separate five-mailbox reply checker -> hard-off SMS eligibility gate.
- Call Loop personal access token is stored in n8n credentials, **never GitHub**.

## Required safeguards before any SMS
1. Correct request/reply conversation linkage and completeness verification across all five mailboxes.
2. Exactly-one reminder via a proven atomic claim or serialization mechanism.
3. Documented customer SMS consent, current STOP status, verified phone and sender.
4. No collision with existing Zapier estimate follow-ups.
5. End-to-end non-sending validation and explicit user activation approval.

## Production rules
Do not modify the existing 14 live dropship Zaps or existing estimate reminder. Do not activate customer texting from this repository. Treat missing evidence as a blocker.
