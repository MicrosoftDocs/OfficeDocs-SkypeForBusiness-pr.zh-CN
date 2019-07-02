---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business 服务器计划工具
ms.openlocfilehash: 90970dd3e82ffe401294307c09f356beca883c3b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418582"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Skype for Business 服务器计划工具
  
你可以使用规划工具的 "**中心网站**" 页面设计 Skype For business 服务器部署。 可以创建两个集中或分布式部署。 集中部署只有一个中心网站, 该网站将为您的组织中的所有 Skype for business 用户提供。 分布式部署有多个中央站点。 如果你在多个中心网站上部署 Skype for Business 服务器, 你将在计划工具中的每个中心网站上输入用户数。
  
为了完成中央站点的定义，您首先需要提供以下信息：
  
- **站点名** 输入中央站点的名称。
    
- **用户数** 输入用户数，包括驻留在中央站点的分支站点用户。
    
- **云托管用户**输入从 Skype for Business Online 托管到中心网站的用户数。
    
## <a name="ui-elements"></a>UI 元素

其余元素要么已经由你在“**入门**”向导中提供的问题答案填充，要么由规划工具自动填充（如果你跳过了该向导）。
  
### <a name="online-collaboration"></a>联机协作

 “**联机协作**”包含以下选项：
  
- **IM 和状态**
    
    即时消息 (IM) 使用户能够使用基于文本的消息在其计算机上实时相互通信。 支持两方和多方 IM 会话。 状态向用户提供网络上其他人的状态信息。 用户的状态提供信息, 以帮助其他人确定用户是否在线以及如何与用户保持最佳联系。 例如，最好通过电子邮件与正在开会的用户联系。
    
- **音频和视频会议**
    
    音频/视频 (A/V) 会议实现实时音频和视频会议。
    
- **电话拨入式会议**
    
    拨入式会议使用户能够从 PSTN 上的电话加入 A/V 会议。拨入式会议需要您部署会议助理和会议公告服务应用程序。
    
- **Web 会议**
    
    Web 会议使防火墙内部和外部的企业用户能够创建和加入在内部服务器上召开的实时会议。
    
