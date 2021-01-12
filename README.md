# midpoint
The files in the repo are configuration files used in my work with the midPoint IdM application from http://midpoint.evolveum.com/

Hopefully they help someone else out

ad-policy.xml
Enables provisoning accounts in Active Directory domains that require complex passwords. Import the object and note the OID. Then update your AD connector in the <credentials> section
              <credentials>
                <password xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="c:ResourcePasswordDefinitionType">
                    <outbound>
                        <expression>
                            <generate xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="c:GenerateExpressionEvaluatorType">
                                <valuePolicyRef oid="OID_Number_From_Object_Import"/>
                            </generate>
                        </expression>
                    </outbound>
                </password>
            </credentials>
  
accounttask.xml and grouptask.xml set up the sync processes for the Active Directory resource. Just change the OID to your resources OID
