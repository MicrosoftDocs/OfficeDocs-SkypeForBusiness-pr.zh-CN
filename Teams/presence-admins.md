---
title: Teams 中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有关工作组中的状态的管理员信息。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573213"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

状态是 Microsoft 团队（以及整个 Office 365）中的用户配置文件的一部分，用于指示用户的当前可用性和其他用户的状态。 默认情况下，使用团队的组织中的任何人都可以在其他用户联机时查看（几乎实时）。

> [!IMPORTANT]
> 如果在将用户移动到“仅 Teams”**** 模式后卸载 Skype for Business 客户端，则在 Outlook 和其他 Office 应用程序中，状态将停止工作。 状态在 Teams 中显示良好。 解决方法：若要在 Outlook （以及其他 Office 应用）中查看状态，必须安装 Skype for business，即使你是在 "**仅团队**" 模式下运行团队也是如此。 Microsoft 已发现此问题且正在开发修补程序。

## <a name="presence-states-in-teams"></a>团队中的状态

团队中可用的用户状态包括：

|用户配置|已配置应用|
|:--- |:---|
| ![稳定绿色复选标记，指示可用状态](media/Presence_Available.png) 有空|![稳定绿色复选标记，指示可用状态](media/Presence_Available.png) 有空|
|| ![打开绿色复选标记，表示可用的 oof](media/Presence_Available_OOF.png) 可用，外出 |
|  ![红色实心圆圈表示占线](media/Presence_Busy.png) / |  ![红色实心圆圈表示占线](media/Presence_Busy.png) /  |
|| ![红色实心圆圈表示通话中的占线](media/Presence_Busy.png) 在通话中|
|| ![纯红色圆圈表示会议中的忙](media/Presence_Busy.png) 在会议中 |
|| ![打开红色圆圈，表示占线](media/Presence_Busy_OOF.png) 在通话中，外出|
|  ![带白线的红色圆圈表示 "请勿打扰"](media/Presence_DND.png) 请勿打扰 ||
|| ![带有白色线的红色圆圈表示演示](media/Presence_DND.png) 演示|
|| ![带白线的红色圆圈表示焦点](media/Presence_DND.png) 介绍|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开| ![黄色时钟图标，表示离开](media/Presence_Away.png) 离开|
|| ![黄色时钟图标，表示离开](media/Presence_Away.png)上次看到的*时间*|
|![黄色时钟图标，表示离开，马上回来](media/Presence_Away.png) 马上回来| |
|| ![黄色时钟图标，表示离开，不起作用](media/Presence_Away.png)  关闭工作|
|| ![X 的灰色圆圈表示离线](media/Presence_Offline.png) 脱机 |
|| ![打开灰色圆圈，指示状态未知](media/Presence_Unknown.png) 状态未知|
||![以对角线打开红色圆圈，指示被阻止](media/Presence_Blocked.png) 已阻止 |
|| ![带箭头的紫色圆圈表示外出](media/Presence_OOF.png) 外出|
|||
 
用户可以手动将其当前状态设置为某些选项，其状态将反映给所有其他用户。 更多用户状态详细信息也会自动更新。 这些更改基于用户活动（可用、离开）、Outlook 日历状态（在会议中）或团队应用状态（正在进行的调用），以及列表中缩进的状态。

15分钟不活动超时，在这种情况下，当前状态将重置为 "离开"。

用户可以指定谁可以中断（这意味着无论 "请勿打扰" 状态，请与他们联系）。 这些设置在团队客户端中可用。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>与 Skype for business 相比，团队中的管理员设置

以下管理员设置 Skype for business 在团队中有所不同：

- 在团队中，始终为组织中的用户启用联机状态共享。 隐私（定义谁可以查看状态）配置在团队中不可用。
- 始终为团队中的用户启用与每个人（包括联合服务）的联机状态共享。 他们的联系人列表（如果他们在 Skype for Business 中）在 "**聊天 > 联系人**" 或 "**通话 > 联系人**" 下可见。
- 对于团队中的用户，将始终启用客户端 "请勿打扰" 和 "特许" 功能。
- 日历（包括外出和其他日历信息）在团队与 Outlook 集成时，将始终为用户启用集成。
- 如果组织还使用 Skype for Business，则 "*最后一次看到*" 或 "*离开*" 将始终为团队中的用户启用指示器。

> [!NOTE]
> 团队管理员自定义这些设置的能力目前不受支持。

## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

有关您的组织还使用 Skype for business 时团队的工作原理的详细信息，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。
