---
title: Lync Server 2013：组间呼叫应答的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512809"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中组呼叫应答的容量规划

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-12_

<div id="sectionSection0" class="section">

下表介绍了可用作容量规划需求基础的组呼叫装货用户模型。

<div>


> [!IMPORTANT]  
> 组呼叫应答基于呼叫寄存应用程序。 请记住，对于灾难恢复容量规划，配对池的每个池应能够在两个池中处理呼叫寄存服务的工作负载，包括组内呼叫应答。



</div>

### <a name="group-call-pickup-user-model"></a>组呼叫应答用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>跃点数</th>
<th>每个前端池 (8 台前端服务器) </th>
<th>每台 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建议的每组用户数</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>建议的组数</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>为组中的呼叫应答启用的每个池的最大用户数</p></td>
<td><p>25,000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>每个池每分钟对每个池启用的组内呼叫的总传入呼叫的最大速率</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>用户每个池每分钟检索组中的呼叫的最大速率</p></td>
<td><p>200</p></td>
<td><p>word</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>对于少于八台前端服务器的前端池，以线性方式计算指标。 例如，如果您的前端池有一个前端服务器，则计算表中显示的值的最大负载为1/8。</P>
> <LI>
> <P>只要您不超过每个池的最大用户数，您就可以按组和组数增加或减少建议的用户数。 例如，您的 Standard Edition server 可以拥有每组25个用户的120组，因为为组内呼叫应答启用的用户数量仍在用户模型中的最大 (，120组数25个用户3000是为用户启用组内呼叫应答) 的用户。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

