---
title: Teams 中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 信息管理员需要了解有关在团队中的状态。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246211"
---
# <a name="user-presence-in-teams"></a>Teams 中的用户状态

状态的用户配置文件中的 Microsoft 团队 （和整个 Office 365） – 的一部分，指示用户的当前的可用性和向组织中的其他用户的状态。 默认情况下使用团队您组织中的任何人都可以看到联机其他用户时可用。

## <a name="presence-states-in-teams"></a>团队中的状态

在工作组中可用的用户显示状态是：

|配置用户|应用程序配置|
|:--- |:---|
| ![状态可用](media/Presence_Available.png) 有空|![状态可用](media/Presence_Available.png) 有空|
|| ![可用 oof](media/Presence_Available_OOF.png) 可用外出 |
|  ![忙](media/Presence_Busy.png) 忙 |  ![忙](media/Presence_Busy.png) 忙  |
|| ![忙](media/Presence_Busy.png) 呼叫中|
|| ![忙](media/Presence_Busy.png) 在会议中 |
|| ![忙 oof](media/Presence_Busy_OOF.png) 在调用中，不在办公室|
|  ![请勿打扰](media/Presence_DND.png) 请勿打扰 ||
|| ![请勿打扰](media/Presence_DND.png) 演示|
| ![离开](media/Presence_Away.png) 离开| ![离开](media/Presence_Away.png) 离开|
|| ![离开](media/Presence_Away.png)离开最后一个看到*时间*|
|![离开](media/Presence_Away.png) 马上回来| |
|| ![离开](media/Presence_Away.png)  Off Work-下班|
|| ![脱机](media/Presence_Offline.png) 脱机 |
|| ![未知](media/Presence_Unknown.png) 状态未知|
||![被阻止](media/Presence_Blocked.png) 已阻止 |
|| ![外出](media/Presence_OOF.png) 外出|
|||
 
用户可以手动将其当前的状态设置为一些选项，并向所有其他用户获取反映其状态。 此外会自动基于用户活动 （如空闲或离开）、 Outlook 日历状态 （例如，如会议中所示） 或团队应用程序状态更新其他用户状态详细信息 (呼叫中，演示)，对列表中缩进的状态。

为 15 分钟无活动超时，其后用户的当前状态将重置为离开。

用户可以指定谁可以直拨 （联系它们替代请勿打扰的设置）。 这些设置是可在应用程序。

## <a name="teams-is-not-skype-for-business"></a>不 for Business 的 Skype 团队。

Skype for Business 中的以下管理设置是团队中的不同：
- 状态始终启用共享团队中的组织中的用户。 隐私 （确定谁可以看到的状态） 配置不在工作组中可用。
- 团队中的用户始终启用共享与所有人 （包括联盟服务） 的状态。 可见或**呼叫 > 联系人**下**聊天 > 联系人**其联系人列表 （如果有一个 SfB 中）。
- 团队中的用户始终启用客户端请勿打扰和突破性的功能。
- （包括 OOF & 其他日历信息） 的日历集成始终启用团队中的用户，如果与 Outlook 集成。
- *上一次发现*或*离开相*（如果使用 Skype for Business 的双环境中） 标记始终启用团队中的用户。

> [!NOTE]
> 当前不支持团队管理员能够自定义这些设置。


## <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

有关与 for Business 的 Skype 共存时，团队状态的工作方式的详细信息，请参阅[使用 Skype for Business 的共存](coexistence-chat-calls-presence.md)。 
