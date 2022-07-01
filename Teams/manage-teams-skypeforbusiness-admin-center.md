---
title: 管理 Teams 过渡到新的 Teams 管理中心
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在从 Microsoft 365 管理中心 中的 Teams 过渡到新的 Teams 管理中心期间管理 Teams 的租户范围和用户设置。
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
ms.openlocfilehash: 39566c490a5de37adc699c39c049717525bd5821
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563950"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>什么是新的 Microsoft Teams 管理中心  

新的管理中心体验将为你提供统一的体验来管理 Teams 和Skype for Business。 我们将提供其他功能、端到端见解，以及在用户级别管理 Teams 设置的能力。

![Microsoft Teams 管理中心的屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>迁移到新的 Microsoft Teams 管理中心的设置

下表标识已迁移的 Teams 体验部分，并显示当前设置与新管理门户中的策略之间的关系。

|Microsoft 365 管理中心中的 Teams 部分  |设置租户级别 (名称)   |Microsoft Teams 管理中心策略   |级别：租户或用户   |
|---------|---------|---------|---------|
|常规     |在个人配置文件中显示组织图表        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  租户       |
|常规     |对没有 Teams 的收件人使用Skype for Business         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|电子邮件集成     |允许用户向频道发送电子邮件         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|电子邮件集成     |允许发件人列表         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |租户         |
|自定义云存储     |箱         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|自定义云存储     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |租户         |
|按用户/许可证类型设置     |为所有用户打开或关闭 Microsoft Teams          |已弃用<sup>1</sup>        |         |
|团队和频道     |         |重定向到 Azure Active Directory 组管理 (与当前体验) 相同。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 (与当前体验) 相同。             |用户          |
|应用|默认启用新的外部应用|组织范围的应用设置|租户|
|应用|允许外部应用|组织范围的应用设置|租户|
|应用|允许旁加载外部应用<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|用户|
|应用|默认应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|应用|外部应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|通话和会议     |允许安排私人会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|通话和会议     |允许即席通道会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|通话和会议     |允许安排频道会议         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|通话和会议     |允许会议中的视频         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|通话和会议     |允许在会议中共享屏幕         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |用户          |
|通话和会议     |允许专用呼叫         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |用户          |
|消息传递     |启用 Giphy，以便用户可以将 GIF 添加到对话         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |内容分级         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话的模因         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话的贴纸         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许所有者删除所有消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户编辑自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户删除自己的消息         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |
|消息传递     |允许用户私下聊天         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |用户         |

<sup>1</sup> 已弃用来宾。 现在可以在 Microsoft Teams 管理中心管理启用/禁用来宾。 启用/禁用 Teams for Business Enterprise、Edu Student 和 Edu 教职员工将很快弃用。 这应该通过在Microsoft 365 管理中心中分配许可证来进行管理。 请参阅 [“管理用户对 Microsoft Teams 的访问权限](user-access.md)”。
<br><br>
<sup>2</sup> 旁加载拆分，如下所示：

- 允许用户旁加载可在 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy) 中的用户级别管理的应用。
- 允许租户中的用户与可在组织范围应用设置中的租户级别管理的自定义应用进行交互。

<sup>3</sup> 可在 TeamsAppPermissionPolicy 的用户级别启用和禁用默认应用和外部应用。 此外，在覆盖任何用户和租户级别设置的组织范围的应用设置中，可以在租户级别阻止应用。

> [!NOTE]
> 你将继续使用Microsoft 365 管理中心中的“组”仪表板进行与 Teams 和频道相关的配置。 应用设置将保留在Microsoft 365 管理中心的 Teams 区域，稍后将迁移。

## <a name="manage-settings-during-the-migration"></a>在迁移期间管理设置

可以继续修改Microsoft 365 管理中心和Skype for Business管理中心的设置，直到租户完成分区的迁移。

下表显示了在迁移期间可以管理功能的位置。

|功能  |Microsoft Teams 管理中心                      |Skype for Business管理中心 (旧)   |Microsoft 365 管理中心  |
|---------|:---------:|:---------:|:---------:|
|Teams 消息传送、会议和实时事件策略     |     X    |         |         |
|Teams 升级策略     |    X     |         |         |
|消息传送、会议和语音的来宾设置     |   X      |         |         |
|Teams 生命周期管理   |    X    |      |       |
|Teams 设置   |    X    |      |       |
|外部访问设置     |    X    |      |       |
|用户管理    |         |         |    X     |
|音频会议     |    X     |    X     |         |
|呼叫计划     |    X    |    X     |         |
|电话系统    |    X    |     X    |         |
|电话号码管理     |    X    |   X      |         |
|云语音功能许可     |         |         |    X     |
|自动助理     |    X    |          |         |
|呼叫队列     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>在迁移后管理设置

这些设置的迁移完成后，我们将在Microsoft 365 管理中心和Skype for Business管理中心中禁用它们，然后可以在新的 Microsoft Teams 管理中心管理这些设置。
