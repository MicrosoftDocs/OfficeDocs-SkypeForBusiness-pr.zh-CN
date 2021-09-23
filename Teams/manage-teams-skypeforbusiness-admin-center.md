---
title: 管理Teams转换到新Teams管理中心
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Teams从 Teams 中心转换到新的 Teams 管理中心Teams Microsoft 365 管理中心租户范围和Teams设置。
ms.localizationpriority: medium
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
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491732"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>管理中心Microsoft Teams是什么  

新的管理中心体验将提供统一的体验来管理Teams Skype for Business。 我们将提供其他功能、端到端见解，以及管理用户Teams设置的功能。

![管理中心Microsoft Teams屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>设置迁移到新的 Microsoft Teams 管理中心

下表列出了已迁移Teams体验的各个部分，并显示了当前设置与新管理门户中的策略之间的关系。

|Teams中的Microsoft 365 管理中心  |将名称 (租户级别)   |Microsoft Teams管理中心策略   |级别：租户或用户   |
|---------|---------|---------|---------|
|常规     |在个人个人资料中显示组织结构图        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  租户       |
|常规     |对Skype for Business没有邮箱的收件人使用Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|电子邮件集成     |允许用户向频道发送电子邮件         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|电子邮件集成     |允许发件人列表         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |租户         |
|自定义云存储     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Google 云端硬盘        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|设置用户/许可证类型显示     |为Microsoft Teams打开或关闭"          |已弃用<sup>1</sup>        |         |
|团队和频道     |         |重定向到组Azure Active Directory管理 (与当前体验) 。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 (与当前体验) 。             |用户          |
|应用|默认启用新的外部应用|组织范围内的应用设置|租户|
|应用|允许外部应用|组织范围内的应用设置|租户|
|应用|允许旁加载外部应用<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|用户|
|应用|默认应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|应用|外部应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|呼叫和会议     |允许安排私人会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|呼叫和会议     |允许临时频道会面         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|呼叫和会议     |允许安排频道会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|呼叫和会议     |允许会议中的视频         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|呼叫和会议     |允许在会议中共享屏幕         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|呼叫和会议     |允许私人通话         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |用户          |
|消息传递     |启用 Giphy，以便用户可以向对话添加 GIF         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |内容分级         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话的 Meme         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |启用用户可编辑和添加到对话的贴纸         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许所有者删除所有邮件         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户编辑其自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户删除自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |

<sup>1</sup> 已弃用来宾。 现在可以在管理中心管理启用/Microsoft Teams来宾。 很快将弃Teams/禁用 Enterprise for Business Enterprise、Edu Student 和 Edu 教职员工。 这应该通过分配许可证管理Microsoft 365 管理中心。 请参阅[管理用户对 Microsoft Teams](user-access.md)的访问权限。
<br><br>
<sup>2</sup> 旁加载拆分如下：

- 允许用户旁加载可在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)中的用户级别管理的应用。
- 允许租户中的用户与可在组织范围应用设置中的租户级别管理的自定义应用交互。

<sup>3</sup> 可以在 TeamsAppPermissionPolicy 的用户级别启用和禁用默认应用和外部应用。 此外，可以在组织范围的应用设置中在租户级别阻止应用，从而覆盖任何用户和租户级别的设置。

> [!NOTE]
> 对于与频道和频道相关的Microsoft 365 管理中心，将继续使用"组Teams仪表板。 设置应用的应用将保留在Teams区域，Microsoft 365 管理中心稍后迁移。

## <a name="manage-settings-during-the-migration"></a>在迁移过程中管理设置

在租户的分区迁移Microsoft 365 管理中心，可以继续Skype for Business管理中心中的设置。

下表显示了在迁移过程中可以管理功能的地方。

|功能  |Microsoft Teams管理中心                      |Skype for Business管理中心 (旧版)   |Microsoft 365 管理中心  |
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

完成这些设置的迁移后，我们将在 Microsoft 365 管理中心 和 Skype for Business 管理中心中禁用这些设置，然后可以在新的 Microsoft Teams 管理中心中管理这些设置。
