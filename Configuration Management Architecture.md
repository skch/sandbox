# Configuration Management Architecture

 <this name="Nielsen" category="Architecture" title="Configuration Management Architecture">
 </this>

## Overview

The Configuration management Services (CMS) solution integrates several custom modules to enable Infrastructure, Configuration Management and Development teams to do their job. 
Environments Management is a critical support function within SDLC, which helps to manage and control the software application deployment in a planned and systematic fashion from development to Staging to production. 

The primary features are:

- Inventory of all resources (servers, ports, applications, environments, etc.)
- Secure access, change management, log and audit;
- Automatic configuration (generate config files and FTP to nodes)
- Automatic verification, diagnostic and notification

This document describes the CMS end-to-end solution design and integration strategy.

## Requirements

### Solution requirements

There are three business users for the CMS: 

- Configuration Management team (CM) – users will setup hardware and software, maintain information about servers and ports

- Application Development team (APP) – users will request environments, maintain information about applications configuration

- Production Support team (PST) – users will maintain and monitor the CMS system and make sure it is available to perform its function.

<interface name="Manage environments" protocol="Web" service="CMS.ViewEnvironment">
  <output name="Dashboard" type="HTML" />
</interface>

## Testing Approach

There are three phases of testing:

- Unit and component testing. Will be performed automatically using scripts developed together with the components;

- Functional test. Will be performed manually by a small team of CM and GBP Developers using functional use cases;

- Acceptance test. Will be performed by CM and GBP Development team on the pilot project.

Each component provide features for self-diagnostic after deployment.

# Solution Design

## Architecture
The Configuration Management Services solution consists of several independent layers:

1. CMS Management Console: A web server that provides users with access to all features;

2. CMS REST services: RESTfull services that implement CMS server API;

3. Process orchestration: Java application that orchestrate and coordinate asynchronous tasks;

4. Database: Storage layer that persist information;

System monitoring and log management are implemented using third-party tools.

### Context diagram

The following diagram shows major subsystems of the CMS application. Note that arrow direction shows interface initiation, not data flow:

 <diagram name="ctx" type="conext">
 </diagram>

There are following components

<component name="CMS">
</component>

<component name="Store">
</component>

<component name="LDAP">
</component>

<component name="Log">
</component>



### Data model

This table describes major data entities used by the CMS server:

### Logical Architecture

This section describes main solution components and interfaces between them. This diagram shows logical architecture:

<diagram name="cmp" type="component">
</diagram>

Text

### Use Cases

The CMS server implement the following major use cases:

- Create Change Request

- Add new or update existing record

- Delete record

- Commit Change Request

- Roll-back change request

- Test a node or an environment


Process diagram:

<diagram name="proc" type="process">
</diagram>

Text

The following diagram illustrates how some of these use cases are implemented by the system components:

#### Create Change Request

<diagram name="sqnc1" type="sequence" call="CMS.CreateCR">
</diagram>


Yes

