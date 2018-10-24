---
title: Set-CsWebServer
TOCTitle: Set-CsWebServer
ms:assetid: 95a7be5b-9e53-40b9-b7b8-3a4bae9c946c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398759(v=OCS.15)
ms:contentKeyID: 49313653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsWebServer

 

_**上一次修改主题：** 2015-03-09_

Modifies one or more of the Web Server services used by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsWebServer [-Identity <XdsGlobalRelativeIdentity>] [-AppSharingPortCount <UInt16>] [-AppSharingPortStart <UInt16>] [-Confirm [<SwitchParameter>]] [-ExternalFqdn <Fqdn>] [-ExternalHttpPort <UInt16>] [-ExternalHttpsPort <UInt16>] [-Force <SwitchParameter>] [-InternalFqdn <Fqdn>] [-McxSipExternalListeningPort <UInt16>] [-McxSipPrimaryListeningPort <UInt16>] [-MeetingRoomAdminPortalExternalListeningPort <UInt16>] [-MeetingRoomAdminPortalInternalListeningPort <UInt16>] [-PrimaryHttpPort <UInt16>] [-PrimaryHttpsPort <UInt16>] [-PublishedExternalHttpPort <UInt16>] [-PublishedExternalHttpsPort <UInt16>] [-PublishedPrimaryHttpPort <UInt16>] [-PublishedPrimaryHttpsPort <UInt16>] [-ReachExternalPsomServerPort <UInt16>] [-ReachPrimaryPsomServerPort <UInt16>] [-RmWebSipExternalListeningPort <UInt16>] [-RmWebSipPrimaryListeningPort <UInt16>] [-SupportConferenceConsoleSipExternalListeningPort <UInt16>] [-SupportConferenceConsoleSipPrimaryListeningPort <UInt16>] [-UcwaSipExternalListeningPort <UInt16>] [-UcwaSipPrimaryListeningPort <UInt16>] [-UserServer <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 changes the PrimaryHttpPort for a single Web Service pool: the pool with the Identity WebServer:atl-cs-001.litwareinc.com. In this example, the port is changed to port number 89.

    Set-CsWebServer -Identity "WebServer:atl-cs-001.litwareinc.com" -PrimaryHttpPort 89

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1. In this case, the PrimaryHttpPort is modified for all the Web Service pools in the organization. To do this, the command starts off by using the **Get-CsService** cmdlet and the WebServer parameter to return a collection of all the Web Services pools currently in use. This collection is then piped to the **ForEach-Object** cmdlet, which takes each pool in the collection and sets the PrimaryHttpPort to port 89. The data must be piped to the **ForEach-Object** cmdlet because the **Set-CsWebServer** cmdlet cannot accept pipelined data itself.

    Get-CsService -WebServer | ForEach-Object {Set-CsWebServer -Identity $_.Identity -PrimaryHttpPort 89}

## Detailed Description

Lync Server makes extensive use of Web servers and web services. For example, Address Book queries can be conducted using web services (the Address Book Query Web service). Lync Server also hosts webpages that enable users to do such things as configure their dial-in conferencing personal identification number (PINs). Considering the important role played by Web servers and web services, it is critical that administrators know how these servers and services are configured. That information that can be returned using the following command:

Get-CsService –WebServer

There are also times where it is critical that administrators be able to change the way their Web servers are configured. For example, you might need to modify the port used for external HTTP or HTTPS connections. Port changes like these (and other modifications) can be made using the **Set-CsWebServer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsWebServer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsWebServer"}

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
<td><p><em>AppSharingPortCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Total number of ports allocated for application sharing. The actual ports to be opened will start with the value configured for AppSharingPortStart and continue through the number of ports specified for AppSharingPortCount. For example, if the AppSharingPortStart is set to 60000 and the AppSharingPortCount is set to 100 then ports 60000 through 60099 will be used for application sharing. The default value is 16383.</p></td>
</tr>
<tr class="even">
<td><p><em>AppSharingPortStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>First port in the range of ports allocated for application sharing. The default value is 49152.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) used by people connecting to the Web Services pool from outside the internal network. For example: -ExternalFqdn &quot;www.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalHttpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for external web connections made using the HTTP protocol. The default value is port 8080.</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalHttpsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for external web connections made using the HTTPS protocol. The default value is port 4443.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the Web Services pool. For example: -Identity &quot;WebServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that you can leave off the prefix &quot;WebServer:&quot; when specifying a Web server. For example: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>InternalFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name for the Mobility Services. The InternalFqdn should only be accessible from inside the organization’s firewall.</p></td>
</tr>
<tr class="even">
<td><p><em>McxSipExternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External listening port for the Mobility service.</p></td>
</tr>
<tr class="odd">
<td><p><em>McxSipPrimaryListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Internal listening port for the Mobility service.</p></td>
</tr>
<tr class="even">
<td><p><em>MeetingRoomAdminPortalExternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External listening port for the Lync Meeting Room Admin Portal. The Admin Portal is a web-based utility that makes it easy for administrator to manage meeting rooms.</p></td>
</tr>
<tr class="odd">
<td><p><em>MeetingRoomAdminPortalInternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Internal listening port for the Lync Meeting Room Admin Portal. The Admin Portal is a web-based utility that makes it easy for administrator to manage meeting rooms.</p></td>
</tr>
<tr class="even">
<td><p><em>PrimaryHttpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for internal web connections made using the HTTP protocol. The default value is port 80.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrimaryHttpsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for internal web connections made using the HTTPS protocol. The default value is port 443.</p></td>
</tr>
<tr class="even">
<td><p><em>PublishedExternalHttpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for the published external HTTP port.</p></td>
</tr>
<tr class="odd">
<td><p><em>PublishedExternalHttpsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External port for the Mobility service.</p></td>
</tr>
<tr class="even">
<td><p><em>PublishedPrimaryHttpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number for the published primary HTTP port.</p></td>
</tr>
<tr class="odd">
<td><p><em>PublishedPrimaryHttpsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Internal port for the Mobility service.</p></td>
</tr>
<tr class="even">
<td><p><em>ReachExternalPsomServerPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External port number for the Persistent Shared Object Model Protocol, a Microsoft protocol used for conferences. The default port number is 8061.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReachPrimaryPsomServerPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Primary port number for the Persistent Shared Object Model (PSOM) Protocol, a Microsoft protocol used for conferences. The default port number is 8060.</p></td>
</tr>
<tr class="even">
<td><p><em>RmWebSipExternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External listening port for the Persistent Chat Room Management Web App. This application is available only if you have installed and configured Persistent Chat.</p></td>
</tr>
<tr class="odd">
<td><p><em>RmWebSipPrimaryListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Primary listening port for the Persistent Chat Room Management Web App. This application is available only if you have installed and configured Persistent Chat.</p></td>
</tr>
<tr class="even">
<td><p><em>SupportConferenceConsoleSipExternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Listening port for the Support Conferencing Console. The default value is 6007.</p></td>
</tr>
<tr class="odd">
<td><p><em>SupportConferenceConsoleSipPrimaryListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by the Office 365 Support Conference Console. This console is used by support personnel to troubleshoot problems with conferences and online meetings.</p></td>
</tr>
<tr class="even">
<td><p><em>UcwaSipExternalListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>External SIP listening port for the Unified Communications Web API (UCWA). The default value is 5088.</p></td>
</tr>
<tr class="odd">
<td><p><em>UcwaSipPrimaryListeningPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Internal SIP listening port for the Unified Communications Web API (UCWA). The default value is 5089.</p></td>
</tr>
<tr class="even">
<td><p><em>UserServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service ID for the User Services pool associated with the Web Services pool. For example: -UserServer &quot;UserServer:atl-cs-001.litwareinc.com&quot;.</p></td>
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

None. The **Set-CsWebServer** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Set-CsWebServer** cmdlet modifies instances of the Microsoft.Rtc.Management.Xds.DisplayWebServer object.

## 另请参阅

#### 其他资源

[Get-CsService](get-csservice.md)

