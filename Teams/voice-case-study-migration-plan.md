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
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785956"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 案例研究：团队升级计划

在决定从 Skype for Business 迁移到团队时，Contoso 希望为最终用户提供轻松的过渡体验。 他们不会同时将每个人切换到团队，而是决定设置混合连接，并使用重叠的功能方法将用户移动到团队。 这允许团队和 Skype for business 中的用户共享联机状态和通信。 当用户输入手机系统的试点时，它们将被移动到 "仅限团队" 模式。

若要了解有关升级、方法和模式的基本概念，Contoso 阅读以下文章：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [从 Skype for Business 升级到 Teams](upgrade-to-teams-on-prem-overview.md) 
- [迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso 还参与了 Ignite 2019 会话[来设计您从 Skype For business 到团队的路径](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。 Contoso 已了解：

- 互操作性、联合身份验证和升级行为等基本概念 

- 基于 TeamsUpgradePolicy 的共存模式和管理 

- 最终用户体验： 

  - 聊天和通话 

  - 会议计划 

  - 团队客户端中的协作功能的可用性 

若要计划和配置混合连接，第一步是将其本地环境移动到云、Contoso 读取[计划混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)和[配置混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)，以了解如何执行以下操作： 

  - 将其本地环境服务配置为与 Office 365 联盟。 

  - 将其本地环境配置为信任 Office 365 并启用 Office 365 的共享 SIP 地址空间 

  - 在其 Office 365 租户中启用共享 SIP 地址空间。

  - 在技术试验期间使用孤岛模式。

  - 用户启用电话系统后，将用户切换到 TeamsOnly 模式。 TeamsOnly 模式是通话计划和直接路由所必需的。 
