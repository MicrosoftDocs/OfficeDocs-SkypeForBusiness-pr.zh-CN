---
title: 池故障期间的 Lync Server 2013 响应组体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>池故障期间 Lync Server 2013 中的响应组体验

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-30_

本部分详细介绍了如何在以下阶段影响响应组活动：

  - 主池出现中断，但尚未启动故障转移。

  - 服务已故障转移到备份池。

  - 服务故障回复到主池。

<div>

## <a name="user-experience-when-outage-occurs"></a>出现停机时的用户体验

当池或网站发生停机，但管理员尚未启动故障转移时，将按下表中所述处理响应组活动。

<div>


> [!NOTE]  
> 在灾难恢复期间，取决于在恢复期间是否将主池响应组导入到备份池中，调用的行为有所不同。 在下表中，对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。



</div>

### <a name="outage-occurs"></a>发生中断

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫或用户操作的类型</th>
<th>停机期间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>连接到代理的通话</p></td>
<td><ul>
<li><p>定期通话仍保持连接状态。</p></li>
<li><p>匿名通话已断开连接。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未连接到代理的正在进行的通话</p></td>
<td><p>通话断开。</p></td>
</tr>
<tr class="odd">
<td><p>新通话</p></td>
<td><ul>
<li><p>通话断开。</p></li>
<li><p>如果已导入响应组，则呼叫将连接到备份池，但无法访问托管在主池中的代理。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代理代表响应组呼叫</p></td>
<td><p>在此阶段中禁用功能。</p></td>
</tr>
<tr class="odd">
<td><p>代理登录和代理信息</p></td>
<td><ul>
<li><p>主池拥有的代理组可以在代理控制台上查看，但代理无法登录。</p></li>
<li><p>可以在代理控制台上查看备份池所拥有的代理组，并且代理可以登录。</p></li>
<li><p>代理控制台上不显示导入的代理组。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>响应组配置</p></td>
<td><ul>
<li><p>可以查看由主池拥有的响应组，具体取决于主池的后端数据库的可用性，但不能进行修改。</p></li>
<li><p>可以查看和修改备份池拥有的响应组。</p></li>
<li><p>无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server Management Shell cmdlet 进行配置。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>故障转移期间的用户体验

当管理员将故障转移调用到备份池时，将在故障转移期间和之后处理响应组活动，如下表所述。 第一列描述可能发生的活动类型。 中间列描述了如何在短时间内处理每个活动，以故障转移到备份池。 最后一列介绍在故障转移过程完成并且为主池准备了备份池后，在持续时间内活动的处理方式。

<div>


> [!NOTE]  
> 在灾难恢复期间，取决于在恢复期间是否将主池响应组导入到备份池中，调用的行为有所不同。 在下表中，对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。



</div>

### <a name="failover-is-initiated"></a>已启动故障转移

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫或用户操作的类型</th>
<th>故障转移期间</th>
<th>故障转移完成后</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>连接到代理的通话</p></td>
<td><ul>
<li><p>定期通话仍保持连接状态。</p></li>
<li><p>匿名通话已断开连接。</p></li>
</ul></td>
<td><ul>
<li><p>定期通话仍保持连接状态。</p></li>
<li><p>对于导入的响应组，已达到备份池的匿名呼叫仍保持连接。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未连接到代理的正在进行的通话</p></td>
<td><p>通话断开。</p></td>
<td><ul>
<li><p>如果未导入响应组，则没有通话处于此状态。</p></li>
<li><p>对于导入的响应组，已达到备份池的呼叫仍保持连接。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新通话</p></td>
<td><ul>
<li><p>通话断开。</p></li>
<li><p>对于导入的响应组，呼叫将连接到备份池，但无法访问主池中托管的代理。</p></li>
</ul></td>
<td><ul>
<li><p>如果未导入响应组，则通话将断开连接。</p></li>
<li><p>对于导入的响应组，呼叫将连接到备份池。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代理代表响应组呼叫</p></td>
<td><p>在此阶段中禁用功能</p></td>
<td><ul>
<li><p>如果未导入响应组，呼叫将失败。</p></li>
<li><p>对于导入的响应组，通话成功。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>代理登录和代理信息</p></td>
<td><ul>
<li><p>主池拥有的代理组可以在代理控制台上查看，但代理无法登录。</p></li>
<li><p>可以在代理控制台上查看备份池所拥有的代理组，并且代理可以登录。</p></li>
<li><p>已导入的代理组将显示在代理控制台上，并且代理可以登录。</p></li>
</ul></td>
<td><ul>
<li><p>主池拥有的代理组可以在代理控制台上查看，但代理无法登录。</p></li>
<li><p>可以在代理控制台上查看备份池所拥有的代理组，并且代理可以登录。</p></li>
<li><p>已导入的代理组将显示在代理控制台上，并且代理可以登录。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>响应组配置</p></td>
<td><ul>
<li><p>可以查看由主池拥有的响应组，具体取决于主池的后端数据库的可用性，但不能进行修改。</p></li>
<li><p>可以查看和修改备份池拥有的响应组。</p></li>
<li><p>无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server Management Shell cmdlet 进行配置。</p></li>
</ul></td>
<td><ul>
<li><p>可以查看由主池拥有的响应组，具体取决于后端数据库的可用性，但不能进行修改。</p></li>
<li><p>可以查看和修改备份池拥有的响应组。</p></li>
<li><p>无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server Management Shell cmdlet 进行配置。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>故障回复期间的用户体验

