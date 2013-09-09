# Cloud Store

Amazon Web Services

<this name="Store" type="datastore">
</this>

<interface name="Read" protocol="REST/HTTP" return="Data">
<input>
  <value name="bucket" type="text" />
  <value name="keys" type="list" />
</input>
<output>
  <value name="status" type="text" />
</output>
</interface>

<interface name="Update" protocol="REST/HTTP" return="Status">
<input>
  <value name="bucket" type="text" />
  <value name="values" type="list" />
</input>
<output>
  <value name="status" type="text" />
</output>
</interface>



