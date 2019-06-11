---
title: Lync Server 2013：Session 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013 中的 Session 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-09-09_

每条记录表示一个包含音频或音频和视频的会话。 它包含有关会话的整体信息。 会话在两个终结点之间定义为音频或视频会话初始协议 (SIP) 对话框。


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
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>会议密钥。 从<a href="lync-server-2013-conference-table.md">Lync Server 2013 中的 "会议" 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>相关密钥。 从<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>对话框类别;0是 Lync 服务器以中介服务器腿;1是中介服务器到 PSTN 网关腿。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示是否已绕过呼叫的标志。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>此字段 (如果存在) 指示无法跳过呼叫的原因, 即使旁路 Id 匹配也是如此。 对于 Lync Server, 只定义一个值。</p>
<p>0x0001-默认网络适配器的旁路 ID 未知。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通话开始时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通话结束时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫方的池。 从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器的池。 从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收终结点的 SIP p 声明标识 (PAI) 中的 SIP URI。 从<a href="lync-server-2013-user-table.md">Lync Server 2013 中的用户表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>调用方的 URI。 从<a href="lync-server-2013-user-table.md">Lync Server 2013 中的用户表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>调用方的终结点。 从<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 的终结点表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>外表</p></td>
<td><p>呼叫方的用户代理。 从<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>此通话的优先级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>此列已弃用, 并且未在 Microsoft Lync Server 2013 中使用。 而是报告每个媒体行基础上的此信息。 有关详细信息, 请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>P-声明-发出呼叫的用户的标识。 P 声明的标识 (PAI) 用于传达发出呼叫的用户的真实标识。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的终结点。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的用户所使用的用户代理。 用户代理代表客户端终结点设备。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的用户的 SIP URI。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

