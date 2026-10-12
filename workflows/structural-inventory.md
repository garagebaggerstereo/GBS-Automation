# Sanitized n8n Development Workflow Inventory

Source: live n8n workflow metadata, October 12, 2026. This is a recovery-oriented structural inventory, **not** a restorable full export. Credentials, mailbox identifiers, private addresses, raw node parameters, and execution data are intentionally excluded.

All listed workflows are currently inactive. No deployment is implied.

## GBS Customer Follow-Up - Development
- Internal workflow key: cvNutkpvioLIXl1L
- State: INACTIVE
- Updated: 2026-10-10T20:26:09.565Z
- Nodes (8):
  - Manual Start — `n8n-nodes-base.manualTrigger`
  - Development Status — `n8n-nodes-base.set`
  - Classify Outbound Email — `n8n-nodes-base.code`
  - Hold 24 Hours - Development Only — `n8n-nodes-base.wait`
  - Block Reminder Until Verified — `n8n-nodes-base.set`
  - Only Qualified Sent Requests — `n8n-nodes-base.if`
  - Read-Only Five-Mailbox Reply Check — `n8n-nodes-base.executeWorkflow`
  - Mandatory SMS Safety Gate - HARD OFF — `n8n-nodes-base.executeWorkflow`

### Topology
```json
{
  "Manual Start": {
    "main": [
      [
        {
          "node": "Development Status",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Development Status": {
    "main": [
      [
        {
          "node": "Classify Outbound Email",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Classify Outbound Email": {
    "main": [
      [
        {
          "node": "Only Qualified Sent Requests",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Only Qualified Sent Requests": {
    "main": [
      [
        {
          "node": "Hold 24 Hours - Development Only",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Hold 24 Hours - Development Only": {
    "main": [
      [
        {
          "node": "Read-Only Five-Mailbox Reply Check",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read-Only Five-Mailbox Reply Check": {
    "main": [
      [
        {
          "node": "Mandatory SMS Safety Gate - HARD OFF",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Mandatory SMS Safety Gate - HARD OFF": {
    "main": [
      [
        {
          "node": "Block Reminder Until Verified",
          "type": "main",
          "index": 0
        }
      ]
    ]
  }
}
```

## GBS Sent Mail Poll - Five Sources (INACTIVE)
- Internal workflow key: mQ4BqsjtccV9xoAH
- State: INACTIVE
- Updated: 2026-10-10T21:23:44.083Z
- Nodes (8):
  - Hourly Sent Items Scan - INACTIVE — `n8n-nodes-base.scheduleTrigger`
  - Read Chris Sent Items — `n8n-nodes-base.microsoftOutlook`
  - Filter and Normalize - READ ONLY — `n8n-nodes-base.code`
  - Read Sales Sent Items — `n8n-nodes-base.microsoftOutlook`
  - Read Support Sent Items — `n8n-nodes-base.microsoftOutlook`
  - Read Ethan Sent Items — `n8n-nodes-base.microsoftOutlook`
  - Read Gmail Sent Items — `n8n-nodes-base.gmail`
  - Stage New Cases For Review - NO SMS — `n8n-nodes-base.executeWorkflow`

### Topology
```json
{
  "Hourly Sent Items Scan - INACTIVE": {
    "main": [
      [
        {
          "node": "Read Chris Sent Items",
          "type": "main",
          "index": 0
        },
        {
          "node": "Read Sales Sent Items",
          "type": "main",
          "index": 0
        },
        {
          "node": "Read Support Sent Items",
          "type": "main",
          "index": 0
        },
        {
          "node": "Read Ethan Sent Items",
          "type": "main",
          "index": 0
        },
        {
          "node": "Read Gmail Sent Items",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read Chris Sent Items": {
    "main": [
      [
        {
          "node": "Filter and Normalize - READ ONLY",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read Sales Sent Items": {
    "main": [
      [
        {
          "node": "Filter and Normalize - READ ONLY",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read Support Sent Items": {
    "main": [
      [
        {
          "node": "Filter and Normalize - READ ONLY",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read Ethan Sent Items": {
    "main": [
      [
        {
          "node": "Filter and Normalize - READ ONLY",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Read Gmail Sent Items": {
    "main": [
      [
        {
          "node": "Filter and Normalize - READ ONLY",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Filter and Normalize - READ ONLY": {
    "main": [
      [
        {
          "node": "Stage New Cases For Review - NO SMS",
          "type": "main",
          "index": 0
        }
      ]
    ]
  }
}
```

