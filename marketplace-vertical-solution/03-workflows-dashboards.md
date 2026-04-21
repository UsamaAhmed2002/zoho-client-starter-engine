# Workflows, Reports, And Dashboards

## Workflow Rules

### New Lead Follow-up

Trigger: lead created.

Conditions:

- Lead Status is not `Closed Lost`
- Lead Type is not empty

Actions:

- Create task: `First follow-up with ${Lead Name}`
- Due: same day
- Owner: Lead Owner
- Priority: High when Urgency = Hot, otherwise Normal

### Hot Lead SLA

Trigger: lead created or edited.

Conditions:

- Urgency = Hot
- Lead Status is New or Contacted

Actions:

- Create task: `Call hot lead`
- Due: same day
- Notify Lead Owner

### Stale Lead Reminder

Trigger: scheduled daily rule where supported, otherwise list-view process.

Criteria:

- Lead Status is New, Contacted, or Qualified
- Last Follow-up Date is empty or older than 2 days

Actions:

- Notify owner.
- Create task: `Follow up stale lead`

### Lead Converted To Deal

Trigger: lead conversion/manual process.

Required behavior:

- Preserve Lead Type, Source, Budget, Location, Property Type, Timeline, Urgency.
- Create Deal with correct Deal Type.
- Assign Deal Owner to original Lead Owner.

### Deal Stage Follow-up

Trigger: Deal stage changes.

Actions by stage:

- Property Matched: create task `Send matching property options`.
- Site Visit Scheduled: create task `Confirm viewing details`.
- Site Visit Completed: create task `Collect client feedback and next step`.
- Offer Sent: create task `Follow up on offer`.
- Booking / Agreement: create task `Start booking/document checklist`.

### Site Visit Completed

Trigger: Site Visit status changes to Completed.

Actions:

- Create task for Agent: `Post-visit follow-up`.
- Due: next business day.
- Update related Deal stage to `Site Visit Completed` if supported by workflow rules.

### No-show Recovery

Trigger: Site Visit status changes to No-show.

Actions:

- Create task: `Reschedule site visit or qualify out`.
- Due: same day.

### Booking Created

Trigger: Booking created.

Actions:

- Create task for admin/agent: `Collect booking documents`.
- Set related Deal stage to `Booking / Agreement` if supported.
- Set related Property status to `Booked` if supported.

### Closed Won

Trigger: Deal stage changes to Closed Won.

Actions:

- Create task: `Add client to referral nurture`.
- Create task: `Review commission payout`.
- Set related Property status to Sold or Rented manually if workflow cannot branch by Deal Type.

### Closed Lost

Trigger: Deal stage changes to Closed Lost.

Actions:

- Require Lost Reason in layout/process where supported.
- Create future task: `Reactivation follow-up`.
- Due: 60 days later.

## Email Templates

Create these basic templates:

- New inquiry acknowledgement
- Buyer property match follow-up
- Site visit confirmation
- Site visit reminder
- Post-visit follow-up
- Offer follow-up
- Document request
- Past client referral request
- Cold lead reactivation

Keep template copy generic and editable by subscribers.

## Reports

Lead reports:

- Leads by source
- Leads by owner
- Hot leads without activity
- Leads converted by source
- Leads created this week

Deal reports:

- Deals by stage
- Deals by owner
- Pipeline by expected closing month
- Stale deals by owner
- Closed Won by source
- Lost deals by reason

Property reports:

- Available properties by city
- Properties by status
- Listings by agent
- Properties without activity

Site visit reports:

- Site visits this week
- Completed visits by agent
- No-shows by source
- Site visits by property

Booking and commission reports:

- Bookings by status
- Confirmed bookings this month
- Pending commissions
- Paid commissions this month

## Dashboards

### Broker Dashboard

Widgets:

- Open pipeline by stage
- Closed Won this month
- Stale leads by agent
- Stale deals by agent
- Lead source conversion
- Site visits this week
- Bookings pending documents
- Pending commissions

### Agent Dashboard

Widgets:

- My new leads
- My hot leads
- My tasks due today
- My site visits this week
- My active deals by stage
- My deals needing follow-up

### Marketing Dashboard

Widgets:

- Leads by source
- Converted leads by source
- Lost leads by reason
- Campaign leads
- Open house leads
- Website leads

### Operations Dashboard

Widgets:

- Upcoming site visits
- No-shows
- Completed visits awaiting follow-up
- Bookings pending documents
- Bookings pending deposit
- Properties missing required listing data

## Automation Limits To Avoid In V1

Do not make V1 depend on:

- WhatsApp API approval
- Twilio or SMS account
- MLS or property portal API
- Zoho Books sync
- Zoho Sign templates
- Zoho Creator portal
- Advanced Deluge scripts unless required

Keep those as paid implementation add-ons.

