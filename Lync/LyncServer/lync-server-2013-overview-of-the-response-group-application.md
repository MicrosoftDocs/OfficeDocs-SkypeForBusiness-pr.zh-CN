---
title: Lync Server 2013：响应组应用程序概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63f13442588a84039fee6e1147a9c29e821e14a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013 中的响应组应用程序概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 响应组应用程序使用标准响应组路由方法将呼叫路由到下一个可用的代理。 呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。 如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。 在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。 如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标。 当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。 代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。

<div>


> [!NOTE]  
> 只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。



</div>

<div>


> [!NOTE]  
> 响应组应用程序使用名为 Match 的内部服务对呼叫进行排队并查找可用代理。 每台运行响应组应用程序的计算机都会运行 Match service，但一次只能有一个匹配的每个 Lync Server 池处于活动状态-其他计算机是被动的。 如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 响应组应用程序将尽力确保呼叫路由和排队继续不中断。 但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。 例如，如果由于前端服务器停机而导致转换，则当前正在处理的活动匹配的所有呼叫都将失去该前端服务器上的服务。



</div>

在 Lync Server 2013 中，有两个管理角色可用于管理响应组：响应组管理器和响应组管理员。 响应组管理员可以管理任何响应组的任何方面。 响应组管理员只能管理某些方面，并且只能管理它们所拥有的响应组。 新的管理员角色有助于降低管理成本，因为您可以将特定响应组的有限责任委派给已启用企业语音的任何用户。

为了适应新的经理角色，Lync Server 2013 响应组应用程序引入了托管或非托管的**工作流类型**。 下表介绍了托管响应组和非托管响应组。

### <a name="managed-and-unmanaged-response-groups"></a>托管响应组和非托管响应组

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>响应组类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受</p></td>
<td><ul>
<li><p>非托管响应组未分配有 Manager。 只有响应组管理员可以配置这些响应组。</p></li>
<li><p>多个非托管响应组可共享一个队列或代理组。</p></li>
<li><p>当您将响应组从以前的版本迁移到 Lync Server 2013 时，该类型将设置为 "非托管"。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>托管</p></td>
<td><ul>
<li><p>响应组管理员可以配置托管响应组的任何方面。</p></li>
<li><p>响应组管理者无法查看或修改未显式分配给它们的响应组。</p></li>
<li><p>响应组管理员可以仅为显式分配给它们的响应组配置部分设置。</p></li>
<li><p>托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表介绍了响应组管理器可为分配给它们的响应组执行和不能执行的操作。

### <a name="response-group-manager-capabilities"></a>响应组 Manager 功能

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可以配置：</th>
<th>可以创建、删除或配置：</th>
<th>无法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agent</p></li>
<li><p>欢迎消息</p></li>
<li><p>响应组名称</p></li>
<li><p>说明</p></li>
<li><p>显示号码</p></li>
<li><p>工作时间</p></li>
<li><p>保持音乐</p></li>
<li><p>状态（活动/非活动）</p></li>
<li><p>智能寻线工作流和互动语音响应 (IVR) 工作流</p></li>
</ul></td>
<td><ul>
<li><p>代理组</p></li>
<li><p>队列</p></li>
<li><p>假日集</p></li>
</ul></td>
<td><ul>
<li><p>创建或删除任意类型的工作流</p></li>
<li><p>修改核心响应组设置，如：“SIP URI”<strong></strong>、“电话号码”<strong></strong>或“工作流类型”<strong></strong>。</p></li>
</ul></td>
</tr>
</tbody>
</table>


响应组管理员可以使用以下工具管理其指定的响应组。

  - Lync 服务器控制面板
    
    <div>
    

    > [!NOTE]  
    > 响应组管理员只能使用此工具来管理响应组设置。 其他 Lync Server 设置对管理者不可用。

    
    </div>

  - 响应组配置工具

  - Lync Server 命令行管理程序

响应组可以很好地扩展到部门或工作组环境（有关详细信息，请参阅[Lync Server 2013 中的响应组容量规划](lync-server-2013-capacity-planning-for-response-group.md)），并且可以在全新的电话安装中部署。 它支持来自企业语音部署和本地运营商网络的传入呼叫。 代理可以使用 Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition 将呼叫路由到它们。

响应组应用程序是企业语音的一个组件。 部署企业语音时，会自动安装并激活响应组应用程序。

</div>

<span> </span>

</div>

</div>

</div>

