---
title: 云语音部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: 在 Microsoft Teams 中部署云语音功能实践指导
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236763"
---
# <a name="cloud-voice-deployment"></a>云语音部署

作为 Office 365 中团队合作和沟通的中心的 Microsoft Teams 现在通过扩展 Teams 会议和通话体验以包含通过公用电话交换网 (PSTN) 连接的外部各方，提供了音频会议、具有通话套餐的电话系统以及电话系统直接路由功能，从而满足额外的业务需求。


> [!Tip] 
> 观看以下会话了解电话系统简介: [Microsoft 团队中的电话系统简介](https://aka.ms/teams-phone-system)
 
我们将更新此页面, 因为随着时间的推移, 团队的其他云语音功能将随时间发布。



## <a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams 中的音频会议


Office 365 中的音频会议允许参与者从任何电话加入 Teams 会议。

下面是 Office 365 中的[音频会议](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)所获得的功能。


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Microsoft 团队中包含通话计划 ("通话计划") 的电话系统

电话系统是一种 Office 365 功能, 可提供管理呼叫路由、策略和用户预配的功能。 这包括电话呼叫管理系统、呼叫路由和呼叫控制。

通话计划是电话系统功能的附加服务, 通过团队和 Skype for business Online 提供。 通话计划要求有问题的用户托管在 Skype for business Online 中, 以便在 Microsoft 团队中工作。 通话计划向企业中的人员提供主要电话号码, 并让他们通过 PSTN 拨打和接听您的组织外部的电话。

若要了解详细信息, 请参阅在 Office 365 和[电话系统和通话计划](calling-plan-landing-page.md)[中使用手机系统获取的功能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)


## <a name="phone-system-direct-routing-direct-routing"></a>电话系统直接路由 ("直接路由")

直接路由可与电话系统功能配合使用, 以向组织中的人员提供通过 PSTN 建立和接收来自组织外部的电话呼叫, 其中 PSTN 连接是通过第三方服务提供商提供的。

若要了解详细信息, 请阅读[计划直接路由](direct-routing-plan.md)和[配置直接路由](direct-routing-configure.md)。

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>适用于 Microsoft 团队的音频会议、通话计划和直接路由的实用指南

通过使用 Office 365 FastTrack 客户版旅行框架及其三个阶段&mdash;"构想"、"板载" 和 "驱动器" 值, 可对此实用指南进行组织。 它旨在帮助你规划、交付和操作成功的音频会议、通话计划或直接路由实施。

> [!div class="mx-tableFixed"]
> |展望  |上线  |推动价值  |
> |---------|---------|---------|
> |[定义成功](1-envision-define-my-success-cloud-voice.md) <br> 提出我的服务决策 <br>&nbsp;&nbsp;[音频会议](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[通话计划](2-envision-make-my-service-decisions-phone-system.md)或[直接路由](2-envision-make-my-service-decisions-direct-routing.md) <br> [评估环境](3-envision-evaluate-my-environment.md) <br> [规划服务管理](4-envision-plan-my-service-management.md) <br> [规划我的用户体验](5-envision-plan-my-users-experience.md) <br> [记录成功计划](6-envision-document-my-success-plan.md)    | [准备服务](1-onboard-prepare-my-service.md) <br> [准备用户](2-onboard-prepare-my-users.md) <br> [部署服务](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [操作服务](1-drive-value-operate-my-service.md) <br> [增强服务](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

内容以有序的形式呈现, 旨在让你通过从开始到结束的端到端部署旅程。 如果您已在主动部署, 我们仍鼓励您参考适用的内容区域。


> [!TIP]
> 在此实用指南中, 我们为每个活动和关键讨论提供示例输出。 本文档中的示例包含在 Tip 标注中, 它们作为可重复使用的模板。 您将看到 "TBA" (要添加) 作为规划过程的一部分需要完成的信息。
