---
title: Lync Server 2013：会话视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Lync Server 2013 中的会话视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

会话视图存储有关在数据库中具有记录的会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>引用自 MediaLine 表。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</p></td>
</tr>
<tr class="odd">
<td><p>相关性</p></td>
<td><p>varchar （max）</p></td>
<td><p>会话的关联 ID。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>位</p></td>
<td><p>对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>位</p></td>
<td><p>指示是否旁路了呼叫。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。 对于 Lync Server，仅定义了一个值：</p>
<p>0x0001 – 默认网络适配器的未知旁路 ID</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>呼叫开始时间。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>呼叫结束时间。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>被叫方池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>呼叫者的 p 已断言标识 URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>被叫方的 p 已断言标识 URI。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者的终结点名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者的终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者的用户代理字符串。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼叫者的用户代理类型。 有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>呼叫者的用户代理的类别。 有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>被叫方的用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的用户代理的类型。 有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>被叫方的用户代理类别。 有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>呼叫者的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>被叫方的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>呼叫的优先级。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

