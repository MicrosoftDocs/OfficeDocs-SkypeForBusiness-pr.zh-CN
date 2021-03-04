---
title: Teams 语音 Contoso 案例研究
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
description: 适用于多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421287"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 案例研究：团队升级计划

在决定从 Skype for Business 迁移到 Teams 时，Contoso 希望为最终用户提供简单的过渡体验。 他们决定不将所有人同时切换到 Teams，而是决定设置混合连接，并使用重叠功能方法将用户移到 Teams。 这允许 Teams 和本地 Skype for Business 中的用户共享状态和进行通信。 当用户进入手机系统的试点时，他们已移至 Teams Only 模式。

若要了解有关升级、方法和模式的基本概念，Contoso 请阅读以下文章：

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [适用于 IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md) 
- [迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso 还参加 Ignite 2019 会话，设计从 [Skype for Business](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)到 Teams 的路径。 Contoso 已了解：

- 基本概念，例如互操作性、联合和升级行为 

- 基于 TeamsUpgradePolicy 的共存模式和管理 

- 最终用户体验： 

  - 聊天和通话 

  - 会议安排 

  - Teams 客户端中协作功能的可用性 

若要计划和配置混合连接，第一步是将其本地环境迁移到云，Contoso 阅读"规划混合连接"[](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)和"[配置混合](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)连接"，了解如何： 

  - 将其本地环境服务配置为与 Office 365 联合。 

  - 将其本地环境配置为信任 Office 365，并启用 Office 365 的共享 SIP 地址空间 

  - 在 Office 365 租户中启用共享 SIP 地址空间。

  - 在技术试运行期间使用群岛模式。

  - 为用户启用电话系统后，将用户切换到 TeamsOnly 模式。 通话计划和直接路由需要 TeamsOnly 模式。 
