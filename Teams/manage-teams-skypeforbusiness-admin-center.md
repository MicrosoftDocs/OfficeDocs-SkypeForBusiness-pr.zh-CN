---
title: 管理Teams转换到新Teams管理中心
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 了解如何在 Teams从 Teams 管理中心中的 Teams Microsoft 365 过渡到新的 Teams 管理中心期间，管理租户范围的 Teams 设置。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 875db7be64e23b32f5f758f9f5a701199c068528
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100898"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>管理中心Microsoft Teams是什么  

新的管理中心体验将提供统一的体验来管理Teams Skype for Business。 我们将提供其他功能、端到端见解，以及管理用户Teams设置的功能。

![管理中心Microsoft Teams屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>设置迁移到新的 Microsoft Teams 管理中心

下表标识了已迁移的 Teams部分，并显示了当前设置与新管理门户中的策略之间的关系。

|管理Teams中Microsoft 365部分  |将名称 (租户级别)   |Microsoft Teams管理中心策略   |级别：租户或用户   |
|---------|---------|---------|---------|
|常规     |在个人个人资料中显示组织结构图        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  租户       |
|常规     |对Skype for Business没有邮箱的收件人使用Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许用户向频道发送电子邮件         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许发件人列表         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |租户         |
|自定义云存储     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Google 云端硬盘        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|设置用户/许可证类型     |为Microsoft Teams打开或关闭"          |已弃用<sup>1</sup>        |         |
|团队和频道     |         |重定向到组Azure Active Directory管理 (与当前体验) 。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 (与当前体验) 。             |用户          |
|应用|默认启用新的外部应用|组织范围内的应用设置|租户|
|应用|允许外部应用|组织范围内的应用设置|租户|
|应用|允许旁加载外部应用<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|用户|
|应用|默认应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|应用|外部应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|呼叫和会议     |允许安排私人会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许临时频道会面         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许安排频道会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许会议中的视频         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许在会议中共享屏幕         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许私人通话         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |用户          |
|消息传递     |启用 Giphy，以便用户可以向对话添加 GIF         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |内容分级         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话的 Meme         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |启用用户可编辑和添加到对话的贴纸         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许所有者删除所有邮件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户编辑其自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户删除自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |

<sup>1</sup> 已弃用来宾。 现在可以在管理中心内管理启用/Microsoft Teams来宾。 启用/禁用 Teams for Business Enterprise、Edu Student 和 Edu 教职员工很快将被弃用。 这应该通过向管理中心分配许可证Microsoft 365进行管理。 请参阅[管理用户对 Microsoft Teams](user-access.md)的访问权限。
<br><br>
<sup>2</sup> 旁加载拆分如下：

- 允许用户旁加载可在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)中的用户级别管理的应用。
- 允许租户中的用户与可在组织范围应用设置中的租户级别管理的自定义应用交互。

<sup>3</sup> 可以在 TeamsAppPermissionPolicy 的用户级别启用和禁用默认应用和外部应用。 此外，可以在组织范围的应用设置中在租户级别阻止应用，从而覆盖任何用户和租户级别的设置。

> [!NOTE]
> 对于与订阅和频道相关的配置，Microsoft 365管理中心中的组Teams。 设置应用的应用将保留在 Teams 管理Microsoft 365区域，稍后将迁移。

## <a name="manage-settings-during-the-migration"></a>在迁移过程中管理设置

在租户的分区迁移Microsoft 365，可以继续修改 Skype for Business 管理中心中的设置。

下表显示了在迁移过程中可以管理功能的地方。

|功能  |Microsoft Teams管理中心                      |Skype for Business管理中心 (旧版)   |Microsoft 365管理中心  |
|---------|:---------:|:---------:|:---------:|
|Teams消息、会议和实时事件策略     |     X    |         |         |
|Teams升级策略     |    X     |         |         |
|消息、会议和语音的来宾设置     |   X      |         |         |
|Teams生命周期管理   |    X    |      |       |
|Teams 设置   |    X    |      |       |
|外部访问设置     |    X    |      |       |
|用户管理    |         |         |    X     |
|音频会议     |    X     |    X     |         |
|通话计划     |    X    |    X     |         |
|电话系统    |    X    |     X    |         |
|电话数字管理     |    X    |   X      |         |
|云语音功能许可     |         |         |    X     |
|自动助理     |    X    |          |         |
|呼叫队列     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>在迁移后管理设置

完成这些设置的迁移后，我们将在 Microsoft 365 管理中心和 Skype for Business 管理中心中禁用这些设置，然后可以在新的 Microsoft Teams 管理中心中管理这些设置。