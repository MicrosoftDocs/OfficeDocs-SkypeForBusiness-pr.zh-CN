---
title: '功能概述 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 规划工具
ms.openlocfilehash: f317b2963e6db83e733a3f0b259a6d0bfe466c9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819822"
---
# <a name="feature-overview-planning-tool"></a>功能概述 (规划工具) 
 
Skype for Business Server 规划工具
  
可以使用规划工具 **的** "中央站点"页设计 Skype for Business Server 部署。 可以创建两个集中部署或分布式部署。 集中式部署只有一个中央站点，该中央站点用于组织的所有 Skype for Business 用户。 分布式部署具有多个中央站点。 如果在多个中央站点部署 Skype for Business Server，你将在规划工具中输入每个中央站点的用户数。
  
若要完成中央网站的定义，首先需要提供以下信息：
  
- **网站名称** 输入中央站点的名称。
    
- **用户数** 输入用户数，包括分支站点中位于中央站点的用户。
    
- **云托管用户** 输入从 Skype for Business Online 中位于中央站点的用户数。
    
## <a name="ui-elements"></a>UI 元素

其余元素已填充为"入门"向导中提供的问题答案，或者，如果跳过了向导，则由规划工具自动填充。
  
### <a name="online-collaboration"></a>联机协作

 **联机协作** 包含以下选项：
  
- **IM 和状态**
    
    即时消息 (IM) 使用户可以使用基于文本的消息在计算机中实时相互通信。 支持双方和多方之间的 IM 会话。 状态会向用户提供有关网络上其他人的状态的信息。 用户的状态信息可帮助其他人确定用户是否联机以及如何最好地与用户联系。 例如，最好通过电子邮件联系参加会议的用户。
    
- **音频和视频会议**
    
    音频/ (A/V) 会议支持实时音频和视频会议。
    
- **电话拨入式会议**
    
    电话拨入式会议使用户能够从 PSTN 上的电话加入 A/V。 电话拨入式会议要求您部署会议助理和会议通知服务应用程序。
    
- **Web 会议**
    
    Web 会议使防火墙内外的企业用户能够创建和加入内部服务器上承载实时会议。
    
