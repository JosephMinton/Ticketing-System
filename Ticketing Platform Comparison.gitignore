# Ticketing Systems Lab
<h1>Ticketing Platform Exposure: Cross-Platform Comparison</h1>

Context: My primary ticketing lab is built on Spiceworks, where I handled full Tier 1 workflows. This supplementary section documents hands-on exposure to four additional industry standard platforms Zendesk, Freshservice, ServiceNow, and Jira Service Management. The goal is to demonstrate platform literacy across the tools most commonly encountered in enterprise and MSP environments.

-----

<h2>Platform Overview</h2>

|Platform               |Primary Use Case              |Tier Target|Notable Strength                      |
|-----------------------|------------------------------|-----------|--------------------------------------|
|Spiceworks             |SMB IT Help Desk              |Tier 1     |Free, lightweight, community-driven   |
|Zendesk                |Customer-facing & internal IT |Tier 1–2   |Omnichannel support, clean UX         |
|Freshservice           |IT Service Management (ITSM)  |Tier 1–2   |ITIL-aligned, asset management        |
|ServiceNow             |Enterprise ITSM               |Tier 2–3   |CMDB, workflow automation, change mgmt|
|Jira Service Management|Dev-adjacent IT & DevOps teams|Tier 1–3   |Deep Jira/Confluence integration      |

-----

<h1>Scenario 1: Password Reset and Request</h1>

*A user submits a ticket reporting they are locked out of their account and cannot log in.*

-----

<h1>Zendesk</h1>

Ticket Creation & SLA
Upon submission, Zendesk automatically routes the ticket based on configured triggers and assigns it a priority. For a password reset, this typically lands as Low or Normal priority with a first-response SLA of 1-4 hours depending on the plan tier.

Workflow
The support specialist can view the requester’s profile, ticket history, and any linked assets on a single pane. I used a macro (Zendesk’s pre-built response template) to send the user a standardized acknowledgment while simultaneously tagging the ticket `account-access` and `password-reset` for reporting purposes.

Resolution & Closure
After confirming the reset in Active Directory, the ticket is marked Solved. Zendesk holds it in a solved state for a configurable window before auto closing, allowing the user to reopen if the issue persists later on. a small but meaningful UX design that reduces duplicate tickets.



-----

<h1>Freshservice</h1>

Ticket Creation & SLA
Freshservice follows ITIL incident management out of the box. A password reset is logged as an Incident, distinct from a Service Request. Which is an important distinction because it implies something broke rather than something being provisioned. SLA policies are attached at the department or group level, and the dashboard surfaces a live SLA compliance percentage.

Workflow
Freshservice’s agent workspace includes a built in Activity Log on every ticket, which automatically timestamps every status change, note, and response. I documented the reset steps directly in the private note field and escalated to Tier 2 briefly to simulate a scenario where AD access required elevated permissions.

Resolution & Closure
Upon resolution, Freshservice prompts the agent to log a Resolution Note and categorize the root cause reinforcing documentation habits expected in ITIL aligned environments.



-----

<h1>ServiceNow</h1>

Ticket Creation & SLA
ServiceNow separates Incidents from Service Requests at the platform level. A forgotten password may be submitted through the Self-Service Portal as a Service Request catalog item, which triggers a pre-built fulfillment workflow rather than requiring manual triage. SLAs here are governed by OLAs (Operational Level Agreements) tied to assignment groups.

Workflow
A support specialist works within the Incident form, which surfaces fields like Category, Subcategory, Configuration Item (CI), and Assignment Group. All feeding into the CMDB (Configuration Management Database). I navigated the fulfillment workflow for a password reset, observing how each task state (Open to Work in Progress then to Resolved) is tracked and auditable.

Resolution & Closure
ServiceNow enforces a close code and resolution notes before a ticket can be resolved. This ensures every ticket contributes clean data for reporting and trend analysis.


-----

<h1>Jira Service Management</h1>

Ticket Creation & SLA
In Jira Service Management (JSM), password reset requests arrive through a customer portal and are classified by request type mapped to issue types in the backend. SLA goals are displayed as countdown timers directly on the issue, color coded by urgency (green → yellow → red).

Workflow
JSM’s agent view is familiar to anyone who has used Jira Software. The issue panel surfaces priority, linked issues, and components. I added an internal comment documenting the reset steps, then a reply to customer confirming resolution status. JSM cleanly separates these two communication lanes, which is useful when collaborating with other agents on the same ticket.

