---
name: servicenow-ticket-classifier
description: >-
  Classifies ServiceNow incidents for the BASE L2C (Business Application Support and Engagement) team into the correct Service Offering, Root Cause Subcategory, and LoB Field 5. Use whenever ticket text, activity log, or ticket content is pasted and the user needs field recommendations. Trigger phrases: "classify this ticket", "what root cause", "which LoB field", "categorize this", "what subcategory", "help me fill in the ticket", "what should I enter", "how do I categorize this", "what fields should I use". Also activates when ticket text is pasted without further instruction.
allowed-tools: read_file
metadata:
  author: Tomasz Kulis
  version: 1.0.0
  tags: servicenow ticket-classification base-l2c lob-field-5 root-cause sap-support
---

# ServiceNow Ticket Classifier — BASE L2C

Activate when the user pastes ServiceNow ticket text (description, activity log, or any ticket content) and asks what fields to enter, how to classify the ticket, or pastes ticket text without further instruction.

## Reference Files

At the start of every classification, read these three files in a single parallel call:
- `references/root-cause-definitions.md` — definitions and signals for each Root Cause subcategory
- `references/lob-field-5-definitions.md` — Service Offering scope and LoB Field 5 options
- `references/case-examples.md` — common mistakes, corrections, and patterns from real cases

## Fixed Fields

Always output these values as-is — do not determine them:

| Field | Fixed Value |
|---|---|
| Service | Opportunity to Close (Harmony) |
| Category | Root Cause |

**Edge case — wrong service:** If ticket content strongly suggests it belongs to a different service (e.g. Order to Cash, Public Cloud Order Management, Fulfillment), add a ⚠️ warning before the table. The reference files only cover Opportunity to Close service offerings. Never force a classification if the ticket clearly belongs elsewhere.

## Fields You Determine

- **Service Offering** — SAPIT-CP-* options from `references/lob-field-5-definitions.md`
- **Subcategory** — Root Cause type from `references/root-cause-definitions.md`
- **LoB Field 5** — sub-option within the chosen Service Offering

---

## Step 1 — Determine Subcategory

Work through these questions in order. Stop at the first YES.

**Is the system not working as designed, requiring a developer or DevOps fix?**
→ **Technical Incident**
*(Key test: "Can a support agent resolve this WITHOUT a developer?" YES → Error Message. NO → Technical Incident. If the agent escalates to DevOps/engineering → Technical Incident.)*

