---
title: Lync Server 2013：适用于前端服务器、即时消息和状态的拓扑和组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-10-24_

即时消息 (IM) 和状态所需的唯一组件是：

  - 您的组织的前端服务器或标准版服务器。 将始终在这些服务器上启用 IM 和状态功能。

  - 负载平衡器（如果您拥有 Enterprise Edition 前端池）。 有关详细信息, 请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>规划前端池的部署

在 Lync Server 2013 中, 前端池体系结构已更改, 这些更改将影响你应如何计划和维护你的前端池。

我们建议你的所有企业版前端池至少包括三个前端服务器。 在 Lync Server 中, 前端池的体系结构使用分布式系统模型, 每个用户的数据都保存在池中的三个前端服务器上。 有关此新体系结构的详细信息, 请参阅[Lync Server 2013 中的拓扑更改](lync-server-2013-topology-changes.md)。

如果你不想部署三个企业版前端服务器并需要灾难恢复, 我们建议你使用 Lync Server 标准版并创建具有配对备份关系的两个池。 这将提供仅包含两台服务器的灾难恢复解决方案。 有关详细信息, 请参阅高可用性和灾难恢复拓扑和功能, 请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

对于前端池, 请按照本部分中的指南操作。

<div>

## <a name="ensuring-that-pools-are-functional"></a>确保池正常运行

对于前端池的新分布式模型, 必须运行一些池服务器的特定号码才能使池正常工作。 池有两种丢失模式

  - 路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。 路由组是驻留在池中的一组用户的聚合。 每个路由组在池中有三个副本: 一个主副本和两个辅助副本。

  - 池级别仲裁丢失，当池中运行的种子服务器不足时导致的。

<div>

## <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中服务器的总数</th>
<th>使池第一次启动所必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>个</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>db-9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>个</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>db-9</p></td>
</tr>
<tr class="odd">
<td><p>至</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


以后每次启动池时，都应启动 85% 的服务器（如上表所示）。 如果无法启动此数量的服务器（但是可以启动足够数量的服务器来避免遭遇池级别仲裁丢失），那么您可以使用 **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery**  cmdlet 来使池从此路由组级别仲裁丢失中恢复，然后继续操作。 有关如何使用此 cmdlet 的详细信息, 请参阅[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。

<div>


> [!NOTE]  
> 由于 Lync Server 使用主 SQL 数据库作为见证, 因此如果关闭主数据库并切换到镜像副本, 并关闭足够的前端服务器, 以便根据前面的表运行时, 整个池将停止运行。 有关详细信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=393672">数据库镜像见证</A>。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

要使前端池完全正常工作, 它不能处于池级别仲裁损失。 如果运行的服务器数低于功能级别, 如下表所示, 则池中剩余的服务器将停止所有 Lync Server 服务。 请注意, 下表中的数字假定池中的后端服务器正在运行。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端服务器总数</th>
<th>使池发挥作用所必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>任意 2 台</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>任意 3 台</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>任意 4 台</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>前 7 台服务器中的任意 4 台</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>前 9 台服务器中的任意 5 台</p></td>
</tr>
</tbody>
</table>


在上表中，“前几台服务器”是指自首次启动池起按时间顺序靠前显示的服务器。 若要确定这些服务器, 你可以将**CsComputer** cmdlet 与 **-PoolFqdn**选项结合使用。 此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>具有两个前端服务器的前端池

我们不建议部署仅包含两个前端服务器的前端池。 如果您确实需要部署此类池, 请遵循以下指南:

  - 如果这两个前端服务器之一出现故障, 您应尽可能快地尝试让故障服务器恢复正常状态。 同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。

  - 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
      - 最佳做法是同时重新启动这两个前端服务器。
    
      - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
      - 如果不能按该顺序恢复它们, 请在重新启动池之前使用以下 cmdlet:。
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常运行的其他步骤

您应注意其他几项因素，以确保您的前端池仍正常工作。

  - 首次将用户移动到池时, 请确保至少有三个前端服务器正在运行。

  - 如果您在此池和另一个池之间建立了一个配对关系以用于灾难恢复, 那么在建立该关系之后, 必须确保此池在一定时间同时运行三台前端服务器才能正确同步带有备份池的数据。 有关池配对和灾难恢复功能的详细信息, 请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>提高池升级的可靠性

当你需要升级或修补前端池中的服务器时, 请按照[升级或更新 Lync Server 2013 中的前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)中所示的工作流和以下指南操作:

  - 从一个升级域移动到另一个升级域进行升级时 (在[升级或更新 Lync Server 2013 中的前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)时), 你将使用**CsPoolUpgradeReadinessState** Cmdlet 并检查 "准备就绪状态"。 在每个升级域达到 "就绪" 后, 每个升级域之间添加20分钟的等待时间将使升级更加可靠。 如果在此20分钟内**未准备就绪**, 请重新启动20分钟计时器。 此外, 你还可以在启动20分钟间隔之前和之后运行**CsPoolFabricState** cmdlet, 确保不会对路由组的 primaries 和辅助映像进行任何更改。

  - 如果上次修补的升级域中的任何服务器堵塞或未重新启动, 请不要转到下一个升级域。 这也适用于升级中的任何服务器无法启动的情况。 运行**CsPoolFabricState**以确保所有路由组都有一个主要和至少一个辅助数据库;这将确认所有用户是否都拥有服务。

  - 如果某些用户拥有服务, 而其他用户没有服务, 请运行**CsPoolFabricState** , 使用-Verbose 选项检查缺少副本的路由组。 不要作为第一步疑难解答步骤重启整个池。 有关此 cmdlet 的详细信息, 请参阅[CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。

  - 确保已关闭 "事件查看器" 或 "性能监视器" 窗口的所有实例, 以便 windows fabric 安装/卸载。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>更改前端池的配置

每当你将前端服务器添加到池, 或者从池中删除它们, 然后发布新拓扑时, 请遵循以下指南:

  - 发布新拓扑后, 必须重新启动池中的每个前端服务器。 一次重新启动一个。

  - 如果在配置更改期间整个池已停机, 则在发布新拓扑后运行以下 cmdlet:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

如果前端服务器出现故障且不太可能被替换几天或更长时间, 请从拓扑结构中删除服务器。 将新的前端服务器添加到拓扑中 (当它再次可用时)。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

