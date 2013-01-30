This tutorial will cover many common tasks that are performed during a project. The tutorial will be explained in context of a fictitious project for a new customer relationship management(CRM) system. After showing how to create a requirements repository the turorial will demonstrate some general uses.

.. contents::
  :depth: 2


Setup repository
################

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

The packages and requiremnts need fleshing out, the following content is added to the files in the *requirements* directory. Both requirements and requirement packages must have at least a *Description* and *Rationale* attribute set.

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
    :end-line: 2


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


Requirement life cycle
######################

Before diving into managing requirements some insight into Reqy's philosphy may help. Requirements will typically follow a lifecycle where they are created, fully formulated and finally implemented. Reqy allows the status of each requirement and which stakeholder approved the status to be documented. It is intended as a documentation of where each requirement stands and it's history. The main goal is to track what has been agreed upon and by who.

.. warning::
  Reqy is not intended as a task management tool, instead it's focus is on capturing requirements and allowing management of them from the command line in a static fashion.

Because Reqy is based on regular files and directories it is easy to version control, meaning changes can be tracked and the agreemed requirements can be tightly controlled.

.. figure:: /graphs/typical_requirement_lifecycle.png
  :alt: Typical requirement life cycle

  Typical requirement life cycle

Requirements may have the following statuses.

============== =======================================
Status         Description                            
============== =======================================
elaboration    Not fully specified/missing information
implementation Ready for implementation               
rejected       Will not be implemented                
approved       Requirement signed off by client       
postponed      May be implemented at later date       
============== =======================================
 

Requirement from inception to completion
========================================

Returning to the requirement customer-service-automation/question-form.req, by default it has status *elaboration* meaning it is not sufficently detailed and needs fleshing out before work can start.

.. attention::
  Detail can be added to a requirement directly by editing the *Description* attribute or by linking the requirement to one or more documents

Assuming the question-form requirement is sufficently detailed the status should be updated, do this by appending the line *Status: implemented* to customer-service-automation/question-form.req.

Further down the line the requirement has now been met and Jill the client is happy, in this case the status must also be changed and a reason must be given for the status using the attribute *Status reason* the attribute *Approved by* must also be set. Reqy makes a point that all statuses must be linked to a stakeholder and must have a comment stating the reason (justification) for the status, this is to maintain traceability. The attribute *Approved on* also allows recording the date that the requirement was approved.

.. include:: ../notes/tutorial-repo/requirements/customer-service-automation/question-form.req
    :literal:

To recap, the requirement status is now *approved*, the reason it is approved is that *Form created and tested* and it was approved by Jill on the 11th of May 2013.


Rejecting or postponing a requirement
=====================================

Requirements may also have status *rejected* or *postponed*. Rejected typically is used for requirements that are no longer in scope and postponed are for requirements that are not to be completed at this point in time. As for the status *approved* both *postponed* and *rejected* require *Status reason* in addition to setting *Postponed by* or *Rejected by*. Optionally *Postponed on* and *Rejected on* may be set.


Assessing change impact
#######################

Examine impact to a requirement, identify what docs may need updating?


Baselineing requirements using git
##################################

Show how to base line using git


Listing and filtering requirements
##################################

Requirement status:
- Generate requirement list for email
- Filter from command line