Resolution & Closure
Resolving the ticket updates its status on the customer portal in real time. JSM’s tight integration with Confluence means resolution steps can be flagged to auto populate a knowledge base article.



-----

<h1>Scenario 2 — New Employee Onboarding / Offboarding Request

*IT receives a request to provision (or deprovision) access, hardware, and software for an employee.*

-----

<h1>Zendesk</h1>

Onboarding
Zendesk handles onboarding requests as a standard ticket, but the real value is in ticket forms. Ticket forms are separate structured forms that can be configured specifically for new hire requests, collecting fields like start date, department, required software, and hardware. This feeds a checklist style workflow managed via side conversations (looping in HR or procurement without creating separate tickets).

Offboarding
For offboarding, a similar form captures the termination date and required access revocations. I observed how agents use tags (`offboarding`, `access-revoke`, `equipment-return`) to filter and report on these tickets in bulk relevant for compliance audits.



-----

<h1>Freshservice</h1>

Onboarding
Freshservice shines here through its Service Catalog. An “Employee Onboarding” catalog item can be prebuilt with child tasks automatically spawned across IT, HR, and Facilities, each with its own assignee and SLA. This is a textbook ITIL Service Request fulfillment flow. I submitted a test onboarding request and watched the parent ticket auto generate subtasks for AD account creation, email provisioning, and hardware assignment.

Offboarding
Freshservice’s Asset Management module becomes directly relevant during offboarding. Support specialist can locate the employee’s assigned assets (laptop, peripherals), initiate a return workflow, and update asset status to `In Transit` or `In Stock` within the same ticket interface.



-----

<h1>ServiceNow</h1>

Onboarding
ServiceNow’s Onboarding workflow is among the most sophisticated of any platform. Within the Service Catalog, a new hire request triggers a multi-stage workflow engine. Tasks are automatically routed to AD admins, licensing teams, and hardware provisioners simultaneously. I navigated the Flow Designer to observe how conditional logic handles exceptions (remote vs on site employees receiving different provisioning paths).

Offboarding
ServiceNow handles offboarding through a similar catalog workflow, often integrated with HR Service Delivery (HRSD) in enterprise configurations. Even in the trial environment, I could see how the offboarding flow triggers access revocation tasks, notifies the security team, and logs all actions to the CMDB. Effectively creating a full audit trail that satisfies compliance requirements.



-----

<h1>Jira Service Management</h1>

Onboarding
JSM handles onboarding through request types in the customer portal, but its differentiates itself using automation rules.  I configured a basic rule that automatically assigns onboarding tickets to the IT provisioning queue and sets a due date based on the employee start date. JSM’s deep Jira integration also allows onboarding tasks to be linked directly to sprint boards if the IT team uses agile project management.

Offboarding
Offboarding in JSM leverages the same automation framework. I observed how linked issues connect the offboarding ticket to any open access requests or pending hardware orders. The audit trail is visible in the issue’s activity feed which can be exportable for compliance review.



-----

<h1>Key Differentiators at a Glance</h1>

|Feature                |Zendesk              |Freshservice      |ServiceNow      |JSM                   |
|-----------------------|---------------------|------------------|----------------|----------------------|
|ITIL Alignment     |Partial              |Full              |Full            |Partial               |
|SLA Visibility     |Trigger-based        |Live dashboard    |OLA/SLA engine  |Countdown timer       |
|Asset Management   |Limited              |Built-in          |CMDB (advanced) |Via integrations      |
|Workflow Automation|Macros & triggers    |Workflow automator|Flow Designer   |Automation rules      |
|Knowledge Base     |Guide (built-in)     |Solution articles |Knowledge module|Confluence integration|
|Best Fit           |Customer support + IT|SMB/Mid ITSM      |Enterprise ITSM |Dev-adjacent IT teams |

-----

<h1>Takeaways</h1>

Working across these five platforms reinforced that the *fundamentals don’t change*. Every platform is ultimately moving a ticket from Open to In Progress then Resolved while practicing SLA. What differs is how workflows are automated, how assets are tracked, how documentation is enforced, and how deeply the tool integrates with the broader IT ecosystem.

The practical implication: switching between platforms is a matter of learning the interface, not relearning IT support or ticket system fundamentals. The mental model transfers.

-----

*Part of the [Ticketing System Lab](../README.md) — IT Support Home Lab Portfolio*
