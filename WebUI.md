WebUI

# Web UI

<this name="WebUI">
</this>

<interface name="Display" protocol="Web" return="HTML5 Page">
</interface>

<interface name="CreateCR" protocol="Web" return="HTML5 Page">~
</interface>

 <interface name="SubmitCR" protocol="Web" return="HTML5 Page">~
</interface>

<call name="Authenticate" protocol="SOAP/HTTP" service="LDAP.Authenticate">
<output>
  <value name="email" type="text" />
  <value name="password" type="text" />
</output>
  <events>
	<when receive="Display" />
  </events>
</call>

<call name="GetData" protocol="REST/HTTP" service="REST.View">
  <security authentication="static" />
  <events>
	<when receive="Authenticate" />
  </events>
</call>

<call name="CallCreateCR" protocol="REST/HTTP" service="REST.UpdateCR">
  <security authentication="static" />
  <events>
	<when receive="Authenticate" />
  </events>
</call>

<call name="ExecuteCR" protocol="REST/HTTP" service="REST.SubmitCR">
  <security authentication="static" />
  <events>
	<when receive="SubmitCR" />
  </events>
</call>