- **持久聊天**
    
    通过持久聊天，多个用户可以参与可在其中发布和访问有关特定主题的内容（包括文本、链接和文件）的对话。尽管在会话过程中用户可以实时通信，但每个会话的内容都是持久存在的，这意味着在会话结束后，内容仍然可用。

    > [!NOTE] 
    > Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[Skype for business 到 Microsoft 团队升级](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队或继续使用 Skype for Business Server 2015。
    
### <a name="users"></a>用户

 “**用户**”包含以下选项：
  
- **内部组织**
    
- **与其他组织的联盟**
    
- **与以前版本的联盟**
    
- **与公共 IM 服务提供商的联盟** 允许组织中的用户与公共即时消息服务提供商（如 MSN、Yahoo! 和 AOL）建立通信。与公共即时消息网络建立联盟需要单独的许可证。
    
- **与基于 XMPP 的服务提供商的联盟**
    
    Skype for Business Server 2015 引入了一个完全集成的 XMPP 代理 (部署在 Edge 服务器上) 和一个部署在前端服务器上的 XMPP 网关。 你可以部署添加和配置 XMPP 代理和 XMPP 网关, 以便你的 Skype for Business 服务器用户能够添加来自基于 XMPP 的合作伙伴的联系人, 以便发送即时消息 (IM) 和状态。
    
- **移动性**
    
    部署 Skype for Business Server 移动服务时, 用户可以使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备执行诸如发送和接收即时消息、查看联系人和查看状态等活动。
    
- **W15 Exchange 邮箱**
    
    Skype for Business 服务器使你能够将语音邮件存储在 Exchange 统一消息 (UM) 中;这些语音邮件将以电子邮件形式显示在用户的收件箱中。

    > [!NOTE]
    > Exchange 2019 中不再提供 exchange 统一消息, 但您仍然可以使用 "电话系统" 录制语音邮件, 然后将录制内容保留在用户的 Exchange 邮箱中。 有关详细信息, 请参阅[规划云语音邮件服务](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
    
### <a name="voice"></a>语音

 “**语音**”包含以下选项：
  
- **企业语音**
    
    企业语音是 Microsft 的软件驱动的 VoIP 解决方案。 企业语音使用户可以使用 Skype for Business 在其计算机上进行电话呼叫。
    
- **Exchange 统一消息**
    
    Exchange 统一消息 (UM) 将语音邮件和电子邮件合并到单个消息传递基础结构中。 Skype for Business Server 2015 使用 Exchange UM 提供呼叫应答、订阅者访问、呼叫通知和自动助理服务。 如果您使用这些服务, 则需要将 Exchange UM 和 Skype for business 服务器集成到共享的 Active Directory 拓扑中。

    > [!NOTE]
    > Exchange 2019 中不再提供 exchange 统一消息, 但您仍然可以使用 "电话系统" 录制语音邮件, 然后将录制内容保留在用户的 Exchange 邮箱中。 有关详细信息, 请参阅[规划云语音邮件服务](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
    
### <a name="additional-deployment-options"></a>其他部署选项

 “**其他部署选项**”包含以下选项：
  
- **高可用性**
    
    高可用性启用备用服务器以支持故障转移。
    
- **灾难恢复**
    
    灾难恢复方法使你能够对位于两个数据中心的前端池进行配对。
    
- **监视**
    
    监控功能捕获与通信会话相关的呼叫详细记录。 它还从参与者终结点处的音频和视频会话收集指标。 监视服务器提供使用率统计信息、趋势和媒体质量统计信息。
    
- **存档**
    
    存档功能存储即时消息对话和会议。
    
- **Exchange 存档集成**
    
    如果您有托管在 Exchange 上的用户, 并且其邮箱已放在原地保留, 则您可以选择将 Skype for Business 服务器存储与 Exchange 存储集成的选项。
    
- **IPv4**
    
    IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。由于世界范围内设备数量的不断增加，可用的 IPv4 地址已经用完。因此，许多新设备开始使用 IPv6 地址。
    
- **IPv6**
    
    IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。这不仅可以提供一组新地址，而且地址数量也大大增加。
    
- **设备更新 Web 服务**
    
    设备更新 Web 服务提供了一种自动方法, 用于更新在组织外部部署的所有设备 (如适用于 Windows Phone 的 Skype for business)。
    
### <a name="server-applications"></a>服务器应用程序

 “**服务器应用程序**”包含以下选项：
  
- **响应组**
    
    "响应组" 应用程序自动应答并将呼叫分发给可用的 "支持人员" 代理。
    
- **公告**
    
    如果你计划部署企业语音, 你可能希望能够配置在拨出的号码有效但未分配给用户公共区域的情况下如何处理电话呼叫。 管理员可以配置公告服务, 以便这些呼叫转移到预先确定的目标 (电话号码或 SIP URI) 或播放音频公告。 使用公告服务避免了呼叫者 misdials 和听到占线音或 SIP 客户端收到错误消息的情况。 公告服务功能是典型的 PBX 功能。 
    
- **呼叫寄存**
    
    呼叫驻留应用程序使企业语音用户可以通过一条电话将呼叫置于保持状态, 然后从另一电话接收呼叫, 而不会在接收呼叫的电话上占用资源。 当用户需要转接呼叫, 但特定收件人未知时, 呼叫寄存应用程序很有用。 
    
- **会议助理**
    
    会议助理应用程序在没有第三方音频会议提供商的服务的情况下向电话用户提供音频会议功能。
    
- **会议公告**
    
    会议公告应用程序将发出声音, 在用户进入或离开会议时发出声音, 以及在手机用户静音或已取消静音时发出通知。
    
- **呼叫允许控制**
    
    呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许建立新的实时通信会话，以帮助防止拥塞网络上出现较差的用户体验质量。 
    
    > [!NOTE]
    > CAC 只控制实时流量，不影响数据流量。 
  
    如果新的语音或视频会话超出您在 WAN 上分配的带宽限制，会话将会被阻止（仅限电话呼叫）或重新路由到 PSTN。
    

