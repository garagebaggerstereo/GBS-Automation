# Production readiness

This is an inactive development project. Before any customer text, verify: complete customer reply identification, documented opt-in, STOP status, an exclusive atomic inquiry claim, exclusion of existing estimate reminders, and an end-to-end dry run. All uncertain states must block sending. No live Zapier automations are to be changed. Final owner approval is mandatory.

Known limitations: the main 24-hour flow has a manual trigger; Gmail MIME decoding is not proved; lack of matching mail is not proof of no reply; table check-then-insert is not atomic. The Call Loop API connection alone does not establish safe sending.
