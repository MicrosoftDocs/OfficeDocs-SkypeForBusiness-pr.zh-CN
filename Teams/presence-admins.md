---
title: Teams 中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 信息管理员需要了解团队中的状态。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fd6ac289df238d9f410266b1eca43a3a18f493e
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548522"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

联机状态是 Microsoft 团队 (以及整个 Office 365) 中的用户配置文件的一部分-并指示用户的当前可用性和组织中其他用户的状态。 默认情况下, 使用团队的组织中的任何人都可以在几乎实时查看-无论其他用户是否在线提供。

## <a name="presence-states-in-teams"></a>团队中的状态

团队中可用的用户状态包括:

|用户配置|已配置应用|
|:--- |:---|
| ![稳定绿色的 chek 标记, 指示可用状态](media/Presence_Available.png) 有空|![稳定绿色的 chek 标记, 指示可用状态](media/Presence_Available.png) 有空|
|| ![打开绿色的 chek 标记, 指示可用的 oof](media/Presence_Available_OOF.png) 可用, 外出 |
|  ![红色实心圆圈, 表示占线](media/Presence_Busy.png) / |  ![/](media/Presence_Busy.png) /  |
|| ![红色实心圆圈, 表示通话中的占线](media/Presence_Busy.png) 在通话中|
|| ![红色实心圆圈, 表示会议中的忙](media/Presence_Busy.png) 在会议中 |
|| ![打开红色圆圈, 指示繁忙的 oof](media/Presence_Busy_OOF.png) 在通话中, 外出|
|  ![带白线的红色圆圈, 指示 "请勿打扰"](media/Presence_DND.png) 请勿打扰 ||
|| ![带有白色线的红色圆圈, 指示演示](media/Presence_DND.png) 演示|
| ![黄色时钟图标, 表示离开](media/Presence_Away.png) 离开| ![离开](media/Presence_Away.png) 离开|
|| ![黄色时钟图标, 指示离开](media/Presence_Away.png)上次看到的*时间*|
|![黄色时钟图标, 表示离开, 马上回来](media/Presence_Away.png) 马上回来| |
|| ![黄色时钟图标, 指示离开、离开工作](media/Presence_Away.png)  关闭工作|
|| ![带有 x 的灰色圆圈, 指示离线](media/Presence_Offline.png) 脱机 |
|| ![打开灰色圆圈, 指示状态未知](media/Presence_Unknown.png) 状态未知|
||![以对角线打开红色圆圈, 指示已阻止](media/Presence_Blocked.png) 已阻止 |
|| ![带箭头的紫色圆圈, 表示外出](media/Presence_OOF.png) 外出|
|||
 
用户可以手动将其当前状态设置为某些选项, 其状态将反映给所有其他用户。 其他用户状态详细信息也会根据用户活动 (如 "可用" 或 "离开")、Outlook 日历状态 (如 "会议") 或团队应用状态 (正在进行的调用) 自动更新, 以显示在列表中缩进的状态。

有15分钟的不活动超时, 用户的当前状态将重置为 "离开"。

用户可以指定谁可以断开连接 (联系他们替代 "请勿打扰" 设置)。 这些设置在应用内可用。

## <a name="teams-is-not-skype-for-business"></a>团队不是 Skype for business

Skype for Business 中的以下管理员设置在团队中有所不同:
- 组织中的用户始终可以在团队中启用联机状态共享。 隐私 (决定谁可以查看状态) 配置在团队中不可用。
- 始终为团队中的用户启用与每个人 (包括联合服务) 的联机状态共享。 他们的联系人列表 (如果他们在 SfB 中有一个) 在 "**聊天 _GT_ 联系人**" 或 "**呼叫 > 联系人**" 下可见。
- 对于团队中的用户, 将始终启用客户端 "请勿打扰" 和 "特许" 功能。
- 日历 (包括 OOF & 其他日历信息) 对于团队中的用户, 如果与 Outlook 集成, 则始终为其启用集成。
- 始终** 为团队中的用户启用 "*自*(如果在具有 Skype for business 的双重环境中)" 指示器。

> [!NOTE]
> 团队管理员自定义这些设置的能力目前不受支持。


## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

请参阅与 skype for business[共存](coexistence-chat-calls-presence.md), 了解有关在与 Skype for business 共存时团队是否正常工作的详细信息。 