## GBS Inquiry Staging - NO SMS (INACTIVE)
- Internal workflow key: Su5GgWMstY0uajGd
- State: INACTIVE
- Updated: 2026-10-10T23:19:01.716Z
- Nodes (4):
  - Validated Sent Email Input — `n8n-nodes-base.executeWorkflowTrigger`
  - Qualify and Prepare Case - NO SMS — `n8n-nodes-base.code`
  - Skip Existing Inquiry Rows — `n8n-nodes-base.dataTable`
  - Insert Pending Review - NO SMS — `n8n-nodes-base.dataTable`

### Topology
```json
{
  "Validated Sent Email Input": {
    "main": [
      [
        {
          "node": "Qualify and Prepare Case - NO SMS",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Qualify and Prepare Case - NO SMS": {
    "main": [
      [
        {
          "node": "Skip Existing Inquiry Rows",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Skip Existing Inquiry Rows": {
    "main": [
      [
        {
          "node": "Insert Pending Review - NO SMS",
          "type": "main",
          "index": 0
        }
      ]
    ]
  }
}
```

## GBS - Five Mailbox Reply Check (INACTIVE)
- Internal workflow key: iW8Dpu4N0m56FBmh
- State: INACTIVE
- Updated: 2026-10-10T22:21:40.772Z
- Nodes (8):
  - Follow-Up Reply Verification Input — `n8n-nodes-base.executeWorkflowTrigger`
  - Validate Request — `n8n-nodes-base.code`
  - Chris Reply Read — `n8n-nodes-base.microsoftOutlook`
  - Sales Reply Read — `n8n-nodes-base.microsoftOutlook`
  - Support Reply Read — `n8n-nodes-base.microsoftOutlook`
  - Ethan Reply Read — `n8n-nodes-base.microsoftOutlook`
  - Gmail Reply Read — `n8n-nodes-base.gmail`
  - Summarize Reply Search - NO SEND — `n8n-nodes-base.code`

### Topology
```json
{
  "Follow-Up Reply Verification Input": {
    "main": [
      [
        {
          "node": "Validate Request",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Validate Request": {
    "main": [
      [
        {
          "node": "Chris Reply Read",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Chris Reply Read": {
    "main": [
      [
        {
          "node": "Sales Reply Read",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Sales Reply Read": {
    "main": [
      [
        {
          "node": "Support Reply Read",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Support Reply Read": {
    "main": [
      [
        {
          "node": "Ethan Reply Read",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Ethan Reply Read": {
    "main": [
      [
        {
          "node": "Gmail Reply Read",
          "type": "main",
          "index": 0
        }
      ]
    ]
  },
  "Gmail Reply Read": {
    "main": [
      [
        {
          "node": "Summarize Reply Search - NO SEND",
          "type": "main",
          "index": 0
        }
      ]
    ]
  }
}
```

## GBS SMS Safety Gate - HARD OFF (INACTIVE)
- Internal workflow key: eatY9C08lWfGvlfL
- State: INACTIVE
- Updated: 2026-10-10T22:38:37.223Z
- Nodes (2):
  - Trusted Internal Verification Input — `n8n-nodes-base.executeWorkflowTrigger`
  - Evaluate SMS Eligibility - HARD OFF — `n8n-nodes-base.code`

### Topology
```json
{
  "Trusted Internal Verification Input": {
    "main": [
      [
        {
          "node": "Evaluate SMS Eligibility - HARD OFF",
          "type": "main",
          "index": 0
        }
      ]
    ]
  }
}
```
