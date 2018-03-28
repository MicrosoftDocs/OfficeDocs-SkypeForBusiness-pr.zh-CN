---
title: 转换为新的 Microsoft 小组和业务管理中心的 Skype 的过程管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 了解如何管理租户范围和用户设置为团队时从团队的过渡经验在 Office 365 管理中心新的 Microsoft 小组与业务管理中心的 Skype。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0f660130ce9fe2973178385e87433cac29fa8733
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>转换为新的 Microsoft 小组和业务管理中心的 Skype 的过程管理团队
======================================================

全新的 Microsoft Teams 和 Skype for Business 管理中心即将推出！ 

从 3 月 2018 年开始，我们正在逐渐迁移设置到 Microsoft 小组和业务管理中心的 Skype 从业务管理中心为这两个当前 Skype 和 Microsoft 小组在 Office 365 管理中心体验。 某项设置迁移完成后，你将收到通知，并被定向到该设置在新 Microsoft Teams 和 Skype for Business 管理中心中的位置。

我们将继续在接下来的几个月中从业务管理中心为 Skype 迁移其他功能。 您可以随时了解最新通过我们公共的[路线图](https://aka.ms/Office365Roadmap)。

> [!NOTE]
> 我们正在推出新的 Microsoft 小组和 Skype 业务管理中心的阶段。 结果，所有客户将不在同一时间看到新管理中心。 我们将通知您，当您可以开始使用新的管理中心。

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>新的 Microsoft 小组和业务管理中心的 Skype 是什么？  

新的中心管理经验将为您提供统一的体验来管理团队和业务的 Skype。 我们提供额外的功能、 端到端的见解和管理团队设置在用户级别上的能力。

![Microsoft 的团队和业务管理中心的 Skype 的屏幕快照。](media/manage-teams-skype-for-business-admin-center-portal.png)


从中间 3 月 2018年，以下功能将为中新的 Microsoft 小组和业务管理中心的 Skype 可用： 

- **Microsoft 小组邮件策略**： 创建消息传递方案的 Microsoft 小组客户端体验的用户级管理的策略。
- **Microsoft 小组互操作策略**： 配置业务的 Skype 和 Microsoft 小组之间的互操作性体验。
- **消息设置 Microsoft 小组来宾**： 控制的消息传递功能的 Microsoft 小组中的来宾帐户。 
- **联盟设置**： 管理 Microsoft 小组的承租人和 Skype 为企业之间的联盟。 
- **用户管理**： 分配策略和配置用户帐户。 
- **音频会议**： 配置拨入号码和 Skype 业务和 Microsoft 小组的设置。 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>设置迁移到新的 Microsoft 小组和 Skype 的业务管理中心

现有设置的常规、 电子邮件集成、 自定义云存储、 联络和会议和在 Microsoft 小组的消息 （请参见下图所示） 将被迁移到新的 Microsoft 小组和 Skype 的业务管理中心 （也称为新管理门户）在接下来的几个月。 



> [!NOTE]
>将继续在 Office 365 管理中心组面板用于配置与**团队和渠道**。 设置**应用程序**都将保留在 Office 365 管理中心的团队区域并将稍后迁移。 

![在 Office 365 管理中心屏幕截图的小组页面。](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

有关**设置用户/许可证类型**中可用的设置中，它实质上被提供以不同的方式配置的用户组的方法。 现在，使用新的管理门户，您可以做到基于每个用户。 


许可证类型设置将被迁移。 如果您当前使用**打开 Microsoft 小组打开或关闭此类型的所有用户**设置来控制用户对小组的访问跨 Sku，我们将保留您当前的配置。 但是，您无法修改此设置的新的管理门户。 相反，将在您的组织通过 Office 365 管理中心向用户分配相应的许可证。 有关详细信息，请参阅[Microsoft 小组管理用户访问](user-access.md)。 

下表列出了当前团队经验将迁移并显示新的管理门户中的当前设置以及策略之间的关系的部分。


|在 Office 365 管理中心团队中的一节  |设置名称 （租户等级）  |Microsoft 的小组和 Skype 业务管理中心策略   |级别： 租户或用户   |
|---------|---------|---------|---------|
|常规     |在个人资料中显示组织的聊天        |  TeamsClientConfiguration       |  租户       |
|常规     |使用 Skype 为收件人没有团队的业务的         |TeamsClientConfiguration         |租户         |
|常规     |允许 T Bot 主动帮助消息         |TeamsClientConfiguration         |租户         |
|电子邮件集成     |允许用户将电子邮件发送到通道         |TeamsClientConfiguration         |租户         |
|电子邮件集成     |允许的发件人列表         |TeamsClientConfiguration        |租户         |
|自定义云存储     |框中         |TeamsClientConfiguration         |租户         |
|自定义云存储     |收存箱        |TeamsClientConfiguration         |租户         |
|自定义云存储     |Google 的驱动器        |TeamsClientConfiguration         |租户         |
|自定义云存储     |ShareFile        |TeamsClientConfiguration         |租户         |
|按用户/许可证类型的设置     |为所有用户启用 Microsoft 小组打开或关闭          |不建议使用。 使用 Office 365 管理中心分配许可证。        |         |
|团队和频道     |         |重定向到 Azure 活动目录组管理 （当前体验相同）。              |用户         |
|团队和频道     |         |重定向到 AAD 组管理 （当前体验相同）。             |用户          |
|联络和会议     |允许安排私人会议         |TeamsMeetingPolicy         |用户          |
|联络和会议     |允许临时通道 meetup         |TeamsMeetingPolicy         |用户          |
|联络和会议     |允许安排频道会议         |TeamsMeetingPolicy         |用户          |
|联络和会议     |允许会议中的视频         |TeamsMeetingPolicy         |用户          |
|联络和会议     |允许在会议中共享的屏幕         |TeamsMeetingPolicy         |用户          |
|联络和会议     |允许私人电话         |TeamsCallingPolicy         |用户          |
|消息     |启用 Giphy，以便用户可添加到对话的 gif 图像         |TeamsMessagingPolicy         |用户         |
|消息     |内容分级         |TeamsMessagingPolicy         |用户         |
|消息     |使用户能够编辑和添加到对话 memes         |TeamsMessagingPolicy         |用户         |
|消息     |使用户能够编辑和添加到对话的不干胶标签         |TeamsMessagingPolicy         |用户         |
|消息     |允许所有者删除的所有邮件         |TeamsMessagingPolicy         |用户         |
|消息     |允许用户编辑他们自己的邮件         |TeamsMessagingPolicy         |用户         |
|消息     |允许用户删除自己的邮件         |TeamsMessagingPolicy         |用户         |
|消息     |使用户能够私下聊天         |TeamsMessagingPolicy         |用户         |



## <a name="manage-settings-during-the-migration"></a>在迁移期间管理设置

我们打算迁移团队在以下序列中的各节中的设置： 消息、 会议、 电话，以及最后，TeamsClient 配置策略内的分区 (常规，电子邮件集成和自定义云存储)。   

您可以继续修改 Office 365 管理中心和 Skype 业务管理中心的设置，直到迁移部分已经完成了您的租户。 

下表显示了您可以在迁移期间管理功能。

|功能  |Microsoft 的小组和 Skype 的业务管理中心                       |Skype 的业务管理中心 （传统）  |Office 365 管理中心  |
|---------|:---------:|:---------:|:---------:|
|邮件策略     |     X    |         |         |
|团队互操作策略     |    X     |         |         |
|访客消息设置     |   X      |         |         |
|外部访问设置    |    X     |         |         |
|用户管理    |         |         |    X     |    
|音频会议     |    X     |    X     |         |
|通话套餐     |         |    X     |         |
|电话系统    |         |     X    |         |
|电话号码管理     |         |   X      |         |
|授权的云语音功能     |         |         |    X     |
|自动助理     |         |    X     |         |
|呼叫队列     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>迁移后管理设置

我们将通知您，在团队中的特定部分已完成迁移后。 那时，您将能够查看现有设置该节在 Office 365 管理中心，但不能进行有任何修改。 相反，您将使用 Microsoft 小组和 Skype 业务管理中心的管理新迁移的设置。

这些设置在迁移完成后，我们会在 Office 365 管理中心和业务管理中心为 Skype 来禁用它们。


