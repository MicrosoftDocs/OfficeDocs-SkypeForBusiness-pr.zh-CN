---
title: Lync Server 2013：为边缘服务器配置端口范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b526611e2e29f1b8d11e731381898a7db5e71aa8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为边缘服务器配置端口范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-07-24_

借助边缘服务器，您无需为音频、视频和应用程序共享配置单独的端口范围；同样地，用于边缘服务器的端口范围无需与用于会议、应用程序和中介服务器的端口范围相匹配。 在继续使用我们的示例之前，请务必强调此选项存在时，我们建议您不要更改端口范围，因为如果移出50000端口范围，这可能会对某些方案产生不利影响。

例如，假定您已将会议、应用程序和中介服务器配置为使用这些端口范围：


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
<th>预留的端口数</th>
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
<td><p><strong>总计</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


正如您所看到的，音频、视频和应用程序共享的端口范围从端口40803开始，总共包括24732个端口。 如果您愿意，可以通过从 Lync Server 命令行管理程序中运行与此命令类似的命令，来将一个给定边缘服务器配置为使用这些端口值：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，可使用以下命令同时配置您组织中的所有边缘服务器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

您可以使用此 Lync Server 命令行管理程序命令验证边缘服务器的当前端口设置：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同样，虽然我们提供了这些选项，但强烈建议您保留它们的端口配置。

</div>

<span> </span>

</div>

</div>

</div>

