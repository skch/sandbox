Splunk

# Splunk Log Manager

<this name="Log">
</this>

<interface name="ViewList" protocol="REST/HTTP" return="Display CMS Console">
</interface>

<call name="GetList" protocol="SSH" service="REST.GetLog">
  <security authentication="static" />
  <events>
	<when receive="ViewList" />
  </events>
</call>


