# Root Cause Category Definitions
Version: 1.0 | Written for human agents and AI classification

---

## How to Use

Each category follows the same structure:
- **WHAT IT IS**: Plain-English summary of when to use this category
- **AGENT SIGNALS**: Phrases an agent typically writes indicating this category
- **CUSTOMER SIGNALS**: Phrases a customer typically writes indicating this category
- **WHAT IT IS NOT**: Common confusion — what to use instead
- **EXAMPLES**: Real-world ticket scenarios

---

## ACCESS ISSUE

**WHAT IT IS:**
The user is trying to do their job but cannot access a specific system, application, report, or function. The barrier is permissions-based, not a system error. The system is working — the user just does not have the right access level, role, or geographic permission to use it.

**AGENT SIGNALS:**
- "I have reviewed your access rights and updated your role"
- "Your authorization profile has been adjusted"
- "I have escalated to ADRM for access provisioning"
- "Your current role does not include edit rights for this module"
- "I have requested the access update from the admin team"

**CUSTOMER SIGNALS:**
- "I cannot log in / sign in"
- "The button is greyed out and I don't have permission"
- "I used to have access but now it is gone"
- "I get an authorization error when I try to open the report"
- "My colleague can see it but I cannot"

**WHAT IT IS NOT:**
- NOT Error Message: the system is not showing an error — the user simply lacks permission
- NOT Usability: the user knows how to use it but is blocked by access rights
- NOT Technical Incident: no bug or code fix is needed — just a role or profile change

**EXAMPLES:**
1. Agent cannot access the pricing dashboard after a role change last week
2. New joiner cannot open the opportunity module — missing authorization profile
3. User can view quotes but cannot edit them — view-only role needs updating
4. GTM access blocked for a user in a different region

---

## ADVISORY

**WHAT IT IS:**
A complex consultation request that goes beyond a simple how-to question. These tickets require discussion, strategic alignment, or expert input across multiple teams. They are not bugs, not access problems, and not routine transactions. They involve hypothetical scenarios, policy interpretation, financial implications, or new/complex business situations.

**AGENT SIGNALS:**
- "I have aligned with the business team on this scenario"
- "This requires a consultation with the pricing and legal teams"
- "I am coordinating with multiple stakeholders on this"
- "This is a complex deal scenario requiring advisory input"
- "I will set up a call with the relevant business owners"

**CUSTOMER SIGNALS:**
- "What would happen if we...?"
- "We are considering a new deal structure and need guidance"
- "Is there a policy for handling this type of situation?"
- "We need to understand the downstream impact before we proceed"
- "This is a new market scenario we have not handled before"

**WHAT IT IS NOT:**
- NOT Usability: Usability is a simple how-to question answerable in one message
- NOT Data Inquiry: Advisory is about decisions and strategy, not data lookups
- NOT Customer Request: Advisory is about guidance, not executing a specific change

**EXAMPLES:**
1. A large enterprise asks how restructuring a deal will affect downstream systems
2. Sales team needs alignment on applying a new pricing policy to legacy contracts
3. Manager asks for input on a financial scenario not covered by existing rules
4. Hypercare situation for a newly launched system requiring proactive support

---

## CUSTOMER REQUEST

**WHAT IT IS:**
A change or update that originates from an external customer (outside SAP) but must be made by an internal support team inside SAP systems. The customer cannot make the change themselves — a support specialist must perform the operation on their behalf in the backend. The key distinction is that the action directly affects the customer's own solution or account.

**AGENT SIGNALS:**
- "I have updated the contact person in the system as requested"
- "I have enabled EU Access on the booked order"
- "I have changed the payment terms as per the customer's request"
- "The tenant access has been provisioned for the customer"
- "I have updated the CPIT information in the backend"

**CUSTOMER SIGNALS:**
- "Please update my contact details in your system"
- "We need EU Access enabled on our order"
- "Can you change the payment terms on our account?"
- "Please add a new user to our tenant"
- "We need our contract address updated"

