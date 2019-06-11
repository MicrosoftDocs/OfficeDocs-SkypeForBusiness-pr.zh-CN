---
title: Lync Server 2013：PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 用法记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-23_

规划 PSTN 用法记录的主要任务是列出当前在贵组织中对从 CEO 到临时工、顾问在内的所有员工实施的所有呼叫权限。 此过程还提供了一个重新检查现有呼叫权限并进行修改的机会。 你可以仅为适用于你预期的企业语音用户的呼叫权限创建 PSTN 使用记录, 但更好的长期解决方案可能是为所有呼叫权限创建 PSTN 使用记录, 而不管当前是否有可能适用于启用企业语音的用户组。 如果呼叫权限发生变化或者添加了具有不同呼叫权限的新用户，会创建所需的 PSTN 用法记录。

下表显示了典型的 PSTN 用法表。

### <a name="pstn-usage-records"></a>PSTN 用法记录

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>电话属性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>本地电话</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>长途电话</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>国际电话</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>德里全职员工</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>雷德蒙德全职员工</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>雷德蒙德临时员工</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>苏黎世全职员工</p></td>
</tr>
</tbody>
</table>


PSTN 用法记录本身不执行任何操作。为了使它们正常工作，必须执行下列操作：

  - 将它们与分配给用户的语音策略相关联。

  - 将它们与分配给电话号码的路由相关联。

有关语音策略和路由的详细信息, 请参阅[lync server 2013 中的语音策略](lync-server-2013-voice-policies.md)和[lync server 2013 中的语音路由](lync-server-2013-voice-routes.md)。 有关如何创建和配置它们的详细信息, 请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。

</div>

<span> </span>

</div>

</div>

</div>

