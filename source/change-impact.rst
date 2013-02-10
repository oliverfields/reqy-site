In order to asses what impact a change of one requirement may have on others, it is important to know which other requirements are connected(trace) to it.

| $ reqy trace requirements/customer-service-automation/ticket-system.req  
|                                                                          
| Traces from "customer-service-automation/ticket-system.req" (1):        
| customer-service-automation                                           
|                                                                          
| Traces to "customer-service-automation/ticket-system.req" (2):          
| /home/reqy/repo/documents/design/ticket_screen_sketch.png             
| /home/reqy/repo/documents/design/ticket_screen_confirmation_sketch.png

The above example shows that the ticket-system requirement have 2 documents that trace to it. This means if the requirement is subjected to change, these 2 documents should probably be reviewd and perhaps updated in response to the change.

Documents may also be examined to determine which requirements trace to them.

| reqy trace documents/design/ticket_screen_sketch.png
|
| Traces from "/home/reqy/repo/documents/design/ticket_screen_sketch.png" (1):
| customer-service-automation/ticket-system.req
|
| No traces to "/home/reqy/repo/documents/design/ticket_screen_sketch.png"

