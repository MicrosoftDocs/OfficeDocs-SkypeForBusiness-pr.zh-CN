---
title: 团队语音 Contoso 个案研究
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
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785975"
---
# <a name="contoso-case-study-phone-system"></a>Contoso 案例研究：电话系统

根据地理位置和其他因素，Contoso 拥有使用以下电话服务解决方案的办事处：

- 网站类型 A： Skype for Business 企业语音

- 网站类型 B：传统的旧电话系统

- 网站类型 C： Skype for Business 企业语音和传统旧式电话系统的组合


若要为整个组织实施 Microsoft Phone 系统解决方案，Contoso 必须确定 &mdash; 每个网站类型将 &mdash; 以下哪一种选项与电话系统一起使用才能连接到公共交换式电话网络（PSTN）：

- 带有呼叫计划的电话系统 

- 通过直接路由使用自己的 PSTN 运营商的电话系统 

- 通过直接路由将电话系统与呼叫计划和电话系统结合到自己的 PSTN 运营商
 
为了为其组织确定合适的解决方案，Contoso 使用[microsoft 电话服务解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)和[microsoft 团队中](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)的 Ignite 2019 会话通话。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>网站类型 A： Skype for Business 企业语音 

Contoso Skype for business 企业语音已设置为中心和分支。 有一个中心位置，它在为国家/地区的 Skype for business Enterprise Voice 用户提供 PSTN 网关的区域中维护 PSTN 网关。 这些卫星办公室通常没有自己的 Internet 出口。 这些用户的数字驻留在与现有 SBC 连接的 SIP 中继上。 

为了确定已部署的 SBC 是否已针对直接路由和媒体绕过认证，Contoso 检查了[认证为直接路由的会话边框控制器列表](direct-routing-border-controllers.md)。  

用户的拨号习惯是使用扩展在旧式电话系统上拨出用户，即使用户有适用于对等音频的 Skype for Business 客户端也是如此。 

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 我们是否需要与第三方 PBX 系统和其他电话设备互操作？<br>
  答： 否 

- 问： 我们是否需要保留当前的第三方运营商？<br> 答：是（管控国家），不 

- 问： 我们是否需要在部署 SBCs 上获得 ROI？<br> 答：是和否  

- 问： 此地区是否提供 Microsoft PSTN 呼叫计划？<br> 答：是和否 

根据问题的答案，Contoso 决定：

- 将位于 PSTN 呼叫计划的区域中的用户移动到使用呼叫计划的电话系统。 

- 移动不在 PSTN 呼叫计划可用的区域中的用户、位于 SBCs 的 ROI 尚未满足的网站中的用户以及驻留在使用直接路由的电话系统所在国家/地区的用户。 

下图显示了初始 Skype for Business 企业语音部署以及如何将此部署迁移到 Microsoft 通话计划和直接路由：

