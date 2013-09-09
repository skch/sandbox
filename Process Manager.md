# Process Manager

<this name="Processor">
</this>

<interface name="RunCR" protocol="REST/HTTP" return="XML">
</interface>

<call name="PushConfig" protocol="SFTP" service="Node.ReceiveConfig">
  <security authentication="static" />
  <events>
	<when receive="RunCR" />
  </events>
</call>