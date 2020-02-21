---
title: Lync Server 2013： Session 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f927957f21c67a8cfca6b169b99f7de9275740fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013 中的会话表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-09_

每个记录代表一个涉及音频或音频和视频的会话。 它包含有关会话的总体信息。 会话定义为两个终结点之间的音频或视频会话初始协议（SIP）对话框。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>会议密钥。 从<a href="lync-server-2013-conference-table.md">Lync Server 2013 中的会议表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>相关密钥。 <a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>指示是否绕过呼叫的标志。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。 对于 Lync Server，只定义一个值。</p>
<p>0x0001 –默认网络适配器的绕过旁路 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>呼叫开始时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>呼叫结束时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>呼叫者的池。 从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>呼叫接收器的池。 从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>接收终结点的 SIP p 声明标识（PAI）中的 SIP URI。 <a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>呼叫者的 URI。 <a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>调用方的终结点。 从<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>位</p></td>
<td><p>对外</p></td>
<td><p>呼叫者的用户代理。 <a href="lync-server-2013-useragent-table.md">在 Lync Server 2013 中从 UserAgent 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>此调用的优先级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>此列已弃用，并且在 Microsoft Lync Server 2013 中未使用。 而是在每个媒体的行基上报告此信息。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>P-声明-发出呼叫的用户的标识。 P 声明标识（PAI）用于传达发出呼叫的用户的真实标识。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>接收呼叫的终结点。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>接收呼叫的用户使用的用户代理。 用户代理代表客户端终结点设备。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>接收呼叫的用户的 SIP URI。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

