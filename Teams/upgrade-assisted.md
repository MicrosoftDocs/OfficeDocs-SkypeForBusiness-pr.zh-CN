---
title: 辅助升级|SkypeBusiness Online Teams升级
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 从联机到 Skype for Business 的辅助Teams概述
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995191"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>协助从 Skype for Business Online 升级到 Microsoft Teams

Microsoft 提供辅助升级Teams帮助组织在 2021 年 7 月 31 日服务停用时Skype for Business从 Skype for Business Online 成功过渡。 辅助升级可以减少需要执行的技术任务数，并可以更专注于组织准备、用户认知Teams培训。

建议在升级之前 [查看升级](https://aka.ms/SkypeToTeams) 指南。 升级指南包括建议的活动和有用的资源，用于完成从 Skype for Business Online 升级到 Teams。 本指南适用于任何计划升级到 Teams的组织，无论他们管理升级的所有方面还是使用辅助流程。

> [!NOTE]
> 如果计划进行辅助升级以升级到 Teams，可以在计划的升级日期之前从 Skype for Business Online 执行自己的升级。 有关如何手动升级到 Teams，请参阅升级[指南](https://aka.ms/SkypeToTeams)。
>
> 辅助升级不适用于本地部署的 Skype for Business Server。

## <a name="notifications-for-scheduled-customers"></a>计划客户的通知

Skype for Business计划进行辅助升级的联机客户Teams一系列升级通知。 这些通知将在计划的升级日期前 90 天开始。 这些通知将作为消息中心内更改Microsoft 365的计划、Teams管理中心中的升级仪表板通知，以及向最终用户发送的应用内标志。

升级通知将包括辅助升级的计划日期，并链接到升级资源和培训，以帮助推动采用和使用Teams。

## <a name="the-assisted-upgrade-experience"></a>辅助升级体验

辅助升级将从 2021 年 8 月开始，在上述计划通知中共享特定于租户的日期。

升级持续时间因用户数量和部署特征而异。 但是，在大多数情况下，租户中的用户将在升级开始后的 24 小时内升级。 在此期间，最终用户仍可访问 Skype for Business Online 功能。 升级完成后，用户从 Skype for Business Online 注销后，他们Teams消息、会议和呼叫。

## <a name="the-post-upgrade-experience"></a>升级后体验

辅助升级完成后，已升级用户的共存模式设置为Teams，并且 Microsoft 只能更改为其他共存模式。 建议在升级[之前Teams仅模式](teams-only-mode-considerations.md)注意事项。 下表提供了仅Teams体验的概要概述。

:::row:::
    :::column span="1":::
        **聊天和通话**
    :::column-end:::
    :::column span="3":::
        - 所有通话和聊天均在 Teams
        - 用户可以与 (用户) 聊天/Skype for Business通信
        - 组织可以通过Teams外部访问权限，Skype使用者服务的用户[进行通信](manage-external-access.md)
        - Teams尝试登录到 Skype for Business Online 的用户将被重定向到Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **会议**
    :::column-end:::
    :::column span="3":::
        - 用户计划新插件中Teams (新) 
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **迁移的数据**
    :::column-end:::
    :::column span="3":::
        - 来自 Skype for Business Online 的现有联系人，包括 (但无通讯组列表
        - 现有Skype for Business联机会议将转换为Teams会议
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>相关内容

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [Skype for Business Online 停用](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [仅 Teams 模式注意事项](teams-only-mode-considerations.md)
