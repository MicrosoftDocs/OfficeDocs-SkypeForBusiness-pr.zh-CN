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
ms.openlocfilehash: c169c6995ca49cc89742bd026b18dc254430cb9d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户状态策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-11_

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
<th>显示名</th>
<th>说明</th>
<th>类型</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>订阅者类别订阅的最大数量</p></td>
<td><p>限制订阅者类别订阅的数量。 例如，当 Communicator 订阅用户的状态时，它会获取每个联系人卡片、日历数据、便笺、服务和状态类别的类别订阅。</p>
<p>设置为0表示用户或联系人对象不能由其他人订阅。</p>
<div>

> [!NOTE]  
> 如果将此设置设置为较高的数值，则此设置可能会对性能产生重大影响，并且一般用户有大量订阅他或她的状态的用户。


</div></td>
<td><p>整数</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>排队状态订阅警报的最大数量</p></td>
<td><p>限制 "提示订阅者" 表中的条目数。 此设置确定可为给定用户排队的最大提示数。 例如，当用户 A 订阅用户 B 的状态时，用户 B 会收到一条提示，指明用户 A 现在已订阅用户 B，并在用户 B 的 "提示订阅者" 表中创建确认提示。 在用户 B 接受（或确认）订阅后，将从用户 B 的 "提示订阅者" 表中删除确认提示。</p>
<p>设置为0表示当有人订阅他或她的状态时不会提示用户。</p></td>
<td><p>Integer 或 Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


默认情况下，在您部署 Lync Server 时，会安装 "**默认策略**和**服务：中等**状态策略"。 下表介绍了这两种状态策略的特定设置。

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
<td><p>典型用户的策略。 这是默认的状态策略。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>服务：中型</p></td>
<td><p>需要更多用户订阅对象状态的应用程序的策略。</p></td>
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

