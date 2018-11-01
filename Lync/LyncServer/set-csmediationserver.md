---
title: Set-CsMediationServer
TOCTitle: Set-CsMediationServer
ms:assetid: 13efdd9d-ba26-4c93-b0b9-b6e4739bb630
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398213(v=OCS.15)
ms:contentKeyID: 49312084
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsMediationServer

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify the properties of one or more Mediation Servers. Mediation Servers are used to route traffic between your internal Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a SIP trunk. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsMediationServer [-Identity <XdsGlobalRelativeIdentity>] [-AudioPortCount <UInt16>] [-AudioPortStart <UInt16>] [-Confirm [<SwitchParameter>]] [-EdgeServer <String>] [-Force <SwitchParameter>] [-Registrar <String>] [-SipClientTcpPort <UInt16>] [-SipClientTlsPort <UInt16>] [-SipServerPort <UInt16>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 sets the SIP gateway TCP listening port to 5072 for the 中介服务器 MediationServer:atl-cs-001.litwareinc.com. After changing the port you will need to restart the Lync Server Mediation service.

    Set-CsMediationServer -Identity "MediationServer:atl-cs-001.litwareinc.com" -SipClientTcpPort 5072

## EXAMPLE 2

Example 2 configures audio port settings for the 中介服务器 MediationServer:atl-cs-001.litwareinc.com. In this example the starting audio port is set to 60000 and the total number of ports allocated for audio is 1000.

    Set-CsMediationServer -Identity "MediationServer:atl-cs-001.litwareinc.com" -AudioPortStart 60000 -AudioPortCount 1000

## Detailed Description

Mediation Servers act as a bridge between your internal Enterprise Voice configuration and either a PSTN gateway, IP-PBX, or a SIP trunk; in turn, this provides a way for your Enterprise Voice users (who are using Voice over Internet Protocol (VoIP) devices) to communicate with people using standard land-line telephones or mobile phones. The **Set-CsMediationServer** cmdlet provides a way for you to make changes to an existing 中介服务器. In particular, you can modify the ports used for communicating with client devices, 前端服务器, and gateways peers. If necessary, the **Set-CsMediationServer** cmdlet can also be used to associate a 中介服务器 with a new Registrar or a new 边缘服务器.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsMediationServer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsMediationServer"}

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
<td><p><em>AudioPortCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Total number of ports allocated for sending and receiving audio traffic. The actual ports to be opened will start with the value configured for AudioPortStart and continue through the number of ports specified for AudioPortCount. For example, if the AudioPortStart is set to 60000 and the AudioPortCount is set to 100, then ports 60000 through 60099 inclusive will be used for audio traffic.</p>
<p>A minimum of seven media ports are needed for relaying a single audio call:</p>
<p>Two gateway ports. One port is needed for real-time transport protocol (RTP) traffic and one for real-time transport control protocol (RTCP) traffic.</p>
<p>Two User Datagram Protocol (UDP) relay ports, one for RTP traffic and one for RTCP traffic.</p>
<p>One Transmission Control Protocol (TCP) relay port. A single TCP relay port can handle both RTP and RTCP traffic.</p>
<p>Two local ports per network interface, one for RTP traffic and one for RTCP traffic</p></td>
</tr>
<tr class="even">
<td><p><em>AudioPortStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>First port in the range of ports allocated for sending and receiving audio traffic. For example: –AudioPortStart 60000.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EdgeServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service identity of the 边缘服务器 to be associated with the 中介服务器. For example: -EdgeServer &quot;EdgeServer:atl-edge-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Service location of the 中介服务器 to be modified. For example: -Identity &quot;MediationServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that you can leave off the prefix &quot;MediationServer:&quot; when specifying a 中介服务器. For example: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Registrar</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service identity of the Registrar to be associated with the 中介服务器. For example: -Registrar &quot;Registrar:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>SipClientTcpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Listening port used for communicating with gateway peers using TCP. By default, no TCP port is defined; however, a TCP port with the port number 5068 will automatically be created when a PSTN gateway is created. If you change the SipClientTcpPort you will need to restart the 中介服务器 service before the new port will actually be used.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipClientTlsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Listening port used for communicating with gateway peers using the Transport Layer Security (TLS) protocol. By default, SipClientTlsPort is configured to use port 5067. If you change the SipClientTlsPort you will need to restart the 中介服务器 service before the new port will actually be used.</p></td>
</tr>
<tr class="even">
<td><p><em>SipServerPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Listening port used for communicating with 前端服务器. By default, SipServerPort is configured to use port 5070. If you change the SipServerPort, you will need to restart the 中介服务器 service before the new port will actually be used.</p></td>
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

None. The **Set-CsMediationServer** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsMediationServer** cmdlet does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.Xds.DisplayMediationServer object.

## 另请参阅

#### 其他资源

[Get-CsService](get-csservice.md)

