# QA And Publish Checklist

## Build QA

- App name is correct: `Real Estate Growth CRM`.
- Category is correct or closest available real estate category is selected.
- Standard modules are selected intentionally.
- Unused modules are hidden or excluded.
- Custom modules exist:
  - Properties
  - Site Visits
  - Bookings
  - Commissions
- Lookup relationships work:
  - Deal to Property
  - Site Visit to Deal
  - Site Visit to Property
  - Booking to Deal
  - Booking to Property
  - Commission to Deal
  - Commission to Agent
- Layouts exist:
  - Buyer Lead
  - Seller Lead
  - Rental Lead
  - Buyer Deal
  - Seller Listing Deal
  - Rental Deal
- Picklists are clean and generic enough for broad brokerage use.
- Required fields do not block normal lead entry.
- Commission fields are restricted from normal agents where supported.

## Workflow QA

Test each scenario in preview/test application:

- New lead creates first follow-up task.
- Hot lead creates urgent follow-up task.
- Stale lead appears in stale lead view/report.
- Lead conversion preserves key lead fields.
- Deal stage change creates correct next-step task.
- Site Visit completed creates post-visit follow-up task.
- Site Visit no-show creates reschedule task.
- Booking creation creates document task.
- Closed Won creates referral/commission tasks.
- Closed Lost supports lost reason and future nurture task.

## Dashboard QA

- Broker Dashboard loads with demo data.
- Agent Dashboard shows only agent-relevant records where permissions support it.
- Marketing Dashboard shows lead source data.
- Operations Dashboard shows site visits and bookings.
- No dashboard uses empty or broken reports.
- Demo data produces meaningful charts.

## Demo Data QA

- Demo records use realistic names and values.
- Demo data covers every pipeline stage.
- Demo data covers all dashboards.
- Demo records do not contain real personal data.
- Demo source names match listing screenshots.

## Install / Preview QA

- Test install/preview in a clean environment.
- Confirm packaged components appear after install.
- Confirm user/profile setup works.
- Confirm required modules are visible.
- Confirm no workflow references missing users, fields, or modules.
- Confirm subscriber can edit local picklists/views where expected.

## Marketplace Asset QA

- Short description is clear and not overpromising.
- Long description explains business value, not just features.
- Screenshots match the installed product.
- Setup guide is accurate.
- No external integration is advertised as included in V1.
- Add-on services are clearly separate from the Marketplace package.

## Publish Readiness Gate

Do not submit until:

- Fresh install test passes.
- All workflow scenarios pass.
- Dashboards show useful demo data.
- Listing copy matches actual package behavior.
- Install guide can be followed by a non-technical brokerage admin.
- Known limitations are documented.

## Known V1 Limitations

- No native MLS integration.
- No WhatsApp/SMS automation included.
- No Zoho Books invoice/payment automation included.
- No Zoho Creator portal included.
- No region-specific real estate compliance workflow included.
- Advanced integrations require custom implementation.

