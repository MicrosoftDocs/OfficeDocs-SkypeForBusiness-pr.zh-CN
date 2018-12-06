---
title: Set-CsConferenceServer
TOCTitle: Set-CsConferenceServer
ms:assetid: 90f9f1f1-0029-4f97-a8f4-719523cfad56
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398738(v=OCS.15)
ms:contentKeyID: 49313606
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConferenceServer

 

_**上一次修改主题：** 2015-03-09_

修改 A/V 会议服务器（也称为会议服务器）的属性。会议服务器可为会议提供音频和视频 (A/V) 功能。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsConferenceServer [-Identity <XdsGlobalRelativeIdentity>] [-AppSharingPortCount <UInt16>] [-AppSharingPortStart <UInt16>] [-AppSharingSipPort <UInt16>] [-AudioPortCount <UInt16>] [-AudioPortStart <UInt16>] [-AudioVideoSipPort <UInt16>] [-Confirm [<SwitchParameter>]] [-DataPsomPort <UInt16>] [-EdgeServer <String>] [-Force <SwitchParameter>] [-ImSipPort <UInt16>] [-MeetingPsomPort <UInt16>] [-PhoneSipPort <UInt16>] [-VideoPortCount <UInt16>] [-VideoPortStart <UInt16>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令修改会议服务器 ConferencingServer:atl-cs-001.litwareinc.com 的即时消息 SIP 端口。在此示例中，将端口更改为 5075。

    Set-CsConferenceServer -Identity "ConferencingServer:atl-cs-001.litwareinc.com" -ImSipPort 5075

## 示例 2

示例 2 是示例 1 中显示的命令的变体，但在此示例中，会更改组织中所有会议服务器的即时消息 SIP 端口。为执行此操作，该命令首先使用 **Get-CsService** cmdlet 和 ConferencingServer 参数返回当前正在使用的所有会议服务器的集合。然后，将此集合通过管道传递到 **ForEach-Object** cmdlet，后者会针对集合中的每台服务器运行 **Set-CsConferenceServer** cmdlet，将 ImSipPort 设置为 5075。

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -ImSipPort 5075}

## 详细说明

会议服务器（也称为 A/V 会议服务器）用于为会议提供音频和视频功能。而 **Set-CsConferenceServer** cmdlet 可用于修改这些服务器的属性。具体而言，可以指定用于音频通信、视频通信和应用程序共享等活动的端口。还可以使用 **Set-CsConferenceServer** cmdlet 将给定的服务器与边缘服务器或存档服务器进行关联。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsConferenceServer** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsConferenceServer"}

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
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AppSharingPortCount</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为应用程序共享分配的端口总数。实际打开的端口从配置的 AppSharingPortStart 值开始，包括为 AppSharingPortCount 指定的端口数范围内的所有端口。例如，如果将 AppSharingPortStart 设置为 60000，并将 AppSharingPortCount 设置为 100，那么会将端口 60000 至 60099 用于应用程序共享。</p></td>
</tr>
<tr class="even">
<td><p><em>AppSharingPortStart</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为应用程序共享分配的媒体端口范围内的第一个端口。例如：–AppSharingPortStart 60000。</p></td>
</tr>
<tr class="odd">
<td><p><em>AppSharingSipPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>用于侦听应用程序共享请求的 SIP 端口。实际用于应用程序共享的端口是使用 AppSharingPortStart 和 AppSharingPortCount 配置的。</p></td>
</tr>
<tr class="even">
<td><p><em>AudioPortCount</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为发送和接收音频通信分配的端口总数。实际打开的端口从配置的 AudioPortStart 值开始，包括为 AudioPortCount 指定的端口数范围内的所有端口。例如，如果将 AudioPortStart 设置为 60000，并将 AudioPortCount 设置为 100，那么会将端口 60000 至 60099 用于音频通信。</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioPortStart</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为发送和接收音频通信分配的媒体端口范围内的第一个端口。例如：–AudioPortStart 60000。</p></td>
</tr>
<tr class="even">
<td><p><em>AudioVideoSipPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>用于侦听音频和视频服务的传入请求的 SIP 端口。实际用于音频和视频通信的端口是使用 AudioPortCount、AudioPortStart、VideoPortCount 和 VideoPortStart 配置的。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DataPsomPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>持续性共享对象模型 (PSOM) 协议使用的数据端口。</p></td>
</tr>
<tr class="odd">
<td><p><em>EdgeServer</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要与会议服务器关联的边缘服务器的服务位置。例如：-EdgeServer &quot;EdgeServer:atl-edge-001.litwareinc.com&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的会议服务器的服务位置。例如：-Identity &quot;ConferencingServer:atl-cs-001.litwareinc.com&quot;。</p>
<p>请注意，指定会议服务器时，可以省略前缀“ConferencingServer:”。例如：-Identity &quot;atl-cs-001.litwareinc.com&quot;。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>ImSipPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>即时消息通信使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><em>MeetingPsomPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>持续性共享对象模型 (PSOM) 协议（用于会议的 Microsoft 协议）使用的端口。</p></td>
</tr>
<tr class="even">
<td><p><em>PhoneSipPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>电话通信使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoPortCount</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为发送和接收视频通信分配的端口总数。实际打开的端口从配置的 VideoPortStart 值开始，包括为 VideoPortCount 指定的端口数范围内的所有端口。例如，如果将 VideoPortStart 设置为 60000，并将 VideoPortCount 设置为 100，那么会将端口 60000 至 60099 用于视频通信。</p></td>
</tr>
<tr class="even">
<td><p><em>VideoPortStart</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>为发送和接收视频通信分配的端口范围内的第一个端口。例如：–VideoPortStart 60000。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Set-CsConferenceServer** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Set-CsConferenceServer** cmdlet 不会返回任何对象或值。此 cmdlet 会修改 Microsoft.Rtc.Management.Xds.DisplayConferenceServer 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsConferencingConfiguration](get-csconferencingconfiguration.md)  
[Get-CsService](get-csservice.md)

