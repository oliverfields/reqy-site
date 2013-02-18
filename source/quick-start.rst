Requirements management using *reqy* is briefly explained adding and updating requirements. This quick start provides a high level introduction to just that.

.. attention::
  The quick start tries to demonstrate basic use of *reqy*. Clone from github with **$ git clone git://github.com/oliverfields/reqy.git**, then please ensure *reqy* is installed as per instructions in the INSTALL_ file before proceeding.

  .. _INSTALL: https://github.com/oliverfields/reqy/blob/master/INSTALL


Create a new requirements repository
------------------------------------

A *reqy* repository is just a directory containing stuff that *reqy* needs, run the following commands in a terminal to create a new repository.

| $ mkdir my_reqs
| $ cd my_reqs
| $ reqy init


Add requirements to repository
------------------------------

Requirements are text files containing attributes (key value pairs), they can be organized by requirement packages. Requirements packages can be nested. All requirements and requirement packages must be created in the *requirements* directory.

| $ cd my_reqs/requirements
| $ reqy new package 'my server'
| $ reqy new req 'my server/debian os'

The above created the following.

* A package consisting of a directory called **my server** and the package attributes file **my server/attributes.pkg**. Each package contains an *attributes.pkg* file that contains the package attributes

* A requirement consisting of the file **my server/debian os** wich will contain the requirement attributes

Both package and requirements must have **Description**, **Rationale** and **Scope** attributes set. Open the **attributes.pkg** file and add the following.

| Description: Web server for the new application
| Rationale: Required for new application
| Scope: Only serve HTTP, no HTTPS required

Add something similarly inane to **my server/debian os**. Once done the repository will be in a working state.


Set requirement status
----------------------

As the project progresses requirements change status, to record this the *Status* attribute must be set, this also applies to requirements packages.

* approved
* elaboration
* implementation
* rejected
* postponed

In order to track who and when deciscions where made some of the statuses have additional attributes that must be set. E.g. if status attribute is set to approved, *reqy* insists that the *approved by* attribute also is set in order to track who approved the requirement.

=============== ==================================
Status          Description
=============== ==================================
approved        Successfully completed

                * *Approved by* must also be set
                * *Approved on* can aslo be set
elaboration     Needs more investigation before
                ready for implementation
implementation  Adequately defined and can be/is
                beign built
rejected        Not part of project. Usefull to
                track also those requirements that
                didn't make it into the project

                * *Rejected by* must also be set
                * *Rejected on* can also be set
postponed       Will be completed at a later date

                * *Postponed by* must also be set
                * *Postponed on* can also be set
=============== ==================================


Link requirement to document
----------------------------

Tracability is crucial to requirements management. *reqy* supports traces (links) from requirements to supporting documentation in the repository.

The **Documents** attribute specifies the documents that are associated with the requirement. *reqy* will check that the documents actually exist. The following setting will add a trace from requirement *my_reqs/requirements/my_server* to *my_reqs/documents/module_design.txt*.

| $ touch my_reqs/documents/module_design.txt
| $ echo 'Documents: module_design.txt' >> my_reqs/requirements/my_server/attributes.pkg

Multiple documents can be specified by comma seperating them.

| Documents: x.pdf, y.pdf


Generate artifacts
------------------

For any project that is not trivial the requirements repository will soon become unweildy and hard to understand, this is part of what makes requirements management hard to do without a tool. To aid understanding *reqy* allows artifacts to be generated from the repository. Each artifact can be thought of as a different perspective or view of the requirements.

Artifacts can be generated all at once or one at a time, all artifacts are saved to the *artifacts* directory.

| $ reqy artifact all
| $ ls artifacts


Next steps
----------

For more information please see the tutorial_ and `user manual`_.

.. _tutorial: /tutorial.html
.. _`user manual`: /user-manual.html
