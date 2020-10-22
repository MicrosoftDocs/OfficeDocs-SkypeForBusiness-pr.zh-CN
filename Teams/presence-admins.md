---
title: Teams 中的用户状态
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 了解团队中的状态和状态功能的管理设置。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fd066fe06126043475a7264b3b2c4501c7ac3ae
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650945"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

联机状态是 Microsoft 团队 (和整个 Microsoft 365 或 Office 365) 中的用户配置文件的一部分。 "状态" 表示用户的当前可用性和对其他用户的状态。 默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。 在移动设备上刷新页面时，联机状态将在网页和桌面版本上实时更新。

 > [!Note]
 > 有关不同平台上的团队用户配置文件的详细信息，请参阅 [按平台的团队功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="presence-states-in-teams"></a>Teams 中的状态

|用户配置|应用配置|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) 可用，外出。 注意：在用户设置 "自动答复" 的时间段内，将自动设置外出。 如果用户在这些时间段内使用应用，则可能会显示双重状态，例如 "外出，可用"。 |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌 |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) 通话中|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) 会议中 |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) 通话中但外出|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) 请勿打扰 ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) 正在演示|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) 介绍. 当用户在日历中的 MyAnalytics/见解中安排焦点时间时，焦点将发生。|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开|
|| ![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线*时间*离开|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) 马上回来| |
|![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) 显示为脱机。 团队即将推出。|![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) 脱机.  当用户没有在任何设备上登录时，它们将显示为离线。 | |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) 未知状态|
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) 外出。 当设置自动答复时，将使用外出。  (仅在 Outlook 中可用。 )  |
|||

应用配置的状态状态基于用户活动 (可用、离开) 、Outlook 日历状态 (在会议) 或团队应用状态 (在通话中，演示) 。 当你处于基于你的日历的焦点模式时 **，焦点** 将是人们在团队中看到的状态。 在其他产品中，焦点模式将显示为 "请勿 **打扰** "。

当您锁定计算机或计算机进入空闲或睡眠模式时，当前状态将更改为 "离开"。 在移动设备上，只要团队应用处于后台，你的状态将更改为 "离开"。

用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。 如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。 如果用户状态设置为 "请勿打扰"，则用户仍将收到聊天消息，但不显示标题通知。

用户接收除 "请勿打扰" 之外的所有状态的呼叫，传入呼叫转到语音邮件。 如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。

用户可以在 Teams 中依次转到“设置”**** > “隐私”****，向自己的优先访问列表添加人员。 如果用户的状态设置为 "请勿打扰"，则具有优先级访问权限的人员可以联系用户。

### <a name="dual-presence"></a>双重状态

  状态适用于大多数用户的方式由日历或设备事件中的事件（如呼叫）所导致。 用户可以通过手动设置状态（具有一些过期时间）在 UI 中替代此状态。

## <a name="user-configured-states-expiration"></a>用户配置状态过期

当用户选择特定的状态时，它优先于任何应用活动更新。 例如，如果用户将她设置为 "请勿打扰"，她的状态将保持为 "请勿打扰"，即使她出席会议或接听呼叫。

用户配置的状态在团队中具有默认过期设置，以防止用户显示一段时间后可能不相关的状态。

|用户配置状态|默认过期|
|:--- |:---|
| 忙碌|1天|
| 请勿打扰|1天|
| 则|7天|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比较 Teams 与 Skype for Business 中的管理员设置

以下管理员设置在 Skype for Business 和 Teams 中是不同的：

- 在 Teams 中，状态共享对组织中的用户始终是启用的。 隐私 (，您可以在其中定义哪些人可以查看状态) 配置在团队中不可用。
- 在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。 在“聊天”>“联系人”**** 或“通话”>“联系人”**** 下，可以看到用户的联系人列表（如果 Skype for Business 中有）。
- 在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。
- 如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。
- 如果组织还使用 Skype for Business，在 Teams 中“上次上线”** 或“离开时间”** 指示器对用户始终是启用的。

> [!NOTE]
> 暂不支持 Teams 管理员自定义这些设置。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>团队中与 Microsoft Outlook 相比的管理员设置

Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。

如果用户帐户的 "升级模式" 策略设置为 "TeamsOnly"，Outlook 将与团队进行合作以获取状态。 如果用户帐户未设置为 TeamsOnly，则 Outlook 将与 Skype for business 进行交谈。

## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

有关您的组织还使用 Skype for business 时团队的工作原理的详细信息，请参阅 [与 Skype for Business 共存](coexistence-chat-calls-presence.md) 。
