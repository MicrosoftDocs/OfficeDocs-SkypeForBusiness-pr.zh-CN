---
title: 配置边缘服务器的端口范围
TOCTitle: 配置边缘服务器的端口范围
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204996(v=OCS.15)
ms:contentKeyID: 49313188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置边缘服务器的端口范围

 

_**上一次修改主题：** 2015-07-24_

借助边缘服务器，您无需为音频、视频和应用程序共享配置单独的端口范围；同样地，用于边缘服务器的端口范围无需与用于会议、应用程序和中介服务器的端口范围相匹配。但是，为了便于管理，您可能需要继续更改您的边缘服务器端口范围以匹配其他服务器上的端口范围。例如，假定您已将会议、应用程序和中介服务器配置为使用这些端口范围：


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


显而易见，您的音频、视频和应用程序共享的端口范围从端口 40803 开始并将包括共 24732 个端口。如果您愿意，可以通过从 Lync Server 命令行管理程序中运行与此命令类似的命令来将一个给定边缘服务器配置为使用这些总体端口值：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，可使用以下命令同时配置您组织中的所有边缘服务器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

可以使用此 Lync Server 命令行管理程序命令来确认您的边缘服务器的当前端口设置：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

