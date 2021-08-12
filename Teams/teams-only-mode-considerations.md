---
title: 仅 Teams 模式注意事项
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理员可以了解如何在管理中心中Microsoft Teams升级到仅Microsoft Teams模式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: da61c6fdda511375010375a785fc06c3549883bf56396fc87daaadb4472cf2af
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312540"
---
# <a name="teams-only-mode-considerations"></a>仅 Teams 模式注意事项

组织或Microsoft 365 Office 365管理员可以将单个用户或整个租户升级到Teams模式。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

升级到仅Teams模式通过单个客户端体验为用户提供 Microsoft Teams（Microsoft 365 或 Office 365 团队协作的中心）的全部优势。 仅Teams模式的用户将在 Teams 中接收所有呼叫和聊天，无论发送方使用的是 Skype for Business 还是 Teams，并且受益于互操作和联合身份验证支持。

尽管成千上万的客户已成功升级到 Microsoft Teams，但有些注意事项可能会影响组织的升级时间线和用户体验。 为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。 

> [!IMPORTANT]
> 如果只是开始进行升级规划，请务必查看我们的升级Microsoft Teams[入门](upgrade-start-here.md)。 

**共存注意事项**：已使用 Skype for Business Online 和/或 Skype for Business Server 的组织Teams其环境中以满足其需求的速度引入资源。 组织可根据需要以Teams方式向一组所需用户推出服务，使用 Teams 的用户可以与使用 Skype for Business 的用户进行通信。反之亦然。 为了管理此体验，管理员使用共存模式来定义最终用户客户端体验、传入聊天和呼叫的路由行为，以及新会议是安排在 Teams 还是 Skype for Business。 如果用户已升级到"仅"，则用户可以与其他Teams **联合**;但是，当两个用户都使用 Teams。 升级到"仅Teams的用户仍可加入Skype for Business会议。 

> [!IMPORTANT]
> 有关共存的更多详细信息，请参阅了解Microsoft Teams Skype for Business[和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 有关使用使用者Teams Skype (服务) ，请参阅Teams[和Skype互操作性](teams-skype-interop.md)。


**特定于用户的注意事项**：某些用户方案仍在不断发展，管理员可能会决定在升级组织中其他用户时暂时推迟某些用户的升级。 具体而言，我们仍在努力解决主要设备基于 VDI 的用户的方案。 有关站点公告，请监视Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。

> [!NOTE]
> 在移动到"仅Teams模式之前，需要替换或更新不支持此Teams。 

> [!IMPORTANT]
> **请记住**：迁移到 Teams不仅仅是技术迁移。 成功升级会评估技术准备情况以及最终用户准备情况。 请查看我们的Skype for Business Teams指南，详细了解如何[](upgrade-framework.md)规划升级到 Teams。  
