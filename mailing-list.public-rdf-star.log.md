---
id: bCbHNvGI5XGE4s9mD5AMJ
title: Log
desc: ''
updated: 1641366981834
created: 1641366235825
---

 2022-01-04
  - 

Hi Thomas

    A side note about what a statement states and what it doesn’t state (unrelated to what I said above, 
    but as the topic came up in this thread recently): the much discussed example
        <<:Burton :marriedTo :Taylor>> :start 1963; :end 1974 .
    can be read as 
        "Let’s assume a statement claiming a marriage relation between Burton and Taylor.
        That marriage relation starts in 1963 and ends in 1974." 
    That’s okay (ignoring for a moment the httpRange-14 issue, that start and end dates could also refer to the statement itself). 
    The second sentence adds detail about which the first sentence makes no claim. It is important that properties are defined in a
     way that they welcome such additional information, not prohibit it. The design principle that no statement is allowed to alter
      the truth of another one OTOH also requires that no statement is allowed to forbid the addition of further detail by other 
      statements. If we can’t rely on that we can forget about weaving a semantic web from disparate sources. 


I'd say most of us on this thread agree by now that that statement is improperly structured. Optional time and space positions, and other fixes I suggested in my two previous messages, seem to solve the problem entirely though. I guess you disagree?

Asserted case:
:Burton :marriedTo :Taylor 1964 1974
    {|
        :stated 2022
    |}

Expands to:

:Burton :marriedTo :Taylor 1964 1974
<< :Burton :marriedTo :Taylor 1964 1974 >> :stated 2022

Unasserted case:
<< :Burton :marriedTo :Taylor 1964 1974 >>
    {|
        :stated 2022
    |}

Expands to:

<< :Burton :marriedTo :Taylor 1964 1974 >> :stated 2022

Regards
Anthony