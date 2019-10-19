---
title: 在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 了解如何在从 Microsoft 365 管理中心的团队体验切换到新的 Microsoft 团队管理中心时管理团队的租户范围和用户设置。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0d473ffa67b21c4ec3a160a8687a1688ea1d1cf5
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37564782"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>什么是新的 Microsoft 团队管理中心？  

新的管理中心体验将为你提供统一的体验来管理团队和 Skype for business。 我们正在提供其他功能、端到端见解以及管理用户级别的团队设置的功能。

![Microsoft 团队管理中心的屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>已迁移到新 Microsoft 团队管理中心的设置

下表标识了已迁移的团队体验部分，并显示了当前设置与新管理门户中的策略之间的关系。

|Microsoft 365 管理中心中的团队部分  |设置名称（租户级别）  |Microsoft 团队管理员中心策略   |级别：租户或用户   |
|---------|---------|---------|---------|
|常规     |在个人资料中显示组织结构图        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  租户       |
|常规     |对没有团队的收件人使用 Skype for Business         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许用户向频道发送电子邮件         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许发件人列表         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |租户         |
|自定义云存储     |箱         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|按用户/许可证类型设置     |为所有用户打开或关闭 Microsoft 团队          |已弃用<sup>1</sup>        |         |
|团队和频道     |         |重定向到 Azure Active Directory 组管理（与当前体验相同）。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理（与当前体验相同）。             |用户          |
|应用|默认启用新的外部应用|组织范围内的应用设置|租户|
|应用|允许外部应用|组织范围内的应用设置|租户|
|应用|允许旁加载外部应用<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|用户|
|应用|默认应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|应用|外部应用<sup>3</sup>|TeamsAppPermissionPolicy|用户|
|通话和会议     |允许针对私人会议进行日程排定         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|通话和会议     |允许临时频道聚会         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|通话和会议     |允许针对频道会议进行日程安排         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|通话和会议     |允许会议中的视频         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|通话和会议     |允许在会议中共享屏幕         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|通话和会议     |允许专用呼叫         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |用户          |
|消息传递     |启用 Giphy，以便用户可以将 gif 添加到对话         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |内容分级         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话的 meme         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |启用用户可以编辑和添加到对话中的不干胶标签         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许所有者删除所有邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户编辑自己的邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户删除自己的邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息传递     |允许用户私下聊天         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |

<sup>1</sup>已弃用来宾。 现在可以在 Microsoft 团队管理中心中管理启用/禁用来宾。 启用/禁用团队 for Business 企业版、教育机构学生版和教育机构教职员工将很快被弃用。 这应该通过在 Microsoft 365 管理中心分配许可证来管理。 请参阅[管理用户对 Microsoft 团队的访问权限](user-access.md)。
<br><br>
<sup>2</sup>个旁加载按如下方式拆分：

- 允许用户在[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)中的用户级别上管理可管理的应用旁加载应用。
- 允许租户中的用户与可在组织范围内应用设置中的租户级别管理的自定义应用交互。
 
<sup>3</sup>在 TeamsAppPermissionPolicy 中的用户级别上，可以启用和禁用默认应用和外部应用。 此外，可以在组织范围内应用设置中的租户级别阻止应用，这些应用会覆盖任何用户和租户级别的设置。 

> [!NOTE]
> 对于与团队和频道相关的配置，您将继续使用 Microsoft 365 管理中心中的组仪表板。 应用的设置将保留在 Microsoft 365 管理中心的 "团队" 区域中，稍后将进行迁移。 

## <a name="manage-settings-during-the-migration"></a>在迁移过程中管理设置

你可以继续修改 Microsoft 365 管理中心和 Skype for business 管理中心中的设置，直到针对你的租户完成了分区的迁移。 

下表显示了在迁移期间可以管理功能的位置。

|功能  |Microsoft 团队管理中心                      |Skype for business 管理中心（旧版）  |Microsoft 365 管理中心  |
|---------|:---------:|:---------:|:---------:|
|团队消息、会议和实时事件策略     |     X    |         |         |
|团队升级策略     |    X     |         |         |
|邮件、会议和语音的来宾设置     |   X      |         |         |
|团队生命周期管理   |    X    |      |       |
|团队设置   |    X    |      |       |
|外部访问设置     |    X    |      |       |
|用户管理    |         |         |    X     |    
|音频会议     |    X     |    X     |         |
|通话计划     |         |    X     |         |
|电话系统    |         |     X    |         |
|电话号码管理     |         |   X      |         |
|云语音功能的许可     |         |         |    X     |
|自动助理     |         |    X     |         |
|呼叫队列     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>迁移后管理设置

完成这些设置的迁移后，我们将在 Office 365 管理中心和 Skype for business 管理中心中禁用它们，然后可以在新的 Microsoft 团队管理中心中管理它们。


## <a name="edu-migration-june-july-2019"></a>教育机构迁移6月2019日

在六月和七月2019中，剩余的教育机构租户将从旧的管理员体验（在 Microsoft 365 管理中心内）迁移到团队管理中心。 检查 "消息中心" （在 Microsoft 365 管理中心内），了解迁移时间。 下面是迁移后将看到的内容：

|Microsoft 365 管理中心中的团队部分  |设置名称（租户级别）  |Microsoft 团队管理员中心策略   |级别：租户或用户   |
|---------|---------|---------|---------|  
| 消息传递  |所有者可以删除已发送的邮件 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递 | 用户可以删除已发送的邮件 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递  | 用户可以编辑已发送的邮件 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |用户|
| 消息传递 | 允许用户聊天 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递 | 在对话中使用 Giphy | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递 | Giphy 内容分级 | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递 | 在对话中使用 meme  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
| 消息传递 | 在对话中使用贴纸 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |

此外，以下是仅适用于 Microsoft 团队管理中心的设置：

|设置名称 | Microsoft 团队管理员中心策略 | 级别：租户或用户
|-------------|-------------------------------------|---------|
|允许 URL 预览 | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
|允许用户从群组聊天中删除用户 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
|允许沉浸式阅读器查看邮件 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| 用户 |
|允许用户翻译邮件 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| 用户 |
|已读回执 | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
|用户可以发送优先级通知 | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | 用户 |
|语音消息创建 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| 用户 |
|在移动设备上，在最近的聊天上显示收藏频道 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| 用户 |
