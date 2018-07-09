# Haha Custom Actuator Profile

## 9 July 2018

This is work in progress by starting with slpf profile and
editing. A lot of editing still to do.

This Custom Actuator Profile (cap) is provided for information purposes.

**Editors**

* Duncan Sparrell (duncan@sfractal.com), sFractal Consulting

## Abstract
Open Command and Control (OpenC2) is a concise and extensible language
to enable the command and control of cyber defense components,
subsystems and/or systems in a manner
that is agnostic of the underlying products,
technologies, transport mechanisms or other aspects of the implementation.
Actuator profiles specify the subset of the optional language components that the actuator will respond to.
This Custom Actuator Profile (CAP) is for a 'hello world'
actuator haha (Https Api Hello-world Actuator). Haha exists just for the purpose of demonstrating
the language/profile/transport with the simplest possible
actuator. Haha also serves as a template for 'real' actuators.

Haha was implemented on beam,
a highly reliable erlang/elixir virtual machine.
Several implementations exist (or will) - see (put link here).

## Status
This document does not go thru the TC approval process.

TC members should send comments on this specification to the TC's email list
or open a pull request.
Others should send comments to the TC's public comment list,
after subscribing to it by following the instructions
at the "Send A Comment" button on the
TC's web page at
[https://www.oasis-open.org/committees/openc2/](https://www.oasis-open.org/committees/openc2/).

This Draft is provided under the Non-Assertion Mode of the OASIS IPR Policy,
the mode chosen when the Technical Committee was established.
For information on whether any patents have been disclosed
that may be essential to implementing this specification,
and any offers of patent licensing terms,
please refer to the Intellectual Property Rights
section of the TC's web page
([https://www.oasis-open.org/committees/openc2/ipr.php](https://www.oasis-open.org/committees/openc2/ipr.php)).

### Citation format:
When referencing this specification the following citation format should be used:

**[TBSL]**

_Haha Custom Actuator Profile_

Edited by Duncan Sparrell.

8 July 2018.


Latest version: N/A.

-------

## Notices
Copyright © OASIS Open 2018. All Rights Reserved.

All capitalized terms in the following text have the meanings
assigned to them in the OASIS Intellectual Property Rights Policy
(the "OASIS IPR Policy").
The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr)
may be found at the OASIS website.

This document and translations of it may be copied and furnished to others,
and derivative works that comment on or otherwise
explain it or assist in its
implementation may be prepared, copied, published, and distributed,
in whole or in part, without restriction of any kind,
provided that the above copyright notice
and this section are included on all such copies and derivative works.
However, this document itself may not be modified in any way,
including by removing the copyright notice or references to OASIS,
except as needed for the purpose of
developing any document or deliverable produced by an
OASIS Technical Committee (in which case the rules
applicable to copyrights,
as set forth in the OASIS IPR Policy, must be followed)
or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS"
basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE
USE OF THE INFORMATION HEREIN WILL NOT
INFRINGE ANY OWNERSHIP RIGHTS OR ANY
IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

OASIS requests that any OASIS Party or any other party that believes
it has patent claims that would necessarily be infringed by implementations
of this OASIS Committee Specification or OASIS Standard,
to notify OASIS TC Administrator and provide an indication of its
willingness to grant patent licenses to such patent claims
in a manner consistent with the IPR Mode of the
OASIS Technical Committee that produced this specification.

OASIS invites any party to contact the OASIS TC Administrator
if it is aware of a claim of ownership of any patent claims
that would necessarily be infringed by implementations
of this specification by a patent holder that is not willing
to provide a license to such patent claims in a manner consistent
with the IPR Mode of the OASIS Technical Committee
that produced this specification. OASIS
may include such claims on its website,
but disclaims any obligation to do so.

OASIS takes no position regarding the validity or scope of any
intellectual property or other rights that might be
claimed to pertain to the implementation or use of the technology
described in this document or the extent
to which any license under such rights might or might not be available;
neither does it represent that it has made any effort
to identify any such rights. Information on OASIS' procedures
with respect to rights in any document or deliverable produced
by an OASIS Technical Committee can be found on the OASIS website.
Copies of claims of rights made available for publication
and any assurances of licenses to be made available,
or the result of an attempt made to obtain a general license
or permission for the use of such proprietary rights
by implementers or users of this OASIS Committee Specification
or OASIS Standard, can be obtained from the OASIS TC Administrator.
OASIS makes no representation that any information or list of
intellectual property rights will at any time be complete,
or that any claims in such list are, in fact, Essential Claims.

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/),
the owner and developer of this specification,
and should be used only to refer to the organization and its official outputs.
OASIS welcomes reference to, and implementation and use of,
specifications, while reserving the right to enforce its
marks against misleading uses.
Please see [https://www.oasis-open.org/policies-guidelines/trademark](https://www.oasis-open.org/policies-guidelines/trademark)
for above guidance.


-------

## Table of Contents
[[TOC]]

-------

# 1 Introduction
Haha stands for Https Api Hello-world Actuator.
Haha exists just for the purpose of demonstrating
the language/profile/transport with the simplest possible
actuator. Haha also serves as a template for 'real' actuators
A ‘Stateless-Packet-Filter’ (SLPF) is a policy enforcement mechanism
that restricts or permits traffic based on
on packet headers such as source address,
destination address, and/or port numbers.
A SLPF does not retain state information between packets.
A SLPF does not consider traffic patterns, connection state, data flows,
applications, or payload information.
The OASIS OpenC2 TC has drafted an OpenC2 Actuator Profile for SLPF
which this document extends for the particular instantiation of a SLPF
using bawnl (link here) to interface to AWS NACL's which implement the
stateless packet filter function.

This custom actuator profile specifies the set of actions,
targets, specifiers, and arguments
that integrate bawnl slpf  functionality
with the Open Command and Control (OpenC2) command set.
Through this command set,
cyber security orchestrators may gain visibility and
provide control into the slpf functionality.

## 1.1 Purpose and Scope

The purpose of this document is to:

* Define a profile for the custom extensions to the haha profile for operation with haha instantiation(s).
* Specify all OpenC2 ACTIONS implemented.
* Specify all OpenC2 TARGETS implemented.
* Specify all OpenC2 TARGET_SPECIFIERS implemented.
* Specify all OpenC2 ARGS implemented.
* Specify the valid command semantics e.g. what combinations of ACTONS/TARGET/TARGET_SPECIFIERS/ARGS are valid.
* Specify the abstract schema for the command consumer

This haha profile:

* Does not define or implement ACTIONS beyond those defined in Version 1.0 of the Language Specification.
* Is conformant with version 1.0 of the OpenC2 Language Specification as it existed in CSD04 (ref).

Cyber defense systems that are utilizing OpenC2 MAY require the following components to implement the SLPF  profile:

* OpenC2 Producers: Devices that send commands, receive responses, and manage the execution of commands involving one or more haha's or other actuators with haha capability. The OpenC2 producer needs _a priori_ knowledge of which commands the actuator can process and execute, therefore must understand the profiles for any device that it intends to command.
* Devices that receive OpenC2 commands and implement the haha profile. Generally these are actuators but could be orchestrators.
* An Openc2 Consumer may provide multiple cyber defense mechanisms including haha functionality as a subset of its capabilities, thus must implement the SLPF  profile.

## 1.2 Terminology
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this specification are to be interpreted as described in IETF RFC 2119 [RFC2119].

## 1.3 Document Conventions
The following typographical conventions are used in this document.

_italics_

Indicates new terms, URLs, email addresses, filenames, and file extensions.

ALL CAPS

Used for components of the abstract syntax: ACTION, TARGET, ACTUATOR, OPTIONS.

'single quotes'

Used for single actions or commands (i.e. action target pairs)

## 1.4 Document Overview
TBD

## 1.5 Normative References
TBD

## 1.6 Non normative References
TBD

## 1.7 Acknowledgements
TBD

# 2 OpenC2 Language Binding
This section defines the set of ACTIONS, TARGETS, SPECIFIERS and ARGUMENTS that are meaningful
in the context of haha's. This section also describes the format of the RESPONSE frame's status
and results field. This section organized into three major subsections; Components, Response and Commands.

An OpenC2 command consists of an ACTION/TARGET pair and associated specifiers and arguments.
This section will enumerate the allowed commands,
identify which are required and present the associated responses.

## 2.1 OpenC2 Components
The components of an OpenC2 command include ID, ACTIONS, TARGETS, ACTUATOR and associated
ARGUMENTS and SPECIFIERS which were defined independently.  
Appropriate aggregation of the components will define a command-body
that is meaningful in the context of a haha.

The components of an OpenC2 command include:

* ID: The ID as specified in the OpenC2 Language Specifiction
* ACTIONS:   The subset of the ACTIONS defined in the OpenC2 Language specification.
    * This profiles does not define ACTIONS that are external to Version 1.0 of the OpenC2 Language Specification.
* TARGETS:   The subset of the TARGETs and target-specifiers defined in the Language specification that are meaningful in the context of haha, and the TARGET and target-specifiers extensions that are defined in this specification.
* ARGUMENTS: For haha as defined in this CAP, the ARGUMENTS field is unused.
* ACTUATOR:  For haha as defined in this CAP, the ACTUATOR field is unused (direct connection only so the consumer and producer are mutually identified and authenticated via the transport).

### 2.1.1 ID
The command ID is REQUIRED.

### 2.1.2 Actions
Table 1 presents the OpenC2 actions that are meaningful
in the context of a haha and identifies
which actions are required for at least one target type.  
The particular action/ target pairs
that are required are presented in section XXX.

**Table 1. HAHA Actions**

| Action | Description | Req/ Opt |
|:---|:---|:---|
| query | The query action initiates a single request for information. Used to communicate the supported options and determine the state or settings of the .  | Required  |

### 2.1.3 Targets
Table 2 lists the TARGETs that are applicable to haha's
and identifies the which target types are required for at least one action/target pair.

**Table 2. Target Data Model Applicable to haha's**

| Target | Description/Notes | Req/Opt |
|:---|:---|:---|
| openc2 | Used to determine the profile(s), schema, and imported targets supported by the actuator  | Required |
| x_hello | "Hello" of "Hello World".  This is an extension target type defined in this specification.  | Required |

### 2.1.4 Command Arguments
Arguments provide additional precision to a command by including information
such as how, when or where a command is to be executed.  
This trivially simple actuator uses no command arguments.

## 2.2 Actuator data model
This section defines the data model for the profile.
The ACTUATOR field within an OpenC2 message command is identified
with the actuator profile, and this section defines the actuator-specifiers
and actuator-arguments needed for additional precision.
For this trivially simple actuator, the ACTUATOR field is unused.
Identification and Authentication will be achieved thru the transport.

Note that although the ACTUATOR field is not used in the command,
the actuator itself exists and has this profile - it's just not included
in the command since it can be inferred.

## 2.5 OpenC2 Responses
Response messages originate from the actuator as a response to a command.

The status codes presented in Table 6 apply to all actions and identifies which responses are required to implement for at least one command.

The formats and what is expected in the response for specific commands will be captured in section 2.3 and examples will be provided in section 5, Appendix A. Responses associated with required actions MUST be implemented. Implementations that include optional actions MUST implement the Responses associated with the implemented action.

**Table 6. Response Codes**

| Status Code | Status Text | Req/Opt |
|:---|:---|:---|
| 200 | OK | Required |
| 400 | Unable to process command, parsing error | Required |
| 500 | Server Error | Optional |

## 2.6 OpenC2 Commands
An OpenC2 command consists of an ACTION/TARGET pair and associated specifiers and arguments.  This section will enumerate the allowed commands, identify which are required and present the associated responses.

### 2.6.5 ‘Query’
The valid target types, associated specifiers, and options are summarized in sections 2.2.3.1 through 2.2.3.2.  Sample commands are presented in Section 5 appendix A.

### 2.6.6 ‘Query openc2’
The ‘query openc2’ command is used to determine the capabilities of the actuator.  SLPF s MUST implement the ‘query openc2’ command. The specifiers for the openc2 target type are summarized in table 10.

**Table 10. Specifiers for the openc2 target type**

| Specifier | Implement | Type | Values/Description |
|:---|:---|:---|:---|
| version | Required | number | 1.0/  Version of the Language specification supported by this profile |
| profiles | Required | array | A two by n array where:<br>[0,i] = name of the profile supported<br>[1, i]= full path where the schema resides<br>‘Stateless-packet-filtering’ MUST be included in the list.  |
| profile-options | Required | array | A three by n array where:<br>[0, i] = "stateless-packet-filtering"<br>[1,i] = action target pair supported. If empty, the option identified applies to all action target pairs<br>[2,i]= option supported for the identified action target pair |
| serialization | Required | list | MUST include ‘json’.  MAY include other serializations that are validated against the abstract schema presented in appendix B |
| product | Optional | string | The particular vendor product or image such as iptables, amazon, azure etc |

Products that send the ‘query openc2’ command:

* MUST populate the command options field with ‘response-type="complete” ‘.
* MUST populate the command-id.
* MAY populate the respond-to option.
* MUST NOT include other command arguments.
* MAY include one or more of the openc2 specifiers identified in table 2.2.1.1.

Products that receive the ‘query openc2’ command:

* That cannot parse or process the query openc2 command MUST respond with response code 400.
* Upon successful parsing and processing of the query openc2 command, products MUST respond with response code 200. The results field MUST be populated with the openc2 target type and associated specifiers identified in the command.
* If no specifiers were identified in the openc2 command, then the results field MUST contain all of the specifiers identified in Table 10.  Refer to section 4 for sample commands.

### 2.6.7 ‘Query x_hello’
The ‘query x_hello’ command is the "Hello World" raison d'etre of the actuator.
Implementation of the ‘query x_hello’ command is REQUIRED.
The x_hello target is defined in this specification. Response to the x_hello query is "World".

#### 2.6.7.1 Type Name: x_hello
Base Type: String


* MUST populate the command options field with ‘response-type="complete”.
* MUST populate the command-id.
* MAY populate the respond-to argument.
* MUST NOT include other command arguments.
* MAY include one or more of the ap-slpf-query specifiers identified in table 2.2.1.2.

Products that receive  the ‘query ap-slpf’ command:

* MUST respond with response code 400 if the command cannot be parsed or processed.
* MUST respond with error code 501 and MAY respond with error description ‘data model not supported’ if the product does not support the ap-slpf target type
* Upon successful parsing and processing of the ‘query ap-slpf’ command, products MUST respond with response code 200 and populate the results field with the ap-slpf-query target type and associated specifiers identified in the command.
* If one or more ip-connection objects were explicitly listed in the allow-rules specifier, then the actuator returns the ip-connection if it is explicitly allowed.  An empty string implies that the ip-connection is not allowed.
* If one or more ip-connection objects were explicitly listed in the deny-rules specifier, then the actuator returns the ip-connection if it is explicitly denied.  An empty string implies that the ip-connection is not denied.
* If no ip-connection objects were explicitly listed in the allow-rules specifier, then the actuator MUST return the complete list of ip-connection objects that are explicitly allowed.
* If no ip-connection objects were explicitly listed in the deny-rules specifier, then the actuator MUST return the complete list of ip-connection objects that are explicitly denied.
* If no specifiers were identified in the query ap-slpf-query command, then the results field MUST return the entire allow and deny list.

Refer to section 4 for sample commands.

### 2.6.9 ‘delete ap-slpf’

# 3 Conformance statements
> **Editor's Note** - This section is a placeholder.  The conformance clauses stated within the body of the profile will be repeated here once general consensus is reached.<Note: need to define "support" - behavior that must occur as a result of executing commands>



Conformant implementations of OpenC2  Functions:

* MUST support OpenC2 commands, responses, and alerts as defined in Section 4.
* MUST implement JSON serialization of the commands, responses and alerts that are consistent with the syntax defined in the OpenC2 Language Specification.
* MAY implement any serialization that provides a one to one mapping of the data elements as defined in the abstract schema presented in the Language Specification to a format that is consistent with the syntax defined in Appendix B OpenC2 SCHEMA –  FUNCTIONS.
* MUST implement the actuator data model as presented in the abstract schema presented in Appendix B.

# 4 References
> **Editor's Note** - This section is a placeholder.  The normative and non-normative references will be populated once general consensus is reached.


# Appendix A. Sample commands
> **Editor's Note** - This section is a placeholder.  he syntax of the sample commands all must be reworked in accordance with the changes that occured in the language specification

This section will summarize and provide examples of OpenC2 commands as they pertain to s. The sample commands will be encoded in verbose JSON, however other encodings are possible provided the command is validated against the schema presented in Appendix A. Examples of corresponding responses and/or alerts will be provided where appropriate.

The samples provided in this section are for illustrative purposes only and are not to be interpreted as operational examples for actual systems. Within the scope of this document, a # character indicates a comment, however it should be noted that OpenC2 itself does not support comments within a command.



**7.4 Query**

The query action is used to gather some set of information from the actuator.  
There are two valid target types for the query command;  
‘openc2’ and ‘hello’.

Implementation of query openc2 is required.
The query openc2 command is intended to enable the openc2 producer
to determine the capabilities of the actuator.
The query openc2 command can also be used to check the status of the actuator.

```
# This thread illustrates the use of query openc2 to verify that the actuator
# is functioning and/or determine the version of the language specification.
# Note that the specifier is identified in the command but the value is not
# populated.
{
    "Id"=12345
    "action": "query"
    "target": {
    	"openc2" {
            	Version:
        }
    }
"Options"{
Response_type=complete}
}

#  The corresponding response would be:
#  Case one, things are OK

    "Id":12345
    "Status":200
    Results{
            	Type: openc2{
            	"Version": 1.0
}
}
#  Case two, error state
    "Id":12345
    "Status":400
    Results{}



# This thread illustrates the use of the query openc2 command to determine the
# the profiles supported and version of openc2.

{
    "Id"=12345
    "action": "query"
    "target": {
    	"openc2" {
            	Version:
            	Profiles:
    	}
    }
"options"{
Response_type=complete}
}

# The corresponding response would be:
# Case one, things are OK
    "Id":12345
    "Status":200
    Results{
            	Type: openc2{
            	"Version": 1.0
            	"profiles": haha,[ http://some.url.org](http://some.url.org)
}
}
#  Case two, error
    "Id":12345
    "Status":400
    Results{}


# Case two:  We know the version and profile, but want to know the options
#  profile-options is present but not populated
{
    "Id"=12345
    "action": "query"
    "target": {
    	"openc2" {
            	Profile-options
    	}
    }
"options"{
Response_type=complete}
}

The corresponding response would be:
            	# response one, things are OK
    "Id":12345
    "Status":200
    Results{
            	Type: openc2{
Profile-options:
            	stateless-packet-filtering, deny domain-name, complete
            	stateless-packet-filtering, deny domain-name, respond-to
            	stateless-packet-filtering, deny hostname, complete
            	stateless-packet-filtering, deny hostname, respond-to
}
}

#  Response two, error
    "Id":12345
    "Status":400
    Results{}

# Case three:  In this case, we don’t know anything and want a complete report from the actuator.
#  None of the specifiers for the openc2 target type are present, so the actuator responds with all of the specifiers populated
{
    "Id"=12345
    "action": "query"
    "target": {
    	"openc2" {
    	}
    }
"options"{
Response_type=2}
}

#The corresponding response would be:
# response one, things are OK

    "Id":12345
    "Status":200
    Results{
        Type: openc2{
            Version: 1.0
              "Profiles":
stateless-packet-filtering,[ http://some.url.org](http://some.url.org)
our-next-oasis-profile,[ http://someother.url.org](http://someother.url.org)
[   ](http://someother.url.org)Profile-options:
            		stateless-packet-filtering, deny domain-name, complete
            		stateless-packet-filtering, deny domain-name, respond-to
            		stateless-packet-filtering, deny hostname, complete
            		stateless-packet-filtering, deny hostname, respond-to
            		our-next-oasis-profile, scan directory, act-specific-option
            		our-next-oasis-profile, scan file, actuator-specific-option
# note in the next entry, we had an optional action target pair, but no options associated with it
our-next-oasis-profile, contain username,
# note in the next entry, we have a command option for all profiles for all actions
,,respond-to
Serialization:
Json
Cbor
XML

}
}
            	#  Response two, error
    "Id":12345
    "Status":400
    Results{}

Implementation of query ap-slpf-query command is optional.  The query ap-slpf-query is intended to enable the openc2 producer to determine the current state of the actuator.

# Verify that the s are blocking all outbound ftp traffic and TELNET traffic
{
    "Id"=12345
    "action": "query"
    "target": {
    	"ap-slpf-query" {
            	Deny-rules:
			{specifiers
{src-port:21}
}
			{specifiers
				{dst-port:23}

}
        }
    }
"Options"{
Response_type=complete}
}

#  The corresponding response would be:
#  Case one, things are OK and both ip-connections are denied

    "Id":12345
    "Status":200
    Results{
            	Type: ap-slpf-query{
            	 	{src-port:21}
			{dst-port:23}
}
}
#  Case two, things are OK.  Telnet is being denied but outbound ftp is notboth ip-connections are denied

    "Id":12345
    "Status":200
    Results{
            	Type: ap-slpf-query{
            	 	{dst-port:23}
}
}
#  Case three, not supported
    "Id":12345
    "Status":501
    Results{}
```

# Appendix B. OpenC2 SCHEMA –  FUNCTIONS
> **Editor's Note** - TBSL
