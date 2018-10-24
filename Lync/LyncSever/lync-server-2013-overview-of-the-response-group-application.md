---
title: Lync Server 2013：响应组应用程序概述
TOCTitle: '响应组应用程序概述 '
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398513(v=OCS.15)
ms:contentKeyID: 49313173
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的响应组应用程序概述

 

_**上一次修改主题：** 2015-03-09_

当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 响应组应用程序使用标准的响应组路由方法，将呼叫路由至下一个可用代理。呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标。当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。

> [!NOTE]  
> 仅本地用户可成为代理。如果一个代理从本地移至联机，则 响应组呼叫将不会被路由到该代理。



> [!NOTE]  
> 响应组应用程序使用一种称为 Match Making 的内部服务对呼叫进行排队并查找可用代理。运行 响应组应用程序的每台计算机都运行 Match Making 服务，但是每个 Lync Server 池一次只能激活一个 Match Making 服务，其他 Match Making 服务均处于非活动状态。如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 响应组应用程序尽力确保呼叫路由和排队不中断。但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。例如，如果由于 前端服务器停机而导致转换，还会丢失该 前端服务器上活动 Match Making 服务正在处理的所有呼叫。



在 Lync Server 2013 中，可通过两个管理角色来管理响应组： 响应组 Manager 和 响应组 Administrator。 响应组 Administrator 可管理任意响应组的各个方面。 响应组 Manager 只能管理其拥有的响应组的特定方面。新的 Manager 角色有助于降低管理成本，因为您可以将特定响应组的有限责任委派给已为其启用 企业语音的任何用户。

为了适应新的 Manager 角色，Lync Server 2013响应组应用程序引入了以下“工作流类型”：“托管”或“非托管”。下表介绍了托管响应组和非托管响应组。

### 托管响应组和非托管响应组

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
<li><p>非托管响应组未分配有 Manager。仅 响应组 Administrator 可配置这些响应组。</p></li>
<li><p>多个非托管响应组可共享一个队列或代理组。</p></li>
<li><p>在将响应组从早期版本迁移到 Lync Server 2013 时，其类型将设置为“非托管”。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>托管</p></td>
<td><ul>
<li><p>响应组 Administrator 可配置托管响应组的任何方面。</p></li>
<li><p>响应组 Manager 无法查看或修改未显式分配给它们的响应组。</p></li>
<li><p>响应组 Manager 只能为显式分配给它们的响应组配置部分设置。</p></li>
<li><p>托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表介绍了 响应组 Manager 可以和不可以对分配给它们的响应组执行的操作。

### 响应组 Manager 功能

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
<li><p>修改核心响应组设置，如：“SIP URI”、“电话号码”或“工作流类型”。</p></li>
</ul></td>
</tr>
</tbody>
</table>


响应组 Manager 可使用以下工具管理其指定的响应组。

  - Lync Server 控制面板
    
    > [!NOTE]  
	> 响应组 Manager 只能通过此工具管理 响应组设置。其他 Lync Server 设置对 Manager 不可用。
    


  - 响应组配置工具

  - Lync Server 命令行管理程序

响应组可适当扩展以适应部门或工作组环境（有关详细信息，请参阅 [Lync Server 2013 中响应组的容量规划](lync-server-2013-capacity-planning-for-response-group.md)），并且可以在全新电话安装中进行部署。它支持来自 企业语音部署和本地运营商网络的传入呼叫。代理可以使用 Lync 2013、 Lync 2010、 Lync 2010 Attendant 或 Lync Phone Edition 将呼叫路由至自己。

响应组应用程序是 企业语音的一个组件。在部署 企业语音时，会自动安装并激活 响应组应用程序。

