---
title: 'Lync Server 2013: 配置边缘服务器的端口范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为 Edge 服务器配置端口范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-07-24_

有了 Edge 服务器, 您无需为音频、视频和应用程序共享配置单独的端口范围;同样, 用于边缘服务器的端口范围不必与你的会议、应用程序和中介服务器使用的端口范围相匹配。 在继续我们的示例之前, 很重要的一点是, 在此选项存在的情况下, 我们建议您不要更改端口范围, 因为如果移出50000端口范围, 这可能会对某些方案产生负面影响。

例如, 假设您已将您的会议、应用程序和中介服务器配置为使用这些端口范围:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>数据包类型</th>
<th>起始端口</th>
<th>保留的端口数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>音频</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>视频</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>求和</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


正如你所看到的, 音频、视频和应用程序共享的端口范围从端口40803开始, 总共包括24732个端口。 如果你愿意, 可以将给定的边缘服务器配置为使用这些整体端口值, 方法是在 Lync Server Management Shell 中运行类似于此的命令:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者, 使用以下命令同时配置组织中的所有边缘服务器:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

你可以使用此 Lync Server Management Shell 命令验证你的 Edge 服务器的当前端口设置:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同样, 虽然我们提供这些选项, 但我们强烈建议你将其保留为用于端口配置的操作。

</div>

<span> </span>

</div>

</div>

</div>