![显示在状态之前和之后的图表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>网站类型 B：传统的旧电话系统

Contoso 拥有许多利用旧式电话系统的办事处。 有一个具有 E 1.64 电话号码的用户子集，而其他用户仅有一个扩展名。 这些号码驻留在用于 PSTN 网关的 TDM 主干中。 站内拨号是通过在扩展的前面利用站点代码来确定呼叫路由的位置来配置的。 用户的拨号习惯是通过分机号码拨号。   

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 我们是否需要与第三方 PBX 系统和其他电话设备互操作？<br> 答：是

- 问： 我们是否需要保留当前的第三方运营商？<br> A. 否 

- 问： 我们的地区是否提供 Microsoft PSTN 的呼叫计划？<br> 答：是和否 

根据问题的答案，Contoso 决定： 

- 将位于 PSTN 呼叫计划的区域中的用户移动到使用呼叫计划的电话系统。 

- 将没有位于 PSTN 呼叫计划的区域中的用户移动到使用直接路由的电话系统。 

- 维护与业务关键模拟设备的 PSTN 连接。

下图显示了具有远程站点的原始旧系统部署以及使用本地媒体优化迁移到直接路由部署的步骤：

**原始旧部署**  
 ![显示在状态之前和之后的图表](media/voice-case-study-2.png)


**直接路由的部署**

![显示在状态之前和之后的图表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>网站类型 C： Skype for Business 企业语音和传统旧式电话系统的组合

Contoso Skype for business 企业语音用户的号码驻留在来自运营商的 SBC 的 SIP 主干中。 传统电话系统的号码驻留在 TDM 主干网关。   

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 我们是否需要与第三方 PBX 系统和其他电话设备互操作？<br> A. 否 

- 问： 我们是否需要保留当前的第三方运营商？<br> A. 否 

- 问： 我们是否需要在部署 SBCs 上获得 ROI？<br> 答：是和否  

- 问： 此地区是否提供 Microsoft PSTN 呼叫计划？<br> A. 否 

根据问题的答案，Contoso 决定以下事项： 

- 对于将为其启用直接路由的传统电话用户，Contoso 将这些号码从 TDM 主干移植到了 SBC 的 SIP 主干，因为 SBC 经认证可直接路由。 

- 若要支持移动到手机系统的用户的子集，并允许通过旧系统继续路由，则将旧电话系统设置为 SBC 的下一跃点。   

- 此外，为了鼓励用户行为更改和删除在站点内部和站点内扩展拨号的相关性，Contoso 提供了用于所有内部通话的团队的指南。  

下图显示了最初的 Skype for Business 企业语音和旧式电话系统部署以及使用直接路由迁移到混合部署的步骤：

**原始混合部署** 
 ![状态之前显示的图表](media/voice-case-study-4.png)

**直接路由** 
 ![ 的混合部署状态之前显示的图表](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通话套餐

为了确定呼叫计划的配置要求，Contoso 已检查[通话计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。 最终做出的决策： 

- 问： 我的用户是否需要国际通话？<br> 答：是 

- 问： 我的用户是否有直接向内拨电话号码？<br> 。不是今天。 所有启用的用户都将收到 "已启用"。 

- 问： 我是否希望屏蔽或禁用来电显示？<br> A. 用户的呼叫方 ID 将被屏蔽到 Contoso 的本地号码。 


## <a name="direct-routing"></a>直接路由

Contoso 参与了 Ignite，以保持最新的 Office 365 功能，包括可通过电话系统和直接路由使用的功能。 技术领导和架构师使用在 Ignite 2019 期间提供的指南确定其方向。  使用的关键会话： 

- [通过 Microsoft 团队直接路由来规划成功](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接路由更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>配置

### <a name="calling-plans-sites"></a>通话计划网站

要获取许可证并为用户分配电话号码，Contoso 按照[设置通话计划](set-up-calling-plans.md)中的步骤进行操作。 

由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。 若要了解如何使用 PowerShell 分配号码 &mdash; 以及其他设置， &mdash; Contoso 使用[团队 PowerShell 概述](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接路由网站

要将 Contoso 的本地电话基础结构连接到 Microsoft 团队，Contoso 管理员按照[配置直接路由](direct-routing-configure.md)和查看[microsoft 团队中的视频直接路由中](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)的步骤进行操作。  Contoso 还通过认证的 SBC 供应商引用直接路由部署文档。 

在 SBC 和 Microsoft Phone 系统之间配置了直接路由后，Contoso 必须对该配置进行测试。 为此，Contoso 管理员使用在[Ignite 2019 的直接路由会话更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)中讨论的 SIP 测试客户端。 SIP 测试客户端脚本和文档已从 PowerShell 脚本下载以测试直接路由会话边界控制器连接。   


### <a name="local-media-optimization"></a>本地媒体优化

Contoso 在全球不同地区看到了利用本地媒体优化的机会。 [用于直接路由的本地媒体优化](direct-routing-media-optimization.md)中介绍了 Contoso 支持的方案。 通过遵循 SBC 供应商和 Microsoft 的指南完成本地媒体优化的配置。 本地媒体优化的配置步骤包括： 

- 配置用户和 SBC 网站 

- 根据 SBC 供应商规范配置 SBC， 

- 将外部受信任的 IP 地址添加到用于本地媒体优化的每个网站    

- 定义网络拓扑 

- 定义虚拟网络拓扑 

- 确定模式：始终绕过或仅适用于本地用户 

## <a name="networking-considerations"></a>网络注意事项

Contoso 在启用电话系统后，有多个用户需要在多长时间内进行远程工作。 使用 VPN 访问特定的业务线应用程序的用户。 在使用 VPN 时，电话系统用户遇到通话质量下降。 

为了解决质量问题，Contoso 实现了 VPN 拆分隧道，该隧道允许其 Office 365 通信在 Internet 上保持与内部应用的连接时通过 Internet。 若要实现 VPN 拆分隧道，Contoso 遵循[实现 Office 365 的 vpn 拆分隧道](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)的指南。  

 





