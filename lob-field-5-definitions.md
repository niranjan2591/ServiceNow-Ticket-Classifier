# LoB Field 5 Definitions
Version: 2.0 | Organized by Service Offering

---

## How to Use

LoB Field 5 identifies the FUNCTIONAL AREA (Service Offering sub-category) of the ticket.
It is determined INDEPENDENTLY from Root Cause Category.

- Root Cause Category = HOW the issue presents (bug, access block, how-to question, etc.)
- LoB Field 5 = WHERE in the system the issue is (which functional topic / area)

If a sub-category is described as covering a specific topic, always prefer it over a more general option within the same Service Offering.

---

## SAPIT-CP-CRM/Harmony Authorizations

**SCOPE:** Access-related issues in CRM and Harmony Quote — inability to view, create, or maintain opportunities; authorization profile selection and request submission.

**LOB FIELD 5 OPTIONS:**
- **Authorizations** — ONLY option. Use for all authorization requests and access-related issues in CRM and Harmony Quote, including post-submission errors.

---

## SAPIT-CP-Opportunity Management

**SCOPE:** Adjustments at the Opportunity level in Harmony, including status changes, deal field updates, and related platforms (VBE, DDA). NOT for booked deal changes — use Booking/Unbooking Opportunities for those.

**LOB FIELD 5 OPTIONS:**
- **Opportunity Details** — Questions or updates about deal update, phase, revenue, deal success, close plan, customer/partner/competitor, or org/team/programs section.
- **Opportunity Status Change** — Requests to change status to discontinued, lost, in process, or won. Does NOT include reopening booked opportunities.
- **CRM Opportunity** — Questions about an opportunity created in CRM only (NOT in Harmony Quote). Identify by CRM URL in the ticket.
- **Value Business Engine** — Issues with VBE engine processing sales transactions from digital stores / SAP Store / Partner stores (App Centers).
- **DDA** — Questions about Digital Discovery Assessment integrated into Harmony deals.

---

## SAPIT-CP-Indirect & Partner Deals

**SCOPE:** EDDF & DCCE workflows; issues for partner-submitted deals from deal to quote.

**LOB FIELD 5 OPTIONS:**
- **EDDF & ECPD Cases** — Issues related to EDDF or ECPD submissions, approvals, or errors.
- **DCCE Cases** — DCCE workflow issues impacting quote approvals.
- **Billing Schedule Update Manually** — Manual updates of billing schedule in quote T&Cs.
- **Delos Deals** — Issues related to Delos Cloud deals.
- **Opportunity Management** — Support at the opportunity level including DRS Deal Discontinuation topics in indirect/partner flows.

---

## SAPIT-CP-Prior Purchase & Bill of Materials Setup

**SCOPE:** BoM uploads, renewal type/duration changes, prior purchase menu in Harmony Quote, and CAA Workbench integration.

**LOB FIELD 5 OPTIONS:**
- **BoM Upload** — BoM Upload requests performed by Transactional Unit as a service. Does not include Deal Modelling Tool or Quote Tool uploads.
- **Renewal Type & Duration** — Requests to update renewal type and/or duration because quote populates incorrectly from prior purchase, or needs an exceptional override.
- **Prior Purchase Menu** — Issues with information displayed in the prior purchase menu.
- **CAA Workbench** — Issues with Cloud Architect Advisor workbench integration, CAA Request Sign Off, and related errors.

---

## SAPIT-CP-Quote Info Section

**SCOPE:** Inputs in the Quote Info section in Harmony or quotation details in CRM quotes, including header fields, quote locking, and CIC topics.

**LOB FIELD 5 OPTIONS:**
- **Parties & Customer** — Issues with the Parties & Customer tab (address not populating, missing ERP number, customer name changes, etc.). Often resolved via flush & fill. May route to Data Management.
- **CRM Quote** — A quote processed in CRM only. Does not include Field Services.
- **Header Fields** — Issues with header fields (header close date, contract start/end dates, etc.).
- **Quote Locking** — Quote is locked due to another active user or an upload blocking edits.
- **CIC Calculations Redirect** — How to add Extension Policy (OnPrem & Cloud) product, insert S/4 conversion item, create a new CIC transaction, view/check CIC cases, or add a conversion product in Harmony Quote.

---

## SAPIT-CP-Bill of Materials and Pricing Section

**SCOPE:** Pricing summary, Phase Builder, Deal Modelling Tool, Price date, products/SKUs, line item edits, material blocking, LEP, and BDC/AI deals.

**LOB FIELD 5 OPTIONS:**
- **Pricing Summary** — Pricing summary section not populating correct values or no values at all.
- **Phasebuilder** — How to use Phase Builder functionality and associated red error handling.
- **Deal Modelling Tool** — How to use DMT and related errors (import/export).
- **Products & SKUs** — Questions about a specific product/SKU/material ID. Often redirected to Pricing teams as BASE does not advise on which product to sell.
- **Line Item Edits (Dates, Discounts, Prices)** — Requests to edit contract start/end dates, pricing dates, pricing, discounts, business type, or other line item information.
- **Material Master Topics** — Material blocking or unblocking issues. Related to red errors about A3, A4, A7, A8, A9, B7, B8, B9 product/material statuses.
- **Incorrect LEP** — Questions about the LEP (Low End Price) of a product. Often redirected to Pricing/Commercial Business Partner.
- **BDC (Business Data Cloud)** — Questions related to BDC deals.
- **AI PUPM** — Questions related to AI product behavior in quotes.

