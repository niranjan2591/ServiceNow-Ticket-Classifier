# Case Examples — Common Mistakes and Corrections

Distilled from the BASE L2C LOB5 Quality Assessment (Aug–Sep sessions) and live classification tests.

---

## Common Classification Mistakes to Avoid

### 1. ATLAS Quotes vs Opportunity Management
**Mistake:** Logging under SAPIT-CP-ATLAS Quotes when the question is a general CRM opportunity question.
**Correct:** SAPIT-CP-ATLAS Quotes is ONLY for actual ATLAS deal mechanics. For general CRM opportunity guidance, use SAPIT-CP-Opportunity Management + CRM Opportunity.
**Rule:** Keywords that signal ATLAS: "configuration", "FUND material", "PTO", "Packaged deal", "ATLAS".
**Case example (Aug 19):** User needed guidance on a CRM opportunity — wrongly tagged ATLAS Quotes + Technical Incident. Correct: Opportunity Management + CRM Opportunity + Usability.

### 2. Technical Incident vs Usability
**Mistake:** Tagging Technical Incident when the user just needed guidance or steps.
**Correct:** If the system IS working as designed and the user simply doesn't know the steps → Usability. Technical Incident requires a developer or DevOps fix.
**Signal:** Resolution = "please follow these steps" → Usability. Resolution = "escalating to DevOps" → Technical Incident.
**Case example (Aug 19):** User needed advice on how to resolve an opportunity issue — wrongly tagged Technical Incident. Correct: Usability.

### 3. Quote Info Section vs Opportunity Management (Header Fields)
**Mistake:** Using SAPIT-CP-Opportunity Management for header field questions.
**Correct:** Header fields (header close date, contract start/end dates) live in the Quote Info Section tab → SAPIT-CP-Quote Info Section + Header Fields.
**Case example (Aug 19):** Initial confusion between OPP MANAGEMENT vs QUOTE INFO SECTION for a header fields issue. Correct: Quote Info Section + Header Fields.

### 4. Quote Info Section vs Deal Health (GTS Error)
**Mistake:** Tagging Quote Info Section + Header Fields when the core issue is a GTS/compliance check error.
**Correct:** If the issue is about a GTS error or compliance check blocking an action → SAPIT-CP-Deal Health + Compliance Checks.
**Case example (Aug 25):** User couldn't extract an Excel file — the reason was an unresolved GTS error. Correct: Deal Health + Compliance Checks + Error Message.

### 5. AI Products — Line Item Edits vs AI PUPM
**Mistake:** Using Line Item Edits when the core issue is about AI product behaviour in a quote.
**Correct:** If the issue is about AI products, AI quantities, or AI SKU behaviour → AI PUPM.
**Case example (live test):** AI SKU greyed out in Phase Builder → Usability + BoM & Pricing + AI PUPM (not Phasebuilder or Line Item Edits).
**Case example (Aug 27):** AI quantity reverted back → Manual Transaction + BoM & Pricing + AI PUPM (not Line Item Edits).

### 6. ATLAS Keywords — Reclassify from BoM & Pricing
**Mistake:** Logging ATLAS-related issues under BoM & Pricing + Line Item Edits.
**Correct:** Keywords PTO, FUND material, ATLAS Packaged, ATLAS configuration → SAPIT-CP-ATLAS Quotes + PTO or Packaged.
**Case example (Aug 27):** Ticket involved ATLAS configuration/FUND material/PTO — correct Service Offering is ATLAS Quotes, not BoM & Pricing.

### 7. DDA vs Deal Health (Compliance Checks)
**Mistake:** Using SAPIT-CP-Deal Health + Compliance Checks when the DDA is the source of the issue.
**Correct:** If the DDA (Digital Discovery Assessment) is preventing the GTS check → SAPIT-CP-Opportunity Management + DDA.
**Case example (Sep 3):** Initially thought Deal Health + Compliance Checks. Changed to Opportunity Management + DDA because DDA was preventing the GTS check.

### 8. Contracting vs Booking/Unbooking (Cancel Booking)
**Mistake:** Using SAPIT-CP-Contracting for cancel booking / restructure requests.
**Correct:** Cancel booking at the opportunity level → SAPIT-CP-Booking/Unbooking Opportunities.
**Note:** No specific LoB Field 5 for restructure exists yet. Flag this gap.
**Case example (Aug 27):** User asking to cancel booking — correctly redirected to Booking/Unbooking, not Contracting.

