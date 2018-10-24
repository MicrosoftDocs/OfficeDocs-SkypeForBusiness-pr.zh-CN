---
title: Set-CsServerApplication
TOCTitle: Set-CsServerApplication
ms:assetid: b0f75629-b6c3-4958-b466-6c8a2f104819
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412850(v=OCS.15)
ms:contentKeyID: 49313973
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsServerApplication

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values of an existing server application. Server applications are applications that are hosted by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsServerApplication [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsServerApplication [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Critical <$true | $false>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-Priority <Int32>] [-Script <String>] [-ScriptName <String>] [-Uri <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 enables the server application that has the Identity Registrar:atl-cs-001.litwareinc.com/ExumRouting. Because Identities must be unique, this command will only enable a single server application.

    Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True

## EXAMPLE 2

Example 2 enables all the server applications that are currently disabled. To do this, the command first calls the **Get-CsServerApplication** cmdlet in order to return a collection of all the server applications currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those applications where the Enabled property is equal to False. In turn, the filtered collection is piped to the **Set-CsServerApplication** cmdlet, which takes each item in the collection and sets the Enabled property to True.

    Get-CsServerApplication | Where-Object {$_.Enabled -eq $False} | Set-CsServerApplication -Enabled $True

## Detailed Description

Server applications refer to the individual programs that run under the Lync Server. The **Set-CsServerApplication** cmdlet provides a way for administrators to modify the property values of any application running as part Lync Server.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsServerApplication** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsServerApplication"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Critical</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True (the default value), then Lync Server will not start unless the application in question can be started. If False, then Lync Server will start regardless of whether or not the application can be started.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set this value to True to enable the application. Set the value to False to disable the application.</p></td>
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
<td><p>Unique identifier for the server application to be modified. Server application Identities are composed of the service where the application is hosted plus the application name. For example, the server application named QoEAgent might have an Identity similar to this: Registrar:atl-cs-001.litwareinc.com/QoEAgent.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ServerApplication.Application object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Indicates the order of execution for server applications. The application with priority 0 is started first; the application with priority 1 is started second; and so on. Note that each service that hosts a server application has its own unique set of priorities. For example, the Registrar service might host three applications with corresponding priorities 0, 1, and 2. Similarly, the 边缘服务器 service might have four applications; these applications will have the priorities 0, 1, 2, and 3.</p>
<p>If you do not specify a priority then the application will automatically be added to the bottom of the priority list. If you add or remove an application, the priorities of the other applications will be adjusted accordingly. For example, if you delete an application that has a priority of 0, then the application that previously had the priority 1 will automatically have its priority set to 0.</p></td>
</tr>
<tr class="even">
<td><p><em>Script</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to associate the server application with a script. To add a script to a server application, use syntax similar to this:</p>
<p>-Script &quot;Update.ps1&quot;</p>
<p>To remove a script, simply set the Script property to a null value:</p>
<p>-Script $Null</p>
<p>Each server application can only be associated with one script.</p></td>
</tr>
<tr class="odd">
<td><p><em>ScriptName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Path to the Microsoft SIP Processing Language (MSPL) script used by the application. MSPL is a scripting language used for filtering and routing SIP messages.</p></td>
</tr>
<tr class="even">
<td><p><em>Uri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique Uniform Resource Identifier (URI) for the application. For example, the QoEAgent application has the URI http://www.microsoft.com/LCS/QoEAgent.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.ServerApplication.Application object. The **Set-CsServerApplication** cmdlet accepts pipelined instances of the server application object.

## Return Types

The **Set-CsServerApplication** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ServerApplication.application object.

## 另请参阅

#### 其他资源

[Get-CsServerApplication](get-csserverapplication.md)  
[New-CsServerApplication](new-csserverapplication.md)  
[Remove-CsServerApplication](remove-csserverapplication.md)

