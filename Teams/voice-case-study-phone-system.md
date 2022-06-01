---
title: Contoso 案例研究：多国公司电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司Teams语音案例研究：电话系统
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823663"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso 案例研究：多国公司电话系统

根据地理位置和其他因素，Contoso 使用以下电话解决方案设有办公室：

- 站点类型 A：Skype for Business 企业语音

- 站点类型 B：传统的旧式电话系统

- 站点类型 C：Skype for Business 企业语音和传统传统电话系统的组合


为了为整个组织实现Microsoft 电话系统解决方案，Contoso 必须针对每个站点类型&mdash;确定&mdash;以下哪些选项将与电话系统一起使用，以连接到公共交换电话网络 (PSTN) ：

- 使用呼叫计划电话系统 

- 通过直接路由使用自己的 PSTN 运营商电话系统 

- 通过直接路由将电话系统与通话套餐和电话系统与自己的 PSTN 运营商相结合
 
为了确定其组织的正确解决方案，Contoso 使用[计划Teams语音解决方案](/microsoftteams/cloud-voice-landing-page)和 Ignite 2019 会话[呼叫Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935)。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>站点类型 A：Skype for Business 企业语音 

Contoso Skype for Business 企业语音已设置为中心辐射。 有一个中心位置在区域中维护 PSTN 网关，该网关为国家/地区的Skype for Business 企业语音用户提供了与 PSTN 的连接。 这些卫星办公室往往没有自己的互联网出口。 这些用户的数字驻留在连接到现有 SBC 的 SIP 中继上。 

为了确定已部署的 SBC 是否已通过直接路由和媒体旁路认证，Contoso 检查了 [已通过直接路由认证的会话边界控制器列表](direct-routing-border-controllers.md)。  

用户的拨号习惯是使用扩展在旧电话系统上拨打用户，即使用户有一个可用于对等音频的Skype for Business客户端。 

Contoso 基于以下问题做出决策：

- 问： 是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 是否需要与第三方 PBX 系统和其他电话设备进行互操作？<br>
  答： 不支持 

- 问： 是否需要保留当前的第三方运营商？<br> A.是 (受监管的国家) 和否 

- 问： 是否需要部署 SBC 上的 ROI？<br> A.是和否  

- 问： Microsoft PSTN 呼叫计划是否在此区域中可用？<br> A.是和否 

根据他们问题的答案，Contoso 决定：

- 移动位于 PSTN 呼叫计划可用于电话系统通话套餐的区域中的用户。 

- 移动未位于 PSTN 呼叫计划可用的区域中的用户、位于 SBC 上的 ROI 尚未满足的站点中的用户，以及驻留在具有电话规则的国家/地区的用户，以使用直接路由电话系统。 

下图显示了初始Skype for Business 企业语音部署，以及如何将此部署迁移到 Microsoft 呼叫计划和直接路由：

