---
title: Teams 中的用户状态
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 了解团队中的状态状态以及状态功能的管理设置。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6432bac9dbbfe65cf3e139ecae00b02cd5ae8651
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905764"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

状态是 Microsoft 团队（以及整个 Office 365）中的用户配置文件的一部分，用于指示用户的当前可用性和其他用户的状态。 默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。

Outlook 2013 桌面应用及更高版本支持 Outlook 中的 Teams 状态。

## <a name="presence-states-in-teams"></a>Teams 中的状态

|用户配置|应用配置|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) 在线但外出 |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌 |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) 通话中|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) 会议中 |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) 通话中但外出|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) 请勿打扰 ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) 正在演示|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) 专注|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开|
|| ![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线*时间*离开|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) 马上回来| |
|| ![黄色时钟图标，表示下班离开](media/Presence_Away.png)  下班|
|| ![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) 离线 |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) 未知状态|
||![带对角线的空心红色圆圈，表示已屏蔽](media/Presence_Blocked.png) 已屏蔽 |
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) 外出|
|||

应用配置的状态取决于用户活动（可用、离开）、Outlook 日历状态（在会议中）或团队应用状态（在通话中）。

当您锁定计算机或进入空闲或睡眠模式时，当前状态将更改为 "离开"。 在手机上，只要团队应用处于后台，你的状态将更改为 "离开"。

用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。 如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。 如果用户处于 "请勿打扰"，则用户仍将收到聊天消息，但不显示标题通知。

用户接收除 "请勿打扰" 之外的所有状态的呼叫，传入呼叫转到语音邮件。 如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。

用户可以在 Teams 中依次转到“设置”**** > “隐私”****，向自己的优先访问列表添加人员。 具有优先级访问权限的用户即使在用户处于 "请勿打扰" 时也可以与用户联系。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比较 Teams 与 Skype for Business 中的管理员设置

以下管理员设置在 Skype for Business 和 Teams 中是不同的：

- 在 Teams 中，状态共享对组织中的用户始终是启用的。 Teams 中没有隐私（定义了谁能看到状态）配置。
- 在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。 在“聊天”>“联系人”**** 或“通话”>“联系人”**** 下，可以看到用户的联系人列表（如果 Skype for Business 中有）。
- 在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。
- 如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。
- 如果组织还使用 Skype for Business，在 Teams 中“上次上线”** 或“离开时间”** 指示器对用户始终是启用的。

> [!NOTE]
> 暂不支持 Teams 管理员自定义这些设置。

## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

若要详细了解 Teams 状态如何在组织还使用 Skype for Business 时发挥作用，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。
