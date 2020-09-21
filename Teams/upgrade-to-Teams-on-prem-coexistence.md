---
title: 与 Microsoft 团队和 Skype for business 共存
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到团队-共存
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955959"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>与团队和 Skype for business 共存

本文概述了在同一组织中运行团队和 Skype for business 客户端时可能遇到的问题，无论使用的是何种模式和使用哪种升级方法：

- [会议](#meetings)
- [交互性](#interoperability)
- [团队对话-互操作与本机线程](#teams-conversations---interop-versus-native-threads)
- [状态](#presence)
- [联合身份验证](#federation)
- [联系人](#contacts)



## <a name="meetings"></a>会议

无论其模式如何，用户始终可以加入受邀的任何类型的会议，无论是 Skype for business 还是团队。  但是，用户必须使用与会议类型匹配的相应客户端加入会议：

- 如果会议是团队会议，则所有参与者 (他们是 TeamsOnly、孤岛还是 Skype for business 用户) 使用团队客户加入会议。 如果未安装团队，则在尝试加入会议时，用户将转到 web。

- 如果会议是 Skype for business 会议，则所有 (参与者无论是 TeamsOnly、孤岛还是 Skype for business 用户) 使用 Skype for business 客户端加入会议。 如果未安装 Skype for Business 客户端，用户将通过 Skype 会议应用定向到 web 以加入。

组织会议时，计划的会议类型基于组织者的模式，如下表所示：

| 组织者模式    |      行为 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    在团队中安排的所有会议。 Outlook 中不提供 Skype for business 加载项。 | 
| SfbWithTeamsCollab, SfbOnly   | Skype for Business 中安排的所有会议。 "团队外接程序" 在 Outlook 中不可用。 | 
| 孤岛 | 默认情况下，可以在 Skype for Business 或团队中安排会议。 Outlook 中提供了这两个加载项。 但是，你可以选择要求在 TeamsMeetingPolicy 中的用户始终通过使用 PreferredMeetingProviderForIslandsMode = 团队向团队分配会议实例来安排团队中的会议。| 


## <a name="interoperability"></a>交互性

在某些情况下，团队支持与 Skype for Business ) 互操作性 ( "互操作"。 互操作通信指的是 Skype for Business 用户与团队用户之间的聊天或通话。  互操作通信仅在两个用户之间可用;不支持多方聊天/通话或添加其他用户。

当满足以下每个条件时，将创建两个用户之间的互操作聊天或呼叫：

- 一个用户使用的是团队，另一个用户使用的是 Skype for Business。

- 初始通信的收件人模式不是孤岛 (否则，如果两个用户都在同一个组织中，则通信将位于同一客户端) 。 在联合方案中，发送用户使用团队，而收件人不处于 TeamsOnly 模式。 

- 团队用户还没有驻留在本地的 Skype for business 帐户。 

在互操作通信中，聊天仅为纯文本。 此外，在 *互操作聊天中*不能进行文件共享和屏幕共享。 但是，互操作对话中的用户可以通过创建按需会议（如下所述）轻松实现文件和/或屏幕共享。

- 如果团队用户尝试共享其屏幕，将自动创建按需团队会议，并将邀请链接发送到 Skype for Business 用户的客户端。 单击该链接后，Skype for Business 用户将打开团队并加入会议。 两个用户现在都在团队会议中，可以根据需要进行共享。

- 如果 Skype for Business 用户使用的是2018或更高版本的客户端，并且尝试共享任何内容，则会自动创建一个按需 Skype for business 会议，并将邀请链接发送到团队用户的客户端。 单击该链接后，团队用户将尝试加入 Skype for Business 会议。 如果团队用户安装了 Skype for Business 客户端，它将打开，并且系统会提示用户登录 (（如果尚未登录) ）。  如果团队用户没有安装 Skype for business 客户端，系统将提示用户使用 web 版本。 这两个用户登录后，他们都在 Skype for business 会议中，并且可以根据需要进行共享。

## <a name="teams-conversations---interop-versus-native-threads"></a>团队对话-互操作与本机线程

由于互操作通信不支持本机团队对话的所有功能，因此团队客户为团队到团队和团队到 Skype for business 通信保留单独的对话线程。 这些对话在用户界面中的呈现方式不同：互操作线程可以通过以下方式与常规本机团队线程区别：

- 缺少格式文本、文件/屏幕共享的控件，无法添加用户。
- 对目标用户的图标的修改，显示 Skype for business 的 "S"。

以下屏幕截图显示了这些差异：

与用户 G3 测试的本机团队间对话

![显示本机团队间对话的图表](media/teams-upgrade-native-thread.png)

具有相同用户 G3 测试的互操作对话

![显示互操作团队到团队对话的图表](media/teams-upgrade-interop-thread.png)

一旦创建了对话线程，其类型将永远不会更改。 创建后，团队中的互操作线程将始终路由到目标用户的 Skype for Business 客户端。 本机线程将始终路由到目标用户的团队客户端。  如果收件人用户的模式发生更改，则该用户的现有团队线程将不再运行，并且将在该聊天上显示一条注释，其中包含用于启动新的本机对话的链接，如以下屏幕截图所示。


![显示已升级的 Skype for Business 用户的聊天的图表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>状态

特定用户的状态基于通过客户端提供的服务中的用户活动。 随后将发布联机状态，供其他用户查看。  Skype for Business 和团队是具有单独客户端的独立服务，因此每个服务都有其自己的状态供用户使用。   团队和 Skype for Business Online 中的状态服务也有同步。  这允许一个服务可能会在需要时从其他服务中发布用户的状态。 

状态发布行为基于用户模式。 有三种基本情况：

- 如果用户处于 TeamsOnly 模式，则所有其他用户可查看该用户的团队状态，无论他们使用的是哪种客户端。

- 如果用户处于任何 Skype for Business 模式，则所有其他用户都可以查看该用户的 Skype for business 状态，无论他们使用哪种客户端。

- 如果用户处于 "孤岛" 模式，在 Skype for business 中发布的联机状态和团队是独立的，因此对同一组织中的用户显示的状态将取决于其他用户的客户端。 联合组织中的用户将根据其 Skype for business 活动查看该用户的状态，因为在 Skype for business 中，联盟模式用户的联盟流量。

例如，假设用户 A 处于孤岛模式。 如果用户 A 在团队中处于活动状态，但未登录到 Skype for business，则其他用户将从其团队客户端看到用户 A 是活动的，但在其 Skype for Business 客户端中，他们将把用户 A 设为 "脱机"。 这是设计使然，因为如果用户不在运行客户端，则无法访问用户 A。 


## <a name="federation"></a>联合身份验证

从团队到其他使用 Skype for Business 的用户的联盟要求团队用户在 Skype for business 中托管用户处于联机状态。 TeamsUpgradePolicy 控制传入联盟聊天和呼叫的路由。 除 "孤岛" 模式之外，联合路由行为与相同租户方案相同。 当收件人处于 "孤岛" 模式时：

- 在 Skype for Business 中从团队土地发起的聊天和通话（如果收件人位于联合租户中）。
- 如果收件人位于同一个租户中，则从团队中的团队土地发起聊天和通话。
- 通过 Skype for Business 发起的聊天和通话始终位于 Skype for business 中。

联合聊天既可以是本机线程，也可以是互操作线程。 请参阅 [团队对话---互操作与本机线程](#teams-conversations---interop-versus-native-threads)。

- 如果接收方和发件人都在 TeamsOnly 升级模式中，则对话将是一个本机聊天体验，包括所有丰富的消息传递和呼叫功能。 若要了解详细信息，请阅读 [团队中的外部 (联盟) 用户的本机聊天体验](native-chat-for-external-users.md)。 

- 如果其中一个对话参与者未处于 TeamsOnly 升级模式，则对话将保持带有纯文本消息的互操作体验。 用户界面以与同一租户互操作线程类似的方式公开联盟聊天，但存在指示用户是外部用户的注释。

有关更多详细信息，请参阅 [管理 Microsoft 团队中的外部访问](manage-external-access.md) 和 [团队中的外部 (联盟) 用户的本机聊天体验](native-chat-for-external-users.md)。

## <a name="contacts"></a>联系人

团队和 Skype for business 具有单独的联系人列表。 这意味着在一个系统中所做的添加、删除和修改不会与其他系统同步。 但是，如果发生两个特定事件之一，来自 Skype for Business 的联系人会自动复制到团队中： 

- 对于任何 Skype for Business Online 用户，当他们第一次登录到团队时，Skype for Business 中的联系人将被复制到团队。  对于在 Skype for Business 服务器中使用本地帐户的用户，此行为不可用。  

- 将用户升级到 TeamsOnly 后 (通过分配 TeamsUpgradePolicy 或通过移动 Move-csuser MoveToTeams) ，当用户下次登录到团队时，Skype for Business 中的现有联系人将与已在团队中的现有联系人合并。 无论用户的 Skype for Business 帐户是托管内部还是联机，都会发生此行为。 

在这两种情况下，从 Skype for Business 到团队的联系人之间的转移是异步的，因此可能需要几分钟才能使联系人显示在团队中。 上述两个事件是触发副本的起因。  

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

