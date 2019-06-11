---
title: 'Lync Server 2013: 为你的会议、应用程序和中介服务器配置端口范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>为你的会议、应用程序和中介服务器在 Lync Server 2013 中配置端口范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-04-30_

为了实现服务质量, 你应该为你的会议、应用程序和中介服务器上的音频、视频和应用程序共享配置相同的端口范围;此外, 这些端口范围不得以任何方式重叠。 若要使用一个简单的示例, 请假设你在你的会议服务器上使用端口10000到10999获取视频。 这意味着你还必须为应用程序和中介服务器上的视频保留端口10000到10999。 如果不这样做, QoS 将不会按预期工作。

同样, 假设您为视频保留了端口10000到 10999, 但随后为音频保留了端口10500至11999。 这可能会导致服务质量出现问题, 因为端口范围重叠。 使用 QoS, 每个模态必须具有一组独特的端口: 如果将端口10000到10999用于视频, 则必须使用不同的范围 (例如, 11000 到11999的音频)。

默认情况下, 在 Microsoft Lync Server 2013 中, 音频和视频端口范围不重叠;但是, 分配给应用程序共享的端口范围与音频和视频端口范围重叠。 (反过来, 这意味着这些范围都不是唯一的。)你可以通过从 Lync Server 2013 管理外壳程序中运行以下三个命令来验证你的会议、应用程序和中介服务器的现有端口范围:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 正如您在前面的命令中所看到的, 每个端口类型 (音频、视频和应用程序共享) 都分配有两个单独的属性值: 端口开始和端口计数。 端口启动指示用于该模态的第一个端口;例如, 如果音频端口开始等于 50000, 则表示音频流量使用的第一个端口是端口50000。 如果音频端口计数为 2 (这是一个无效值, 但在此处用于说明用途), 则意味着只有两个端口分配了音频。 如果第一个端口是端口 50000, 并且总共有两个端口, 则意味着第二个端口必须是端口 50001 (端口范围必须保持连续)。 因此, 音频的端口范围将是端口50000到 50001 (包括端口到)。<BR>请注意, 应用服务器和中介服务器仅支持音频的 QoS;无需在应用程序服务器或中介服务器中更改视频或应用程序共享端口。



</div>

如果你运行上述三个命令, 你将看到 Lync Server 2013 的默认端口值配置如下:


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


如前所述, 为 QoS 配置 Lync 服务器端口时, 应确保: 1) 音频端口设置在你的所有会议、应用程序和中介服务器上都相同;和 2) 端口范围不重叠。 如果仔细查看上表, 您将看到端口范围在三种服务器类型中相同。 例如, 每个服务器类型上的起始音频端口设置为端口 49152, 并且每台服务器中为音频保留的端口总数也相同: 8348。 但是, 端口范围重叠: 音频端口从端口49152开始, 但将为应用程序共享预留端口。 为了获得最佳使用服务质量, 应将应用程序共享重新配置为使用唯一的端口范围。 例如, 你可以将应用程序共享配置为从端口40803开始, 并使用8348端口。 (为什么是8348端口？ 如果将这些值一起添加-40803 + 8348-这意味着应用程序共享将通过端口49150使用端口40803。 由于音频端口不会在端口49152开始, 因此你将不再有任何重叠的端口范围。)

为应用程序共享选择新的端口范围后, 您可以使用 CsConferencingServer cmdlet 进行更改。 无需在应用程序服务器或中介服务器上进行此更改, 因为这些服务器不处理应用程序共享流量。 如果你决定重新分配用于音频流量的端口, 则只需在这些服务器上更改端口值。

若要修改单个会议服务器上的应用程序共享的端口值, 请在 Lync Server Management Shell 中运行类似下面的命令:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

如果要在所有的会议服务器上进行这些更改, 可以改为运行此命令:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

更改端口设置后, 你应该停止并重新启动受更改影响的每个服务。

不强制您的会议服务器、应用程序服务器和中介服务器共享完全相同的端口范围;唯一的真正要求是, 您可以在所有服务器上留出唯一的端口范围。 但是, 如果你在所有服务器上使用相同的端口集, 管理通常会更容易。

</div>

<span> </span>

</div>

</div>

</div>

