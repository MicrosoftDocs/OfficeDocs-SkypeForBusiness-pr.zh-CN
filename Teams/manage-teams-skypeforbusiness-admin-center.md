---
title: 转换为新的 Microsoft 团队和业务管理中心的 Skype 的过程管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 了解如何管理租户范围和团队从团队转换期间的用户设置在 Office 365 管理中心，为新的 Microsoft 团队业务管理中心的 Skype 体验。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 38706497fc83cdc5eea4cafb7177d23d55879bf0
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436625"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>转换为新的 Microsoft 团队和业务管理中心的 Skype 的过程管理团队
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>什么是新的 Microsoft 团队和业务管理中心的 Skype？  

新的管理中心体验将为您提供管理团队和 Skype for Business 的统一体验。 我们提供附加功能、 端到端见解和管理用户级别上的团队设置的功能。

![Microsoft 团队和 Skype 业务管理中心的屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>设置迁移到新的 Microsoft 团队和 Skype 的业务管理中心

下表标识团队体验已迁移并显示新的管理门户中的当前设置和策略之间的关系的部分。

|Office 365 管理中心中的团队的部分  |设置名称 （租户级别）  |Microsoft 团队和 Skype Business Admin Center 策略   |级别： 租户或用户   |
|---------|---------|---------|---------|
|常规     |显示个人配置文件中的组织聊天        |  [TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  租户       |
|常规     |用于未设置团队收件人 Skype for Business         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|常规     |允许 T Bot 主动帮助消息         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许用户向通道发送电子邮件         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|电子邮件集成     |允许的发件人列表         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |租户         |
|自定义云存储     |框         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |收存箱        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |Google 驱动器        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|自定义云存储     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |租户         |
|设置用户/许可证类型     |为所有用户打开或关闭的 Microsoft 团队          |已弃用的<sup>1</sup>        |         |
|团队和频道     |         |重定向到 Azure Active Directory 组管理 （当前体验相同）。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 （当前体验相同）。             |用户          |
|呼叫和会议     |允许安排私人会议         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许点对点通道 meetup         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许安排频道会议         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |在会议中允许视频         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许在会议中共享的屏幕         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |用户          |
|呼叫和会议     |允许专用的呼叫         |[TeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |用户          |
|消息     |启用 Giphy，以便用户可以向对话添加 gif 图像         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |内容评级         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |启用的用户可以编辑并将添加到对话的 memes         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |启用的用户可以编辑并将添加到对话的标签         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |允许所有者删除所有的邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |允许用户编辑其自己的邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |允许用户删除其自己的邮件         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |
|消息     |允许用户私下聊天         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |用户         |

<sup>1</sup>弃用的来宾。 启用/禁用来宾现在中的 Microsoft 团队业务管理中心的 Skype 管理。 启用/禁用团队业务 enterprise，Edu 学生，并将很快弃用 Edu 教职员工。 这应该通过分配许可证在 Office 365 管理中心中的管理。 请参阅[Microsoft 团队管理用户访问](user-access.md)。

> [!NOTE]
> 您将继续在 Office 365 管理中心中配置与团队和频道使用组仪表板。 应用程序设置将保留在 Office 365 管理中心的团队区域，并且将更高版本迁移。 

## <a name="manage-settings-during-the-migration"></a>在迁移期间管理设置

您可以继续修改在 Office 365 管理中心和业务管理中心的 Skype 中的设置，直到完成您的租户的节的迁移。 

下表显示了您可以在迁移期间管理功能。

|功能  |Microsoft 团队和 Skype 的业务管理中心                       |Skype 的业务管理中心 （旧）  |Office 365 管理中心  |
|---------|:---------:|:---------:|:---------:|
|团队消息、 会议和 Live 事件策略     |     X    |         |         |
|团队升级策略     |    X     |         |         |
|来宾消息、 会议和语音设置     |   X      |         |         |
|团队生命周期管理   |    X    |      |       |
|团队设置   |    X    |      |       |
|外部访问设置     |    X    |      |       |
|用户管理    |         |         |    X     |    
|音频会议     |    X     |    X     |         |
|通话套餐     |         |    X     |         |
|电话系统    |         |     X    |         |
|电话号码管理     |         |   X      |         |
|许可使用云语音功能     |         |         |    X     |
|自动助理     |         |    X     |         |
|呼叫队列     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>迁移后管理设置

这些设置的迁移完成后，我们将在 Office 365 管理中心和业务管理中心中，为 Skype 中禁用这些，然后中新的 Microsoft 团队业务管理中心的 Skype 进行管理。


