---
title: Lync Server 2013：规划中央站点语音恢复能力
description: Lync Server 2013：规划中央站点语音恢复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567378"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>在 Lync Server 2013 中规划中心站点语音恢复

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-30_

企业在全球拥有多个站点的情况日益普遍。 维护紧急服务、访问技术支持以及在中心站点停止服务时执行关键业务任务的能力对于任何企业语音恢复解决方案来说都至关重要。 当中央站点不可用时，必须满足以下条件：

  - 必须提供语音故障转移。

  - 通常在中心网站上向前端池注册的用户必须能够使用备用前端池进行注册。 可以通过创建多个 DNS SRV 记录来实现此操作，每个记录分别解析为每个中心站点中的控制器池或前端池。 您可以调整 SRV 记录的优先级和权重，以便该中心网站提供服务的用户可以在其他 SRV 记录中获取相应的控制器和前端池。

  - 必须将其他站点的用户发送和接收的呼叫重新路由到 PSTN。

本主题介绍可用于保护中央站点语音恢复能力的安全的推荐解决方案。

<div>

## <a name="architecture-and-topology"></a>体系结构和拓扑

若要在中央站点规划语音弹性，需要对 Lync Server 2013 注册机构在启用语音故障转移时扮演的中心角色有一个基本的了解。 Lync Server 注册器是一种服务器角色，可启用客户端注册和身份验证并提供路由服务。 它与 Standard Edition server、前端服务器、控制器或 Survivable 分支设备上的其他组件驻留在一起。 注册器池由在前端池上运行并驻留在同一站点上的注册机构服务组成。 前端池必须进行负载平衡。 建议使用 DNS 负载平衡，但也支持使用硬件负载平衡。 Lync 客户端通过以下发现机制发现前端池：

1.  DNS SRV 记录

2.  自动发现 Web 服务 (Lync Server 2013 中的新增) 

3.  DHCP 选项 120

Lync 客户端连接到前端池之后，它会被负载平衡器定向到池中的前端服务器之一。 而该前端服务器又会将客户端重定向到池中的首选注册器。

为企业语音启用的每个用户都将分配给特定的注册器池，这将成为该用户的主注册器池。 在给定的站点上，通常成百上千个用户共享一个主注册器池。 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点注册的用户。 对分支站点用户的数量（包括在 Survivable 分支设备中注册的用户），目前没有限制。

为确保中央站点具有发生故障时的语音恢复能力，主注册器池必须有一个单独指定的备份注册器池，该注册器池位于另一个站点。 可以使用拓扑生成器恢复能力设置来配置备份。 假定两个站点之间有一个可恢复的 WAN 链路，其主注册器池不再可用的用户将自动定向到备份注册器池。

以下步骤介绍了客户端发现和注册过程：

1.  客户端通过 DNS SRV 记录发现 Lync Server。 在 Lync Server 2013 中，可以将 DNS SRV 记录配置为将多个 FQDN 返回给 DNS SRV 查询。 例如，如果企业 Contoso 具有三个中央站点（北美、欧洲和亚太），且每个中央站点有一个控制器池，则 DNS SRV 记录可以指向每个位置中的控制器池 FQDN。 只要其中一个位置中的控制器池可用，客户端就可以连接到第一个跃点 Lync Server。
    
    <div>
    

    > [!NOTE]  
    > 使用控制器池是可选的。 可以改为使用前端池。

    
    </div>

2.  控制器池通知 Lync 客户端用户的主注册器池和备份注册器池。

3.  Lync 客户端首先尝试连接到用户的主注册器池。 如果主注册器池可用，则该注册器接受注册。 如果主注册器池不可用，Lync 客户端将尝试连接到备份注册器池。 如果备份注册器池可用且已确定用户的主注册器池不可用（检测出指定故障转移间隔期间检测信号不足），则备份注册器池将接受用户的注册。 在备份注册器检测到主注册器再次可用后，备份注册器池会将故障转移 Lync 客户端重定向到其主池。

下图显示了可确保中央站点恢复能力的推荐拓扑。这两个站点由可恢复的 WAN 链路相连。如果中央站点变得不可用，则已分配给该池的用户会定向到备份站点以进行注册。

**中央站点语音恢复能力的推荐拓扑**

