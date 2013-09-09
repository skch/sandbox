CMS

# Configuration Management System

<this name="CMS">
</this>

## Use Cases

### Browsing Dashboard

Display list of all available environments, or see details for one particular environment:

<interface name="ViewEnvironment" protocol="Web" return="Environment(s)" service="WebUI.Display">
</interface>

Display list of all available environments, or see details for one particular environment:

<interface name="ViewServers" protocol="Web" return="Environment(s)" service="WebUI.Display">
</interface>

Display list of all available environments, or see details for one particular environment:

<interface name="ViewApplications" protocol="Web" return="Environment(s)" service="WebUI.Display">
</interface>

Sequence diagram:

<diagram name="sqnc1" type="sequence" call="WebUI.Display">
</diagram>


### Create Change Request

Any changes to the system are done using change requests. Once CR is created user can add changes to the CR. Create, update or delete the following items:

- Servers
- Ports
- Environments

<interface name="CreateCR" protocol="Web" return="Dashboard" service="WebUI.CreateCR">
</interface>


### Submit Change Request

<interface name="SubmitCR" protocol="Web" return="Display dashboard" service="WebUI.SubmitCR">
</interface>

Sequence diagram:

<diagram name="sq_submit" type="sequence" call="WebUI.SubmitCR">
</diagram>

## CMS Components

<component name="WebUI">
</component>

<component name="REST">
</component>

<component name="Processor">
</component>

