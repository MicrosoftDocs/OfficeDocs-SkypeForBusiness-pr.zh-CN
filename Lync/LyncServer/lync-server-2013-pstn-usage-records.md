---
title: Lync Server 2013： PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60700070c5426d4df4d1957367ccfd743a5ba44b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 用法记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-23_

规划 PSTN 用法记录的主要任务是列出当前在贵组织中对从 CEO 到临时工、顾问在内的所有员工实施的所有呼叫权限。此过程还提供了一个重新检查现有呼叫权限并进行修改的机会。可以只为那些应用于预期企业语音用户的呼叫权限创建 PSTN 用法记录，但是，更好的长期解决方案可能是为所有呼叫权限创建 PSTN 用法记录，而无论其中的某些权限当前是否应用于要为企业语音启用的用户组。如果呼叫权限发生变化或者添加了具有不同呼叫权限的新用户，会创建所需的 PSTN 用法记录。

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>本地电话</p></td>
</tr>
<tr class="even">
<td><p>远距离</p></td>
<td><p>长途电话</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>国际电话</p></td>
</tr>
<tr class="even">
<td><p>德里</p></td>
<td><p>德里全职员工</p></td>
</tr>
<tr class="odd">
<td><p>雷蒙德</p></td>
<td><p>雷德蒙德全职员工</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>雷德蒙德临时员工</p></td>
</tr>
<tr class="odd">
<td><p>苏黎世</p></td>
<td><p>苏黎世全职员工</p></td>
</tr>
</tbody>
</table>


PSTN 用法记录本身不执行任何操作。为了使它们正常工作，必须执行下列操作：

  - 将它们与分配给用户的语音策略相关联。

  - 将它们与分配给电话号码的路由相关联。

有关语音策略和路由的详细信息，请参阅 lync server [2013 中的语音策略](lync-server-2013-voice-policies.md)和[lync server 2013 中的语音路由](lync-server-2013-voice-routes.md)。 有关如何创建和配置这些设置的详细信息，请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。

</div>

<span> </span>

</div>

</div>

</div>

