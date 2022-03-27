---
title: 辅助升级|Skype Business Online Teams升级
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 从联机到 Skype for Business 的辅助Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456885"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>从 Skype for Business Online 到 Microsoft Teams 的辅助升级

Microsoft 于 2021 Skype for Business 31 日停用了 Online。  Microsoft 提供辅助升级过程，帮助组织将剩余的用户Skype for Business Online 用户Teams迁移。  无论你的组织是以下组织，Microsoft 辅助升级都减少了技术任务的数量，并简化了在无需Skype for Business Online 的情况下过渡到世界：
 - 一个纯在线组织，*需要从 Skype for Business Online 升级为* 纯Teams，或
 - 一个混合组织，其用户同时位于 *Skype for Business Online*  和本地 *Skype for Business Server* 环境中，这只能将 Skype for Business *Online* 用户升级到Teams环境。

建议在升级之前 [查看升级](https://aka.ms/SkypeToTeams) 指南。 我们的升级指南包括建议的活动和有用的资源，用于完成从 Skype for Business Online 升级到 Teams。 本指南适用于任何计划升级到 Teams的组织，无论他们管理升级的所有方面还是使用辅助过程。

## <a name="the-assisted-upgrade-experience"></a>辅助升级体验
Skype for Business计划向 Teams 进行辅助升级的联机客户将收到各种通知：计划更改 Microsoft 365 消息中心中的帖子、Teams 管理中心中的升级仪表板通知，以及向最终用户发送的应用内标志。 消息中心和 Teams 管理中心中的升级通知包括辅助升级的计划日期，以及用于升级资源和培训的链接，以帮助推动用户采用和Teams。

辅助升级体验略有不同，具体取决于组织是否将任何用户放在本地Skype for Business Server环境中：
- **纯在线组织：** 对于 *没有任何针对* Busineess Server `TeamsUpgradeOverridePolicy` Skype本地部署的组织，辅助升级过程会向组织应用策略。 应用此策略后，Skype for Business Online 的所有用户将处于 TeamsOnly 模式。
- **具有本地用户Skype for Business** 混合组织：这包括任何用户位于 Skype for Business Server 的组织，无论是否已配置混合。 这些组织的用户可能分为以下类别之一：

  - 本地用户位于可能Skype for Business Server (也可能不使用 Teams，但并非仅Teams用户) 
  - 在 Skype for Business Online 中Skype for Business的 TeamsOnly 用户
  - 在 Skype for Business Online 中管理的非 TeamsOnly 用户

辅助升级过程将仅影响最后一类用户：非Teams仅位于 Skype for Business Online 中的用户将升级到Teams模式。 本地Skype for Business现有 TeamsOnly 用户不会受辅助升级过程的影响。

> [!NOTE]
> 您的组织可以继续使用 Skype for Business Online，直到升级完成。 如果计划进行辅助升级以升级到 Teams，可以在计划的升级日期之前从 Skype for Business Online 执行自己的升级。 有关如何手动升级到 Teams，请参阅升级[指南](https://aka.ms/SkypeToTeams)。

升级持续时间因用户数量和部署特征而异。 在大多数情况下，租户中的用户将在升级开始后的 24 小时内升级。 在此期间，最终用户仍可访问 Skype for Business Online 功能。 升级完成后，用户从 Skype for Business Online 注销后，他们Teams消息、会议和呼叫。

## <a name="the-post-upgrade-experience"></a>升级后体验

辅助升级完成后 **，已升级** 用户的共存模式设置为Teams模式。 建议在升级[之前Teams仅模式](teams-only-mode-considerations.md)注意事项。 下表提供了仅Teams体验的概要概述。

:::row:::
    :::column span="1":::
        **聊天和通话**
    :::column-end:::
    :::column span="3":::
        - 所有通话和聊天均在 Teams
        - 用户可以与 (用户) 聊天/Skype for Business通信
        - 组织可以通过Teams外部访问权限，Skype使用者服务的用户[进行通信](manage-external-access.md)
        - Teams尝试登录 Skype for Business Online 的用户会被重定向到Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **会议**
    :::column-end:::
    :::column span="3":::
        - 用户计划已替换为Teams (插件的所有) 
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **迁移的数据**
    :::column-end:::
    :::column span="3":::
        - 来自 Skype for Business Online 的现有联系人，包括联合 (但没有通讯组) 
        - 当用户首次登录到 Teams将迁移联系人。
            > [!IMPORTANT]
            >必须在升级完成后的 90 天内迁移联系人。
        - 现有Skype for Business联机会议将转换为Teams会议
            > [!IMPORTANT]
            > 具有纯 Skype for Business Online 配置的客户需要使用会议迁移服务 (MMS) 将现有 Skype for Business Online 会议迁移到 Teams 会议。 我们建议在辅助升级日期之前使用 MMS。 有关 MMS 详细信息，请参阅 [使用会议迁移服务 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
    :::column-end:::
:::row-end:::

如果有一个Skype for Business Server部署并升级到 Teams，可以在升级完成后Skype for Business Server Teams用户。

## <a name="related-content"></a>相关内容

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [Skype for Business Online 停用](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [仅 Teams 模式注意事项](teams-only-mode-considerations.md)