**WHAT IT IS NOT:**
- NOT Manual Transaction: Manual Transaction is for internal user operations (SAP employees); Customer Request is for changes requested by and affecting the external customer
- NOT Data Inquiry: Data Inquiry is for questions about data; Customer Request is an action
- NOT Advisory: Customer Request is a specific change, not a consultation

**EXAMPLES:**
1. Customer requests EU Access to be enabled on a booked order
2. Customer asks to update their billing contact in the system
3. Customer requests a new user be added to their SAP tenant
4. Customer needs payment terms updated on their account record

---

## DATA INQUIRY

**WHAT IT IS:**
A question or concern about specific data values in the system — whether something is correct, why two systems show different numbers, or what a particular data record contains. The user is not blocked from access and there is no system error. They simply need data clarified, verified, or explained.

**AGENT SIGNALS:**
- "I have verified the pricing data in the backend"
- "The SKU is showing correctly in the system"
- "The discrepancy between the two values is due to..."
- "I have checked the sales organization data and confirmed..."
- "The account data has been reviewed and updated"

**CUSTOMER SIGNALS:**
- "Why does the price in system A differ from system B?"
- "Is this SKU number correct?"
- "The data shown here does not match what we have on file"
- "Can you confirm the sales organization assigned to this account?"
- "The material blocking status shows incorrectly"

**WHAT IT IS NOT:**
- NOT Error Message: there is no error on a process step — just a data question
- NOT Reporting Logic: Reporting is about calculation logic and KPI definitions; Data Inquiry is about specific data values in records
- NOT Customer Request: Data Inquiry is a question; Customer Request is an action

**EXAMPLES:**
1. Account manager asks why two systems show different pricing for the same product
2. User queries whether the SKU listed on a quote is the correct material number
3. Data discrepancy between the tenant record and the CRM system
4. Question about which sales organization is assigned to a specific partner

---

## ERROR MESSAGE

**WHAT IT IS:**
The system is showing an error message, warning, or flag to the user on a specific process step or entry point. The error causes uncertainty — the user does not know how to proceed. The solution is either to remove the error/flag directly in the backend, or guide the user through steps that clear it. This category also covers errors that the agent CANNOT REPRODUCE on their end but that the user is definitely seeing — these are environment-specific or client-side error messages.

**AGENT SIGNALS:**
- "Upon checking there is no error" (agent cannot reproduce — still Error Message)
- "We don't see any error from our end" (environment-specific error — still Error Message)
- "We have removed the invalid error flag"
- "I have cleared the error from the system"
- "The system is showing an error on step X — please follow these steps to clear it"
- "We have investigated and resolved the error message"
- "The error is not visible on our side but we are investigating"

**CUSTOMER SIGNALS:**
- "I am getting an error message when I try to..."
- "The system shows a red error / warning on this step"
- "I cannot proceed because of an error"
- "GTS is showing an error even after execution"
- "The error is still there after I cleared the cache and restarted"
- "The error appears for me but my colleague says they don't see it"
- "Even after removing the product the error persists"

**WHAT IT IS NOT:**
- NOT Technical Incident: Technical Incident requires a developer/coding fix. Error Message can be resolved by clearing a flag, guiding the user, or investigating the user's environment — no code change needed.
- NOT User Interface / Design: the issue is an error message, not a design complaint
- NOT Access Issue: the user is not blocked by permissions — they are seeing an error

**CRITICAL RULE — AGENT CANNOT SEE THE ERROR:**
If the agent writes "we don't see any error", "no error from our end", "system looks fine on our side", "cannot reproduce", or "upon checking there is no error" — the category is STILL Error Message. The error exists on the user's specific environment.

**KEY DISTINCTION FROM TECHNICAL INCIDENT:**
Ask: "Can a support agent resolve this WITHOUT a developer?"
- YES → Error Message
- NO → Technical Incident

