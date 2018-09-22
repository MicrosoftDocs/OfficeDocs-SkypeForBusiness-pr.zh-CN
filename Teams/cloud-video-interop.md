---
title: Microsoft 团队云视频互操作
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: 云视频互操作使第三方会议房间设备加入 Microsoft 小组会议。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3219190a112615122ebc55e3a28e5abedd2d5e1
ms.sourcegitcommit: 69d1cea64425f03e562b5fb930493e27b61db96b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "24968267"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft 团队云视频互操作

云视频互操作使第三方会议房间设备加入 Microsoft 小组会议。

电话会议与内容协作的视频可帮助您进行充分利用会议。 但是，会议室系统和设备的升级的费用。 云视频互操作的 Microsoft 团队系统处理，而所有参与者 – 在会议室内或内部团队客户端提供本机会议体验。 

## <a name="partners-certified-for-microsoft-teams"></a>Microsoft 团队认证的合作伙伴

以下合作伙伴具有 Microsoft 团队视频互操作的解决方案。 您的公司可以选择使用这些合作伙伴在企业内的任意组合。 


|合作伙伴|合作伙伴解决方案|可用性|
|----|---|----|
|![Polycom RealConnect](media/polycom.png) |   [Office 365 的 Polycom RealConnect](https://aka.ms/PolycomRealConnect)|现在空闲|
|![Pexip 无穷大](media/pexip.png)| [Microsoft 团队 Pexip 无穷大](https://aka.ms/PexipInfinity) | 2018 年 10 月 19 日|
|![BlueJeans 网关](media/bluejeans.png)|[Microsoft 团队 blueJeans 网关](https://aka.ms/BluejeansGateway) | 2018 年 10 月 31 日|

## <a name="partner-solutions"></a>合作伙伴解决方案

我们的合作伙伴开发了网关解决方案，将第三方基于标准的 SIP 和 H.323 设备连接到 Microsoft 小组会议。  
 
**认证和 Microsoft 支持**

- 只能通过认证合作伙伴解决方案
- 与 Microsoft 共同工程
- 客户点击之前证书

**企业**

- HD 视频 (1080p) 和内容 (VBSS)
- 支持 H.323 和 SIP 会议室内设备-本机团队/Exchange 安排-而不是 VMR 的网关设计

**针对云的标尺**

- 部署和托管在 Azure
- 与云解决方案自动缩放

 
## <a name="reference-architecture"></a>参考体系结构

下图介绍团队合作伙伴解决方案的高级体系结构。

![团队云视频互操作合作伙伴解决方案](media/teams-cloud-video-interop-partner-solution.png)

## <a name="key-business-considerations"></a>关键业务注意事项

**旁 3 P 视频基础结构的 Microsoft 团队**

- 您是否有 3 P 视频设备的大型部署？
- 您必须在您的组织中调用控制器 3 P？
- 您计划如何使您当前的呼叫控制器旁的 Microsoft 团队？
- 您想 infra 运行您自己的视频或托管？ 
- 您计划部署团队会议室系统？ 当？

**已存在的认证互操作的提供程序**

- 若要继续与您当前的认证合作伙伴吗？
- 您是否需要继续支持集成的会议室环境 （Exchange，一个触摸拨号）？

**其他要求**

- 您需要实时监控、 疑难解答、 和报告功能？
- 是否需要可在 sovereign 或政府群？
- 您是否有外部公司加入团队会议？ 

## <a name="business-workflow-scenarios"></a>业务工作流方案

- **业务服务器 Skype-> Microsoft 团队：** 您的组织有第三方设备和 Skype 从业务上 prem 服务器移到的 Microsoft 团队  
- **For Business 的 Skype 联机-> Microsoft 团队：** 您的组织迁移到 Microsoft 团队从 Skype 业务 online。
- **Cisco UC-> Microsoft 团队：** 从 Cisco 移动到 Microsoft 团队，但未就绪，以替换 Cisco 设备，您的组织。
- **混合的系统-> Microsoft 团队：** 您的组织具有多个系统环境并排中的 （Cisco、 BroadSoft、 SfB 服务器、 SfBO）。
- **另一个云会议提供商-> Microsoft 团队：** 您的组织已迁移到 Microsoft 团队的另一个云会议提供商的用户。


选择之后的伙伴，您已准备好[设置 Microsoft 团队的云视频互操作](cloud-video-interop-for-teams-set-up.md)。 