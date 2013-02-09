Whilst working with requirements it will frequently be usefull to gain a birdseyes view of what state the requirements are in. To do this reqy provides an ability to filter requirements by status. However, as the repository consists of regular directories and files, common command line tools can be used to great effect.


Filtering requirements
======================

Requirements may be filtered by status, fire up a shell and go to the repo directory before this command to show all requirments that hav status approved.

| $ reqy filter status approved

The filter mode supports negations to print all requirements that do not match.

| $ reqy filter status not approved


Searching with other tools
==========================

Unix has a plethora of tools for sorting, searching and manipulating files, below are a few basic commands, but more info is only a search engine away.

Finds all files containing 'bills' in the file name.

| $ find . -name '\*bills\*'

List files containing the string 'Title: Nice'.

| $ grep -R 'Title: Nice' \*

Find all .req files and change status from elaboration to approved.

| $ find . -name '\*.req' -exec sed 's/^Status:\ elaboration$/Status:\ approved/' {} \;
