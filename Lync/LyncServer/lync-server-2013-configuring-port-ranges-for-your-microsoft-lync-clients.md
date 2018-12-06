---
title: 配置 Microsoft Lync 客户端的端口范围
TOCTitle: 配置 Microsoft Lync 客户端的端口范围
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204760(v=OCS.15)
ms:contentKeyID: 49312316
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Microsoft Lync 客户端的端口范围

 

_**上一次修改主题：** 2015-03-09_

默认情况下，Lync 客户端应用程序在参与通信会话时可以使用介于 1024 和 65535 之间的任何端口；这是因为不会为客户端自动启用特定端口范围。但是，若要使用服务质量，您将需要为一系列特定端口范围重新分配各种通信类型（音频、视频、媒体、应用程序共享和文件传输）。可使用 Set-CsConferencingConfiguration cmdlet 完成此操作。

通过从 Microsoft Lync Server 2013 命令行管理程序中运行以下命令可确定当前用于通信会话的端口范围：

    Get-CsConferencingConfiguration

假设您自从安装 Lync Server 2013 后尚未对会议设置进行任何更改，您应获得包括这些属性值的信息：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果您仔细查看上面的输出，您会发现两点很重要。首先，ClientMediaPortRangeEnabled 属性设置为 False：

    ClientMediaPortRangeEnabled : False

这一点之所以很重要，是因为当此属性设置为 False 时，Lync 客户端会在参与通信会话时使用介于 1024 和 65535 之间的任意可用端口；无论任何其他端口设置（例如 ClientMediaPort 或 ClientVideoPort）如何皆如此。如果要限制对一组指定端口的使用（如果您计划实施服务质量，则需要这样做），则必须首先启用客户端媒体端口范围。可使用以下 Windows PowerShell命令完成此操作：

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上述命令为会议配置设置的全局集合启用客户端媒体端口范围；但是，这些设置也可应用于站点范围和/或服务范围（仅限会议服务器服务）。若要为特定站点或服务器启用客户端媒体端口范围，请在调用 Set-CsConferencingConfiguration 时指定该站点或服务器的标识：

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者，也可以使用此命令同时为您的所有会议配置设置启用端口范围：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您将发现的另一个重要事项是，示例输出显示默认情况下为每种类型的网络通信设置的媒体端口范围是相同的：

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

若要实施 QoS，其中每个端口范围都需要是唯一的。例如，您可以按如下所示配置端口范围：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端通信类型</th>
<th>起始端口</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


在上表中，客户端端口范围表示为您的服务器配置的端口范围的一部分。例如，在服务器上，应用程序共享已配置为使用 40803 和 49151 之间的端口；在客户端计算机上，应用程序共享配置为使用 42000 和 42019 之间的端口。这样做也是为了便于管理 QoS：客户端端口不必表示为服务器上使用的端口的一部分。（例如，在客户端计算机上，您可以配置应用程序共享以使用 10000 和 10019 之间的端口。）但是，建议您使您的客户端端口范围位于服务器端口范围内。

另外，您可能已注意到，为服务器上的应用程序共享留出了 8348 个端口，但为客户端上的应用程序共享只留出了 20 个端口。这也是建议做法，但不是硬性规定。通常，您可以考虑用每个可用端口来表示一个通信会话：如果端口范围内有 100 个可用端口，则意味着相关计算机在任何给定时间内最多可参与 100 个通信会话。因为服务器参与的会话数可能多于客户端，所以在服务器上打开的端口数应多于在客户端上打开的端口数。为客户端上的应用程序共享留出 20 个端口意味着用户可以参与指定设备上的 20 个应用程序共享会话，并且所有会话是同时进行的。对于您的大多数用户来说，这样做应该足够了。

若要为您的会议配置设置的全局集合分配上述端口范围，您可以使用以下 Lync Server 命令行管理程序命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者，使用此命令为您的所有会议配置设置分配这些相同的端口范围：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

单个用户必须从 Lync 注销然后重新登录，这些更改才会实际生效。

> [!NOTE]  
> 您还可以启用客户端媒体端口范围，然后使用单个命令分配这些端口范围。例如：<br />
<code>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</code>


