---
title: Lync Server 2013：为您的会议、应用程序和中介服务器配置端口范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3df859017ca54d32ad56580c842f748114166d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535059"
---
# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置端口范围

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-04-30_

为了实现服务质量，您应在会议、应用程序和中介服务器上为音频、视频和应用程序共享配置相同的端口范围；此外，这些端口范围在任何情况下不得重叠。为了使用简单示例，假定您在会议服务器上将端口 10000 至 10999 用于视频。这意味着，您还必须在应用程序和中介服务器上为视频保留 10000 至 10999 这些端口。如果不这样做，QoS 将不会按预期工作。

同样，假定您为视频保留了端口 10000 至 10999，但之后为音频保留了端口 10500 至 11999。这会产生服务质量问题，因为端口范围重叠。对于 QoS，每种形式必须具有一组唯一的端口：如果您将端口 10000 至 10999 用于视频，则必须使用不同的范围（例如，对音频使用 11000 至 11999）。

默认情况下，Microsoft Lync Server 2013 中的音频和视频端口范围不重叠;但是，分配给应用程序共享的端口范围与音频和视频端口范围重叠。  (这意味着，这些范围都不是唯一的。 ) 您可以通过在 Lync Server 2013 命令行管理程序中运行以下三个命令来验证您的会议、应用程序和中介服务器的现有端口范围：

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 正如您在上面的命令中看到的，每种端口类型（音频、视频和应用程序共享）将分配有两个不同的属性值：起始端口和端口计数。起始端口指示用于相应形式的第一个端口；例如，如果音频起始端口等于 50000，则意味着用于音频通信的第一个端口为端口 50000。如果音频端口计数为 2（这不是一个有效值，但在此处作说明之用），则意味着仅为音频分配了 2 个端口。如果第一个端口为端口 50000 并且总共有两个端口，则意味着第二个端口必须为端口 50001（端口范围必须是连续的）。因此，音频的端口范围将为 50000 到 50001（包括 50000 和 50001）。<BR>注意，应用程序服务器和中介服务器仅支持音频的服务质量；您无需更改应用程序服务器或中介服务器中的视频或应用程序共享端口。



</div>

如果您运行上述三个命令，则会看到 Lync Server 2013 的默认端口值配置如下：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>会议服务器</th>
<th>应用程序服务器</th>
<th>中介服务器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


如前所述，为 QoS 配置 Lync Server 端口时，应确保在您的所有会议、应用程序和中介服务器上的： 1) 音频端口设置相同;2) 端口范围不重叠。 如果仔细查看前面的表，您将看到端口范围在三种服务器类型中相同。 例如，在每个服务器类型上，启动音频端口设置为端口49152，在每个服务器上为音频保留的端口总数也相同：8348。 但是，端口范围重叠：音频端口从端口49152开始，但这些端口设置为应用程序共享。 为了获得最佳使用服务质量，应将应用程序共享重新配置为使用唯一的端口范围。 例如，可以将应用程序共享配置为在端口40803处启动，并使用8348端口。  (为什么要8348端口？ 如果将这些值一起添加--40803 + 8348--这意味着应用程序共享将使用端口40803通过端口49150。 由于音频端口不会开始到端口49152，因此您将不再具有任何重叠的端口范围。 ) 

为应用程序共享选择新的端口范围之后，您可使用 Set-CsConferencingServer cmdlet 进行更改。此更改无需在应用程序服务器或中介服务器上进行，因为这些服务器不会处理应用程序共享流量。如果您决定重新分配用于音频通信的端口，则只需更改这些服务器上的端口值。

若要修改单个会议服务器上的应用程序共享的端口值，请在 Lync Server 命令行管理程序中运行与此类似的命令：

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

如果要在所有会议服务器上进行这些更改，则可改为运行以下命令：

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

更改端口设置之后，您应停止，然后重新启动受更改影响的每个服务。

会议服务器、应用程序服务器和中介服务器不必共享完全相同的端口范围；您唯一必须做的是在所有服务器上留出唯一的端口范围。但是，如果您在所有服务器上使用相同的端口集，则管理一般会更加轻松。

</div>

<span> </span>

</div>

</div>

</div>

