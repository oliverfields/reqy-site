Whilst working with requirements it will frequently be usefull to gain a birdseyes view of what state the requirements are in. Reqy does not provide any built in search functionality, the reason for this is that there are many tools that are specialized for searching regular directories and files. Below are a few basic commands, but more info is only a search engine or man command away.

Finds all files containing 'bills' in the file name.

| $ find . -name '\*bills\*'

Find all items with status approved, use *grep -v* to invert the search.

| $ grep -R '^Status:\ approved$' *

List files containing the string 'Title: Nice'.

| $ grep -R 'Title: Nice' \*

Find all .req files and change status from elaboration to approved.

| $ find . -name '\*.req' -exec sed 's/^Status:\ elaboration$/Status:\ approved/' {} \;
