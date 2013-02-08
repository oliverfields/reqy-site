Before reqy can do anything sensible it needs some requirements, documentation further elaborating requirements and details about the stakeholders involved in the project, but first the repository must be created.


Initialize repository
=====================

Initialy the requirements repository must be setup. It consists of regular files and directories and will include the various requirements, stakeholders, documents and project glossary.

| $ mkdir crm
| $ cd crm
| $ reqy init


Add requirements
================

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

The packages and requiremnts need fleshing out, the following content is added to the files in the *requirements* directory. Both requirements and requirement packages must have at least a *Description*, *Rationale* and *Scope* attribute set.

.. warning::
  All attributes are specified as *<name>: <value>*. Value must be all on one line or subsequent lines must be indented by two spaces.


Requirement package: customer-service-automation/attributes.pkg
---------------------------------------------------------------

.. include:: ../notes/tutorial-repo/requirements/customer-service-automation/attributes.pkg
    :literal:


Requirement: customer-service-automation/question-form.req
----------------------------------------------------------

.. include:: ../notes/tutorial-repo/requirements/customer-service-automation/question-form.req
    :literal:
    :end-line: 3


Requirement: customer-service-automation/ticket-system.req
----------------------------------------------------------

.. include:: ../notes/tutorial-repo/requirements/customer-service-automation/ticket-system.req
    :literal:


Requirement package: sales-force-automation/attributes.pkg
----------------------------------------------------------

.. include:: ../notes/tutorial-repo/requirements/sales-force-automation/attributes.pkg
    :literal:

Requirement: sales-force-automation/provide-customer-info.req
-------------------------------------------------------------

.. include:: ../notes/tutorial-repo/requirements/sales-force-automation/provide-customer-info.req
    :literal:


Add supporting documentation
============================

To more completely describe a solution, the requirements will most probably benefit from including documentation that further supports them. For instance database designs or wireframes/screen mock ups. Linking a requirement to documents allows reqy to keep track of them and allows users to find more information about a requirement.

.. attention::
    Supporting documentation is stored in the *documents* directory. Any number of directories may be created in *documents* to organize supporting documentation.

Lets assume there exists two sketches of the online ticket form. Updating the requirement *customer-service-automation/question-form.req* as follows would link both sketches (*documents/design/ticket_screen_sketch.png* and *documents/design/ticket_screen_confirmation_sketch.png*) to the requirement. 

.. include:: ../notes/tutorial-repo/requirements/customer-service-automation/question-form.req
    :literal:


Adding stakeholders
===================

Requirements are closely tied to the people that create, manage or ask for them. As requirements mature from inception to fully agreed upon, chances are that various stakeholders will contribute in different ways. Decisions made about a requirement (such as choosing to accepting it) require a link to the stakeholder that made the call. As such stakeholders must be added to the repository.

Create *stakeholders/jim.sth* with the following content to add Jim the Requirements Manager as a stakeholder.

.. include:: ../notes/tutorial-repo/stakeholders/jim.sth
    :literal:

And then add Jill the client.

.. include:: ../notes/tutorial-repo/stakeholders/jill.sth
    :literal:

We now have a working repository!
