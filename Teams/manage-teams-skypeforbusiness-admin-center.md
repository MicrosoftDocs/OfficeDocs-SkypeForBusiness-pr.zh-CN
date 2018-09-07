---
title: 转换为新的 Microsoft 团队和业务管理中心的 Skype 的过程管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 了解如何管理租户范围和团队从团队转换期间的用户设置 Office 365 管理中心到新的 Microsoft 团队和业务管理中心的 Skype 的体验。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: b81853b33f457dd8a69890774b4b7ff8902d8226
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864824"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>转换为新的 Microsoft 团队和业务管理中心的 Skype 的过程管理团队
======================================================

全新的 Microsoft Teams 和 Skype for Business 管理中心即将推出！ 

从年 3 月 2018年开始，我们正在逐步迁移设置到 Microsoft 团队和业务管理中心的 Skype 从业务管理中心的两个当前 Skype 和 Office 365 管理中心中的 Microsoft 团队体验。 某项设置迁移完成后，你将收到通知，并被定向到该设置在新 Microsoft Teams 和 Skype for Business 管理中心中的位置。

我们将继续迁移从业务管理中心的 Skype 在几个月中的其他功能。 您可以随时了解最新通过我们公共[路线图](https://aka.ms/Office365Roadmap)。

> [!NOTE]
> 我们正在推出新的 Microsoft 团队和 Skype 业务管理中心的分阶段。 因此，所有客户将不会看到新的 Admin Center 在同一时间。 您可以开始使用新的 Admin Center 时，我们将通知您。

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>什么是新的 Microsoft 团队和业务管理中心的 Skype？  

新的 Admin Center 体验将为您提供管理团队和 Skype for Business 的统一体验。 我们提供附加功能、 端到端见解和管理用户级别上的团队设置的功能。

![Microsoft 团队和 Skype 业务管理中心的屏幕截图。](media/manage-teams-skype-for-business-admin-center-portal.png)


从中间年 3 月 2018年，以下功能已在新的 Microsoft 团队和 Skype 的业务管理中心中可用： 

- **Microsoft 团队邮件策略**： 创建用于用户级管理的消息方案的 Microsoft 团队客户端体验的策略。
- **Microsoft 团队升级策略**： 配置 Microsoft 团队之间 for Business 的 Skype 的互操作性和升级体验。 请参阅， https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype。 
- **消息设置的 Microsoft 团队来宾**： 控制中的 Microsoft 团队的来宾帐户的消息功能。 
- **联合身份验证设置**： 管理 Microsoft 团队的租户之间 for Business 的 Skype 联合身份验证。 
- **用户管理**： 分配策略和配置用户帐户。 
- **音频会议**： 配置电话拨入式号码和 Skype 的业务和 Microsoft 团队的设置。 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>设置迁移到新的 Microsoft 团队和 Skype 的业务管理中心

常规、 电子邮件集成、 自定义云存储、 呼叫和会议和消息中的 Microsoft 团队的现有设置 （请参阅下面的图像） 将迁移到新的 Microsoft 团队和 Skype 的业务 Admin Center （也称为新管理门户）在下一步的几个月。 



> [!NOTE]
>您将继续在 Office 365 管理中心中配置与**团队和频道**使用组仪表板。 **应用**程序设置将保留在 Office 365 管理中心的团队区域，并且将更高版本迁移。 

![Office 365 管理中心中的屏幕快照的团队页。](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

相对于中**设置用户/许可证类型**提供设置，它本质上提供不同配置的用户组的方法。 现在，使用新的管理门户中，您可以执行操作的基于每个用户。 


将迁移的许可证类型设置。 如果当前使用的**打开的 Microsoft 团队打开或关闭此类型的所有用户的**设置来控制用户对团队的访问跨 Sku，我们将保持当前配置。 但是，您将无法修改新的管理门户中的此设置。 相反，您将通过 Office 365 管理中心租户中向用户分配相应的许可证。 有关详细信息，请参阅[Microsoft 团队管理用户访问](user-access.md)。 

下表标识了将迁移和新的管理门户中显示的当前设置和策略之间的关系的当前团队体验的部分。


|Office 365 管理中心中的团队的部分  |设置名称 （租户级别）  |Microsoft 团队和 Skype Business Admin Center 策略   |级别： 租户或用户   |
|---------|---------|---------|---------|
|常规     |显示个人配置文件中的组织聊天        |  TeamsClientConfiguration       |  租户       |
|常规     |用于未设置团队收件人 Skype for Business         |TeamsClientConfiguration         |租户         |
|常规     |允许 T Bot 主动帮助消息         |TeamsClientConfiguration         |租户         |
|电子邮件集成     |允许用户向通道发送电子邮件         |TeamsClientConfiguration         |租户         |
|电子邮件集成     |允许的发件人列表         |TeamsClientConfiguration        |租户         |
|自定义云存储     |框         |TeamsClientConfiguration         |租户         |
|自定义云存储     |收存箱        |TeamsClientConfiguration         |租户         |
|自定义云存储     |Google 驱动器        |TeamsClientConfiguration         |租户         |
|自定义云存储     |ShareFile        |TeamsClientConfiguration         |租户         |
|设置用户/许可证类型     |为所有用户打开或关闭的 Microsoft 团队          |已弃用。 使用 Office 365 管理中心分配许可证。        |         |
|团队和频道     |         |重定向到 Azure Active Directory 组管理 （当前体验相同）。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 （当前体验相同）。             |用户          |
|呼叫和会议     |允许安排私人会议         |TeamsMeetingPolicy         |用户          |
|呼叫和会议     |允许点对点通道 meetup         |TeamsMeetingPolicy         |用户          |
|呼叫和会议     |允许安排频道会议         |TeamsMeetingPolicy         |用户          |
|呼叫和会议     |在会议中允许视频         |TeamsMeetingPolicy         |用户          |
|呼叫和会议     |允许在会议中共享的屏幕         |TeamsMeetingPolicy         |用户          |
|呼叫和会议     |允许专用的呼叫         |TeamsCallingPolicy         |用户          |
|消息     |启用 Giphy，以便用户可以向对话添加 gif 图像         |TeamsMessagingPolicy         |用户         |
|消息     |内容评级         |TeamsMessagingPolicy         |用户         |
|消息     |启用的用户可以编辑并将添加到对话的 memes         |TeamsMessagingPolicy         |用户         |
|消息     |启用的用户可以编辑并将添加到对话的标签         |TeamsMessagingPolicy         |用户         |
|消息     |允许所有者删除所有的邮件         |TeamsMessagingPolicy         |用户         |
|消息     |允许用户编辑其自己的邮件         |TeamsMessagingPolicy         |用户         |
|消息     |允许用户删除其自己的邮件         |TeamsMessagingPolicy         |用户         |
|消息     |允许用户私下聊天         |TeamsMessagingPolicy         |用户         |



## <a name="manage-settings-during-the-migration"></a>在迁移期间管理设置

我们计划迁移的以下序列中的各节中的团队设置： 消息、 会议、 通话和最后，TeamsClient 配置策略内的分区 (常规，电子邮件集成和自定义云存储)。   

您可以继续修改 Office 365 管理中心和业务管理中心的 Skype 中的设置，直到完成您的租户的节的迁移。 

下表显示了您可以在迁移期间管理功能。

|功能  |Microsoft 团队和 Skype 的业务管理中心                       |Skype 的业务 Admin Center （旧）  |Office 365 管理中心  |
|---------|:---------:|:---------:|:---------:|
|邮件策略     |     X    |         |         |
|团队互操作性策略     |    X     |         |         |
|来宾消息设置     |   X      |         |         |
|外部访问设置    |    X     |         |         |
|用户管理    |         |         |    X     |    
|音频会议     |    X     |    X     |         |
|通话套餐     |         |    X     |         |
|电话系统    |         |     X    |         |
|电话号码管理     |         |   X      |         |
|许可使用云语音功能     |         |         |    X     |
|自动助理     |         |    X     |         |
|呼叫队列     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>迁移后管理设置

团队中的特定部分已完成迁移后，我们将通知您。 此时，您将能够看到您在 Office 365 管理中心，该节的现有设置，但您将无法进行任何修改有。 相反，您将使用的 Microsoft 团队和 Skype 业务管理中心的可管理的新迁移的设置。

这些设置的迁移完成后，我们将在 Office 365 管理中心和业务管理中心的 Skype 禁用它们。


