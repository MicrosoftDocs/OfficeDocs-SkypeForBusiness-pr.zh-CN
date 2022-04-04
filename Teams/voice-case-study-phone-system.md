---
title: Contoso 案例研究：适用于一家跨国公司的电话系统
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
description: Teams多语言公司语音案例研究：电话系统
appliesto:
- Microsoft Teams
ms.openlocfilehash: abc7c2b3eb8cbbaf98842638526514171a8b23c7
ms.sourcegitcommit: a77116a0b0fd7e3cf14de694c559338bea198851
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2022
ms.locfileid: "64628326"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso 案例研究：适用于一家跨国公司的电话系统

根据地理位置和其他因素，Contoso 设有办公室，其电话解决方案如下：

- 网站类型 A：Skype for Business 企业语音

- 站点类型 B：传统传统电话系统

- 站点类型 C：Skype for Business 企业语音传统旧电话系统的组合


若要为整个组织实施 Microsoft Phone System 解决方案，Contoso&mdash;&mdash; 必须针对每种网站类型确定以下选项与电话系统一起用于连接到公共电话交换网 (PSTN) ：

- 具有通话套餐的电话系统 

- 通过直接路由使用自己的 PSTN 运营商的电话系统 

- 通过直接路由将电话系统与呼叫计划和电话系统与自己的 PSTN 运营商结合使用
 
