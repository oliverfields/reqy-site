Before diving into managing requirements some insight into Reqy's philosphy may help. Requirements will typically follow a lifecycle where they are created, fully formulated and finally implemented. Reqy allows the status of each requirement and which stakeholder approved the status to be documented. It is intended as a documentation of where each requirement stands and it's history. The main goal is to track what has been agreed upon and by who.

.. warning::
  Reqy is not intended as a task management tool, instead it's focus is on capturing requirements and allowing management of them from the command line in a static fashion.

Because Reqy is based on regular files and directories it is easy to version control, meaning changes can be tracked and the agreed upon requirements can be tightly controlled.

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

These are the basics of what happens to a requirement.
