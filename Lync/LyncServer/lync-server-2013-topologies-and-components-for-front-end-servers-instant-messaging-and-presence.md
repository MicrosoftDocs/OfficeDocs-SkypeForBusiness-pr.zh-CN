---
title: Lync Server 2013：前端服务器、即时消息和状态的拓扑和组件
description: Lync Server 2013：前端服务器、即时消息和状态的拓扑和组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550288"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-10-24_

即时消息 (IM) 和状态所需的唯一组件是：

  - 组织的前端服务器或 Standard Edition Server。这些服务器中始终启用 IM 和状态功能。

  - 负载平衡器（如果有一个 Enterprise Edition 前端池）。 有关详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>规划部署前端池

在 Lync Server 2013 中，前端池体系结构已更改，这些更改将影响您应如何规划和维护前端池。

我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器。 在 Lync Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据都保存在池中的三台前端服务器上。 有关此新体系结构的详细信息，请参阅 [Lync Server 2013 中的拓扑更改](lync-server-2013-topology-changes.md)。

如果您不想部署三个 Enterprise Edition 前端服务器并希望进行灾难恢复，我们建议使用 Lync Server Standard Edition 并创建具有配对备份关系的两个池。 这将提供仅包含两台服务器的灾难恢复解决方案。 有关详细信息，请参阅高可用性和灾难恢复拓扑和功能，请参阅在 [Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>规划管理前端池

对于前端池，请遵循本节中的指南。

<div>

## <a name="ensuring-that-pools-are-functional"></a>确保池正常运行

使用新的分布式模型进行前端池时，池服务器的某些号码必须运行，池才能正常工作。 池有两个丢失模式

  - 路由组级别仲裁丢失，因特定路由组的副本服务器不足而导致。 路由组是驻留在池中的一组用户的聚合。 每个路由组在池中都有三个副本：一个主副本和两个辅助副本。

  - 池级别仲裁丢失，在池中没有足够的种子服务器运行时导致。

<div>

## <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

首次启动新的前端池时，有85% 的服务器已启动并且正在运行，这一点非常重要，如下表所示。 如果运行较少的服务器，服务可能会处于 "启动" 状态，并且池可能无法启动。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的服务器总数</th>
<th>在首次启动池时必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双面</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>第三章</p></td>
<td><p>第三章</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>第三章</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10  </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11x17</p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10  </p></td>
</tr>
</tbody>
</table>


每次启动池时，应启动85% 的服务器 (，如上表中所示) 。 如果无法启动此数量的服务器 (但可以启动足够的服务器以使您不会处于池级别的仲裁丢失) ，则可以使用 **ResetType QuorumLossRecovery** cmdlet 使池能够从此路由组级别仲裁丢失恢复并进行操作。 有关如何使用此 cmdlet 的详细信息，请参阅 [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。

<div>


> [!NOTE]  
> 由于 Lync Server 使用主 SQL 数据库作为见证，如果关闭主数据库并切换到镜像副本，并且关闭了足够的前端服务器，以便根据前面的表运行，则整个池将会停止运行。 有关详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/?linkid=393672">数据库镜像见证</A>。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

为了让前端池能够正常运行，它不能处于池级别仲裁丢失。 如果运行的服务器数低于功能级别，如下表所示，池中的其余服务器将停止所有 Lync Server 服务。 请注意，下表中的数字假定池中的后端服务器正在运行。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端服务器总数</th>
<th>要使池正常工作所必须运行的服务器的数目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双面</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>任意2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>任意3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>任意4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>前7台服务器中的任意4个</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>前9个服务器中的任何5个</p></td>
</tr>
</tbody>
</table>


在上表中，"第一台服务器" 是第一次启动池时的服务器。 若要确定这些服务器，可以结合使用 **CsComputer** cmdlet 和 **– PoolFqdn** 选项。 此 cmdlet 将按其在拓扑中出现的顺序显示服务器，列表顶部的服务器是第一台服务器。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>带有两个前端服务器的前端池

建议不要部署仅包含两台前端服务器的前端池。如果您确实需要这样的池，请遵循以下指导原则：

  - 如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。

  - 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
      - 最佳做法是同时重新启动这两个前端服务器。
    
      - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
      - 如果按此顺序无活使其启动，则在启动该池前使用以下 cmdlet：
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常运行的其他步骤

您应观看几个其他因素，以确保前端池保持正常运行。

  - 当第一次将用户移动到池时，确保至少运行三个前端服务器。

  - 如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。 有关池配对和灾难恢复功能的详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>改进池升级的可靠性

当您需要升级或修补前端池中的服务器时，请遵循在 [Lync Server 2013 中的升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)中显示的工作流和以下指南：

  - 当您从一个升级域迁移到另一个升级域进行升级时 (在 [升级或更新前端服务器的 Lync Server 2013) 中](lync-server-2013-upgrade-or-update-front-end-servers.md) ，请使用 **CsPoolUpgradeReadinessState** Cmdlet 并检查 "就绪" 状态。 在每个升级域达到 "就绪" 时，在每个升级域之间添加20分钟等待可提高升级的可靠性。 如果在此20分钟内 **未准备就绪** ，请重新启动20分钟计时器。 此外，还可以在启动20分钟间隔之前和之后运行 **CsPoolFabricState** cmdlet，并确保不会对路由组的 primaries 和辅助映像进行任何更改。

  - 如果上一次修补的升级域中的任何服务器被卡住或没有重新启动，请不要移动到下一个升级域。 如果升级中的任何服务器无法启动，也会应用此规则。 运行 **CsPoolFabricState** 以确保所有路由组都有主和至少一个辅助数据库;这将确认是否所有用户都有服务。

  - 如果某些用户具有服务，而其他用户没有，请运行 **CsPoolFabricState** 和– Verbose 选项，以检查包含丢失副本的路由组。 请勿将整个池重新启动为第一个故障排除步骤。 有关此 cmdlet 的详细信息，请参阅 [CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。

  - 确保已关闭事件查看器或性能监视器窗口的所有实例，以供 windows fabric 安装/卸载。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>更改前端池的配置

每当将前端服务器添加到池，或从池将其删除，然后发布新拓扑时，请遵循以下指导原则：

  - 发布新拓扑后，必须重新启动池中的每台前端服务器。 一次重新启动一个。

  - 如果在配置更改期间整个池已关闭，则在发布新拓扑后运行下列 cmdlet：
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