![关系图显示状态之前和之后。](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>站点类型 B：传统的旧式电话系统

Contoso 有许多利用旧电话系统的办公室。 有一部分用户的电话号码为 E1.64，而其他用户只有扩展名。 这些数字驻留在到 PSTN 网关的 TDM 中继上。 站点内拨号是利用扩展前面的站点代码来确定呼叫路由位置来配置的。 用户的拨号习惯是按扩展拨号。   

Contoso 基于以下问题做出决策：

- 问： 是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 是否需要与第三方 PBX 系统和其他电话设备进行互操作？<br> A.是的

- 问： 是否需要保留当前的第三方运营商？<br> A.不 

- 问： Microsoft PSTN 的通话计划是否在我们的区域中可用？<br> A.是和否 

根据他们问题的答案，Contoso 决定： 

- 移动位于 PSTN 呼叫计划可用于电话系统通话套餐的区域中的用户。 

- 移动不位于 PSTN 呼叫计划可用于使用直接路由电话系统的区域中的用户。 

- 维护与业务关键模拟设备的 PSTN 连接。

下图显示了具有远程站点的原始旧系统部署，以及使用本地媒体优化迁移到直接路由部署：

**原始旧版部署** 
![关系图显示状态之前和之后。](media/voice-case-study-2.png)


**使用直接路由进行部署**

![显示前后状态的图表。](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>站点类型 C：Skype for Business 企业语音和传统传统电话系统的组合

Contoso Skype for Business 企业语音用户号码驻留在从运营商到 SBC 的 SIP 中继上。 传统电话系统的数字驻留在到 PSTN 网关的 TDM 中继上。   

Contoso 基于以下问题做出决策：

- 问： 是否需要保留本地部署提供的功能？<br>
  答： 不支持 

- 问： 是否需要与第三方 PBX 系统和其他电话设备进行互操作？<br> A.不 

- 问： 是否需要保留当前的第三方运营商？<br> A.不 

- 问： 是否需要部署 SBC 上的 ROI？<br> A.是和否  

- 问： Microsoft 的 PSTN 呼叫计划是否在此区域可用？<br> A.不 

根据他们问题的答案，Contoso 决定以下内容： 

- 对于将启用直接路由的旧式电话用户，Contoso 将数字从 TDM 中继移植到 SBC 的 SIP 中继，因为 SBC 已通过直接路由认证。 

- 为了支持一部分用户迁移到电话系统，并允许通过旧系统继续路由，旧电话系统已设置为 SBC 的下一跃点。   

- 此外，为了鼓励用户行为更改并删除对站点间和站点内扩展拨号的依赖关系，Contoso 提供了针对所有内部调用使用Teams的指导。  

下图显示了原始Skype for Business 企业语音和旧电话系统部署，以及使用直接路由迁移到混合部署：

**原始混合部署**
![显示之前状态的图 1。](media/voice-case-study-4.png)

**使用直接路由进行**
![混合部署显示之前状态的图 2。](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通话套餐

为了确定通话套餐的配置要求，Contoso 查看了 [通话计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。 生成的决策已作出： 

- 问： 我的用户是否需要国际呼叫？<br> A.是的 

- 问： 我的用户是否都有直接的向内 DID 电话号码？<br> 不是今天 所有启用的用户都将收到 DID。 

- 问： 是否要屏蔽或禁用呼叫者 ID？<br> A.用户的调用方 ID 将屏蔽为 Contoso 的本地号码。 


## <a name="direct-routing"></a>直接路由

Contoso 参加了 Ignite，以随时了解Office 365功能，包括可用于电话系统和直接路由的功能。 技术领导和架构师使用 Ignite 2019 期间提供的指导来确定其方向。  所用的关键会话： 

- [使用Microsoft Teams直接路由规划成功](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [直接路由更新](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>配置

### <a name="calling-plans-sites"></a>呼叫计划网站

为了获取许可证并向用户分配电话号码，Contoso 遵循 [了“设置呼叫计划](set-up-calling-plans.md)”中的步骤。 

由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。 若要了解如何使用 PowerShell&mdash;以及 Contoso 的其他设置&mdash;分配数字，[请使用 Teams PowerShell 概述](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接路由站点

为了将 Contoso 的本地电话基础结构连接到Microsoft Teams，Contoso 的管理员遵循[了配置直接路由](direct-routing-configure.md)中的步骤，并在Microsoft Teams中查看了视频[直接路由](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)以获取指导。  Contoso 还提到经认证的 SBC 供应商直接路由部署文档。 

在 SBC 和 Microsoft 电话 系统之间配置直接路由后，Contoso 必须测试配置。 为此，Contoso 管理员使用了在 [Ignite 2019 的“直接路由更新”会话](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138)中讨论的 SIP 测试器客户端。 SIP 测试器客户端脚本和文档已从 PowerShell 脚本下载，用于测试直接路由会话边界控制器连接。   


### <a name="local-media-optimization"></a>本地媒体优化

Contoso 看到了在全球不同区域利用本地媒体优化的机会。 适用于 Contoso 的受支持方案在 [用于直接路由的本地媒体优化](direct-routing-media-optimization.md)中进行了介绍。 本地媒体优化的配置已按照 SBC 供应商和 Microsoft 的指导完成。 本地媒体优化的配置步骤包括： 

- 配置用户和 SBC 站点 

- 根据 SBC 供应商规范配置 SBC， 

- 将外部受信任的 IP 地址添加到用于本地媒体优化的每个站点    

- 定义网络拓扑 

- 定义虚拟网络拓扑 

- 确定模式：始终绕过或仅供本地用户使用 

## <a name="networking-considerations"></a>网络注意事项

Contoso 有许多用户在启用电话系统后需要长时间远程工作。 用户使用 VPN 访问某些业务线应用程序。 在 VPN 上，电话系统用户的呼叫质量下降。 

为了解决质量问题，Contoso 实现了 VPN 拆分隧道，允许其Office 365流量遍历 Internet，而与内部应用的连接仍保留在 VPN 上。 为了实现 VPN 拆分隧道，Contoso 遵循了[为Office 365实现 VPN 拆分隧道](/office365/enterprise/office-365-vpn-implement-split-tunnel)的指导。  

