---
title: Lync Server 2013：适用于前端服务器、即时消息和状态的拓扑和组件
TOCTitle: 适用于前端服务器、即时消息和状态的拓扑和组件
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412996(v=OCS.15)
ms:contentKeyID: 49314690
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件

 

_**上一次修改主题：** 2016-12-08_

即时消息 (IM) 和状态所需的唯一组件是：

  - 组织的前端服务器或 Standard Edition Server。这些服务器中始终启用 IM 和状态功能。

  - 如果您有一个 企业版前端池，则使用负载平衡器。有关详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

## 规划部署前端池

在 Lync Server 2013 中，已更改 前端池体系结构，且这些更改会影响应规划和维护 前端池的方式。

建立您的所有 企业版前端池至少包括三个前端服务器。在 Lync Server 中， 前端池的体系结构会使用分布式系统模型，使每个用户的数据保留在池中的三个前端服务器上。有关此新体系结构的详细信息，请参阅 [Lync Server 2013 中的拓扑更改](lync-server-2013-topology-changes.md)。

如果您不想部署三个 企业版前端服务器，但想获得灾难恢复功能，则建议您使用 Lync Server标准版，并创建两个带有一对备份关系的池。这样可以提供仅使用两台服务器的灾难恢复解决方案。有关高可用性和灾难恢复拓扑和功能的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

## 规划管理前端池

对于前端池，请按照此部分的指南执行操作。

## 确保池正常工作

使用适用于前端池的新分发模型，必须运行池中特定数量的服务器，池才能正常工作。池存在两种丢失模式：

  - 路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。路由组是指驻留在池中的一组用户的聚合。每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。

  - 池级别仲裁丢失，当池中运行的种子服务器不足时导致的。

## 路由组级别仲裁丢失

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
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


以后每次启动池时，都应启动 85% 的服务器（如上表所示）。如果无法启动此数量的服务器（但是可以启动足够数量的服务器来避免遭遇池级别仲裁丢失），那么您可以使用 **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet 来使池从此路由组级别仲裁丢失中恢复，然后继续操作。有关如何使用此 cmdlet 的详细信息，请参阅 [Reset-CsPoolRegistrarState](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsPoolRegistrarState)。

> [!NOTE]  
> 由于 Lync Server 使用主 SQL 数据库作为见证，如果您关闭主 SQL 并切换到镜像副本，同时关闭足够多的前端服务器，结果正在运行的数量不足（根据上表），那么整个池都将关闭。有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/?linkid=393672">数据库镜像见证</a>。


## 池级别仲裁丢失

为使前端池正常工作，它不能遭遇池级别仲裁丢失。如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Lync Server 服务。请注意，下表中的数目假定池中的后端服务器正在运行。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中前端服务器的总数</th>
<th>使池发挥作用所必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3 -4</p></td>
<td><p>任意 2 台</p></td>
</tr>
<tr class="odd">
<td><p>5 -6</p></td>
<td><p>任意 3 台</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>任意 4 台</p></td>
</tr>
<tr class="odd">
<td><p>8 -9</p></td>
<td><p>前 7 台服务器中的任意 4 台</p></td>
</tr>
<tr class="even">
<td><p>10 -12</p></td>
<td><p>前 9 台服务器中的任意 5 台</p></td>
</tr>
</tbody>
</table>


在上表中，“前几台服务器”是指自首次启动池起按时间顺序靠前显示的服务器。要确定这些服务器，您可以配合使用 **Get-CsComputer** cmdlet 和 **–PoolFqdn** 选项。此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。

## 带有两个前端服务器的前端池

建议不要部署仅包含两台前端服务器的前端池。如果您确实需要这样的池，请遵循以下指导原则：

  - 如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。

  - 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
      - 最佳实践是，同时重新启动两台前端服务器。
    
      - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
      - 如果按此顺序无活使其启动，则在启动该池前使用以下 cmdlet：
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

## 确保池正常工作的其他步骤

您应注意其他几项因素，以确保您的前端池仍正常工作。

  - 当第一次将用户移动到池时，确保至少运行三个前端服务器。

  - 如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。有关池对和灾难恢复功能的详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

## 提高池升级的可靠性

当您需要升级或修补前端池中的服务器时，请按照[在 Lync Server 2013 中升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)中所示的工作流和以下指南执行操作：

  - 当您从一个升级域移动到另一个升级域来执行升级时（遵循[在 Lync Server 2013 中升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)上的工作流），您将使用 **Get-CsPoolUpgradeReadinessState** cmdlet 并检查就绪状态。在每个升级域达到“就绪”之后额外等待 20 分钟的时间将使升级更可靠。如果在这 20 分钟内它变为“**未就绪**”，请重新开始 20 分钟计数器。此外，您可以在开始 20 分钟间隔之前和之后运行 **Get-CsPoolFabricState** cmdlet，确保未对路由组的主要副本和辅助副本做任何更改。

  - 如果上次修补的升级域中的任何服务器遇到问题或未重新启动，请不要移动到下一升级域。如果某个升级内的任何服务器无法启动，这同样适用。请运行 **Get-CsPoolFabricState** 以确保所有路由组都具有一个主要副本和至少一个辅助副本；这将确认所有用户是否具有服务。

  - 如果有些用户具有服务，而某些用户没有，请运行 **Get-CsPoolFabricState** 与 –Verbose 选项来检查具有缺少副本的路由组。不要将重新启动整个池作为第一个故障排除步骤。有关此 cmdlet 的详细信息，请参阅 [Get-CsPoolFabricState](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPoolFabricState)。

  - 确保事件查看器或性能监视器窗口的所有实例均已关闭，以便执行 Windows Fabric 安装/卸载。

## 更改前端池的配置

每当将前端服务器添加到池，或从池将其删除，然后发布新拓扑时，请遵循以下指导原则：

  - 发布新拓扑后，必须在池中重新启动每个 前端服务器。一次重新启动一个。

  - 如果在配置更改期间整个池已关闭，则在发布新拓扑后运行下列 cmdlet：
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。

