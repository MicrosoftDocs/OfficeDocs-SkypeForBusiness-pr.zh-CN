---
title: 在"会议"中为用户设置会议拨出Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置Teams以请求拨出确认，以防止当被呼叫者无法接听呼叫时语音邮件系统连接到会议。
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 121a4cbd4527f4724f9868a83ab70dd75fb9b327
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865511"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>在"会议"中为用户设置会议拨出Microsoft Teams

会议拨出和呼叫我是邀请参与者加入会议以及让现有参与者使用传统或移动电话加入会议非常有用的方法。 但是，当被呼叫者无法接听呼叫并且呼叫由语音邮件系统应答时，语音邮件系统将连接到会议，参与者将能够收听它，直到从会议中删除它。

若要防止在将会议拨出发送到电话号码且被呼叫者无法接听呼叫时，语音邮件系统连接到会议，你可以设置 Teams 以请求被呼叫者确认他们加入会议。 如果被呼叫者无法接听呼叫且呼叫由语音邮件系统应答，则语音邮件系统不会连接到会议，因为它不会提供加入会议确认。

启用此功能后，接收拨出或呼叫我的人必须通过在传统电话或移动电话上按 1 确认他们想要加入会议。

若要为组织的所有会议启用此功能，请设置 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数 ```true``` 。 要执行此操作，请运行以下命令：

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相关主题

- [为用户设置“致电我”功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)