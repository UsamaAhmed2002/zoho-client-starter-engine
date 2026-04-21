# Build Spec - Real Estate Growth CRM

## Product Definition

App name: `Real Estate Growth CRM`

Category: `Real Estate`

Target user:

- Brokerage owner
- Broker or sales manager
- Real estate agent
- Marketing/admin user

Core promise:

> Capture property leads, assign them fast, manage buyer/seller pipelines, track site visits, and give brokers visibility into follow-up and agent activity.

## Vertical Studio Setup

1. Log in to Zoho Developer Console.
2. Open `Vertical Studio` or `CRM for Verticals`.
3. Create a new application.
4. Set application name to `Real Estate Growth CRM`.
5. Select real estate or closest available business category.
6. Include these standard modules:
   - Leads
   - Contacts
   - Accounts
   - Deals / Potentials
   - Tasks
   - Events
   - Calls
   - Documents
   - Campaigns
   - Reports
   - Dashboards
7. Exclude or hide inventory-heavy modules for V1 unless Zoho requires them:
   - Products
   - Vendors
   - Purchase Orders
   - Sales Orders
   - Invoices
   - Price Books
   - Cases
   - Solutions
8. Add custom modules:
   - Properties
   - Site Visits
   - Bookings
   - Commissions
9. Configure module order:
   - Home
   - Leads
   - Contacts
   - Accounts
   - Deals
   - Properties
   - Site Visits
   - Bookings
   - Tasks
   - Calls
   - Events
   - Campaigns
   - Documents
   - Commissions
   - Reports
   - Dashboards

## Profiles And Roles

Roles:

- Owner / Broker
- Sales Manager
- Agent
- Marketing / Admin

Profiles:

- Administrator
- Broker Manager
- Agent
- Marketing Admin

Permission intent:

- Administrator: full access.
- Broker Manager: full sales visibility, dashboard access, workflow visibility.
- Agent: own leads, contacts, deals, properties assigned, site visits, tasks, calls, events.
- Marketing Admin: lead source, campaigns, imports, reports, no commission edit access.

Restrict commission details from normal agents where field/module permission supports it.

## Required Demo Data

Create enough demo data for screenshots and QA:

- 5 agents
- 20 leads
- 10 contacts
- 3 accounts
- 15 properties
- 10 deals across multiple stages
- 8 site visits
- 3 bookings
- 3 commissions
- 2 campaigns
- 10 open tasks
- 5 completed calls

Use realistic lead sources:

- Website
- Zillow
- Realtor.com
- Facebook Lead Ad
- Google Ad
- Referral
- Open House
- Walk-in
- Phone Call
- WhatsApp

## Version Strategy

V1:

- CRM-only brokerage template.
- No external API dependencies.
- No paid SMS/WhatsApp/telephony dependency.
- No finance app dependency.

V1.1:

- Add optional developer unit-sales layout.
- Add more dashboards and views based on customer feedback.

V2:

- Optional Zoho Books, Zoho Sign, Zoho Forms, Zoho Flow, WhatsApp/SMS, and portal setup as service add-ons.

## Implementation Order

1. Create app and select standard modules.
2. Create roles, profiles, and permission model.
3. Build custom modules.
4. Add fields and picklists.
5. Add relationships through lookup fields.
6. Build page layouts.
7. Build list views.
8. Build workflows and tasks.
9. Build reports.
10. Build dashboards.
11. Add demo data.
12. Test install/preview behavior.
13. Prepare Marketplace listing and screenshots.