当管理员将故障回复调用到主池时，将在故障回复期间和之后处理响应组活动，如下表所述。

<div>


> [!NOTE]  
> 在灾难恢复期间，取决于在恢复期间是否将主池响应组导入到备份池中，调用的行为有所不同。 在下表中，对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。



</div>

### <a name="call-handling-in-failback"></a>故障回复中的呼叫处理

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫或用户操作的类型</th>
<th>在故障回复期间</th>
<th>故障回复完成后</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>连接到代理的通话</p></td>
<td><ul>
<li><p>定期通话仍保持连接状态。</p></li>
<li><p>如果未导入响应组，则没有任何匿名通话处于此状态。</p></li>
<li><p>对于导入的响应组，匿名通话仍保持连接。</p></li>
</ul></td>
<td><ul>
<li><p>定期通话仍保持连接状态。</p></li>
<li><p>如果未导入响应组，则没有任何匿名通话处于此状态。</p></li>
<li><p>对于导入的响应组，匿名通话仍保持连接。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未连接到代理的正在进行的通话</p></td>
<td><ul>
<li><p>如果未导入响应组，则没有通话处于此状态。</p></li>
<li><p>对于导入的响应组，呼叫将断开连接。</p></li>
</ul></td>
<td><ul>
<li><p>如果未导入响应组，则没有通话处于此状态。</p></li>
<li><p>对于导入的响应组，呼叫将断开连接。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新通话</p></td>
<td><p>呼叫连接到主池，但驻留在主池中的代理不可访问。</p></td>
<td><p>呼叫将连接到主池。</p></td>
</tr>
<tr class="even">
<td><p>代理代表响应组呼叫</p></td>
<td><p>在此阶段中禁用功能。</p></td>
<td><p>通话成功。</p></td>
</tr>
<tr class="odd">
<td><p>代理登录和代理信息</p></td>
<td><ul>
<li><p>主池拥有的代理组可以在代理控制台上查看，但代理无法登录。</p></li>
<li><p>可以在代理控制台上查看备份池所拥有的代理组，并且代理可以登录。</p></li>
<li><p>已导入的代理组将显示在代理控制台上，并且代理可以登录。</p></li>
</ul></td>
<td><ul>
<li><p>可以在代理控制台上查看主池拥有的代理组，并且代理可以登录。</p></li>
<li><p>可以在代理控制台上查看备份池所拥有的代理组，并且代理可以登录。</p></li>
<li><p>代理控制台上不显示导入的代理组。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>响应组配置</p></td>
<td><ul>
<li><p>可以查看由主池拥有的响应组，具体取决于主池的后端数据库的可用性，但不能进行修改。</p></li>
<li><p>可以查看和修改备份池拥有的响应组。</p></li>
<li><p>无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server Management Shell cmdlet 进行配置。</p></li>
</ul></td>
<td><ul>
<li><p>可以查看和修改主池拥有的响应组。</p></li>
<li><p>可以查看和修改备份池拥有的响应组。</p></li>
<li><p>无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server Management Shell cmdlet 进行配置。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

