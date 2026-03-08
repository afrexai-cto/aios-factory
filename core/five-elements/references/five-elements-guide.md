# Five Elements Decomposition Guide

A practical guide for decomposing any business vertical into the Five Elements architecture.

---

## How to Use This Guide

When generating a workspace for a new vertical, work through each element in order. Answer the guiding questions, select patterns, and document the mapping. The output of this process feeds directly into the workspace scaffold.

---

## E1: Intake Decomposition

### Guiding Questions

1. What types of work does this business process?
2. How does each work type currently arrive? (email, phone, form, referral)
3. What information must be captured at intake?
4. What validation is needed before work can proceed?
5. Who initiates the intake? (client, staff member, automated system)

### Decision Matrix

| If work arrives via... | Use pattern... | Notes |
|------------------------|---------------|-------|
| Email | Email Parser | Parse subject, body, attachments |
| Phone/in-person | Conversational or Form Wizard | Staff enters data during or after call |
| Website form | Form Wizard | Direct integration |
| Another software system | API Webhook | Map external fields to internal schema |
| Scheduled batch | Scheduled Pull | Set frequency based on business rhythm |

### Output: Intake Specification

```yaml
intake:
  primary_method: [pattern name]
  secondary_methods: [list]
  required_fields:
    - field_name: [name]
      type: [text/number/date/select]
      required: true/false
      validation: [rules]
  confirmation_method: [email/screen/both]
  deduplication_key: [field or combination]
```

---

## E2: Processing Decomposition

### Guiding Questions

1. What does a professional in this field actually DO with the work?
2. What decisions do they make, and what information informs those decisions?
3. Which decisions follow clear rules (automatable)?
4. Which decisions require genuine expertise (AI-assisted)?
5. Are there approval steps or review gates?
6. What external systems or data sources are consulted?

### AI Opportunity Assessment

For each processing step, evaluate:

| Step | Can AI help? | How? | Confidence level |
|------|-------------|------|-----------------|
| [step] | Yes/Partially/No | [description] | High/Medium/Low |

Steps where AI confidence is high and the task is repetitive are prime automation candidates.

### Output: Processing Specification

```yaml
processing:
  steps:
    - name: [step name]
      type: [ai_analysis/rule_engine/human_review/integration]
      input: [what it receives]
      output: [what it produces]
      ai_applicable: true/false
      ai_prompt_hint: [brief description of what the AI should do]
  review_gates:
    - after_step: [step name]
      reviewer: [role]
      criteria: [what they check]
```

---

## E3: Output Decomposition

### Guiding Questions

1. What does the client or end-user ultimately receive?
2. In what format? (PDF, email, dashboard, verbal advice)
3. What professional standards govern the output format?
4. Does the output need to be archived or versioned?
5. Are there secondary outputs (notifications, internal reports)?

### Output: Output Specification

```yaml
output:
  primary:
    type: [report/notification/dashboard/export]
    format: [pdf/html/email/json]
    sections:
      - [section 1]
      - [section 2]
    branding: [client branding requirements]
  secondary:
    - type: [notification]
      trigger: [when to send]
      channel: [email/sms/slack]
```

---

## E4: Tracking Decomposition

### Guiding Questions

1. What statuses can work be in?
2. Who needs visibility into work status? (staff, clients, managers)
3. Are there SLAs or deadlines that must be tracked?
4. Is there a regulatory requirement for audit trails?
5. What metrics matter to the business owner?

### Output: Tracking Specification

```yaml
tracking:
  statuses:
    - name: [status name]
      display_label: [what users see]
      transitions_to: [list of valid next statuses]
  notifications:
    - on_status: [status]
      notify: [role or person]
      via: [email/slack/dashboard]
  metrics:
    - name: [metric name]
      calculation: [how to calculate]
      target: [what good looks like]
```

---

## E5: Deployment Decomposition

### Guiding Questions

1. Who will use the workspace? (individual, small team, organization)
2. What devices will they use? (desktop, mobile, both)
3. Does the workspace need to be shared or is it personal?
4. Are there security or compliance requirements for hosting?
5. Will this grow into a hosted product or stay as a local workspace?

### Output: Deployment Specification

```yaml
deployment:
  type: [local/shared/cloud/white-label]
  users: [count estimate]
  devices: [desktop/mobile/both]
  sharing: [git_repo/cloud_sync/none]
  security_requirements:
    - [requirement 1]
    - [requirement 2]
```

---

## Putting It Together

After decomposing all five elements, combine the specifications into a single niche configuration. This configuration drives the workspace scaffold.

The factory templates in `factory/templates/` accept these specifications and produce the final workspace files.
