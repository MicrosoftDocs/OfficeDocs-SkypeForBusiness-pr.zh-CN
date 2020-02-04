---
title: Lync Server 2013：分配每用户状态策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户状态策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-11_

状态策略是一组影响状态的限制和限制。 下表描述了 Lync Server 2013 中可用的状态策略设置。

### <a name="presence-policy-settings"></a>状态策略设置

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>XML 名称</th>
<th>显示名称</th>
<th>说明</th>
<th>类型</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>订阅者类别订阅的最大数量</p></td>
<td><p>限制订阅者类别订阅数。 例如，当 Communicator 订阅用户的状态时，它将为每个联系人卡片、日历数据、便笺、服务和状态类别获取类别订阅。</p>
<p>设置为0表示用户或联系人对象不能由其他人订阅。</p>
<div>

> [!NOTE]  
> 如果设置为较高的数字，此设置可能会对性能产生重大影响，并且平均用户有大量用户订阅其状态。


</div></td>
<td><p>整型</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>排队状态订阅警报的最大数量</p></td>
<td><p>限制 "提示订阅者" 表中的条目数。 此设置确定可为给定用户排队的最大提示数。 例如，当用户 A 订阅用户 B 的状态时，用户 B 会收到一条提示，指示用户 A 现在已订阅用户 B，并且在用户 B 的 "提示订阅者" 表中创建了确认提示。 在用户 B 接受或确认订阅后，将从用户 B 的 "提示订阅者" 表中删除确认提示。</p>
<p>设置为0意味着当有人订阅他或她的状态时，不会提示用户。</p></td>
<td><p>整型或标记</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


默认情况下，当你部署 Lync Server 时，**默认策略**和**服务： "中等**状态" 策略已安装。 下表介绍了这两种状态策略的特定设置。

### <a name="presence-policies"></a>状态策略

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>策略名称</th>
<th>说明</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认策略</p></td>
<td><p>适用于典型用户的策略。 这是默认的状态策略。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>服务：中等</p></td>
<td><p>需要更多用户才能订阅对象状态的应用程序的策略。</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

