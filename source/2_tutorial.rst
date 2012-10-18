This tutorial will cover many common tasks that are performed during a project. The tutorial will be explained in context of a fictitious project for a new customer relationship management(CRM) system.


Initialize repository
---------------------

Initialy the requirements repository must be setup. It consists of regular files and directories and will include the various requirements, stakeholders, documents and project glossary.

| $ mkdir crm
| $ cd crm
| $ reqy init


Add requirements
................

The CRM project is to provide customer service and sales force automation capabilities with the following requirements.

* Customer service automation
 
  * Online question form
  * Ticket system

* Sales force automation

  * Provide sales force with current customer information

The two main capabilities will be represented as requirements packages.

| $ reqy new package requirements/customer-service-automation
| $ reqy new package requirements/sales-force-automation

Further the requirements must be added to the respective packages.

| $ reqy new req requirements/customer-service-automation/question-form
| $ reqy new req requirements/customer-service-automation/ticket-system
| $ reqy new req requirements/sales-force-automation/provide-customer-info

The packages and requiremnts need fleshing out, the following content is added to the files in the *requirements* directory. Both requirements and requirement packages must have at least a *Description* and *Rationale* attributes set.

.. warning::
  All attributes are specified as *<name>:* and *<value>*. Value must be all on one line or subsequent lines must be indented by two spaces. 

Requirement package: customer-service-automation/attributes.pkg
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

| Description: Provide tools and techniques that allow customer interaction.
| Rationale: Customer interaction should where appropriate be funneled thorough online services to ensure capture of information to allow best possible service leveles and quickest possible response times. Aim to provide sufficent information to service personel to reduce ticket response times by 10%.


Requirement: customer-service-automation/question-form.req
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

| Description: Online form where customers can submit tickets.
| Rationale: Ensure customers submit appropriate information by requireing all necassary fields are completed befor accepting submission.


Requirement: customer-service-automation/ticket-system.req
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

| Description: Online system for handling customer tickets.
| Rationale: All customer service personel need common system to handle tickets.

Requirement package: sales-force-automation/attributes.pkg
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

| Description: Online sales data repository.
| Rationale: Allow sales team to manage contacts and opportunities.


Requirement: sales-force-automation/provide-customer-info.req
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

| Description: Customer contact details and overview of purchases and purchase history.
| Rationale: Sales team need access to up to date information about their existing and potential clients.


Add supporting documents
------------------------

To describe a system the requirements must also include supporting documentation 










Setup initial requitements, add documents, stakeholders and glossary

Follow a requirement from initial to approved

Follow a requirement from inital to rejected

Examine impact to a requirement, identify what docs may need updating?

Show how to base line using git

Requirement status:
- Generate requirement list for email
- Filter from command line