为了确定适合其组织的解决方案，Contoso 在 Microsoft Teams 中[](/microsoftteams/cloud-voice-landing-page)规划了 Teams 语音解决方案和 Ignite 2019 [Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>网站类型 A：Skype for Business 企业语音 

Contoso Skype for Business 企业语音已设置为中心和分支。 该区域中的 PSTN 网关位于一个中心位置，该网关为国家/地区的用户Skype for Business 企业语音 PSTN。 通常，这些卫星办事处没有其自己的 Internet 出口。 这些用户的数字驻留在连接到现有 SBC 的 SIP 中继上。 

为了确定已部署的 SBC 是否通过了直接路由和媒体旁路认证，Contoso 检查了通过直接路由认证的会话 [边界控制器列表](direct-routing-border-controllers.md)。  

用户的拨号习惯是使用分机拨打旧电话系统上的用户，即使该用户有可用于对等音频的 Skype for Business 客户端。 

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 我们是否需要和第三方 PBX 系统和其他电话设备互操作？<br>
  答： 不支持 

- 问： 我们是否需要保留当前第三方运营商？<br> A.是 (国家/地区) 和否 

- 问： 是否需要部署 SDC 的 ROI？<br> A.是和否  

- 问： Microsoft PSTN 呼叫计划是否在此区域可用？<br> A.是和否 

Contoso 根据其问题的答案决定：

- 移动位于 PSTN 呼叫计划可用于具有呼叫计划的电话系统的区域的用户。 

- 将不在提供 PSTN 呼叫计划的区域的用户、位于尚未满足 SBC ROI 的网站中的用户，以及居住在具有电话法规的国家/地区且具有直接路由的电话系统的用户移动。 

下图显示了初始部署Skype for Business 企业语音以及此部署如何迁移到 Microsoft 呼叫计划和直接路由：

![关系图显示状态之前和之后。](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>站点类型 B：传统传统电话系统

Contoso 有许多办公室利用旧式电话系统。 有一部分用户拥有 E1.64 电话号码，而其他用户只有分机号。 这些号码驻留在到 PSTN 网关的 TDM 中继上。 通过利用扩展前面的站点代码来确定呼叫的路由位置，配置了站点内拨号。 用户的拨号习惯是按分机进行拨号。   

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 否 

- 问： 我们是否需要和第三方 PBX 系统和其他电话设备互操作？<br> A.是的

- 问： 我们是否需要保留当前第三方运营商？<br> A.不 

- 问： Microsoft PSTN 的呼叫计划是否在我们的区域可用？<br> A.是和否 

Contoso 根据其问题的答案决定： 

- 移动位于 PSTN 呼叫计划可用于具有呼叫计划的电话系统的区域的用户。 

- 移动未位于 PSTN 呼叫计划可用于具有直接路由的电话系统的区域的用户。 

- 保持与业务关键型模拟设备的 PSTN 连接。

下图显示了使用远程站点的原始旧系统部署，以及使用本地媒体优化迁移到直接路由部署：

**原始旧版部署** 
![图表显示状态之前和之后。](media/voice-case-study-2.png)


**使用直接路由进行部署**

![显示状态之前和之后的图表。](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>站点类型 C：Skype for Business 企业语音传统旧电话系统的组合

Contoso Skype for Business 企业语音用户号码位于从运营商发至 SBC 的 SIP 中继上。 传统电话系统的数字驻留在到 PSTN 网关的 TDM 中继上。   

Contoso 基于以下问题做出决策：

- 问： 我们是否需要保留本地部署提供的功能？<br>
  答： 不支持 

- 问： 我们是否需要和第三方 PBX 系统和其他电话设备互操作？<br> A.不 

- 问： 我们是否需要保留当前第三方运营商？<br> A.不 

- 问： 是否需要部署 SDC 的 ROI？<br> A.是和否  

- 问： Microsoft 的 PSTN 呼叫计划是否在此区域可用？<br> A.不 

Contoso 根据其问题的答案决定以下事项： 

- 对于将启用直接路由的旧式电话用户，Contoso 将 TDM 中继中的号码移植到 SBC 的 SIP 中继，因为 SBC 已通过直接路由认证。 

- 为了支持一部分用户迁移到电话系统并允许通过旧系统持续路由，旧式电话系统已设置为 SBC 的下一跃点。   

- 此外，为了鼓励用户行为更改并消除对站点内和内部分机拨号的依赖，Contoso 提供了在所有内部呼叫Teams使用服务指南。  

下图显示了原始Skype for Business 企业语音旧电话系统部署以及使用直接路由迁移到混合部署：

**原始混合部署**
![显示前状态图 1。](media/voice-case-study-4.png)

**使用直接路由的混合部署**
![图 2 显示之前的状态。](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通话套餐

为了确定调用计划的配置要求，Contoso 查看了调用 [计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。 做出以下决策： 

- 问： 我的用户是否需要国际呼叫？<br> A.是的 

- 问： 我的用户是否都有直接向内 DID 电话号码？<br> 答：今天不能。 启用的所有用户都将收到 DID。 

- 问： 是否要屏蔽或禁用来电显示？<br> A.用户的来电显示将被屏蔽为 Contoso 的本地号码。 


## <a name="direct-routing"></a>直接路由

Contoso 参加 Ignite，Office 365手机系统和直接路由提供的功能。 技术领导和架构师使用 Ignite 2019 期间提供的指南来确定方向。  使用的关键会话： 

- [规划使用直接路由Microsoft Teams成功](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接路由的更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>配置

### <a name="calling-plans-sites"></a>呼叫计划网站

为了获取许可证并将电话号码分配给用户，Contoso 按照设置 [呼叫计划中的步骤操作](set-up-calling-plans.md)。 

由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。 若要了解如何使用 PowerShell&mdash; 和其他&mdash;设置分配数字Contoso Teams [PowerShell 概述](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接路由站点

为了将 Contoso 本地电话基础结构连接到 Microsoft Teams，Contoso 的管理员遵循了配置直接路由中的步骤，并查看了 Microsoft Teams 中的[](direct-routing-configure.md)视频"直接[路由"获得](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)指导。  Contoso 还参考了经过认证的 SBC 供应商提供的直接路由部署文档。 

在 SBC 和 Microsoft Phone System 之间配置直接路由后，Contoso 必须测试配置。 为此，Contoso 管理员使用了 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) 直接路由更新会话中讨论的 SIP 测试器客户端。 SIP 测试器客户端脚本和文档从 PowerShell 脚本下载，用于测试直接路由会话边界控制器连接。   


### <a name="local-media-optimization"></a>本地媒体优化

Contoso 看到了在全球不同区域利用本地媒体优化的机会。 直接路由的本地媒体优化中介绍了 Contoso [支持的方案](direct-routing-media-optimization.md)。 根据 SBC 供应商和 Microsoft 的指导完成本地媒体优化的配置。 本地媒体优化的配置步骤包括： 

- 配置用户和 SBC 站点 

- 根据 SBC 供应商规范配置 SBC， 

- 将外部受信任的 IP 地址添加到用于本地媒体优化的每个站点    

- 定义网络拓扑 

- 定义虚拟网络拓扑 

- 确定模式："始终绕过"或"仅针对本地用户" 

## <a name="networking-considerations"></a>网络注意事项

Contoso 有一些用户在启用电话系统后需要长时间远程工作。 用户使用 VPN 访问某些业务线应用程序。 在 VPN 上，电话系统用户遇到呼叫质量下降的情况。 

为了解决质量问题，Contoso 实施了 VPN 拆分隧道，允许其 Office 365 流量遍历 Internet，同时与内部应用的连接仍位于 VPN 上。 为了实施 VPN 拆分隧道，Contoso 遵循了为用户实现 [VPN](/office365/enterprise/office-365-vpn-implement-split-tunnel) 拆分隧道中的Office 365。  

