---
title: Teams 中的用户状态
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 了解 Teams 中的状态以及状态功能的管理设置。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616946"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

状态是 Microsoft Teams（和所有 Microsoft 365 或 Office 365）中用户配置文件的一部分。 状态表示用户当前对其他用户的可用性和状态。 默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。 当你在移动设备上刷新页面时，将在 Web 和桌面版本上实时更新状态。

 > [!Note]
 > 有关不同平台上 Teams 用户配置文件的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="presence-states-in-teams"></a>Teams 中的状态

|用户配置|应用配置|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) 在线|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) 在线但外出。 注意：在用户设置“自动答复”的时间段内，将自动设置“外出”。 如果用户在这段时间内使用应用，则可能会显示双重状态，例如“在线但外出”。 |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌 |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) 通话中|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) 会议中 |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) 通话中但外出|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) 请勿打扰 ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) 正在演示|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) 专注。 当用户在日历的 MyAnalytics/Insights 中安排专注时间时，就会发生专注。|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开|
|| ![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线 *时间* 离开|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) 马上回来| |
|![带 x 的灰色圆圈，表示脱机](media/Presence_Offline.png) 显示为脱机|![带 x 的灰色圆圈，表示脱机](media/Presence_Offline.png) 脱机。  当用户在几分钟内未登录其任何设备时，他们将显示为脱机。 | |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) 未知状态|
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) 外出。 设置自动答复时，将使用“外出”。 （仅适用于 Outlook。） |
|||

应用配置的状态基于用户活动（在线、离开）、Outlook 日历状态（会议中）或 Teams 应用状态（通话中、正在演示）。 当根据你的日历，你正处于专注模式时，“**专注**”将是人们在 Teams 中看到的状态。 在其他产品中，专注模式将显示为“**请勿打扰**”。

当你锁定计算机或计算机进入空闲或睡眠模式时，你当前的状态将更改为“离开”。 在移动设备上，每当 Teams 应用处于后台时，你的状态就会更改为“离开”。

用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。 如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。 无论用户处于何种状态，他们都能在 Teams 中收到发送给他们的所有聊天消息。

用户在所有状态下都可以接听呼叫，但“请勿打扰”状态除外，在这种状态下，来电会转接到语音邮件。 如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。

用户可以在 Teams 中依次转到“设置” > “隐私”，向自己的优先访问列表添加人员。 即使用户的状态设置为“请勿打扰”，拥有优先访问权限的人也可以与该用户联系。

### <a name="dual-presence"></a>双重状态

  状态对大多数用户的工作方式是由日历中的事件或设备事件（如呼叫）驱动的。 用户可以通过手动设置状态来覆盖 UI 中的此状态，这些状态具有一定的过期时间。

## <a name="user-configured-states-expiration"></a>用户配置的状态过期

当用户选择特定状态时，它优先于任何应用活动更新。 例如，如果用户将自己设置为“请勿打扰”，则即使她出席会议或接听电话，她的状态仍将保持为“请勿打扰”。

用户配置的状态在 Teams 中具有默认的过期设置，以防止用户在一段时间后显示可能不相关的状态。

|用户配置的状态|默认到期时间|
|:--- |:---|
| 忙碌|1 天|
| 请勿打扰|1 天|
| 其他|7 天|
|||

> [!NOTE]
> 用户还可以手动配置其状态的持续时间。 例如，用户可以将自己设置为“显示为脱机”，直到明天早上。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比较 Teams 与 Skype for Business 中的管理员设置

以下管理员设置在 Skype for Business 和 Teams 中是不同的：

- 在 Teams 中，状态共享对组织中的用户始终是启用的。 Teams 中没有隐私（定义了谁能看到状态）配置。
- 在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。 在“聊天”>“联系人”或“通话”>“联系人”下，可以看到用户的联系人列表（如果 Skype for Business 中有）。
- 在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。
- 如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。
- 如果组织还使用 Skype for Business，在 Teams 中“上次上线”或“离开时间”指示器对用户始终是启用的。

> [!NOTE]
> 暂不支持 Teams 管理员自定义这些设置。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>比较 Teams 与 Microsoft Outlook 中的管理员设置

对于同一组织中的联系人，Outlook 2013 桌面版及更高版本应用支持 Outlook 中的 Teams 状态。

如果用户帐户的升级模式策略设置为 TeamsOnly，则 Outlook 将与 Teams 进行通信来获取状态。 如果用户帐户未设置为 TeamsOnly，则 Outlook 将与 Skype for Business 进行通信。

## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

若要详细了解 Teams 状态如何在组织还使用 Skype for Business 时发挥作用，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。