**Is there an error message, warning, or persistent flag the user cannot clear?**
→ **Error Message**
*(Critical rule: If the agent says "we don't see any error on our end" or "cannot reproduce" but the user IS seeing one — still Error Message. The error exists in the user's specific environment.)*

**Is the user blocked from accessing something due to missing permissions or roles?**
→ **Access Issue**
*(Not to be confused with Usability: user has access but doesn't know how to use it = Usability.)*

**Is someone asking support to execute a transaction on their behalf because they lack authorization?**
→ Internal SAP user asking → **Manual Transaction**
→ External customer requesting a change that directly affects their account → **Customer Request**
*(Manual Transaction vs Customer Request: who is the requester? Internal SAP user = Manual Transaction. External customer = Customer Request.)*
*(Manual Transaction vs Temporary Exception: does the action require a formal business approval email or split ticket before the agent can act? YES = Temporary Exception. NO = Manual Transaction.)*
*(Manual Transaction vs Access Issue: "do it for me because I will never have this permission" = Manual Transaction. "give me the permission so I can do it myself" = Access Issue.)*

**Does the user simply not know how to do something?**
→ **Usability**
*(Only if no error is shown and no access is blocked. Resolution is guidance, steps, or a knowledge article.)*

**Is the system slow or down for multiple users simultaneously — not fixable by VPN or restart?**
→ **Performance & Downtimes**
*(Single-user slow loading linked to a specific action → check Error Message or Technical Incident instead.)*

**Is the question about why a number, KPI, or metric is calculated a certain way?**
→ **Reporting Logic & Insights**

**Is it about specific data values, missing data, or discrepancies between systems?**
→ **Data Inquiry**

**Did the issue start within 3 weeks of a system release or deployment?**
→ **Release Related** *(After 3 weeks → Technical Incident.)*

**Does executing the action require a formal external business approval (email, split ticket, sign-off) before proceeding?**
→ **Temporary Exception**

**Does it require multi-stakeholder consultation, strategic alignment, or complex advisory input across teams?**
→ **Advisory**

**Is the user frustrated by confusing UI/design — not a bug, not a how-to?**
→ **User Interface / Design**

**Is this an internal support team improvement action (article creation, categorization fix, process change)?**
→ **Internal Improvement** *(almost never correct for a customer-facing ticket)*

---

## Step 2 — Determine Service Offering and LoB Field 5

Match the ticket to the Service Offering based on WHERE in the system the issue is located. Then pick the most specific LoB Field 5 within that offering. Full scopes and options are in `references/lob-field-5-definitions.md`.

**Quick routing guide:**

| Issue area | Service Offering | LoB Field 5 |
|---|---|---|
| Phase Builder (how-to, errors, greyed checkbox) | SAPIT-CP-Bill of Materials and Pricing Section | Phasebuilder |
| AI product SKU behaviour / AI qty in quote | SAPIT-CP-Bill of Materials and Pricing Section | AI PUPM |
| Line item change (price, date, discount, business type, manually priced flag) | SAPIT-CP-Bill of Materials and Pricing Section | Line Item Edits (Dates, Discounts, Prices) |
| Pricing summary section values | SAPIT-CP-Bill of Materials and Pricing Section | Pricing Summary |
| Specific SKU/product/material question | SAPIT-CP-Bill of Materials and Pricing Section | Products & SKUs |
| Material blocking (A3, A4, A7, A8, A9, B7, B8, B9) | SAPIT-CP-Bill of Materials and Pricing Section | Material Master Topics |
| LEP (Low End Price) | SAPIT-CP-Bill of Materials and Pricing Section | Incorrect LEP |
| BDC deals | SAPIT-CP-Bill of Materials and Pricing Section | BDC (Business Data Cloud) |
| Deal Modelling Tool | SAPIT-CP-Bill of Materials and Pricing Section | Deal Modelling Tool |
| Payment terms in T&C | SAPIT-CP-Quote Terms & Conditions | Payment Terms |
| MCCA (non-CCFlex quote) | SAPIT-CP-Quote Terms & Conditions | MCCA |
| MCCA on CCFlex deal | SAPIT-CP-CCFlex | MCCA - CCFlex |
| Increase type / percentage | SAPIT-CP-Quote Terms & Conditions | Increase Type & Percentage |
| Other T&C fields | SAPIT-CP-Quote Terms & Conditions | Other T&Cs |
| EU Data Act fields | SAPIT-CP-Quote Terms & Conditions | EU Data Act |
| Parties & Customer tab / customer name in quote | SAPIT-CP-Quote Info Section | Parties & Customer |
| Header fields (close date, contract start/end dates) | SAPIT-CP-Quote Info Section | Header Fields |
| Quote locking | SAPIT-CP-Quote Info Section | Quote Locking |
| CIC topics | SAPIT-CP-Quote Info Section | CIC Calculations Redirect |
| CRM-only quote | SAPIT-CP-Quote Info Section | CRM Quote |
| CRM-only opportunity | SAPIT-CP-Opportunity Management | CRM Opportunity |
| Opportunity status, phase, revenue, deal fields | SAPIT-CP-Opportunity Management | Opportunity Details or Opportunity Status Change |
| DDA (Digital Discovery Assessment) | SAPIT-CP-Opportunity Management | DDA |
| VBE / SAP Store / digital channel transactions | SAPIT-CP-Opportunity Management | Value Business Engine |
| GTS / Commission / AR Control check | SAPIT-CP-Deal Health | Compliance Checks (GTS Check, Commission Check, AR Control) |
| Auto Attach / Prerequisite check | SAPIT-CP-Deal Health | BoM Checks (Auto Attach, Prerequisite Check) |
| Harmony authorizations / access issues | SAPIT-CP-CRM/Harmony Authorizations | Authorizations |
| Renewal type or duration | SAPIT-CP-Prior Purchase & Bill of Materials Setup | Renewal Type & Duration |
| CAA Workbench | SAPIT-CP-Prior Purchase & Bill of Materials Setup | CAA Workbench |
| BoM Upload | SAPIT-CP-Prior Purchase & Bill of Materials Setup | BoM Upload |
| Prior purchase menu | SAPIT-CP-Prior Purchase & Bill of Materials Setup | Prior Purchase Menu |
| ATLAS (PTO, Packaged, FUND material, configuration keywords) | SAPIT-CP-ATLAS Quotes | PTO or Packaged |
| NGCS | SAPIT-CP-NGCS Runway | NGCS |
| OBV Validation (OQR only — NOT IQR) | SAPIT-CP-OBV | OBV Validation |
| OBV Correction (OQR only — NOT IQR) | SAPIT-CP-OBV | OBV Correction |
| Deal approval routing / status / approver questions | SAPIT-CP-Deal Reviews & Approval | Deal Approval Routing & Status |
| Deal Review (mandatory or optional) | SAPIT-CP-Deal Reviews & Approval | Deal Review |
| Special Bid Offering (SBO) | SAPIT-CP-Deal Reviews & Approval | Special Bid Offering |
| BTP Deal Approval App | SAPIT-CP-Deal Reviews & Approval | Deal Approval BTP App |
| EU Access / Data Center (in-progress quote) | SAPIT-CP-Provisioning Details | [field] - Quote Issue |
| EU Access / Data Center (booked/fulfilled order) | SAPIT-CP-Provisioning Details | [field] - Fulfillment Issue |
| CCFlex commission adjustment | SAPIT-CP-CCFlex | CCFlex C&S Commission Adjustment |
| CCFlex Change Quote commission | SAPIT-CP-CCFlex | C&S Commission Rate Updates for Change Quote |
| CCFlex eligibility / descriptor | SAPIT-CP-CCFlex | CCFlex Program Eligibility & Descriptor |
| CMS / Icertis / contracting system or templates | SAPIT-CP-Contracting | CMS System / CMS Contracts / CMS Templates / Icertis System / Icertis Contracts |
| Legal content / Trust Center / CCS | SAPIT-CP-Contracting | Legal Content / Trust Center / CCS |
| Changes to already-booked opportunities | SAPIT-CP-Booking/Unbooking Opportunities | Reopen Booked / Set to Booked / Unbooking Maint. |
| Services deals (OPUS, PS/PE bundles, Field Services, Max Success) | SAPIT-CP-Services Deals | appropriate option |
| EDDF / ECPD / DCCE / partner deals | SAPIT-CP-Indirect & Partner Deals | appropriate option |
| AliChina / Neo DC / DHI reviews | SAPIT-CP-Technical Check | appropriate option |

**Always apply the "What to consider changing" triggers** from `references/lob-field-5-definitions.md` after selecting your primary recommendation.

**Critical rules — apply before finalising:**
- IQR deals → do NOT use SAPIT-CP-OBV. IQR uses the CRC process.
- VBE / SAP Store / digital channel → use Value Business Engine even if the question appears to be about an opportunity.
- MCCA on a CCFlex deal → use MCCA - CCFlex, not MCCA.
- Docusign-related → use CMS Templates as the closest available option; flag that no specific Docusign LoB Field 5 exists yet.
- Order management / fulfillment tags (PC-OM, fulfillment ops, stuck restructure) → flag potential wrong service before classifying.

---

## Step 3 — Output Format

Present the result in this exact format:

---
| Field | Value |
|---|---|
| **Service** | Opportunity to Close (Harmony) |
| **Service Offering** | [value] |
| **Category** | Root Cause |
| **Subcategory** | [value] |
| **LoB Field 5** | [value] |

**Reasoning:**
- **Subcategory**: [1–2 sentences citing specific text from the ticket]
- **Service Offering / LoB Field 5**: [1–2 sentences citing specific text from the ticket]

**Top 2 LoB Field 5 alternatives:**
1. [Option] (Service Offering) — [brief reason]
2. [Option] (Service Offering) — [brief reason]

**What to consider changing:** [ticket-specific note applying LoB triggers and case example patterns]

---

Add a ⚠️ flag before the table if the ticket appears to belong to a different Service than Opportunity to Close.

If the ticket is ambiguous, state what is uncertain and what information would help resolve it.

If the ticket has field change history showing an agent reclassification, note whether you agree or would suggest differently.