---

## SAPIT-CP-Deal Health

**SCOPE:** Mandatory deal health checks — BoM Checks (Auto Attach, Prerequisite) and Compliance Checks (GTS, Commission, AR Control) and associated errors.

**LOB FIELD 5 OPTIONS:**
- **BoM Checks (Auto Attach, Prerequisite Check)** — Questions about Auto Attach and Prerequisite Checks based on products added to the BoM.
- **Compliance Checks (GTS Check, Commission Check, AR Control)** — Questions about status or next steps for GTS, Commission, or AR Control Check. May need flush & fill if status is incorrect.

---

## SAPIT-CP-Provisioning Details

**SCOPE:** Errors or advisory for provisioning configuration in in-progress quotes (EU Access, Data Center, infrastructure provider, etc.) and Simulation Tool inquiries.

**LOB FIELD 5 OPTIONS:**
- **EU Access - Quote Issue** — Error handling or advisory on EU Access selection at quote stage.
- **EU Access - Fulfillment Issue** — Error handling or advisory on EU Access at fulfillment stage.
- **Data Center - Quote Issue** — Error handling or advisory on Data Center selection at quote stage.
- **Data Center - Fulfillment Issue** — Error handling or advisory on Data Center at fulfillment.
- **Other Prov. Fields - Quote Issue** — Error handling or advisory on other provisioning fields (location, infrastructure provider, etc.) at quote stage.
- **Other Prov. Fields - Fulfillment Issue** — Same as above at fulfillment stage.

**RULE:** Use "Quote Issue" for issues on in-progress quotes. Use "Fulfillment Issue" for issues on booked or fulfilled orders.

---

## SAPIT-CP-Quote Terms & Conditions

**SCOPE:** Payment Terms, Increase Type & Percentage, MCCA, other T&Cs, and EU Data Act fields. BASE advises only on where to enter information — not on commercial/legal content.

**LOB FIELD 5 OPTIONS:**
- **Payment Terms** — Questions about the payment terms section in quote T&Cs.
- **Increase Type & Percentage** — Questions about updating increase type & percentage, including when system pulls incorrect information from prior purchase.
- **MCCA** — Questions about MCCA eligibility and related red error messages on the quote. NOT for CCFlex deals — use MCCA - CCFlex instead.
- **Other T&Cs** — Any T&C question NOT covered by MCCA, Payment Terms, or Increase Type & Percentage.
- **EU Data Act** — Questions about EU Data Act fields in T&Cs, including requests to manually update selections with super user authorization.

---

## SAPIT-CP-Services Deals

**SCOPE:** Solutioning Tool (OPUS), Field Services CRM deals, PS/PE Bundles in Harmony, Delay Flush & Fill, and Max Success Plan.

**LOB FIELD 5 OPTIONS:**
- **Solutioning Tool (OPUS)** — Questions about the solutioning tool platform linked within Services deals in Harmony.
- **Field Services (CRM)** — Questions about Field Services (FS) deals run exclusively in CRM.
- **PS or PE Bundles** — Questions about PS (Professional Services) or PE (Premium Engagement) Services deals. Identifiable by bundles entered in the BoM.
- **Delay Flush & Fill** — Questions about delay flush & fill exclusively in Services deals. Deal revenue reflects main quote value only when quote status is "Contract in Validation".
- **Max Success Plan** — Questions about Max Success Plan (cloud or services component).

---

## SAPIT-CP-CCFlex

**SCOPE:** CCFlex commission rate adjustments, CCFlex descriptor maintenance, and other CCFlex deal-related issues.

**LOB FIELD 5 OPTIONS:**
- **CCFlex C&S Commission Adjustment** — Commission adjustments for CCFlex deals (excluding Change Quote).
- **C&S Commission Rate Updates for Change Quote** — Commission adjustments for CCFlex Change Quote deals specifically.
- **CCFlex Program Eligibility & Descriptor** — Validating CCFlex eligibility and descriptor maintenance.
- **MCCA - CCFlex** — MCCA eligibility and red error messages on CCFlex quotes specifically.
- **CCFlex Other** — Any CCFlex-related inquiry not covered by the above options.

---

## SAPIT-CP-ATLAS Quotes

**SCOPE:** Questions related to ATLAS deals only.

**LOB FIELD 5 OPTIONS:**
- **PTO** — Questions related to ATLAS PTO deals.
- **Packaged** — Questions related to ATLAS Packaged deals.

**Signal keywords:** configuration, FUND material, PTO, Packaged deal, ATLAS

---

## SAPIT-CP-NGCS Runway

**SCOPE:** Deals being processed in NGCS (Next Generation Cloud Selling).

