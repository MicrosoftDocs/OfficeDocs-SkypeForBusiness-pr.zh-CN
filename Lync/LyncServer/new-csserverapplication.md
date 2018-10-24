---
title: New-CsServerApplication
TOCTitle: New-CsServerApplication
ms:assetid: 045e6e65-8ad6-49af-8bfb-aa9045fa4dd8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398096(v=OCS.15)
ms:contentKeyID: 49311853
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsServerApplication

 

_**上一次修改主题：** 2015-03-09_

Creates a new server application. Server applications are applications that are hosted by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsServerApplication -Name <String> -Parent <String> <COMMON PARAMETERS>

    New-CsServerApplication -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Uri <String> [-Confirm [<SwitchParameter>]] [-Critical <$true | $false>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Priority <Int32>] [-Script <String>] [-ScriptName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new server application with the Identity EdgeServer:atl-edge-001.litwareinc.com/EdgeMonitor. In addition to specifying the Identity, the parameters Uri and Critical are included; these parameters are used to specify the application URI and to indicate the application is not considered critical.

    New-CsServerApplication -Identity "EdgeServer:atl-edge-001.litwareinc.com/EdgeMonitor" -Uri http://www.litwareinc.com/edgemonitor -Critical $False

## EXAMPLE 2

The commands shown in Example 2 demonstrate how you can create a new server application that initially exists only in memory. To do this, the first command calls the **New-CsServerApplication** cmdlet along with two parameters: Identity (which specifies the Identity for the application) and InMemory, which indicates that the new application should be created in memory only. The resulting server application object is then stored in the variable $x.

After this virtual server application has been created, commands 2 and 3 are used to modify the values of the Uri and Critical properties, respectively. Finally, command 4 is used to transform the virtual server application into an actual server application. Note that this final command is mandatory. If you do not call the **Set-CsServerApplication** cmdlet, no application will be configured for EdgeServer:atl-edge-001.litwareinc.com/EdgeMonitor, and the virtual application will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsServerApplication -Identity "EdgeServer:atl-edge-001.litwareinc.com/EdgeMonitor" -InMemory
    $x.Uri = "http://www.litwareinc.com/edgemonitor"
    $x.Critical = $False
    Set-CsServerApplication -Instance $x

## Detailed Description

Server applications refer to the individual programs that run under Lync Server. The **New-CsServerApplication** cmdlet provides a way for administrators to configure new server applications.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsServerApplication** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsServerApplication"}

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
<td><p>Unique identifier for the server application to be created. Server application Identities are composed of the service where the application is hosted plus the application name. For example, the server application named QoEAgent might have an Identity similar to this: service:Registrar:atl-cs-001.litwareinc.com/QoEAgent.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Friendly name for the service. If you use the Identity parameter you do not need to include the Name parameter when creating a new service; instead, the Name property will be populated using the name portion of the application Identity. For example, if you create a new application with the Identity service:Registrar:atl-cs-001.litwareinc.com/TestService the application will automatically be named TestService. The Name parameter is required only if you use the Parent parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Specifies the service that will host the new server application. If you use the Identity parameter, then you do not need to use either the Parent or the Name parameters; that’s because the application Identity combines the values of the Parent and Name properties. However, you can omit the Identity parameter by using the Parent and Name parameters instead. In that case, the Parent parameter would need to look something like this: -Parent &quot;Registrar:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Uri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Unique Uniform Resource Identifier (URI) for the application. For example, the QoEAgent application has the URI http://www.microsoft.com/LCS/QoEAgent.</p></td>
</tr>
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
<td><p>If set to True, then Lync Server will not start unless the application in question can be started. If False, then Lync Server will start regardless of whether or not the application can be started. If this parameter is not specified the Critical property will be set to True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set this value to True to enable the application. Set the value to False to disable the application. If this parameter is not specified the Enabled property will be set to False and the new application will be disabled.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Indicates the order of execution for server applications. The application with priority 0 is started first; the application with priority 1 is started second; and so on. Note that each service that hosts a server application has its own unique set of priorities. For example, the Registrar service might host three applications with corresponding priorities 0, 1, and 2. Similarly, the 边缘服务器 service might have four applications; these applications will have the priorities 0, 1, 2, and 3.</p>
<p>If you do not specify a priority then the application will automatically be added to the bottom of the priority list. If you add or remove an application the priorities of the other applications will be adjusted accordingly. For example, if you delete an application that has a priority of 0 then the application that previously had the priority 1 will automatically have its priority set to 0.</p></td>
</tr>
<tr class="odd">
<td><p><em>Script</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to associate the server application with a script. To add a script to a server application, use syntax similar to this:</p>
<p>-Script &quot;Update.ps1&quot;</p>
<p>To remove a script, simply set the Script property to a null value:</p>
<p>-Script $Null</p>
<p>Each server application can only be associated with one script.</p></td>
</tr>
<tr class="even">
<td><p><em>ScriptName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Path to the Microsoft SIP Processing Language (MSPL) script used by the application (if applicable). MSPL is a scripting language used for filtering and routing SIP messages.</p></td>
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

None. The **New-CsServerApplication** cmdlet does not accept pipelined input.

## Return Types

The **New-CsServerApplication** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ServerApplication.Application object.

## 另请参阅

#### 其他资源

[Get-CsServerApplication](get-csserverapplication.md)  
[Remove-CsServerApplication](remove-csserverapplication.md)  
[Set-CsServerApplication](set-csserverapplication.md)

