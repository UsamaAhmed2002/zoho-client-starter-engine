# Module And Field Blueprint

## Standard Modules

### Leads

Purpose: unqualified buyer, seller, renter, investor, or referral inquiries.

Layouts:

- Buyer Lead
- Seller Lead
- Rental Lead

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Lead Type | Picklist | Yes | Buyer, Seller, Renter, Landlord, Investor, Referral |
| Lead Source | Picklist | Yes | Website, Zillow, Realtor.com, Facebook Lead Ad, Google Ad, Referral, Open House, Walk-in, Phone Call, WhatsApp, Other |
| Inquiry Channel | Picklist | No | Form, Call, Email, Chat, WhatsApp, Social, Manual Import |
| Budget Min | Currency | No | Buyer/renter search |
| Budget Max | Currency | No | Buyer/renter search |
| Desired Location | Single Line / Picklist | No | Use picklist for local template, text for generic Marketplace |
| Property Type | Picklist | No | Apartment, House, Condo, Townhome, Land, Commercial, Office, Retail, Industrial, Other |
| Bedrooms | Number | No | Residential |
| Bathrooms | Number | No | Residential |
| Timeline | Picklist | No | Immediately, 0-30 Days, 1-3 Months, 3-6 Months, 6+ Months, Unknown |
| Financing Status | Picklist | No | Cash Buyer, Pre-approved, Needs Financing, Unknown |
| Urgency | Picklist | Yes | Hot, Warm, Cold |
| Preferred Contact Method | Picklist | No | Call, Email, SMS, WhatsApp |
| First Response Due | Date/Time | No | Used by SLA views |
| Last Follow-up Date | Date | No | Manual/workflow maintained |
| Next Follow-up Date | Date | No | Agent-facing |
| Lead Quality | Picklist | No | A, B, C, Unqualified |
| Lost Reason | Picklist | No | No Response, Budget Mismatch, Location Mismatch, Bought Elsewhere, Not Ready, Duplicate, Other |

### Contacts

Purpose: qualified clients, past clients, sellers, landlords, referral partners.

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Contact Type | Picklist | Yes | Buyer, Seller, Renter, Landlord, Investor, Past Client, Referral Partner |
| Preferred Contact Method | Picklist | No | Call, Email, SMS, WhatsApp |
| Buying Timeline | Picklist | No | Same values as Lead Timeline |
| Selling Timeline | Picklist | No | Same values as Lead Timeline |
| Referral Source | Lookup / Single Line | No | Use text in V1 if lookup adds friction |
| Past Client Status | Picklist | No | Active, Closed, Referral Nurture, Inactive |
| Anniversary Date | Date | No | Nurture use |

### Accounts

Purpose: companies, investors, landlords, developers, and referral partners.

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Account Type | Picklist | Yes | Investor, Developer, Landlord, Vendor, Referral Partner, Company Buyer, Other |
| Primary Market | Single Line | No | City/region |
| Relationship Owner | Lookup User | No | Internal owner |

### Deals / Potentials

Purpose: active real estate opportunities.

Layouts:

- Buyer Deal
- Seller Listing Deal
- Rental Deal

Pipeline stages:

- New Inquiry
- Contacted
- Qualified
- Property Matched
- Site Visit Scheduled
- Site Visit Completed
- Offer Sent
- Negotiation
- Booking / Agreement
- Payment / Closing
- Closed Won
- Closed Lost
- Nurture

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Deal Type | Picklist | Yes | Buyer, Seller Listing, Rental, Investor |
| Related Property | Lookup: Properties | No | Main property |
| Buyer / Client | Lookup: Contacts | No | If not native contact field |
| Assigned Agent | Lookup: Users | Yes | Owner can also be used |
| Budget Min | Currency | No | Buyer/renter |
| Budget Max | Currency | No | Buyer/renter |
| Target Location | Single Line | No | Generic field |
| Expected Commission | Currency | No | Manager use |
| Close Probability | Percent | No | Keep simple |
| Last Stage Change Date | Date | No | Stale deal reporting |
| Next Action | Single Line | No | Agent-facing |
| Next Action Due | Date | No | Agent-facing |
| Lost Reason | Picklist | No | No Response, Price, Location, Financing, Competitor, Not Ready, Other |

