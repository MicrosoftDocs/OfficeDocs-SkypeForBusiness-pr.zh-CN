---
title: Start-CsWindowsService
TOCTitle: Start-CsWindowsService
ms:assetid: 7491b91f-d342-4f9a-878b-d20b35294a9c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398561(v=OCS.15)
ms:contentKeyID: 49313262
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Start-CsWindowsService

 

_**上一次修改主题：** 2015-03-09_

The **Start-CsWindowsService** cmdlet enables you to start a Lync Server service. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Start-CsWindowsService [-ComputerName <String>] [-Name <String>] <COMMON PARAMETERS>

    Start-CsWindowsService [-InputObject <NTService>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NoWait <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 starts all the Lync Server services on the local computer. This is done by calling the **Start-CsWindowsService** cmdlet without any parameters. Note that you will not receive an error if you try to start a service that has already been started.

    Start-CsWindowsService

## EXAMPLE 2

Example 2 starts the 响应组应用程序 service on the local computer. To do this, the command uses the Name parameter followed by the service name: RTCRGS.

    Start-CsWindowsService -Name "RTCRGS"

## EXAMPLE 3

The command shown in Example 3 also starts the 响应组应用程序 service; in this case, however, the service is started on the remote computer atl-cs-001.litwareinc.com. To start a service on a remote computer, include the ComputerName parameter followed by the FQDN of the remote computer.

    Start-CsWindowsService -Name "RTCRGS" -ComputerName atl-cs-001.litwareinc.com

## EXAMPLE 4

In Example 4, the command searches the local computer for all the Lync Server services that are not currently running, then starts each of these inactive services. To do this, the command first calls the **Get-CsWindowsService** cmdlet to return a collection of all the Lync Server services. This collection is then piped to the **Where-Object** cmdlet, which selects only those services where the Status property is not equal to Running. This filtered collection is then piped to the **Start-CsWindowsService** cmdlet, which starts each service in the collection.

    Get-CsWindowsService | Where-Object {$_.Status -ne "Running"} | Start-CsWindowsService

## Detailed Description

Many Lync Server components run as standard Windows services; for example, the 会议助理应用程序 is actually a service named RTCCAA. If one of your Lync Server services is currently stopped, you can restart that service by using the **Start-CsWindowsService** cmdlet.

Note, however, that the **Start-CsWindowsService** cmdlet can only start Lync Server services; an error will occur if you attempt to start a non-Lync Server service (such as the print spooler) using this cmdlet.

Functionally, the **Start-CsWindowsService** cmdlet is very similar to the generic Windows PowerShell **Start-Service**cmdlet; if you wanted to, you could use the **Start-Service** cmdlet to start a Lync Server service. On the other hand, the **Start-CsWindowsService** cmdlet includes a ComputerName parathemeter that makes it easy to start a service on a remote computer: you simply include the ComputerName parameter followed by the fully qualified domain name (FQDN) of the remote computer. The **Start-Service** cmdlet does not have a comparable parameter. In addition, the cmdlet’s Report parameter enables you to keep a log of any errors that might occur when calling **Start-CsWindowsService**.

Like other Windows services, some Lync Server services have a dependency on another service; for example, the Lync Server Conferencing Attendant service cannot run unless the 应用程序服务 is already running. If you try to start a service that depends on another service, the **Start-CsWindowsService** cmdlet will start both of those services. That means that, if you try to start the Conferencing Attendant service, the cmdlet will first start the 应用程序服务 and then start the Conferencing Attendant service. However, the **Start-CsWindowsService** cmdlet will not automatically start any dependent services of a service: if you start the 应用程序服务, the command will not automatically start the Conferencing Attendant service as well.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Start-CsWindows** cmdlet locally: RTCUniversalServerAdmins. In addition, you must also have local administrator rights on the destination computer in order to run this cmdlet. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Start-CsWindowsService"}

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
<td><p><em>ComputerName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the remote computer hosting the service to be started; if this parameter is not included, then the <strong>Start-CsWindowsService</strong> cmdlet will start the specified service (or services) on the local computer. The remote computer should be referenced using its FQDN; for example, atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InputObject</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.Core.NTService</p></td>
<td><p>Enables you to start a service using an object reference rather than a service name. For example, if you use the <strong>Get-CsWindowsService</strong> cmdlet to return information about a service, and if you store the returned object in a variable named $x, you can then start the service using this command:</p>
<p>$x = Get-CsWindowsService -Name &quot;RTCCPS&quot;</p>
<p>Start-CsWindowsService -InputObject $x.Name</p></td>
</tr>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the Lync Server service you want to start. Note that you must use the service name (for example, RTCCAA) and not the service display name. You can only pass a single service name to the Name parameter, and you cannot use wildcards in the service name. Service names can be retrieved using the <strong>Get-CsWindowsService</strong> cmdlet.</p>
<p>Keep in mind that the <strong>Start-CsWindowsService</strong> cmdlet can only start Lync Server services; you cannot use this cmdlet to start other Windows services. For those services, you might be able to use the Windows PowerShell <strong>Start-Service</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>NoWait</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, causes the command to run and then immediately return control to the Windows PowerShell prompt. If not present, control will not be returned until the command has completed and a status report has been written to the screen.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Path to an HTML file where error information can be stored. If this parameter is included, any errors that occur during the running of this cmdlet will be logged to the specified file (for example, C:\Logs\Service_report.html).</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.Deployment.Core.NTService object. The **Start-CsWindowsService** cmdlet accepts pipelined instances of the Windows service object.

## Return Types

None. Instead, the **Start-CsWindowsService** cmdlet starts instances of the Microsoft.Rtc.Management.Deployment.Core.NTService object.

## 另请参阅

#### 其他资源

[Get-CsWindowsService](get-cswindowsservice.md)  
[Stop-CsWindowsService](stop-cswindowsservice.md)

