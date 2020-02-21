---
title: Lync Server 2013：为 Microsoft Lync 客户端配置端口范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfe8c9848e5e015a22bcc7975c6bbdaf1c7465e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>在 Lync Server 2013 中为 Microsoft Lync 客户端配置端口范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-22_

默认情况下，Lync 客户端应用程序可以在通信会话中参与时使用端口1024和65535之间的任何端口;这是因为不会为客户端自动启用特定端口范围。 但是，若要使用服务质量，您将需要为一系列特定端口范围重新分配各种通信类型（音频、视频、媒体、应用程序共享和文件传输）。 可使用 Set-CsConferencingConfiguration cmdlet 完成此操作。

<div>


> [!NOTE]  
> 最终用户不能自行进行这些更改。 仅使用 CsConferencingConfiguration cmdlet 的管理员才能进行端口更改。



</div>

您可以通过在 Microsoft Lync Server 2013 命令行管理程序中运行以下命令，来确定当前用于通信会话的端口范围：

    Get-CsConferencingConfiguration

假定您在安装 Lync Server 2013 后未对会议设置进行任何更改，则应返回包含这些属性值的信息：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果您仔细查看上面的输出，您会发现两点很重要。 首先，ClientMediaPortRangeEnabled 属性设置为 False：

    ClientMediaPortRangeEnabled : False

这一点很重要，因为当此属性设置为 False 时，Lync 客户端将在通信会话中涉及时使用端口1024和65535之间的任何可用端口;无论任何其他端口设置（例如，ClientMediaPort 或 ClientVideoPort），都是如此。 如果要限制对一组指定端口的使用（如果您计划实施服务质量，则需要这样做），则必须首先启用客户端媒体端口范围。 可以使用以下 Windows PowerShell 命令来执行此操作：

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

若要将之前的端口范围分配给全局会议配置设置集合，可以使用以下 Lync Server 命令行管理程序命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者，使用此命令为您的所有会议配置设置分配这些相同的端口范围：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

单个用户必须从 Lync 注销，然后重新登录才能使这些更改实际生效。

<div>


> [!NOTE]  
> 您还可以启用客户端媒体端口范围，然后使用单个命令分配这些端口范围。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