## Custom Modules

### Properties

Purpose: brokerage listings and property inventory.

Record name: `Property Name`

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Property Code | Auto Number / Single Line | Yes | Unique internal ID |
| Property Status | Picklist | Yes | Available, Under Offer, Booked, Sold, Rented, Withdrawn |
| Listing Type | Picklist | Yes | Sale, Rent, Lease |
| Property Type | Picklist | Yes | Apartment, House, Condo, Townhome, Land, Commercial, Office, Retail, Industrial, Other |
| Address | Multi-line | No | Keep generic for Marketplace |
| City | Single Line | Yes | |
| Area / Community | Single Line | No | |
| Bedrooms | Number | No | |
| Bathrooms | Number | No | |
| Size | Number | No | Sq ft or local unit |
| Asking Price | Currency | No | |
| Rent Amount | Currency | No | |
| Owner Contact | Lookup: Contacts | No | Seller/landlord |
| Owner Account | Lookup: Accounts | No | Developer/landlord company |
| Listing Agent | Lookup: Users | No | |
| Available From | Date | No | |
| Listing URL | URL | No | |
| Notes | Multi-line | No | |

### Site Visits

Purpose: showings, viewings, and appointment outcomes.

Record name: `Site Visit Name`

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Deal | Lookup: Deals | Yes | |
| Property | Lookup: Properties | Yes | |
| Client | Lookup: Contacts | No | |
| Agent | Lookup: Users | Yes | |
| Visit Date/Time | Date/Time | Yes | |
| Visit Status | Picklist | Yes | Scheduled, Completed, No-show, Cancelled, Rescheduled |
| Client Feedback | Picklist | No | Interested, Not Interested, Needs Follow-up, Offer Possible |
| Follow-up Required | Checkbox | No | |
| Follow-up Due | Date | No | |
| Visit Notes | Multi-line | No | |

### Bookings

Purpose: accepted offer, agreement, or booking status before final close.

Record name: `Booking Name`

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Deal | Lookup: Deals | Yes | |
| Property | Lookup: Properties | Yes | |
| Client | Lookup: Contacts | Yes | |
| Booking Status | Picklist | Yes | Draft, Documents Pending, Agreement Sent, Deposit Pending, Confirmed, Cancelled |
| Booking Amount | Currency | No | |
| Deposit Amount | Currency | No | |
| Agreement Status | Picklist | No | Not Started, Drafted, Sent, Signed, Cancelled |
| Payment Status | Picklist | No | Not Due, Pending, Partial, Paid, Failed |
| Booking Date | Date | No | |
| Closing Date | Date | No | |
| Admin Notes | Multi-line | No | |

### Commissions

Purpose: simple commission tracking for broker visibility.

Record name: `Commission Name`

Fields:

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Deal | Lookup: Deals | Yes | |
| Booking | Lookup: Bookings | No | |
| Agent | Lookup: Users | Yes | |
| Commission Type | Picklist | Yes | Sale, Rental, Referral, Bonus |
| Gross Commission | Currency | No | |
| Agent Split % | Percent | No | |
| Agent Commission | Currency | No | If formula not supported in package, use manual currency field |
| Payout Status | Picklist | Yes | Pending, Approved, Paid, On Hold |
| Payout Date | Date | No | |
| Finance Notes | Multi-line | No | |

## Custom Views

Leads:

- Hot Leads
- New Leads Today
- No Follow-up Leads
- Open House Leads
- Website Leads
- Lead Source Cleanup

Deals:

- My Active Deals
- Stale Deals
- Deals With Site Visits
- Offers In Negotiation
- Closing This Month
- Nurture Deals

Properties:

- Available Properties
- Under Offer
- Sold / Rented
- My Listings
- Properties Missing Price

Site Visits:

- Today
- This Week
- Completed Awaiting Follow-up
- No-shows

Bookings:

- Documents Pending
- Deposit Pending
- Confirmed This Month

Commissions:

- Pending Approval
- Approved Not Paid
- Paid This Month

