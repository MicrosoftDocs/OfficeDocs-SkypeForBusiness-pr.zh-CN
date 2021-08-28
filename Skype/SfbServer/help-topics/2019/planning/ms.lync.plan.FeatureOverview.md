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
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server规划工具
ms.openlocfilehash: c1272cf0809be097e9f5b0282b165ef899744520
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600497"
---
# <a name="feature-overview-planning-tool"></a>功能概述 (规划工具) 
 
Skype for Business Server规划工具
  
可以使用规划 **工具的**"中央站点"页设计Skype for Business Server部署。 可以创建两个集中部署或分布式部署。 集中式部署只有一个中央站点，Skype for Business组织中所有用户。 分布式部署具有多个中央站点。 如果您在多个Skype for Business Server部署网站，则您将在规划工具中输入每个中央站点的用户数。
  
若要完成中央站点的定义，首先需要提供以下信息：
  
- **网站名称** 输入中央站点的名称。
    
- **用户数** 输入用户数，包括分支站点中位于中央站点的用户数。
    
- **云托管用户** 输入从 Skype for Business Online 中位于中央站点的用户数。
    
## <a name="ui-elements"></a>UI 元素

其余元素已填充为 **"入门"** 向导中的问题提供的答案，或者，如果跳过了向导，则由规划工具自动填充。
  
### <a name="online-collaboration"></a>联机协作

 **联机协作** 包含以下选项：
  
- **IM 和状态**
    
    即时消息 (IM) 使用户可以使用基于文本的消息在计算机中实时相互通信。 支持双方和多方之间的 IM 会话。 状态为用户提供有关网络上其他人的状态的信息。 用户的状态信息可帮助其他人确定用户是否联机以及如何最好地与用户联系。 例如，最好通过电子邮件联系正在参加会议的用户。
    
- **音频和视频会议**
    
    音频/ (A/V) 会议支持实时音频和视频会议。
    
- **电话拨入式会议**
    
    电话拨入式会议使用户能够从 PSTN 上的电话加入 A/V。 电话拨入式会议要求部署 会议助理 会议公告 服务应用程序。
    
- **Web 会议**
    
    Web 会议使防火墙内外的企业用户能够创建和加入内部服务器上承载实时会议。
    
