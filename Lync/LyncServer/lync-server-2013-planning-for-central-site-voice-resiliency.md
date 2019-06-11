---
title: Lync Server 2013：规划中央站点语音恢复能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>在 Lync Server 2013 中规划中央站点语音恢复能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-30_

企业在全球拥有多个站点的情况日益普遍。 维护紧急服务、访问技术支持以及在中心网站退出服务时执行关键业务任务的功能对于任何企业语音复原解决方案都至关重要。 当中央站点不可用时，必须满足以下条件：

  - 必须提供语音故障转移。

  - 通常在中心网站上使用前端池注册的用户必须能够注册到备用的前端池。 这可以通过创建多个 DNS SRV 记录来实现, 每个 DNS SRV 记录都可以解析为每个中心网站中的控制器池或前端池。 你可以调整 SRV 记录的优先级和权重, 以便该中心网站提供的用户可以在其他 SRV 记录中获得相应的 Director 和前端池。

  - 必须将其他站点的用户发送和接收的呼叫重新路由到 PSTN。

本主题介绍可用于保护中央站点语音恢复能力的安全的推荐解决方案。

<div>

## <a name="architecture-and-topology"></a>体系结构和拓扑

在中心站点规划语音弹性需要基本了解 Lync Server 2013 注册机构在启用语音故障切换时扮演的中心角色。 Lync 服务器注册机构是支持客户端注册和身份验证并提供路由服务的服务器角色。 它与标准版服务器、前端服务器、控制器或 Survivable 分支装置上的其他组件一起存放。 注册机构池由在前端池中运行的注册机构服务以及驻留在同一站点上的注册机构服务组成。 前端池必须进行负载平衡。 建议使用 DNS 负载平衡, 但硬件负载平衡是可接受的。 Lync 客户端通过以下发现机制发现前端池:

1.  DNS SRV 记录

2.  自动发现 Web 服务 (Lync Server 2013 中的新增)

3.  DHCP 选项 120

在 Lync 客户端连接到前端池后, 它由负载平衡器定向到池中的前端服务器之一。 然后, 该前端服务器反过来将客户端重定向到池中的一个首选注册机构。

启用企业语音的每位用户都将分配给特定的注册机构池, 这将成为该用户的主注册机构池。 在给定的站点上，通常成百上千个用户共享一个主注册器池。 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点注册的用户。 分支网站用户数目前没有限制, 包括向 Survivable 分支装置注册的用户。

为确保中央站点具有发生故障时的语音恢复能力，主注册器池必须有一个单独指定的备份注册器池，该注册器池位于另一个站点。 可以使用拓扑生成器复原设置配置备份。 假定两个站点之间有一个可恢复的 WAN 链路，其主注册器池不再可用的用户将自动定向到备份注册器池。

以下步骤介绍了客户端发现和注册过程：

1.  客户端通过 DNS SRV 记录来发现 Lync 服务器。 在 Lync Server 2013 中, 可以将 DNS SRV 记录配置为将多个 FQDN 返回到 DNS SRV 查询。 例如，如果企业 Contoso 具有三个中央站点（北美、欧洲和亚太），且每个中央站点有一个控制器池，则 DNS SRV 记录可以指向每个位置中的控制器池 FQDN。 只要其中一个位置中的控制器池可用, 客户端就可以连接到第一个跃点 Lync 服务器。
    
    <div>
    

    > [!NOTE]  
    > 使用控制器池是可选的。 可以改为使用前端池。

    
    </div>

2.  控制器池通知 Lync 客户端用户的主注册池和备份注册机构池。

3.  Lync 客户端首先尝试连接到用户的主注册池。 如果主注册器池可用，则该注册器接受注册。 如果主注册池不可用, 则 Lync 客户端会尝试连接到备份注册机构池。 如果备份注册器池可用且已确定用户的主注册器池不可用（检测出指定故障转移间隔期间检测信号不足），则备份注册器池将接受用户的注册。 在备份注册机构检测到主注册机构再次可用后, 备份注册机构池会将故障转移 Lync 客户端重定向到其主池。

下图显示了用于确保中心站点弹性的推荐拓扑。 这两个站点通过弹性 WAN 链接连接。 如果中心网站不可用, 则分配到该池的用户将被定向到要注册的备份网站。

**中心网站语音复原的推荐拓扑**

![中心网站语音 Resliency 拓扑](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中心网站语音 Resliency 拓扑")

</div>

<div>

## <a name="requirements-and-recommendations"></a>要求与建议

以下有关实现中央站点语音恢复能力的要求和建议适用于大多数组织：

  - 主注册器池和备份注册器池所在的站点应由可恢复的 WAN 链路相连。

  - 每个中央站点必须包含由一个或多个注册器组成的注册器池。

  - 必须使用 DNS 负载平衡和/或硬件负载平衡使每个注册器池负载平衡。 有关规划负载平衡配置的详细信息, 请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

  - 每个用户都必须使用 Lync Server Management Shell **move-csuser** Cmdlet 或 Lync server 控制面板分配到一个主注册器池。

  - 主注册器池必须具有单个备份注册器池，该注册器池位于不同的中央站点。

  - 必须将主注册器池配置为可故障转移到备份注册器池。 默认情况下，将主注册器设置为每隔 300 秒故障转移到备份注册器池。 你可以使用 Lync Server 2013 拓扑生成器来更改此间隔。

  - 按照规划文档中的 "[在 Lync Server 2013 中配置故障转移路由](lync-server-2013-configuring-a-failover-route.md)" 主题中所述配置故障转移路由。 配置该路由后，指定网关，该网关的站点与在主路由中指定的网关的站点不同。

  - 如果中央站点包含主管理服务器且该站点可能还要再关闭一段时间，则需要在备份站点重新安装管理工具，否则将不能更改任何管理设置。

</div>

<div>

## <a name="dependencies"></a>依赖项

Lync Server 依赖以下基础结构和软件组件来确保语音复原:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>组件</strong></p></td>
<td><p><strong>功能</strong></p></td>
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
<td><p>如果 DNS SRV 不可用，则客户端将尝试使用 DHCP 选项 120 来发现注册器。 为使此操作正常运行, 必须配置 DHCP 服务器或启用 Lync Server 2013 DHCP。 有关详细信息, 请参阅<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013</a>部分的分支站点恢复要求中的分支站点恢复的硬件和软件要求。</p></td>
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
    
      - 将每个用户的 Exchange UM 拨号计划配置为同时在中心站点和备份站点中包括 Exchange UM 服务器, 但将备份 Exchange UM 服务器指定为 "已禁用"。 如果主站点不可用, Exchange 管理员必须将备份站点上的 Exchange UM 服务器标记为 "已启用"。
    
    如果上述解决方案均无法使用, 则 Exchange UM 将在中心网站不可用的事件中不可用。

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


[在 Lync Server 2013 中规划分支站点语音恢复能力](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