**LOB FIELD 5 OPTIONS:**
- **NGCS** — All questions related to deals being processed in NGCS.

---

## SAPIT-CP-OBV (Order Based Value)

**SCOPE:** OBV Validation and Correction for OQR deals. IQR deals are handled with the CRC — do NOT use this service offering for IQR.

**LOB FIELD 5 OPTIONS:**
- **OBV Validation** — Questions or requests for OBV Validation.
- **OBV Correction** — Questions or requests for OBV Correction.

**RULE:** Distinguish by whether the user is asking to verify (Validation) or fix (Correction). If the ticket mentions IQR, do NOT use this service offering.

---

## SAPIT-CP-Deal Reviews & Approval

**SCOPE:** Special Bid Offering functionality, deal reviews and approvals, approval routing & status, and the deal approval BTP app.

**LOB FIELD 5 OPTIONS:**
- **Special Bid Offering** — Questions about SBO check related to third-party products in Harmony Quotes.
- **Deal Review** — Questions about requesting a deal review (mandatory or optional).
- **Deal Approval Routing & Status** — Questions about who the approvers are, number of approvers, approval status (in progress vs. approved), or technical issues with approval stuck in incorrect status. Does NOT include BTP Deal Approval App questions.
- **Deal Approval BTP App** — Questions about the BTP Deal Approval Workflow app shown in the Review/Approval tab of the quote.

---

## SAPIT-CP-Technical Check

**SCOPE:** Mandatory reviews for AliChina and Neo/Non-standard DCs, and quote review/approval of DHI provisioning flags.

**LOB FIELD 5 OPTIONS:**
- **AliChina CCEM Review** — CCEM verification process for Alibaba Cloud China deals.
- **Neo and Non-standard DC CCEM Review** — CCEM verification process for Neo and Non-standard data centers.
- **DHI Flag Review and Approval** — Review and approval of provisioning DHI flags.

---

## SAPIT-CP-Contracting

**SCOPE:** Interaction between CMS case and quote, print format options, quote-to-order form mismatches, Icertis, templates, legal content, Trust Center, and CCS.

**LOB FIELD 5 OPTIONS:**
- **CMS System** — Issues with CMS platform functionality, configuration, or integration.
- **CMS Contracts** — Issues with Print Format Options button on Quote or order form mismatch and document-related issues in CMS.
- **Icertis System** — Issues with Icertis system operations, connectivity, or configuration.
- **CMS Templates** — Problems with CMS templates or automated contract generation / workflow. Also use for Docusign-related topics (no specific Docusign LoB Field 5 exists — flag this gap).
- **Icertis Contracts** — Problems with Icertis templates or automated contract generation.
- **Legal Content** — Issues related to clause libraries, legal text accuracy, or clause formatting.
- **Trust Center** — Concerns about document publication, retrieval, or integrity in the Trust Center repository.
- **CCS (Contracting Content Solution)** — Issues related to Contracting Content Solutions applications.

---

## SAPIT-CP-Booking/Unbooking Opportunities

**SCOPE:** Changes to already-booked opportunities. Valid changes: adding SDE/Digital Hub Advisor to Sales Team, Maintenance Renewal Unbooking, correcting Opportunity status that did not automatically change to Booked.

**LOB FIELD 5 OPTIONS:**
- **Unbooking Maint. Opportunity** — Requests to unbook on-premise maintenance renewal or "maint." opportunities in CRM. Requested only by select users.
- **Reopen Booked Opportunity** — Requests to reopen booked opportunities for changes. Only for highly exceptional cases — reopening booked deals poses significant compliance risk.
- **Set Opportunity to Booked (Incorrect Status)** — Setting an Opportunity to Booked status when the Quote is already fully booked but the Opportunity status did not change automatically (often due to a red error on the Opportunity).

---

## WHAT TO CONSIDER CHANGING

After recommending LoB Field 5, always check these triggers and include a ticket-specific note:

- **If the ticket touches BOTH the quote stage AND the fulfillment stage:** Confirm whether the provisioning issue is on the quote (use "Quote Issue" variant) or on the booked order (use "Fulfillment Issue" variant).

- **If the issue is about an in-process Harmony deal but involves a booked opportunity:** Reconsider whether Service Offering should be SAPIT-CP-Booking/Unbooking Opportunities rather than SAPIT-CP-Opportunity Management.

- **If the ticket mentions VBE / SAP Store / digital channel transactions:** LoB Field 5 should be "Value Business Engine" not "Opportunity Details", even if the question appears to be about the opportunity.

- **If the ticket mentions MCCA but is for a CCFlex deal:** Use "MCCA - CCFlex" not "MCCA" — the CCFlex-specific sub-category routes differently.

- **If the ticket is about OBV but the deal is an IQR (not OQR):** Do not use SAPIT-CP-OBV — redirect to the CRC process instead.

- **If the ticket mentions both a BoM upload AND a prior purchase mismatch:** These belong to different Service Offerings. Identify the PRIMARY issue the user needs resolved first and classify accordingly.

Always state: what specific condition changes the recommendation, and which Service Offering + LoB Field 5 to switch to instead.