**EXAMPLES:**
1. GTS executed successfully but error message still displayed — agent clears the flag
2. User gets a pop-up error on the quote entry step — agent guides them through steps to clear it
3. Error appears after removing a product from cart — agent investigates and removes invalid flag
4. Agent cannot reproduce the error but user sends screenshot — Error Message (environment-specific)
5. "Upon checking there is no error. We don't see any error regarding AI" — still Error Message

---

## INTERNAL IMPROVEMENT

**WHAT IT IS:**
This category is for INTERNAL support team actions only — NOT for customer-facing tickets. It covers work where the support team is improving their own processes, tools, knowledge articles, AI, or categorization systems.

**WHAT IT IS NOT:**
- NOT for customer-facing error tickets
- NOT for customer access requests
- ALMOST NEVER the correct category for a customer-facing ticket

**EXAMPLES:**
1. Creating a new knowledge article for a recurring question
2. Improving categorization logic in the ticketing system
3. Updating the AI classification model for support routing

---

## MANUAL TRANSACTION

**WHAT IT IS:**
An operation that the SAP user (internal employee or partner) cannot perform themselves because they lack the required system authorizations. A support specialist must perform the transaction directly in the backend on behalf of the user. These are specific, executable transactions — not access changes, not error removals, not data questions. Includes: change price date, unit list price, and tools that only have support agent access.

**AGENT SIGNALS:**
- "I have performed the OBV correction on your behalf"
- "I have pushed the opportunity change into the quote"
- "The manual pricing adjustment has been applied"
- "I have removed the CIC case from the system"
- "I have completed the entitlement set reassignment"
- "The line item date has been updated manually"
- "We have changed the Price Date"
- "We have updated the payment terms..."

**CUSTOMER SIGNALS (internal SAP users):**
- "Please push the discount to the quote — I don't have authorization"
- "Can you correct the OBV entry? I cannot access that field"
- "Please remove this CIC case — I don't have the rights"
- "I need a manual pricing override — I cannot do it from my role"

**WHAT IT IS NOT:**
- NOT Customer Request: Manual Transaction is for internal SAP user operations; Customer Request is for changes affecting external customers
- NOT Access Issue: Access Issue = give me the permission so I can do it myself; Manual Transaction = do it for me because I will never have this permission
- NOT Error Message: the system is not showing an error — the user just cannot execute
- NOT Temporary Exception: Temporary Exception requires a formal business approval before the agent can act

**EXAMPLES:**
1. Sales rep needs a non-standard discount applied — authorization is support-only
2. OBV correction needed on an order — only support specialists can access
3. Line item date change required — user does not have write access to that field
4. Entitlement set reassignment requested — requires backend support tool access

---

## PERFORMANCE & DOWNTIMES

**WHAT IT IS:**
The system is running very slowly, completely down, or showing a spinning wheel for an extended time. This is NOT a problem for a single user — multiple users are experiencing it simultaneously. The issue cannot be fixed by restarting the browser or changing VPN. It requires technical investigation at the infrastructure level, and may need OCC involvement.

**AGENT SIGNALS:**
- "We have identified a performance degradation affecting multiple users"
- "We have escalated to OCC for investigation"
- "The system is currently experiencing downtime — we are working on restoration"
- "This is a widespread performance issue, not isolated to your account"

**CUSTOMER SIGNALS:**
- "The system is very slow for our entire team"
- "There is a spinning wheel and nothing is loading"
- "Multiple colleagues are experiencing the same slowness"
- "The platform has been down since this morning"

**WHAT IT IS NOT:**
- NOT Error Message: a spinning wheel affecting everyone is performance, not an error flag
- NOT Technical Incident: Technical Incident is a code bug for one scenario; Performance is a system-wide infrastructure issue

