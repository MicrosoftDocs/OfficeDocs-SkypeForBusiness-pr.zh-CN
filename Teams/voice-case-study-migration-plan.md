---
title: Teams语音 Contoso 案例研究升级计划
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
description: Teams跨国企业语音案例研究：升级规划。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822981"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 案例研究：Teams升级计划

在决定从Skype for Business迁移到Teams时，Contoso 希望为最终用户提供简单的过渡体验。 他们决定设置混合连接，并使用重叠功能方法将用户移动到Teams，而不是同时将所有人切换到Teams。 这允许Teams和本地Skype for Business用户共享状态和通信。 当用户进入试点进行电话系统时，他们被移动到“仅Teams模式”。

为了了解有关升级、方法和模式的基本概念，Contoso 阅读以下文章：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md) 
- [迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso 还参加了 Ignite 2019 会话，[设计从Skype for Business到Teams的路径](https://myignite.microsoft.com/archives/IG20-OD251)。 Contoso 了解以下内容：

- 基本概念，如互操作性、联合身份验证和升级行为 

- 基于 TeamsUpgradePolicy 的共存模式和管理 

- 最终用户体验： 

  - 聊天和通话 

  - 会议日程安排 

  - Teams客户端中协作功能的可用性 

若要规划和配置混合连接，Contoso 将本地环境迁移到云的第一步是阅读 [计划混合连接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 并 [配置混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 以了解如何： 

  - 配置其本地环境服务以与Office 365联合。 

  - 将本地环境配置为信任Office 365，并使用Office 365启用共享 SIP 地址空间 

  - 在其Office 365租户中启用共享 SIP 地址空间。

  - 在技术试点期间使用“岛屿”模式。

  - 为用户启用电话系统后，将用户切换到 TeamsOnly 模式。 调用计划和直接路由需要 TeamsOnly 模式。