![中央站点语音拓扑的拓扑](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央站点语音拓扑的拓扑")

</div>

<div>

## <a name="requirements-and-recommendations"></a>要求与建议

以下有关实现中央站点语音恢复能力的要求和建议适用于大多数组织：

  - 主注册器池和备份注册器池所在的站点应由可恢复的 WAN 链路相连。

  - 每个中央站点必须包含由一个或多个注册器组成的注册器池。

  - 每个注册器池都必须使用 DNS 负载平衡和/或硬件负载平衡进行负载平衡。 有关规划负载平衡配置的详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

  - 必须使用 Lync Server Management Shell **get-csuser** Cmdlet 或 Lync server 控制面板将每个用户分配给主注册器池。

  - 主注册器池必须具有单个备份注册器池，该注册器池位于不同的中央站点。

  - 必须将主注册器池配置为可故障转移到备份注册器池。 默认情况下，将主注册器设置为每隔 300 秒故障转移到备份注册器池。 您可以使用 Lync Server 2013 拓扑生成器来更改此间隔。

  - 配置故障转移路由，如规划文档中的 "[在 Lync Server 2013 中配置故障转移路由](lync-server-2013-configuring-a-failover-route.md)" 主题中所述。 配置该路由后，指定网关，该网关的站点与在主路由中指定的网关的站点不同。

  - 如果中央站点包含主管理服务器且该站点可能还要再关闭一段时间，则需要在备份站点重新安装管理工具，否则将不能更改任何管理设置。

</div>

<div>

## <a name="dependencies"></a>相关性

Lync Server 取决于以下基础结构和软件组件，以确保语音恢复能力：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>组件</strong></p></td>
<td><p><strong>完善</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>解析有关服务器到服务器和服务器到客户端连接的 SRV 记录和 A 记录</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 和 Exchange Web 服务 (EWS)</p></td>
<td><p>联系人存储；日历数据</p></td>
</tr>
<tr class="even">
<td><p>Exchange 统一消息和 Exchange Web 服务</p></td>
<td><p>呼叫日志、语音邮件列表、语音邮件</p></td>
</tr>
<tr class="odd">
<td><p>DHCP 选项 120</p></td>
<td><p>如果 DNS SRV 不可用，则客户端将尝试使用 DHCP 选项 120 来发现注册器。 为使其正常工作，必须配置 DHCP 服务器或启用 Lync Server 2013 DHCP。 有关详细信息，请参阅 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</a> 一节中 Branch-Site 复原的硬件和软件要求。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Survivable 语音功能

如果上述要求和建议已付诸实行，则备份注册器池将提供以下语音功能：

  - 出站 PSTN 呼叫

  - 入站 PSTN 呼叫，前提是电话服务提供商支持故障转移到备份站点的功能

  - 同一站点的用户间和两个不同站点的用户间的企业呼叫

  - 基本呼叫处理功能（包括呼叫保持、取回和转接）

  - 双方即时消息和在同一站点的用户间共享音频和视频

  - 呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置呼叫委派的双方或所有团队成员。

  - 现有电话和客户端继续工作。

  - 呼叫详细信息记录 (CDR)

  - 身份验证和授权

在主中央站点停用时，以下语音功能可能会工作，也可能不会工作，具体取决于配置方式：

  - 语音邮件处理和检索
    
    如果要使 Exchange UM 在主中央站点停用时可用，必须执行以下操作之一：
    
      - 更改 DNS SRV 记录，使中央站点的 Exchange UM 服务器指向其他站点的备份 Exchange UM 服务器。
    
      - 将每个用户的 Exchange UM 拨号计划配置为同时在中心站点和备份站点上包括 Exchange UM 服务器，但将备份 Exchange UM 服务器指定为已禁用。 如果主站点变得不可用，则 Exchange 管理员必须将备份站点上的 Exchange UM 服务器标记为 "已启用"。
    
    如果上述解决方案均无法使用，则 Exchange UM 将无法在中心站点不可用的情况下使用。

  - 所有类型的会议
    
    故障转移到备份站点的用户，可以加入到由其池可用但不能在自己的主池（不再可用）上创建或承载会议的组织者创建或承载的会议。同样，其他用户也不能加入在受影响的用户的主池上承载的会议。

在主中央站点停用时，以下语音功能不会工作：

  - 会议自动助理

  - 基于状态和 DND 的路由

  - 更新呼叫转接设置

  - 响应组服务和呼叫寄存

  - 设置新的电话和客户端

  - 通讯簿 Web 搜索

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

