---
title: New-CsClientVersionPolicyRule
TOCTitle: New-CsClientVersionPolicyRule
ms:assetid: d28df005-0db0-4b17-9ca0-9dc9ed063d73
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398905(v=OCS.15)
ms:contentKeyID: 49314328
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsClientVersionPolicyRule

 

_**上一次修改主题：** 2015-03-09_

Creates a new client version policy rule. Client version policy rules help determine whether users can use a specific client application to log on to Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsClientVersionPolicyRule -Identity <XdsIdentity> <COMMON PARAMETERS>

    New-CsClientVersionPolicyRule -Parent <String> -RuleId <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Action <Allow | AllowAndUpgrade | AllowWithUrl | Block | BlockAndUpgrade | BlockWithUrl>] [-ActionUrl <String>] [-BuildNumber <UInt16>] [-CompareOp <EQL | NEQ | GTR | GEQ | LSS | LEQ>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MajorVersion <UInt16>] [-MinorVersion <UInt16>] [-Priority <Int32>] [-QfeNumber <UInt16>] [-UserAgent <String>] [-UserAgentFullName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 demonstrates how you can create a new client version policy rule. Policy rules have Identities that are composed of two parts: the scope where the announcement is to be assigned, and a 36-character GUID. Creating an Identity for a new client version policy rule first requires you to use the .NET Framework method NewGuid to create a new GUID. This step is carried out in the first command in the example, with the resulting GUID being stored in the variable $x.

After the GUID has been created, you can then use the **New-CsClientVersionPolicyRule** cmdlet to create the new rule. This command uses four parameters: Parent, with a parameter value representing the scope (site:Redmond) for the new rule; RuleId, with the parameter value $x (representing the newly-created GUID); MajorVersion (4); and UserAgent (InHouse). In this case, the UserAgent parameter represents an in-house client application.

    $x = [guid]::NewGuid()
    
    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse

## EXAMPLE 2

The commands shown in Example 2 represent a variation of the command shown in Example 1: in this case, however, the new rule is initially created in memory only, and only later added to Lync Server. To carry out this task, the first command in the example creates the GUID portion of the Identity. In command 2, a new in-memory-only client version policy rule is created; the InMemory parameter ensures that the rule exists only in memory and is not immediately added to the Lync Server infrastructure. As in Example 1, the Parent and RuleId parameters are used to specify the scope and GUID for the new rule, the two pieces that make up the rule Identity.

After the virtual rule has been created, the next two commands are used to assign values to the MajorVersion and UserAgent properties, respectively. When those tasks are complete, the final command in the example and the **Set-CsClientVersionPolicyRule** cmdlet is used to create the actual client version policy rule and assign the rule to the Redmond site.

    $x = [guid]::NewGuid()
    
    $z = New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -InMemory
    $z.MajorVersion = 4 
    $z.UserAgent = "Inhouse"
    Set-CsClientVersionPolicyRule -Instance $z

## Detailed Description

Client version policy rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server, his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information is then checked against a collection of client version rules to see if any rules apply to that particular application. For example, suppose a user attempts to log on by using Microsoft Office Communicator 2007 R2. Before the user can log on to Lync Server, the system will check to see if there is a client version rule that applies to Office Communicator 2007 R2. If a rule exists, Lync Server will then take the action specified by the rule. That action must be one of the following:

Allow. The user will be allowed to log on.

AllowAndUpgrade. The user will be allowed to log on, and his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

AllowWithUrl. The user will be allowed to log on, and a message will be displayed pointing the user to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Block. The user will not be allowed to log on.

BlockAndUpgrade. The user will not be allowed to log on, but his or her copy of Communicator 2007 R2 will automatically be upgraded to the latest version of Lync. The user can then try to log on by using the new client application. Upgrades are carried out using either Microsoft Update or Windows Server Update Services, depending on how you have configured your system.

BlockWithUrl. The user will not be allowed to log on, but a message will be displayed pointing him or her to a URL where the latest version of Lync can be downloaded and installed. The URL must point to a website that you have created yourself; no such site is created for you when you install Lync Server.

Client version policy rules are collected in client version policies, policies that can be configured at the global scope, the site scope, the service scope (Registrar service), or the per-user scope. New client version rules are created by using the **New-CsClientVersionPolicyRule** cmdlet. When you create a new rule you must also specify the Identity for that rule; that Identity consists of a scope (for example, site:Redmond) and a globally unique identifier (GUID). You can either put together an Identity yourself, or provide the scope (the Parent parameter) and the GUID (the RuleId parameter) to have the **New-CsClientVerisonPolicyRule** cmdlet create the Identity for you.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsClientVersionPolicyRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsClientVersionPolicyRule"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the client version policy rule to be created. The Identity of a client version policy rule consists of the scope where the rule has been configured plus a globally unique identifier (GUID). That means that a rule will have an Identity similar to this: site:Redmond/1987d3c2-4544-489d-bbe3-59f79f530a83.</p>
<p>Instead of using the Identity parameter you can use the Parent and RuleId parameters to have the <strong>New-CsClientVerisonPolicyRule</strong> cmdlet create the Identity for you.</p></td>
</tr>
<tr class="even">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Scope information for the new rule. To use the Parent parameter and create a new rule for the global policy, use this syntax: -Parent global. To create a new rule for a site policy, use syntax similar to this: -Parent &quot;site:Redmond&quot;. To create a new rule for a service policy, use syntax similar to this: -parent &quot;Registrar:atl-cs-001.litwareinc.com&quot;. To create a new rule for a per-user policy, use syntax similar to this: -Parent &quot;RedmondClientVersionPolicy&quot;.</p>
<p>You must use either the Identity parameter or both the Parent and RuleId parameters when creating a new rule.</p></td>
</tr>
<tr class="odd">
<td><p><em>RuleId</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Globally unique identifier (GUID) for the rule. In Windows PowerShell, you can create a GUID by using the following command:</p>
<p>$x = [guid]::NewGuid()</p>
<p></p></td>
</tr>
<tr class="even">
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
<tr class="odd">
<td><p><em>ActionUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL where users can download the latest version of Lync. This property is required if the Action is set to BlockWithUrl or AllowWithUrl.</p></td>
</tr>
<tr class="even">
<td><p><em>BuildNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Build number of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the BuildNumber is 6362. Build numbers represent internal versions of the software during the development process, and help to ensure that you are using the final release version as opposed to a pre-release version.</p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional information about the client version rule. For example, the Description might include information about who to contact if you believe the rule should be changed.</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the client version rule is to be used. If the Enabled property is set to False ($False), then the rule will be ignored any time a user attempts to log on with the specified software. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>MajorVersion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Major version of the software. For example, if your copy of Communicator is version 2.0.6362.111, then the MajorVersion is 2. Major versions equate to primary releases of the software. You must assign a value to the MajorVersion property any time you create a new rule.</p></td>
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
<td><p>Relative priority of the rule. Rules are processed in priority order, with the rule that has priority 0 being processed first, the rule that has priority 1 being processed second, and so on. If you assign a priority that is already in use, the new rule will use that priority and other rules will be renumbered accordingly.</p></td>
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
<td><p>Designator used to identify the software client. For example, OC is the user agent designation for Communicator.</p></td>
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

None. The **New-CsClientVersionPolicyRule** cmdlet does not accept pipelined input.

## Return Types

The **New-CsClientVersionPolicyRule** cmdlet creates new instances of Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.Rule object.

## 另请参阅

#### 其他资源

[Get-CsClientVersionPolicyRule](get-csclientversionpolicyrule.md)  
[Remove-CsClientVersionPolicyRule](remove-csclientversionpolicyrule.md)  
[Set-CsClientVersionPolicyRule](set-csclientversionpolicyrule.md)