- **持久聊天**
    
    持久聊天使多个用户可以参与对话，他们可在其中发布和访问有关特定主题的内容，包括文本、链接和文件。 尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。

    > [!NOTE] 
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Skype for Business 到 Microsoft Teams 的升级](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。
    
### <a name="users"></a>用户

 **用户** 包含以下选项：
  
- **内部组织**
    
- **与其他组织的联盟**
    
- **与以前版本的联盟**
    
- **与公共 IM 服务提供商联盟** 允许贵组织的用户与 MSN、Yahoo！和 AOL 等公共即时消息服务提供商建立通信。 与公共即时消息网络建立联盟需要单独的许可证。
    
- **与基于 XMPP 的服务提供商的联盟**
    
    Skype for Business Server 2015 引入了完全集成的 XMPP 代理 (部署在边缘服务器) 和部署在前端服务器的 XMPP 网关上。 你可以部署添加和配置 XMPP 代理，XMPP 网关将允许你的 Skype for Business Server 用户添加来自基于 XMPP 的合作伙伴的联系人，以便即时消息 (IM) 和状态。
    
- **移动性**
    
    部署 Skype for Business Server Mobility Service 时，用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备执行发送和接收即时消息、查看联系人和查看状态等活动。
    
- **W15 Exchange 邮箱**
    
    Skype for Business Server 使您可以将语音邮件存储在 Exchange 统一消息 (UM) ;这些语音邮件随后将在用户的收件箱中显示为电子邮件。

    > [!NOTE]
    > Exchange 2019 中不再提供以前已知的 Exchange 统一消息，但您仍可以使用电话系统录制语音邮件消息，然后将记录留在用户的 Exchange 邮箱中。 有关详细信息 [，请参阅"](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 规划云语音邮件服务"。
    
### <a name="voice"></a>语音

 **语音** 包含以下选项：
  
- **企业语音**
    
    企业语音是 Microsft 的软件支持 VoIP 解决方案。 企业语音允许用户使用 Skype for Business 从计算机发出电话呼叫。
    
- **Exchange 统一消息**
    
    Exchange 统一 (UM) 将语音邮件和电子邮件合并到单个邮件基础结构中。 Skype for Business Server 2015 使用 Exchange UM 提供呼叫应答、订阅者访问、呼叫通知和自动助理服务。 如果使用这些服务，则需要在共享的 Active Directory 拓扑中集成 Exchange UM 和 Skype for Business Server。

    > [!NOTE]
    > Exchange 2019 中不再提供以前已知的 Exchange 统一消息，但您仍可以使用电话系统录制语音邮件消息，然后将记录留在用户的 Exchange 邮箱中。 有关详细信息 [，请参阅"](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 规划云语音邮件服务"。
    
### <a name="additional-deployment-options"></a>其他部署选项

 **其他部署选项** 包含以下选项：
  
- **高可用性**
    
    高可用性使备用服务器能够支持故障转移。
    
- **灾难恢复**
    
    灾难恢复措施使您能够对位于两个数据中心的前端池进行配对。
    
- **监视**
    
    监控捕获与通信会话相关的呼叫详细信息记录。 它还从参与者终结点的音频和视频会话收集指标。 监控服务器提供使用情况统计信息、趋势和媒体质量统计信息。
    
- **存档**
    
    存档存储即时消息对话和会议。
    
- **Exchange 存档集成**
    
    如果你的用户位于 Exchange 上并且其邮箱已置于In-Place保留状态，可以选择将 Skype for Business Server 存储与 Exchange 存储集成。
    
- **IPv4**
    
    IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。 由于全球设备数量不断增加，可用 IPv4 地址已用完。因此，许多新设备都迁移到使用 IPv6 地址。
    
- **IPv6**
    
    IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。 这不仅提供了一组新的地址，而且数量远远超过原来的地址集。
    
- **设备更新 Web 服务**
    
    设备更新 Web 服务提供了一种自动更新在组织外部部署的所有设备（如 Skype for Business for Windows Phone）的方法。
    
### <a name="server-applications"></a>服务器应用程序

 **服务器应用程序** 包含以下选项：
  
- **响应组**
    
    响应组应用程序会自动应答呼叫并将呼叫分发给可用的支持人员代理。
    
- **公告**
    
    如果计划部署企业语音，可能需要能够配置拨打的号码有效但没有分配给用户公用区域时如何处理电话呼叫。 管理员可以配置通知服务，以便这些呼叫转接到预定 (电话号码或 SIP URI) 播放音频通知或同时播放两者。 使用通知服务可以避免呼叫者拨错电话并听到忙音或 SIP 客户端收到错误消息的情况。 通知服务功能是典型的 PBX 功能。 
    
- **呼叫寄存**
    
    呼叫保留应用程序使 企业语音 用户可以从一部电话将呼叫置于保持状态，然后从另一部电话接收呼叫，而不会使接听电话上的资源不足。 当用户需要转接呼叫，但特定收件人未知时，呼叫转移应用程序非常有用。 
    
- **会议助理**
    
    会议助理应用程序为没有第三方音频会议提供商服务的电话用户提供音频会议功能。
    
- **会议通知**
    
    会议通知应用程序会生成提示音，以在用户进入或离开会议时发出信号，在电话用户静音或取消静音时向这些用户发送通知。
    
- **呼叫允许控制**
    
    呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许和建立新的实时通信会话，帮助防止在交通塞塞网络上用户获得较差的体验质量。 
    
    > [!NOTE]
    > CAC 仅控制实时流量，不会影响数据流量。 
  
    如果新语音或视频会话超出在 WAN 上分配的带宽限制，则只会将 (呼叫的会话阻止或) 重新路由到 PSTN。
    

