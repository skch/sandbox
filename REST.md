REST

# CMS REST API

<this name="REST">
</this>

<interface name="View" protocol="REST/HTTP" return="XML">
</interface>

<interface name="UpdateCR" protocol="REST/HTTP" return="XML">
</interface>

<interface name="SubmitCR" protocol="REST/HTTP" return="XML">
</interface>

<interface name="GetLog" protocol="SSH" return="Text">
</interface>

Authenticate user:


<call name="Authenticate" protocol="SOAP/HTTP" service="LDAP.Authenticate">
<output>
  <value name="email" type="text" />
  <value name="password" type="text" />
</output>
  <events>
	<when receive="View" />
  </events>
</call>

<call name="GetList" protocol="REST/HTTP" service="Store.Read">
  <security authentication="static" />
<output>
  <value name="bucket" type="text" />
  <value name="keys" type="list" />
</output>
  <events>
	<when completed="Authenticate" />
  </events>
</call>

<call name="CallUpdate" protocol="REST/HTTP" service="Store.Update">
  <security authentication="static" />
<output>
  <value name="bucket" type="text" />
  <value name="values" type="list" />
</output>
  <events>
	<when receive="UpdateCR" />
<when receive="SubmitCR" />
  </events>
</call>

<call name="SendToPM" service="Processor.RunCR" protocol="REST/HTTP">
<events>
 <when completed="UpdateCR" />
  </events>
</call>




