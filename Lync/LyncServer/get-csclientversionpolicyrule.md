---
title: Get-CsClientVersionPolicyRule
TOCTitle: Get-CsClientVersionPolicyRule
ms:assetid: f81f4f6c-5201-46c5-89f6-da859ce99b2e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413048(v=OCS.15)
ms:contentKeyID: 49314796
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClientVersionPolicyRule

 

_**上一次修改主题：** 2015-03-09_

Returns the client version policy rules configured for use in your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsClientVersionPolicyRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsClientVersionPolicyRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns information about all of the client version policy rules currently in use in the organization.

    Get-CsClientVersionPolicyRule

## EXAMPLE 2

In Example 2, information about a single client version policy rule is returned: the rule with the Identity Global/2336c611-a243-4c5d-994b-eea8a524d0e4.

    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"

## EXAMPLE 3

Example 3 returns all the client version policy rules that have been configured at the global scope. To do this, the command uses the Filter parameter and the filter value "Global/\*". That filter value returns only those rules that have an Identity that begins with the string value "Global/".

    Get-CsClientVersionPolicyRule -Filter "Global/*"

## EXAMPLE 4

The command shown in Example 4 returns all the client version policy rules that are currently disabled. To do this, the command first calls the **Get-CsClientVersionPolicy** cmdlet in order to return a collection of all the available client policy rules. This collection is then piped to the **Where-Object** cmdlet, which picks out the rules where the Enabled property is equal to False.

    Get-CsClientVersionPolicyRule | Where-Object {$_.Enabled -eq $False}

## EXAMPLE 5

Example 5 returns all the client version policy rules that block a client application from logging on. To do this, the command first calls the **Get-CsClientVersionPolicy** cmdlet without any parameters; that returns a collection of all the rules currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those rules where the Action property is equal to Block.

    Get-CsClientVersionPolicyRule | Where-Object {$_.Action -eq "Block"}

## Detailed Description

Client version policy rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server, his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information is then checked against a collection of client version rules to see if any rules apply to that particular application. For example, suppose a user attempts to log on by using Microsoft Office Communicator 2007 R2. Before the user can log on to Lync Server, the system will check to see if there is a client version rule that applies to Office Communicator 2007 R2. If a rule exists, Lync Server will then take the action specified by the rule. That action must be one of the following:

Allow. The user will be allowed to log on.

AllowAndUpgrade. The user will be allowed to log on, and his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

AllowWithUrl. The user will be allowed to log on, and a message will be displayed pointing the user to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Block. The user will not be allowed to log on.

BlockAndUpgrade. The user will not be allowed to log on, but his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. The user can then try to log on by using the new client application. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

BlockWithUrl. The user will not be allowed to log on, but a message will be displayed pointing him or her to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Client version rules are collected in client version policies. These policies can be configured at the global scope, the site scope, the service scope (Registrar service), or the per-user scope. The **Get-CsClientVersionPolicyRule** cmdlet provides a way for administrators to view detailed information about each of the policy rules configured for use in their organization.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsClientVersionPolicyRule** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClientVersionPolicyRule"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when specifying the client version policy rules to be returned. For example, to return all the rules configured for the Redmond site, use this syntax: -Filter &quot;site:Redmond/*&quot;.</p>
<p>You cannot use both the Filter and the Identity parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the client version policy rule to be retrieved. The Identity of a client version rule consists of the scope where the rule has been configured plus a globally unique identifier (GUID). That means that a rule will have an Identity similar to this: site:Redmond/1987d3c2-4544-489d-bbe3-59f79f530a83. Because GUIDs are difficult to remember and to work with, the Examples section in this Help topic lists alternate ways that you can identify the rules to be returned.</p>
<p>If this parameter is not specified all of the client version policy rules configured for use will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the client version policy rule data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsClientVersionPolicyRule** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsClientVersionPolicyRule** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.Rule object.

## 另请参阅

#### 其他资源

[New-CsClientVersionPolicyRule](new-csclientversionpolicyrule.md)  
[Remove-CsClientVersionPolicyRule](remove-csclientversionpolicyrule.md)  
[Set-CsClientVersionPolicyRule](set-csclientversionpolicyrule.md)

