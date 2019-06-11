---
title: 'Lync Server 2013: 为您的 Microsoft Lync 客户端配置端口范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cd4c109760756dd265526bd9d5285fdc9fed30
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>在 Lync Server 2013 中为您的 Microsoft Lync 客户端配置端口范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-04-22_

默认情况下, Lync 客户端应用程序可以使用端口1024和65535之间的任何端口参与通信会话;这是因为不会为客户端自动启用特定端口范围。 但是, 为了使用服务质量, 你需要将各种流量类型 (音频、视频、媒体、应用程序共享和文件传输) 重新分配给一系列唯一的端口范围。 可通过使用 CsConferencingConfiguration cmdlet 完成此操作。

<div>


> [!NOTE]  
> 最终用户不能自行进行这些更改。 仅管理员可以使用 CsConferencingConfiguration cmdlet 进行端口更改。



</div>

通过从 Microsoft Lync Server 2013 命令行管理程序中运行以下命令, 可以确定当前用于通信会话的端口范围:

    Get-CsConferencingConfiguration

假设你在安装 Lync Server 2013 后未对会议设置进行任何更改, 你应返回包含这些属性值的信息:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果仔细查看前面的输出, 您将看到两个重要内容。 首先, ClientMediaPortRangeEnabled 属性设置为 False:

    ClientMediaPortRangeEnabled : False

这很重要, 因为当此属性设置为 False 时, 当你参与通信会话时, Lync 客户端将使用端口1024和65535之间的任何可用端口;无论任何其他端口设置 (例如, ClientMediaPort 或 ClientVideoPort), 都是如此。 如果你想要将使用率限制为指定的一组端口 (如果计划实现服务质量, 则需要执行此操作), 然后必须首先启用客户端媒体端口范围。 可以使用以下 Windows PowerShell 命令执行此操作:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

前面的命令为会议配置设置的全局集合启用了客户端媒体端口范围;但是, 这些设置也可以应用于网站范围和/或服务范围 (仅适用于会议服务器服务)。 若要启用特定网站或服务器的客户端媒体端口范围, 请在调用 CsConferencingConfiguration 时指定该网站或服务器的标识:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者, 你可以使用此命令同时为所有会议配置设置启用端口范围:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

你将注意到的第二个重要事项是示例输出显示, 默认情况下, 为每种类型的网络流量设置的媒体端口范围是相同的:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

为了实现 QoS, 这些端口范围中的每一个都必须是唯一的。 例如, 你可以配置如下所示的端口范围:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端流量类型</th>
<th>端口启动</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>名</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>名</p></td>
</tr>
</tbody>
</table>


在上表中, 客户端端口范围表示为服务器配置的端口范围的子集。 例如, 在服务器上, 应用程序共享配置为使用端口40803到 49151;在客户端计算机上, 将应用程序共享配置为使用端口42000到42019。 这样做还主要是为了简化 QoS 的管理: 客户端端口不必表示服务器上使用的端口子集。 (例如, 在客户端计算机上, 你可以配置要使用的应用程序共享, 例如端口10000到10019。)但是, 建议你将客户端端口范围设置为服务器端口范围的子集。

此外, 你可能已注意到已为服务器上的应用程序共享保留了8348端口, 但仅为客户端上的应用程序共享设置了20个端口。 我们也建议这样做, 但这并不是一种既难又快的规则。 通常, 你可以考虑每个可用的端口来表示单个通信会话: 如果端口范围内有100个端口, 这意味着所涉及的计算机可以参与, 在任何给定时间最多可参与100个通信会话。 由于服务器可能会涉及比客户端更多的对话, 因此打开服务器上的更多端口比在客户端上更有意义。 在客户端上为应用程序共享设置20个端口意味着, 用户可以同时在指定设备上参与20个应用程序共享会话。 这应该足以满足大多数用户的需要。

若要将之前的端口范围分配给你的会议配置设置的全局集合, 你可以使用以下 Lync Server Management Shell 命令:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者, 使用此命令为所有会议配置设置分配这些相同的端口范围:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

单个用户必须从 Lync 注销, 然后重新登录才能使这些更改实际生效。

<div>


> [!NOTE]  
> 您还可以启用客户端媒体端口范围, 然后使用一个命令分配这些端口范围。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

