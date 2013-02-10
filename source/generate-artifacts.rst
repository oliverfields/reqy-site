Reqy makes several views of the repository available, these are known as artifacts and are useful for understanding and communicating the requirements with other. The available artifacts can be listed by running the following to show a usage message.

| $ reqy artifact

Use argument *all* to generate all artifacts.

| $ reqy artifact all

Generated artifacts are placed in the *artifacts* directory, when regenerated they are overwritten, i.e. to make changes persistent update the acrual requirements files. The table below describes the artifacts currently available. The Artifact name is the command line argument, as in *reqy artifact [artifact name]*.

============= =================================== =================================================================================================
Artifact name File name                           Description                                                                                      
============= =================================== =================================================================================================
estimate      project-estimation.ods              LibreOffice spreadsheet listing all requirements and sums of estimated effort and estimated cost 
graph         overview_graph.dot                  Dot file for further generating visualization of traces(dependencies) between requirments        
list          requirement-list.odt                LibreOffice text document listing all requirements and their details                             
basiclist     requirement-basic-list.odt          Less verbose version of *list*                                                                   
planner       export.planner                      Gnome Planner (project management tool) containing all requirements                              
rtm           requitement-traceability-matrix.csv Spreadsheet listing requirements downwards, and columns showing the documents that trace to them 
============= =================================== =================================================================================================

To generate, say the requirement list artifact, run the following command, it will create *artifacts/requirement-list.odt*.

| $ reqy artifact list

Please note that some artifacts are intended as input for other programs and may need additional processing. For instance the planner file requires Gnome Planner whilst the overview graph must be passed to Dot for processing.

| $ dot -Tpng -o overview_graph.png overview_graph.dot
