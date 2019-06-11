---
title: 'Lync Server 2013: 响应组应用程序概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013 中的 "响应" 组应用程序概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-11_

当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 "响应组" 应用程序使用标准响应组路由方法将呼叫路由到下一个可用的代理。 呼叫路由方法包括串行、最长空闲、并行、循环和助理路由 (即, 所有代理都将同时针对每个传入呼叫进行调用, 无论其当前状态如何)。 如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。 在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。 如果队列已满, 或者呼叫在队列中超时, 呼叫方可能会听到一条消息, 然后断开连接或将其转移到其他目标。 当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。 代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。

<div>


> [!NOTE]  
> 仅本地用户可成为代理。 如果代理从本地移动到联机, 则响应组调用将不会路由到该代理。



</div>

<div>


> [!NOTE]  
> 响应组应用程序使用名为 "匹配" 的内部服务对呼叫进行排队和查找可用的代理。 运行响应组应用程序的每台计算机都运行 "匹配" 服务, 但每个 Lync 服务器池仅有一个匹配的服务同时处于活动状态。 如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 响应组应用程序最适合确保呼叫路由和队列继续不间断。 但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。 例如, 如果由于前端服务器出现故障而导致的转换, 则当前由活动的匹配进行的任何通话将在该前端服务器上提供服务也将丢失。



</div>

在 Lync Server 2013 中, 有两个管理角色可用于管理响应组: 响应组管理器和响应组管理员。 响应组管理员可以管理任何响应组的任何方面。 响应组管理器只能管理某些方面, 并且仅可管理其拥有的响应组。 新的经理角色有助于减少管理费用, 因为您可以将有限的特定响应组的责任委派给任何已启用企业语音的用户。

为了适应新的经理角色, Lync Server 2013 响应组应用程序引入了托管或非托管的**工作流类型**。 下表介绍了托管响应组和非托管响应组。

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
<td><p>非托管</p></td>
<td><ul>
<li><p>非托管响应组未分配有 Manager。 只有响应组管理员可以配置这些响应组。</p></li>
<li><p>多个非托管响应组可共享一个队列或代理组。</p></li>
<li><p>将响应组从以前的版本迁移到 Lync Server 2013 时, 该类型将设置为 "未管理"。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>托管</p></td>
<td><ul>
<li><p>响应组管理员可以配置托管响应组的任何方面。</p></li>
<li><p>响应组管理器无法查看或修改未明确分配给它们的响应组。</p></li>
<li><p>响应组管理器只能为显式分配给它们的响应组配置某些设置。</p></li>
<li><p>托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表介绍了对于分配给他们的响应组, 响应组管理器可以执行和不能执行的操作。

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
<th>无法：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>代理</p></li>
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
<li><p>修改核心响应组设置，如：“<strong>SIP URI</strong>”、“<strong>电话号码</strong>”或“<strong>工作流类型</strong>”。</p></li>
</ul></td>
</tr>
</tbody>
</table>


响应组管理员可以使用以下工具管理其指定的响应组。

  - Lync Server 控制面板
    
    <div>
    

    > [!NOTE]  
    > 响应组管理器仅可通过此工具管理响应组设置。 其他 Lync Server 设置对经理不可用。

    
    </div>

  - 响应组配置工具

  - Lync Server 命令行管理程序

响应组很好地扩展到部门或工作组环境 (有关详细信息, 请参阅[Lync Server 2013 中的 "响应" 组的容量规划](lync-server-2013-capacity-planning-for-response-group.md)), 并且可以在全新的电话安装中部署。 它支持来自企业语音部署和本地运营商网络的传入呼叫。 代理可以使用 Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition 将呼叫路由到它们。

"响应组" 应用程序是企业语音的一个组件。 部署企业语音时, 将自动安装并激活 "响应组" 应用程序。

</div>

<span> </span>

</div>

</div>

</div>