- **持久聊天**
    
    持久聊天使多个用户可以参与对话，用户可在对话中发布和访问有关特定主题的内容，包括文本、链接和文件。 尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。

    > [!NOTE] 
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams 中可用。 有关详细信息，请参阅[Skype for Business Microsoft Teams升级](/MicrosoftTeams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。
    
### <a name="users"></a>用户

 **用户** 包含以下选项：
  
- **内部组织**
    
- **与其他组织的联盟**
    
- **与以前版本的联盟**
    
- **与公共 IM 服务提供商联盟** 允许贵组织的用户与公共即时消息服务提供商（如 MSN、Yahoo！和 AOL）建立通信。 与公共即时消息网络建立联盟需要单独的许可证。
    
- **与基于 XMPP 的服务提供商联盟**
    
    Skype for Business Server 2015 年 10 月引入了完全集成的 XMPP 代理 (部署在边缘服务器上) 前端服务器上部署的 XMPP 网关。 您可以部署 添加和配置 XMPP 代理和 XMPP 网关将允许 Skype for Business Server 用户添加来自基于 XMPP 的合作伙伴的联系人，以便 (IM) 和状态。
    
- **行动能力**
    
    部署 Skype for Business Server Mobility Service 时，用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备执行发送和接收即时消息、查看联系人和查看状态等活动。
    
- **W15 Exchange邮箱**
    
    Skype for Business Server使您可以将语音邮件存储在统一消息Exchange UM (中) ;这些语音邮件随后将在用户的收件箱中显示为电子邮件。

    > [!NOTE]
    > Exchange以前已知的统一消息在 Exchange 2019 中不再可用，但您仍可以使用 电话系统 录制语音邮件，然后在用户的 Exchange 邮箱中保留录制。 有关详细信息[，请参阅云语音邮件](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)服务。
    
### <a name="voice"></a>语音

 **语音** 包含以下选项：
  
- **企业语音**
    
    Enterprise是 Microsft 的软件支持 VoIP 解决方案。 Enterprise使用户可以使用Skype for Business从计算机发出电话呼叫。
    
- **Exchange 统一消息**
    
    Exchange统一 (UM) 将语音邮件和电子邮件合并到单个邮件基础结构中。 Skype for Business Server 2015 Exchange UM 提供呼叫应答、订阅者访问、呼叫通知和自动助理服务。 如果使用这些服务，则需要将 UM 和 Exchange集成Skype for Business Server Active Directory 拓扑中。

    > [!NOTE]
    > Exchange以前已知的统一消息在 Exchange 2019 中不再可用，但您仍可以使用 电话系统 录制语音邮件，然后在用户的 Exchange 邮箱中保留录制。 有关详细信息[，请参阅云语音邮件](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)服务。
    
### <a name="additional-deployment-options"></a>其他部署选项

 **其他部署选项** 包含以下选项：
  
- **高可用性**
    
    高可用性为备用服务器启用故障转移支持。
    
- **灾难恢复**
    
    灾难恢复措施使您能够对位于两个数据中心的前端池进行配对。
    
- **监视**
    
    监控捕获与通信会话相关的呼叫详细信息记录。 它还从参与者终结点的音频和视频会话收集指标。 监控服务器提供使用情况统计信息、趋势和媒体质量统计信息。
    
- **存档**
    
    存档存储即时消息对话和会议。
    
- **Exchange存档集成**
    
    如果您的用户位于 Exchange且其邮箱已置于 In-Place 保留状态，您可以选择将 Skype for Business Server 存储与 Exchange 存储集成。
    
- **IPv4**
    
    IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。 由于全球设备数量不断增加，可用 IPv4 地址已用完。因此，许多新设备都迁移到使用 IPv6 地址。
    
- **IPv6**
    
    IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。 这不仅提供了一组新的地址，而且数量远远超过原来的地址集。
    
- **设备更新 Web 服务**
    
    设备更新 Web 服务提供了一种自动方法，用于更新在组织Windows Phone版Skype for Business部署的所有设备（如设备）。
    
### <a name="server-applications"></a>服务器应用程序

 **服务器应用程序** 包含以下选项：
  
- **响应组**
    
    响应组应用程序会自动应答呼叫并将呼叫分发给可用的支持人员代理。
    
- **公告**
    
    如果计划部署企业语音，可能需要能够配置拨打的号码有效但没有分配给用户公用区域时如何处理电话呼叫。 管理员可以配置通知服务，以便这些呼叫转接到预先确定的目标 (电话号码或 SIP URI) 播放音频通知或同时播放两者。 使用通知服务可以避免呼叫者拨错电话并听到忙音或 SIP 客户端收到错误消息的情况。 通知服务功能是典型的 PBX 功能。 
    
- **呼叫寄存**
    
    呼叫保留应用程序使呼叫企业语音用户从一部电话将呼叫置于保持状态，然后从另一部电话接收呼叫，而不会使接收呼叫的电话上的资源不足。 当用户需要转移呼叫，但特定收件人未知时，呼叫呼叫管理应用程序非常有用。 
    
- **会议助理**
    
    会议助理应用程序为没有第三方音频会议提供商服务的电话用户提供音频会议功能。
    
- **会议公告**
    
    会议公告应用程序会生成提示音，提示用户进入或离开会议时，以及电话用户被静音或取消静音时向这些用户发送通知。
    
- **呼叫允许控制**
    
    呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它通过根据可用带宽确定是否允许和建立新的实时通信会话，帮助防止出现塞塞网络的用户体验质量差。 
    
    > [!NOTE]
    > CAC 仅控制实时流量，不会影响数据流量。 
  
    如果新语音或视频会话超出在 WAN 上分配的带宽限制，则只会将 (呼叫的会话阻止或) 重新路由到 PSTN。
