LDAP

# Nielsen LDAP

<this name="LDAP" title=“Home title”>
</this>

This is an existing web service:

<interface name="Authenticate" protocol="SOAP/HTTP" return="User information">
<input>
  <value name="email" type="text" />
  <value name="password" type="text" />
</input>
<output>
  <value name="user" type="text" />
  <value name="groups" type="list" />
</output>
</interface>