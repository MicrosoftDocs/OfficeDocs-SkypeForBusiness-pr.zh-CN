---
title: 仅 Teams 模式注意事项
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理员可以了解如何准备在 Microsoft Teams 管理中心升级到仅限 Microsoft Teams 模式。
ms.localizationpriority: medium
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
ms.openlocfilehash: b80a563d6d3938a597e57aab4ac93e41df976d32
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605861"
---
# <a name="teams-only-mode-considerations"></a>仅 Teams 模式注意事项

Microsoft 365 或Office 365组织的管理员可以将单个用户或整个租户升级到仅限 Teams 模式。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

升级到仅限 Teams 模式可为用户提供 Microsoft Teams 的全部优势，Microsoft Teams 是 Microsoft 365 或 Office 365 中的团队合作中心，通过单个客户端体验。 仅限 Teams 模式的用户将收到 Teams 中的所有呼叫和聊天，无论发件人是使用Skype for Business还是 Teams，并受益于互操作和联合身份验证支持。

尽管成千上万的客户已成功升级到 Microsoft Teams，但一些注意事项可能会影响组织的升级时间线和用户体验。 为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。 

> [!IMPORTANT]
> 如果刚刚开始升级计划，请务必查看 [Microsoft Teams 升级](upgrade-start-here.md) 指南入门。 

**共存注意事项**：已使用 Skype for Business Online 和/或 Skype for Business Server 的组织可以按满足其需求的速度将 Teams 引入其环境。 组织可以根据需要以增量方式向所需的一组用户推出 Teams，而使用 Teams 的用户可以与使用Skype for Business的用户进行通信，反之亦然。 为了管理此体验，管理员使用共存模式，定义最终用户客户端体验、传入聊天和呼叫的路由行为，以及新会议是在 Teams 中安排还是Skype for Business。 如果用户已升级到 **仅 Teams**，则用户可以与其他组织中的用户联合;但是，当两个用户都使用 Teams 时，将提供最佳体验。 升级到 Teams 的用户仍可以加入Skype for Business会议。 

> [!IMPORTANT]
> 有关共存的详细信息，请参阅[了解 Microsoft Teams 和Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 有关 Teams 和 Skype (使用者) 的详细信息，请参阅 [Teams 和 Skype 互操作性](teams-skype-interop.md)。


**特定于用户的注意事项**：某些用户方案仍在发展，管理员可能会决定在升级组织中的其他用户时暂时推迟某些用户的升级。 特别是，我们仍在处理主设备基于 VDI 的用户的方案。 有关网站公告，请监视 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。

> [!NOTE]
> 在迁移到仅限 Teams 模式之前，需要替换或更新不支持 Teams 的设备。 

> [!IMPORTANT]
> **请记住**：迁移到 Teams 不仅仅是技术迁移。 成功升级可评估技术准备情况和最终用户就绪情况。 查看 Teams [升级指南](upgrade-framework.md)的Skype for Business，详细了解如何规划到 Teams 的升级。  
