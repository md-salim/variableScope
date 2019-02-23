# variableScope

variableScope mule configuration output:
URL: http://localhost:8081/flowa
Before HTTP Request in FlowA: 	FV1 SV1 null null
FlowB Request:					null null FV2 SV2
FlowB Response: 				null null FV2 SV2
After HTTP Request in FlowA:	FV1 SV1 null null
In FlowA Response: 				FV1 SV1 null null
Conclusion: Session variable cannot be accessible to the another flow if it traverse through HTTP requestor. In this case flow/session variable both have same scope.

variableScopevm mule configuration output:
URL: http://localhost:8081/flowc
Before VM in FlowC:  FV1 SV1 null null
After VM in FlowC: FV1 SV1 null null
In FlowC Response:     FV1 SV1 null null
FlowD Request:     null SV1 FV2 SV2
FlowD Response:     null SV1 FV2 SV2
Conclusion: Session variable can traverse through VM connector and accessible in another flow thru VM inbound endpoint. 

variablescopeinasync mule configuration output:
FlowE:     FV SV
FlowF:     null SV