### 9. Prior Purchase vs BoM & Pricing (CAA Workbench)
**Mistake:** Logging CAA Workbench errors under Quote T&C or BoM & Pricing.
**Correct:** CAA Workbench is under SAPIT-CP-Prior Purchase & Bill of Materials Setup.
**Case example (Aug 13):** Initial confusion between Quote T&C and Prior Purchase. Correct: Prior Purchase + CAA Workbench.

### 10. Docusign-related issues
**Gap:** No specific LoB Field 5 exists for Docusign. Use SAPIT-CP-Contracting + CMS Templates as the closest available option. Flag this limitation in your output.

### 11. Services Deals — Delay Flush & Fill
**Pattern:** Revenue discrepancy between quote value and opportunity value in a Services deal → SAPIT-CP-Services Deals + Delay Flush & Fill.
**Rule:** Deal revenue reflects main quote value only when quote status is "Contract in Validation".

### 12. Deal Reviews & Approval — T&C Triggers Approver
**Pattern:** User wants to remove a TI approver, but it was triggered by T&C settings → SAPIT-CP-Deal Reviews & Approval + Deal Review.
**Note:** LoB Field 5 follows the ACTION the user is requesting (managing the approver), not where the root cause is.

---

## Patterns from Live Classification Tests

### AI SKU greyed out in Phase Builder
- **Subcategory:** Usability (resolution = simple guidance: remove and re-add phase)
- **Service Offering:** SAPIT-CP-Bill of Materials and Pricing Section
- **LoB Field 5:** AI PUPM (AI SKU behaviour; KB articles on AI products were attached)
- **Not:** Phasebuilder (Phase Builder was the location, not the core issue)

### CRM Renewal Opportunity auto-renewed earlier than scheduled
- **Subcategory:** Data Inquiry (investigating why renewal executed on wrong date)
- **Service Offering:** SAPIT-CP-Opportunity Management
- **LoB Field 5:** CRM Opportunity (CRM URL confirmed in ticket)
- **⚠️ Warning:** Ticket mentioned IQR → do NOT use SAPIT-CP-OBV

### Line item business type change (e.g. Downsell)
- **Subcategory:** Manual Transaction (asking support to set it, not asking how)
- **Service Offering:** SAPIT-CP-Bill of Materials and Pricing Section
- **LoB Field 5:** Line Item Edits (Dates, Discounts, Prices) — "other line item information" covers business type

### "Manually priced" flag persisting in quote
- **Subcategory:** Error Message (flag/warning that persists despite user's attempt to clear it)
- **Service Offering:** SAPIT-CP-Bill of Materials and Pricing Section
- **LoB Field 5:** Line Item Edits (Dates, Discounts, Prices) — manual price override on a line item
- **Consider:** If the user manually set the price themselves and needs guidance to undo it → Usability instead

### T&C fields not saving — agent also cannot save
- **Subcategory:** Technical Incident (agent reproduced the same issue → not user-specific → requires DevOps)
- **Service Offering:** SAPIT-CP-Quote Terms & Conditions
- **LoB Field 5:** Payment Terms (primary change requested was payment terms)
- **Consider:** If slow loading affects multiple users system-wide → Performance & Downtimes

### Customer name change in Parties section
- **Subcategory:** Manual Transaction (internal user asking support to update the field — OFs already created)
- **Service Offering:** SAPIT-CP-Quote Info Section
- **LoB Field 5:** Parties & Customer
- **Note:** LoB definition says "may route to Data Management" — flag this
- **Consider:** If trigger was an external customer legally renaming themselves → Customer Request instead

### CRM PC stuck restructure (prior order ID missing)
- **Subcategory:** Technical Incident (stuck restructure = system not completing as designed)
- **⚠️ WARNING:** This ticket type may belong to Order to Cash / SAPIT-CP-Public Cloud Order Management, NOT Opportunity to Close. Always flag when fulfillment/order management tags (PC-OM_Fulfillment, PC-OM_Restructure) are present. The LoB Field 5 reference only covers Opportunity to Close service offerings.

### Quote locking issue misidentified as Quote Info Section
- **Case example (Aug 27):** Ticket involved Phase Builder technical issue, not quote locking → Correct: BoM & Pricing + Phasebuilder + Technical Incident (not Quote Info Section + Quote Locking)

### Approval routing confusion — T&C vs Deal Reviews
- **Case example (Sep 2):** User wanted to remove TI approver from quote. The approver was triggered by T&C settings, making LoB Field 5 confusing. Correct path: Deal Reviews & Approval + Deal Review (follow the action requested, not the root cause location).