**SINGLE-USER RULE:**
If only ONE user has the issue and restarting/VPN switching helps, it is likely Error Message or Access Issue, not Performance & Downtimes.

**EXAMPLES:**
1. Entire sales team cannot access the quoting tool — platform is down
2. Dashboard loading takes 5+ minutes for all users in the region
3. Spinning wheel on quote creation for all users after a deployment

---

## REPORTING LOGIC & INSIGHTS

**WHAT IT IS:**
Questions or concerns about how numbers are calculated, why a metric shows a certain value, what a KPI definition means, or why two reports show different numbers for the same thing. The user understands how to USE the system but disagrees with or cannot understand what the numbers MEAN.

**AGENT SIGNALS:**
- "The KPI is calculated based on the following logic..."
- "The discrepancy between the two dashboards is due to different time filters"
- "GPAL calculates this metric by..."
- "The forecasting model uses the following inputs..."

**CUSTOMER SIGNALS:**
- "Why does this KPI show X when I expected Y?"
- "The forecast in system A does not match system B — which is correct?"
- "How is this calculation done?"
- "I don't understand what this metric is measuring"

**WHAT IT IS NOT:**
- NOT Data Inquiry: Data Inquiry is about specific data records being wrong; Reporting Logic is about understanding the calculation or metric definition
- NOT Error Message: the system is working correctly — the user questions the logic

**EXAMPLES:**
1. Why does the revenue forecast show a different number than the pipeline report?
2. How is the Win Rate KPI calculated — it seems incorrect compared to our records?
3. GPAL showing inconsistent metrics between two modules — which logic is authoritative?

---

## RELEASE RELATED

**WHAT IT IS:**
The issue or inquiry is DIRECTLY caused by a recent system release, feature update, or process change — and occurred WITHIN 3 WEEKS of that release. After 3 weeks, the same issue becomes a Technical Incident or other category.

**AGENT SIGNALS:**
- "This behavior changed after the release on [date]"
- "We have raised a problem record with the DevOps team"
- "This is a known issue following the recent deployment"

**CUSTOMER SIGNALS:**
- "This stopped working after your last update"
- "It was working fine before the new release"
- "Since the update on [date], we have been seeing this issue"

**WHAT IT IS NOT:**
- NOT Technical Incident: if more than 3 weeks have passed since the release, reclassify as Technical Incident

**EXAMPLES:**
1. Quote calculation breaks the day after a pricing module update
2. Button stops functioning immediately after a new feature deployment
3. Users unable to submit approvals following last Tuesday's release

---

## TECHNICAL INCIDENT

**WHAT IT IS:**
A confirmed bug or system defect where the system is NOT behaving as it was designed to behave. This requires investigation by a developer or DevOps team, and typically results in a code fix, hotfix, or problem record.

**AGENT SIGNALS:**
- "We are forwarding this to the DevOps team for investigation"
- "This has been escalated to the engineering team"
- "We have raised a bug report with the development team"
- "This appears to be a system defect — a developer fix is required"
- "We have confirmed this is not working as designed"
- "Escalating to L2 / L3 support for technical investigation"

**CUSTOMER SIGNALS:**
- "This worked before but now it is broken with no explanation"
- "The button does not do anything when I click it"
- "Data is not replicating correctly between systems"
- "The system is blocking me with an error I cannot clear"

**WHAT IT IS NOT:**
- NOT Error Message: Error Message can be cleared by a support agent without a code fix; Technical Incident requires a DEVELOPER to fix the underlying code
- NOT Performance: Technical Incident is a functional defect, not system slowness

**KEY DISTINCTION FROM ERROR MESSAGE:**
Ask: "Can a support agent resolve this WITHOUT a developer?"
- YES → Error Message
- NO → Technical Incident

