---
title: Set-CsClientVersionPolicyRule
TOCTitle: Set-CsClientVersionPolicyRule
ms:assetid: 2e061fa8-bb1a-4382-bb0d-298f81aefb3d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425790(v=OCS.15)
ms:contentKeyID: 49312365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientVersionPolicyRule

 

_**上一次修改主题：** 2015-03-09_

Modifies one or more client version policy rules currently configured for use in your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsClientVersionPolicyRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClientVersionPolicyRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Action <Allow | AllowAndUpgrade | AllowWithUrl | Block | BlockAndUpgrade | BlockWithUrl>] [-ActionUrl <String>] [-BuildNumber <UInt16>] [-CompareOp <EQL | NEQ | GTR | GEQ | LSS | LEQ>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-MajorVersion <UInt16>] [-MinorVersion <UInt16>] [-Priority <Int32>] [-QfeNumber <UInt16>] [-UserAgent <String>] [-UserAgentFullName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 disables the client version policy rule that has the Identity site:Redmond/74ba9211-8610-42f9-91ba-846cdee98820. To disable the rule, the command includes the Enabled parameter and the parameter value $False.

    Set-CsClientVersionPolicyRule -Identity site:Redmond/74ba9211-8610-42f9-91ba-846cdee98820 -Enabled $False

## EXAMPLE 2

Example 2 adds a generic description to all the client version policy rules assigned to the Redmond site. To do this, the command first calls the **Get-CsClientVersionPolicyRule** cmdlet along with the Filter parameter; the filter value "site:Redmond\*" limits the returned data to policy rules assigned to the Redmond site. This collection is then piped to the **Set-CsClientVersionPolicyRule** cmdlet, which assigns the Description "Client policy rules for Redmond" to each item in that collection.

    Get-CsClientVersionPolicyRule -Filter "site:Redmond*" | Set-CsClientVersionPolicyRule -Description "Client policy rules for Redmond"

## EXAMPLE 3

Example 3 blocks the use of Unified Communications Client Platform (UCCP) clients for any client version policy rule that references UCCP as the user agent. To carry out this task, the command first calls the **Get-CsClientVersionPolicyRule** cmdlet to retrieve a collection of all the client policy rules currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out only those rules where the UserAgent property is equal to (-eq) UCCP. This filtered collection is then piped to the **Set-CsClientVersionPolicyRule** cmdlet, which takes each item in the collection and sets the Action property to Block.

    Get-CsClientVersionPolicyRule | Where-Object {$_.UserAgent -eq "UCCP"} | Set-CsClientVersionPolicyRule -Action "Block"

## Detailed Description

Client version rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server, his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information is then checked against a collection of client version rules to see if any rules apply to that particular application. For example, suppose a user attempts to log on by using Microsoft Office Communicator 2007 R2. Before the user can log on to Lync Server, the system will check to see if there is a client version rule that applies to Office Communicator 2007 R2. If a rule exists, Lync Server will then take the action specified by the rule. That action must be one of the following:

Allow. The user will be allowed to log on.

AllowAndUpgrade. The user will be allowed to log on, and his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

AllowWithUrl. The user will be allowed to log on, and a message will be displayed pointing the user to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Block. The user will not be allowed to log on.

BlockAndUpgrade. The user will not be allowed to log on, but his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. The user can then try to log on by using the new client application. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

BlockWithUrl. The user will not be allowed to log on, but a message will be displayed pointing him or her to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Client version rules are collected in client version policies; these policies that can be configured at the global scope, the site scope, the service scope (Registrar service), or the per-user scope. The **Set-CsClientVersionPolicyRule** cmdlet provides a way for you to modify the properties of an existing client version rule.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsClientVersionPolicyRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClientVersionPolicyRule"}

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
<td><p><em>Action</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.Action</p></td>
<td><p>Action to be taken any time the rule is triggered (that is, any time someone attempts to log on by using the specified software). Valid values are:</p>
<p>Allow. The user will be allowed to log on.</p>
<p>AllowWithUrl. The user will be allowed to log on, and a message will be displayed pointing him or her to a URL where the latest version of Lync can be downloaded and installed.</p>
<p>AllowAndUpgrade. The user will be allowed to log on, and his or her copy of Communicator will automatically be upgraded to the latest version of Lync.</p>
<p>Block. The user will not be allowed to log on.</p>
<p>BlockWithUrl. The user will not be allowed to log on, but a message will be displayed pointing him or her to a URL where the latest version of Lync can be downloaded and installed.</p>
<p>BlockAndUpgrade. The user will not be allowed to log on, but his or her copy of Communicator will automatically be upgraded to the latest version of Lync. The user can then try to log on by using the new client application.</p></td>
</tr>
<tr class="even">
<td><p><em>ActionUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL where users can download the latest version of Lync. This property is required if the Action is set to BlockWithUrl or AllowWithUrl.</p></td>
</tr>
<tr class="odd">
<td><p><em>BuildNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Build number of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the BuildNumber is 6362. Build numbers represent internal versions of the software during the development process, and help to ensure that you are using the final release version as opposed to a pre-release version.</p></td>
</tr>
<tr class="even">
<td><p><em>CompareOp</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.CompareOp</p></td>
<td><p>Comparison operator used to determine if the client software attempting to log on was released before, after, or at the same time as the version specified in the rule. Valid values are:</p>
<p>EQL (equal to)</p>
<p>NEQ (not equal to)</p>
<p>GTR (greater than)</p>
<p>GEQ (greater than or equal to)</p>
<p>LSS (less than)</p>
<p>LEQ (less than or equal to)</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional information about the client version rule. For example, the Description might include information about who to contact if you believe the rule should be changed.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the client version rule is to be used. If the Enabled property is set to False the rule will be ignored any time a user attempts to log on with the specified software. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the client version policy rule to be modified. The Identity of a client version rule consists of the scope where the rule has been configured plus a globally unique identifier (GUID). That means that a rule will have an Identity similar to this: site:Redmond/1987d3c2-4544-489d-bbe3-59f79f530a83.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Rule object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>MajorVersion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Major version of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the MajorVersion is 2. Major versions equate to primary releases of the software.</p></td>
</tr>
<tr class="even">
<td><p><em>MinorVersion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Minor version of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the MinorVersion is 0. Minor versions equate to interim releases of the software.</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Relative priority of the rule. Rules are processed in priority order, with the rule with priority 0 being processed first, the rule with priority 1 being processed second, and so on. If you assign a priority already in use, the new rule will use that priority and other rules will be renumbered accordingly.</p></td>
</tr>
<tr class="even">
<td><p><em>QfeNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Quick fix engineering number of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the QfeNumber is 111. QFE numbers represent planned updates to an application that are made available after the software’s official release.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserAgent</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Designator used to identify the software client. For example, OC is the user agent designation for Communicator. The <strong>Get-CsClientVersionConfiguration</strong> cmdlet provides corresponding friendly names for each user agent designation.</p></td>
</tr>
<tr class="even">
<td><p><em>UserAgentFullName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide a friendly name for the user agent. For example, instead of relying on the user agent UCCP to identify the agent administrators might spell the name out in full: Microsoft Unified Communications Client.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.Rule object. The **Set-CsClientVersionPolicyRule** cmdlet accepts pipelined instances of the client version rule object.

## Return Types

None. Instead, the **Set-CsClientVersionPolicyRule** cmdlet modifies instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.Rule object.

## 另请参阅

#### 其他资源

[Get-CsClientVersionPolicyRule](get-csclientversionpolicyrule.md)  
[New-CsClientVersionPolicyRule](new-csclientversionpolicyrule.md)  
[Set-CsClientVersionPolicyRule](set-csclientversionpolicyrule.md)