**EXAMPLES:**
1. Replication error between two systems — data not syncing, requires DevOps
2. Clicking the "Submit" button does nothing — no error shown, just broken
3. Cache clearing happens every time user opens quote — consistent technical bug
4. Downstream system not receiving data from upstream — pipeline defect
5. Agent says "forwarding to DevOps" or "escalating to engineering team"
6. Support agent experienced the SAME issue as the user — reproducible defect

---

## TEMPORARY EXCEPTION

**WHAT IT IS:**
A situation where the normal automated process cannot handle a specific case, so a support specialist must make a one-time manual exception — but this exception requires a FORMAL BUSINESS APPROVAL (email, split ticket, manager sign-off) before it can be executed. Distinguished from Manual Transaction because Temporary Exception REQUIRES an external business approval to proceed. A roadmap for automating this exception exists or is planned.

**AGENT SIGNALS:**
- "I will need a business approval before I can process this exception"
- "Please attach the manager approval to this ticket so we can proceed"
- "A split ticket approval is required for this workaround"
- "This is a compliance-related exception — I need sign-off before executing"

**WHAT IT IS NOT:**
- NOT Manual Transaction: Manual Transaction needs no approval — agent just does it; Temporary Exception specifically requires a formal business approval first
- NOT Error Message: the issue is not an error — it is a process gap requiring approval

**EXAMPLES:**
1. Non-standard discount requires a VP-level approval email before agent applies it
2. Compliance exception for a payment term change — legal sign-off required first
3. Manual contract override that requires a split ticket with documented approval

---

## USABILITY

**WHAT IT IS:**
The user does not know how to do something. They are asking for guidance on HOW to use the system, WHERE to find something, or WHY a behavior works the way it does. These are knowledge and skill questions — the user understands what they want to achieve but does not know the steps. Usually resolved in a single interaction with a clear answer, a WalkMe guide, or a knowledge article.

**AGENT SIGNALS:**
- "Please follow these steps to complete the action..."
- "You can find this feature in the following location..."
- "Here is the guide on how to..."
- "To achieve this, please navigate to..."

**CUSTOMER SIGNALS:**
- "How do I...?"
- "Where can I find...?"
- "Why is this button greyed out?" (when the answer is a simple step, not a bug)
- "I don't know how to start a restructure"
- "Can you walk me through the process for...?"

**WHAT IT IS NOT:**
- NOT Error Message: the user is not seeing an error — they just need guidance
- NOT Access Issue: the user has the access but does not know how to use it; if they lack the permission, it is Access Issue
- NOT Advisory: Advisory involves strategic complexity; Usability is a simple how-to

**EXAMPLES:**
1. User asks how to start a quote restructure
2. User cannot find the approval button — needs navigation guidance
3. User does not understand how to interpret a field value — needs explanation
4. User asks what steps to follow to complete a standard approval workflow

---

## USER INTERFACE / DESIGN

**WHAT IT IS:**
The user CAN do their job and KNOWS how to do it, but the interface makes it unnecessarily difficult, confusing, or error-prone. This is a DESIGN complaint — the layout, labeling, or workflow is poorly structured. No system error and no missing permission.

**AGENT SIGNALS:**
- "I have logged this as a UI improvement request with the product team"
- "I have raised this as a UX feedback item for the next sprint"
- "This has been flagged to the design team for review"

**CUSTOMER SIGNALS:**
- "The button is in a confusing location"
- "The page is cluttered and hard to navigate"
- "The labels are unclear and misleading"
- "The workflow does not make sense — the steps are in the wrong order"

**WHAT IT IS NOT:**
- NOT Error Message: there is no error — the user is complaining about design
- NOT Usability: Usability = user does not know how; UI/Design = user knows how but the design makes it harder than it should be
- NOT Technical Incident: the system is working as designed — the design itself is the problem

**EXAMPLES:**
1. User complains that the "Submit" button is hidden below the fold and hard to find
2. User says the new dashboard layout is confusing because key metrics were moved
3. User reports that field labels are ambiguous and cause repeated mistakes